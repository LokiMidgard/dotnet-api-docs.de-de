### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="b79a1-101">Die Vorwärtskompatibilität für XSLT funktioniert jetzt</span><span class="sxs-lookup"><span data-stu-id="b79a1-101">XSLT forward compat now works</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b79a1-102">Details</span><span class="sxs-lookup"><span data-stu-id="b79a1-102">Details</span></span>|<span data-ttu-id="b79a1-103">In .NET Framework 4 verursachte die XSLT 1.0-Vorwärtskompatibilität die folgenden Probleme:</span><span class="sxs-lookup"><span data-stu-id="b79a1-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="b79a1-104">Beim Laden eines Stylesheets trat ein Fehler auf, wenn die Version auf 2.0 festgelegt war und der Parser ein unbekanntes XSLT 1.0-Konstrukt feststellte.</span><span class="sxs-lookup"><span data-stu-id="b79a1-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="b79a1-105">Das <code>xsl:sort</code>-Konstrukt konnte keine Daten sortieren, wenn die Stylesheetversion auf 1.1 festgelegt war.</span><span class="sxs-lookup"><span data-stu-id="b79a1-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="b79a1-106">In .NET Framework 4.5 wurden diese Probleme behoben, und der XSLT 1.0-Vorwärtskompatibilitätsmodus funktioniert ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="b79a1-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>|
|<span data-ttu-id="b79a1-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b79a1-107">Suggestion</span></span>|<span data-ttu-id="b79a1-108">Die meisten Apps sollten zwar davon nicht betroffen sind, aber die Daten werden teilweise unterschiedlich sortiert, da das xsl:sort-Element jetzt berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="b79a1-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="b79a1-109">Wenn <code>xsl:sort</code> in 1.1-Stylesheets verwendet wird, sollten Sie sicherstellen, dass die Apps nicht von der unsortierten Reihenfolge von Daten abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="b79a1-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="b79a1-110">Wenn Apps von dem in Version 4.0 enthaltenen Sortierverhalten abhängig ist, sollten Sie <code>xsl:sort</code> aus dem Stylesheet entfernen.</span><span class="sxs-lookup"><span data-stu-id="b79a1-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>|
|<span data-ttu-id="b79a1-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="b79a1-111">Scope</span></span>|<span data-ttu-id="b79a1-112">Edge</span><span class="sxs-lookup"><span data-stu-id="b79a1-112">Edge</span></span>|
|<span data-ttu-id="b79a1-113">Version</span><span class="sxs-lookup"><span data-stu-id="b79a1-113">Version</span></span>|<span data-ttu-id="b79a1-114">4.5</span><span class="sxs-lookup"><span data-stu-id="b79a1-114">4.5</span></span>|
|<span data-ttu-id="b79a1-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b79a1-115">Type</span></span>|<span data-ttu-id="b79a1-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b79a1-116">Runtime</span></span>|
|<span data-ttu-id="b79a1-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b79a1-117">Affected APIs</span></span>|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
