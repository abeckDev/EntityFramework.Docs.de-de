---
title: 'Entity Framework-Anbieter: EF6'
author: divega
ms.date: 2018-06-27
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 7BFB7763-CD6C-4520-93A2-7B265F5FA586
caps.latest.revision: 3
ms.openlocfilehash: 8bd5a5a420d741accd1167845575e23c09579ae1
ms.sourcegitcommit: 390f3a37bc55105ed7cc5b0e0925b7f9c9e80ba6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2018
ms.locfileid: "37914296"
---
# <a name="entity-framework-6-providers"></a><span data-ttu-id="fc6bc-102">Anbieter von Entity Framework 6</span><span class="sxs-lookup"><span data-stu-id="fc6bc-102">Entity Framework 6 Providers</span></span>
> [!NOTE]
> <span data-ttu-id="fc6bc-103">**Nur EF6 und höher:** Die Features, APIs usw., die auf dieser Seite erläutert werden, wurden in Entity Framework 6 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-103">**EF6 Onwards Only** - The features, APIs, etc. discussed in this page were introduced in Entity Framework 6.</span></span> <span data-ttu-id="fc6bc-104">Wenn Sie eine frühere Version verwenden, gelten manche Informationen nicht.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-104">If you are using an earlier version, some or all of the information does not apply.</span></span>

<span data-ttu-id="fc6bc-105">Das Entity Framework wird nun unter einer Open Source-Lizenz entwickelt, und EF6 und höher werden nicht als Teil von .NET Framework zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-105">The Entity Framework is now being developed under an open-source license and EF6 and above will not be shipped as part of the .NET Framework.</span></span> <span data-ttu-id="fc6bc-106">Dies bringt viele Vorteile mit sich, erfordert jedoch auch, dass EF-Anbieter für die EF6-Assemblys neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-106">This has many advantages but also requires that EF providers be rebuilt against the EF6 assemblies.</span></span> <span data-ttu-id="fc6bc-107">Das heißt, dass EF-Anbieter für EF5 und darunter nicht mit EF6 funktionieren, es sei denn, sie wurden neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-107">This means that EF providers for EF5 and below will not work with EF6 until they have been rebuilt.</span></span>

## <a name="which-providers-are-available-for-ef6"></a><span data-ttu-id="fc6bc-108">Welche Anbieter sind für EF6 verfügbar?</span><span class="sxs-lookup"><span data-stu-id="fc6bc-108">Which providers are available for EF6?</span></span>

<span data-ttu-id="fc6bc-109">Anbieter, von denen wir wissen, dass Sie für EF6 neu erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="fc6bc-109">Providers we are aware of that have been rebuilt for EF6 include:</span></span>

