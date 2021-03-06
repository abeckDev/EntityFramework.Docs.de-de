---
title: 'Globale Abfragefilter: EF Core'
author: anpete
ms.author: anpete
ms.date: 11/03/2017
ms.technology: entity-framework-core
uid: core/querying/filters
ms.openlocfilehash: 4e3c3c99d155f69e00fed99c415f519808ea1a68
ms.sourcegitcommit: 6e379265e4f087fb7cf180c824722c81750554dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
ms.locfileid: "26053900"
---
# <a name="global-query-filters"></a>Globale Abfragefilter

Globale Abfragefilter sind LINQ-Abfrageprädikate (ein boolescher Ausdruck, der in der Regel an den LINQ-Abfrageoperator *Where* übergeben wird), die auf Entitätstypen im Metadatenmodell (normalerweise in *OnModelCreating*) angewendet werden. Solche Filter werden automatisch auf alle diese Entitätstypen betreffenden LINQ-Abfragen (z.B. indirekt referenzierte Entitätstypen) angewendet, beispielsweise durch include-Verweise oder direkte Verweise auf Navigationseigenschaften. Zu den häufigsten Anwendungsfällen dieses Features zählen Folgende:

* **Vorläufiges Löschen:** Ein Entitätstyp definiert eine *IsDeleted*-Eigenschaft.
* **Mehrinstanzenfähigkeit:** Ein Entitätstyp definiert eine *TenantId*-Eigenschaft.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird in einem einfachen Blogmodell dargestellt, wie globale Abfragefilter zum Implementieren des Abfrageverhaltens für das vorläufige Löschen und die Mehrinstanzenfähigkeit verwendet werden.

> [!TIP]
> Das in diesem Artikel verwendete [Beispiel](https://github.com/aspnet/EntityFrameworkCore/tree/dev/samples/QueryFilters) finden Sie auf GitHub.

Definieren Sie zunächst die Entitäten:

[!code-csharp[Main](../../../efcore-dev/samples/QueryFilters/Program.cs#Entities)]

Beachten Sie die Deklaration eines __tenantId_-Felds in der Entität _Blog_. Dies wird dazu verwendet, jede Bloginstanz einem bestimmten Mandanten zuzuordnen. Außerdem wird eine _IsDeleted_-Eigenschaft auf dem Entitätstyp _Post_ definiert. Damit wird nachverfolgt, ob eine _Post_-Instanz „vorläufig gelöscht“ wurde. Das bedeutet, dass die Instanz als „gelöscht“ gekennzeichnet wird, ohne dass die zugrundeliegenden Daten physisch entfernt werden.

Konfigurieren Sie als nächstes die Abfragefilter in _OnModelCreating_ mithilfe der ```HasQueryFilter```-API.

[!code-csharp[Main](../../../efcore-dev/samples/QueryFilters/Program.cs#Configuration)]

Die Prädikatausdrücke, die an _HasQueryFilter_ weitergegeben werden, werden nun automatisch auf alle LINQ-Abfragen dieser Typen angewendet.

> [!TIP]
> Beachten Sie die Verwendung eines DbContext-Instanzfelds: ```_tenantId``` wird zum Festlegen des aktuellen Mandanten verwendet. Filter auf Modellebene verwenden den Wert aus der entsprechenden Kontextinstanz. Das bedeutet, dass die Instanz die Abfrage ausführt.

## <a name="disabling-filters"></a>Deaktivieren von Filtern

Filter können für einzelne LINQ-Abfragen mit dem ```IgnoreQueryFilters()```-Operator deaktiviert werden.

[!code-csharp[Main](../../../efcore-dev/samples/QueryFilters/Program.cs#IgnoreFilters)]

## <a name="limitations"></a>Einschränkungen

Globale Abfragefilter unterliegen den folgenden Einschränkungen:

* Filter können keine Verweise auf Navigationseigenschaften enthalten.
* Filter können nur für den Stammentitätstyp einer Vererbungshierarchie definiert werden.
