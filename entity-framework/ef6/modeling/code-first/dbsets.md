---
title: Definieren von "dbsets" – EF6
author: divega
ms.date: 2016-10-23
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 4528a509-ace7-4dfb-8065-1b833f5e03a0
caps.latest.revision: 3
ms.openlocfilehash: 8a495c6ce74d9a346a84b0e10fb28395f4dce07b
ms.sourcegitcommit: 00cb52625b57c1ea339ded1454179fe89b6bcfea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2018
ms.locfileid: "39121727"
---
# <a name="defining-dbsets"></a>Definieren von "dbsets"
Bei der Entwicklung mit Code First-Workflow definieren Sie einen abgeleiteten "DbContext", das von der Sitzung mit der Datenbank, und stellt einen "DbSet" für jeden Typ im Modell. Dieses Thema behandelt die verschiedenen Möglichkeiten, die Sie die Eigenschaften "DbSet" definieren können.  

## <a name="dbcontext-with-dbset-properties"></a>"DbContext" mit "DbSet"-Eigenschaften  

Meistens in Code First-Beispielen gezeigt ist, um einen "DbContext" mit öffentlichen automatische "DbSet"-Eigenschaften für die Entitätstypen des Modells zu erhalten. Zum Beispiel:  

``` csharp
public class BloggingContext : DbContext
{
    public DbSet<Blog> Blogs { get; set; }
    public DbSet<Post> Posts { get; set; }
}
```  

Bei Verwendung in Code First-Modus wird dieses Blogs und Beiträgen als Entitätstypen sowie die Konfiguration anderer Endpunkttypen, die von diesen erreichbar konfiguriert. Darüber hinaus ruft "DbContext" automatisch den Setter für jede dieser Eigenschaften, die eine Instanz der entsprechenden "DbSet" festgelegt.  

## <a name="dbcontext-with-idbset-properties"></a>"DbContext" mit IDbSet-Eigenschaften  

Es gibt Situationen, z. B. beim Erstellen oder mocks fakes, in denen es sinnvoller, Ihre Eigenschaften festlegen, die mit einer Schnittstelle deklariert ist. In solchen Fällen die IDbSet kann Schnittstelle anstelle von "DbSet" verwendet werden. Zum Beispiel:  

``` csharp
public class BloggingContext : DbContext
{
    public IDbSet<Blog> Blogs { get; set; }
    public IDbSet<Post> Posts { get; set; }
}
```  

Dieser Kontext funktioniert in genau die gleiche Weise wie der Kontext, der die "DbSet"-Klasse für die festgelegte Eigenschaften verwendet.  

## <a name="dbcontext-with-read-only-set-properties"></a>"DbContext" mit schreibgeschützten Eigenschaften festlegen.  

Wenn Sie nicht möchten, um öffentliche Setter für die Eigenschaften "DbSet" oder IDbSet verfügbar zu machen, Sie stattdessen schreibgeschützte Eigenschaften erstellen und die Instanzen selbst erstellen. Zum Beispiel:  

``` csharp
public class BloggingContext : DbContext
{
    public DbSet<Blog> Blogs
    {
        get { return Set<Blog>(); }
    }

    public DbSet<Post> Posts
    {
        get { return Set<Post>(); }
    }
}
```  

Beachten Sie, dass "DbContext" speichert die Instanz von "DbSet" von der Set-Methode zurückgegeben wird, sodass jede dieser Eigenschaften wird die gleiche Instanz zurückgeben, jedes Mal, wenn sie aufgerufen wird.  

Ermittlung von Entitätstypen für Code First funktioniert hier genauso, wie er für Eigenschaften mit öffentlichen Getter und Setter ist.  
