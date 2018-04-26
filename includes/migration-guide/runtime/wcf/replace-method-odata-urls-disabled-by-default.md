### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="2d7df-101">Die Replace-Methode in OData-URLs ist standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2d7df-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2d7df-102">Details</span><span class="sxs-lookup"><span data-stu-id="2d7df-102">Details</span></span>|<span data-ttu-id="2d7df-103">Ab .NET Framework 4.5 ist die Replace-Methode in OData-URLs standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d7df-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="2d7df-104">Wenn „Replace“ für OData (jetzt standardmäßig) deaktiviert ist, schlagen alle Benutzeranforderungen fehl, einschließlich der Ersetzungsfunktionen (die nicht üblich sind).</span><span class="sxs-lookup"><span data-stu-id="2d7df-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="2d7df-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2d7df-105">Suggestion</span></span>|<span data-ttu-id="2d7df-106">Wenn die Replace-Methode erforderlich ist (was nicht üblich ist), kann sie über die Konfigurationseinstellung <xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name> erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2d7df-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="2d7df-107">Eine aktivierte Replace-Methode kann jedoch Sicherheitslücken öffnen und sollte nur nach sorgfältiger Prüfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d7df-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="2d7df-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="2d7df-108">Scope</span></span>|<span data-ttu-id="2d7df-109">Edge</span><span class="sxs-lookup"><span data-stu-id="2d7df-109">Edge</span></span>|
|<span data-ttu-id="2d7df-110">Version</span><span class="sxs-lookup"><span data-stu-id="2d7df-110">Version</span></span>|<span data-ttu-id="2d7df-111">4.5</span><span class="sxs-lookup"><span data-stu-id="2d7df-111">4.5</span></span>|
|<span data-ttu-id="2d7df-112">Typ</span><span class="sxs-lookup"><span data-stu-id="2d7df-112">Type</span></span>|<span data-ttu-id="2d7df-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2d7df-113">Runtime</span></span>|
|<span data-ttu-id="2d7df-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2d7df-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