*   <span data-ttu-id="fc6bc-110">**Microsoft SQL Server-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-110">**Microsoft SQL Server provider**</span></span>
    *   <span data-ttu-id="fc6bc-111">Erstellt aus der [Open Sources-Codebasis des Entity Framework](http://github.com/aspnet/EntityFramework6)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-111">Built from the [Entity Framework open source code base](http://github.com/aspnet/EntityFramework6)</span></span>
    *   <span data-ttu-id="fc6bc-112">Geliefert als Teil des [EntityFramework NuGet-Pakets](http://nuget.org/packages/EntityFramework)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-112">Shipped as part of the [EntityFramework NuGet package](http://nuget.org/packages/EntityFramework)</span></span>
*   <span data-ttu-id="fc6bc-113">**Microsoft SQL Server Compact Edition-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-113">**Microsoft SQL Server Compact Edition provider**</span></span>
    *   <span data-ttu-id="fc6bc-114">Erstellt aus der [Open Sources-Codebasis des Entity Framework](http://github.com/aspnet/EntityFramework6)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-114">Built from the [Entity Framework open source code base](http://github.com/aspnet/EntityFramework6)</span></span>
    *   <span data-ttu-id="fc6bc-115">Im Lieferumfang des [EntityFramework.SqlServerCompact NuGet-Pakets](http://nuget.org/packages/EntityFramework.SqlServerCompact)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-115">Shipped in the [EntityFramework.SqlServerCompact NuGet package](http://nuget.org/packages/EntityFramework.SqlServerCompact)</span></span>
*   [<span data-ttu-id="fc6bc-116">**Devart dotConnect-Datenanbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-116">**Devart dotConnect Data Providers**</span></span>](http://www.devart.com/dotconnect/)
    *   <span data-ttu-id="fc6bc-117">Es gibt Anbieter von Drittanbietern von [Devart](http://www.devart.com/) für eine Vielzahl von Datenbanken, einschließlich Oracle, MySQL, PostgreSQL, SQLite, Salesforce, DB2 und SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-117">There are third-party providers from [Devart](http://www.devart.com/) for a variety of databases including Oracle, MySQL, PostgreSQL, SQLite, Salesforce, DB2, and SQL Server</span></span>
*   [<span data-ttu-id="fc6bc-118">**CData Software-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-118">**CData Software providers**</span></span>](http://www.cdata.com/ado/)
    *   <span data-ttu-id="fc6bc-119">Es gibt Anbieter von Drittanbietern von [CData Software](http://www.cdata.com/ado/) für eine Vielzahl von Datenspeichern, einschließlich Salesforce, Azure Table Storage, MySql und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-119">There are third-party providers from [CData Software](http://www.cdata.com/ado/) for a variety of data stores including Salesforce, Azure Table Storage, MySql, and many more</span></span>
*   <span data-ttu-id="fc6bc-120">**Firebird-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-120">**Firebird provider**</span></span>
    *   <span data-ttu-id="fc6bc-121">Verfügbar als [NuGet-Paket](http://www.nuget.org/packages/FirebirdSql.Data.FirebirdClient/)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-121">Available as a [NuGet Package](http://www.nuget.org/packages/FirebirdSql.Data.FirebirdClient/)</span></span>
*   <span data-ttu-id="fc6bc-122">**Visual FoxPro-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-122">**Visual Fox Pro provider**</span></span>
    *   <span data-ttu-id="fc6bc-123">Verfügbar als [NuGet-Paket](https://www.nuget.org/packages/VFPEntityFrameworkProvider2/)</span><span class="sxs-lookup"><span data-stu-id="fc6bc-123">Available as a [NuGet package](https://www.nuget.org/packages/VFPEntityFrameworkProvider2/)</span></span>
*   <span data-ttu-id="fc6bc-124">**MySQL**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-124">**MySQL**</span></span>
    *   [<span data-ttu-id="fc6bc-125">MySQL Connector/Net</span><span class="sxs-lookup"><span data-stu-id="fc6bc-125">MySQL Connector/Net</span></span>](http://dev.mysql.com/downloads/connector/net/)
*   <span data-ttu-id="fc6bc-126">**PostgreSQL**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-126">**PostgreSQL**</span></span>
    *   <span data-ttu-id="fc6bc-127">Npgsql ist als [NuGet-Paket](http://www.nuget.org/packages/Npgsql.EF6/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-127">Npgsql is available as a [NuGet package](http://www.nuget.org/packages/Npgsql.EF6/)</span></span>
*   <span data-ttu-id="fc6bc-128">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="fc6bc-128">**Oracle**</span></span>
    *   <span data-ttu-id="fc6bc-129">ODP.NET ist als [NuGet-Paket](https://www.nuget.org/packages/Oracle.ManagedDataAccess.EntityFramework/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-129">ODP.NET is available as a [NuGet package](https://www.nuget.org/packages/Oracle.ManagedDataAccess.EntityFramework/)</span></span>

<span data-ttu-id="fc6bc-130">Beachten Sie, dass eine Aufnahme in die Liste keine Auskunft über die Ebene der Funktion oder Unterstützung für einen angegebenen Anbieter gibt, sondern nur darüber, dass ein Build für EF6 nun verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-130">Note that inclusion in this list does not indicate the level of functionality or support for a given provider, only that a build for EF6 has been made available.</span></span>

## <a name="registering-ef-providers"></a><span data-ttu-id="fc6bc-131">Registrieren von EF-Anbietern</span><span class="sxs-lookup"><span data-stu-id="fc6bc-131">Registering EF providers</span></span>

<span data-ttu-id="fc6bc-132">Ab Entity Framework 6 können EF-Anbieter über die codebasierte Konfiguration oder die Konfigurationsdatei der Anwendung registriert werden.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-132">Starting with Entity Framework 6 EF providers can be registered using either code-based configuration or in the application’s config file.</span></span>

### <a name="config-file-registration"></a><span data-ttu-id="fc6bc-133">Registrierung über die Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fc6bc-133">Config file registration</span></span>

<span data-ttu-id="fc6bc-134">Die Registrierung des EF-Anbieters in „app.config“ oder „web.config“ besitzt folgendes Format:</span><span class="sxs-lookup"><span data-stu-id="fc6bc-134">Registration of the EF provider in app.config or web.config has the following format:</span></span>


``` xml
    <entityFramework>
       <providers>
         <provider invariantName="My.Invariant.Name" type="MyProvider.MyProviderServices, MyAssembly" />
       </providers>
    </entityFramework>
```

<span data-ttu-id="fc6bc-135">Beachten Sie, dass es oft vorkommt, dass wenn der EF-Anbieter von NuGet installiert wird, das NuGet-Paket diese Registrierung automatisch der Konfigurationsdatei hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-135">Note that often if the EF provider is installed from NuGet, then the NuGet package will automatically add this registration to the config file.</span></span> <span data-ttu-id="fc6bc-136">Wenn Sie das NuGet-Paket in einem Projekt installieren, das nicht das Startprojekt Ihrer App ist, müssen Sie die Registrierung in die Konfigurationsdatei für Ihr Startprojekt kopieren.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-136">If you install the NuGet package into a project that is not the startup project for your app, then you may need to copy the registration into the config file for your startup project.</span></span>

<span data-ttu-id="fc6bc-137">Der invariante Name, „invariantName“, ist in dieser Registrierung derselbe invariante Name, der für die Identifizierung eines ADO.NET-Anbieters verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-137">The “invariantName” in this registration is the same invariant name used to identify an ADO.NET provider.</span></span> <span data-ttu-id="fc6bc-138">Dieser kann als „invariant“-Attribut in einer DbProviderFactories-Registrierung und als „providerName“-Attribut in einer Verbindungszeichenfolgenregistrierung gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-138">This can be found as the “invariant” attribute in a DbProviderFactories registration and as the “providerName” attribute in a connection string registration.</span></span> <span data-ttu-id="fc6bc-139">Der invariante Name, der verwendet werden soll, sollte auch in der Dokumentation für den Anbieter enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-139">The invariant name to use should also be included in documentation for the provider.</span></span> <span data-ttu-id="fc6bc-140">Beispiele für invariante Namen sind u.a. „System.Data.SqlClient“ für SQL Server und „System.Data.SqlServerCe.4.0“ für SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-140">Examples of invariant names are “System.Data.SqlClient” for SQL Server and “System.Data.SqlServerCe.4.0” for SQL Server Compact.</span></span>

<span data-ttu-id="fc6bc-141">Der Typ („type“) in dieser Registrierung ist der Name mit Assemblyqualifikation des Anbietertyps, der von „System.Data.Entity.Core.Common.DbProviderServices“ abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-141">The “type” in this registration is the assembly-qualified name of the provider type that derives from “System.Data.Entity.Core.Common.DbProviderServices”.</span></span> <span data-ttu-id="fc6bc-142">Die Zeichenfolge, die z.B. für SQL Compact verwendet werden soll, ist „System.Data.Entity.SqlServerCompact.SqlCeProviderServices, EntityFramework.SqlServerCompact“.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-142">For example, the string to use for SQL Compact is “System.Data.Entity.SqlServerCompact.SqlCeProviderServices, EntityFramework.SqlServerCompact”.</span></span> <span data-ttu-id="fc6bc-143">Der Typ, der hier verwendet werden soll, sollte in der Dokumentation für den Anbieter enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-143">The type to use here should be included in documentation for the provider.</span></span>

### <a name="code-based-registration"></a><span data-ttu-id="fc6bc-144">Codebasierte Registrierung</span><span class="sxs-lookup"><span data-stu-id="fc6bc-144">Code-based registration</span></span>

<span data-ttu-id="fc6bc-145">Ab Entity Framework 6 kann die anwendungsweite Konfiguration für EF im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-145">Starting with Entity Framework 6 application-wide configuration for EF can be specified in code.</span></span> <span data-ttu-id="fc6bc-146">Ausführliche Informationen dazu finden Sie unter _[Entity Framework – Code-Based Configuration (Codebasierte Konfiguration von Entity Framework)](https://msdn.microsoft.com/en-us/data/jj680699)_.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-146">For full details see _[Entity Framework Code-Based Configuration](https://msdn.microsoft.com/en-us/data/jj680699)_.</span></span> <span data-ttu-id="fc6bc-147">Normalerweise wird ein EF-Anbieter, der die codebasierter Konfiguration verwendet, durch Erstellung einer neuen Klasse registriert, die von System.Data.Entity.DbConfiguration abstammt und in der gleichen Assembly platziert wird, wie Ihre DbContext-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-147">The normal way to register an EF provider using code-based configuration is to create a new class that derives from System.Data.Entity.DbConfiguration and place it in the same assembly as your DbContext class.</span></span> <span data-ttu-id="fc6bc-148">Ihre DbConfiguration-Klasse sollte dann den Anbieter in ihrem Konstruktor registrieren.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-148">Your DbConfiguration class should then register the provider in its constructor.</span></span> <span data-ttu-id="fc6bc-149">Die DbConfiguration-Klasse sieht wie folgt aus, um beispielsweise den SQL Compact-Anbieter zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="fc6bc-149">For example, to register the SQL Compact provider the DbConfiguration class looks like this:</span></span>

``` csharp
    public class MyConfiguration : DbConfiguration
    {
        public MyConfiguration()
        {
            SetProviderServices(
                SqlCeProviderServices.ProviderInvariantName,
                SqlCeProviderServices.Instance);
        }
    }
```

<span data-ttu-id="fc6bc-150">In diesem Code stellt „SqlCeProviderServices.ProviderInvariantName“ ein praktisches Feature für die Zeichenfolge des invarianten Namens des SQL Server Compact-Anbieters („System.Data.SqlServerCe.4.0“) dar, und SqlCeProviderServices.Instance gibt die Singletoninstanz des SQL Compact-EF-Anbieters zurück.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-150">In this code “SqlCeProviderServices.ProviderInvariantName” is a convenience for the SQL Server Compact provider invariant name string (“System.Data.SqlServerCe.4.0”) and SqlCeProviderServices.Instance returns the singleton instance of the SQL Compact EF provider.</span></span>

## <a name="what-if-the-provider-i-need-isnt-available"></a><span data-ttu-id="fc6bc-151">Was passiert, wenn der Anbieter, den ich benötige, nicht verfügbar ist?</span><span class="sxs-lookup"><span data-stu-id="fc6bc-151">What if the provider I need isn’t available?</span></span>

<span data-ttu-id="fc6bc-152">Wenn der Anbieter für vorherige Version von EF verfügbar ist, wenden Sie sich an den Besitzer des Anbieters, und bitten Sie diesen, eine EF6-Version zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-152">If the provider is available for previous versions of EF, then we encourage you to contact the owner of the provider and ask them to create an EF6 version.</span></span> <span data-ttu-id="fc6bc-153">Sie sollten einen Verweis zur [Dokumentation für das EF6-Anbietermodell](~/ef6/fundamentals/providers/provider-model.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-153">You should include a reference to the [documentation for the EF6 provider model](~/ef6/fundamentals/providers/provider-model.md).</span></span>

## <a name="can-i-write-a-provider-myself"></a><span data-ttu-id="fc6bc-154">Kann ich selbst einen Anbieter schreiben?</span><span class="sxs-lookup"><span data-stu-id="fc6bc-154">Can I write a provider myself?</span></span>

<span data-ttu-id="fc6bc-155">Es ist bestimmt möglich, selbst einen EF-Anbieter zu erstellen, obwohl dies nicht als triviales Unterfangen angesehen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-155">It is certainly possible to create an EF provider yourself although it should not be considered a trivial undertaking.</span></span> <span data-ttu-id="fc6bc-156">Der Link oben zum EF6-Anbietermodell bietet einen guten Einstiegspunkt.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-156">The the link above about the EF6 provider model is a good place to start.</span></span> <span data-ttu-id="fc6bc-157">Es kann auch nützlich sein, den Code für den SQL Server- und SQL CE-Anbieter, der in der [Open Source-Codebasis von EF](https://github.com/aspnet/EntityFramework6) enthalten ist, als Startpunkt oder zur Referenz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-157">You may also find it useful to use the code for the SQL Server and SQL CE provider included in the [EF open source codebase](https://github.com/aspnet/EntityFramework6) as a starting point or for reference.</span></span>

<span data-ttu-id="fc6bc-158">Beachten Sie, dass der EF-Anbieter nicht so eng mit dem zugrunde liegenden ADO.NET-Anbieter verbunden ist, wenn Sie mit EF6 beginnen.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-158">Note that starting with EF6 the EF provider is less tightly coupled to the underlying ADO.NET provider.</span></span> <span data-ttu-id="fc6bc-159">Dadurch wird es einfacher, einen EF-Anbieter zu schreiben, da ADO.NET-Klassen nicht geschrieben oder umschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fc6bc-159">This makes it easier to write an EF provider without needing to write or wrap the ADO.NET classes.</span></span>