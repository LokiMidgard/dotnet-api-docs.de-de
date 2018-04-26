### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="e2b76-101">Die ResolveAssemblyReference-Aufgabe warnt jetzt vor Abhängigkeiten von der falschen Architektur</span><span class="sxs-lookup"><span data-stu-id="e2b76-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e2b76-102">Details</span><span class="sxs-lookup"><span data-stu-id="e2b76-102">Details</span></span>|<span data-ttu-id="e2b76-103">Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht.</span><span class="sxs-lookup"><span data-stu-id="e2b76-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="e2b76-104">Dies erfolgt z. B., wenn eine App, die mit der <code>AnyCPU</code>-Option kompiliert wurde, einen x86-Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="e2b76-104">For example, this occurs if an app that was compiled with the <code>AnyCPU</code> option includes an x86 reference.</span></span> <span data-ttu-id="e2b76-105">Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).</span><span class="sxs-lookup"><span data-stu-id="e2b76-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>|
|<span data-ttu-id="e2b76-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e2b76-106">Suggestion</span></span>|<span data-ttu-id="e2b76-107">Es gibt zwei Bereiche mit Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="e2b76-107">There are two areas of impact:</span></span><ul><li><span data-ttu-id="e2b76-108">Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2b76-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="e2b76-109">Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="e2b76-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span></li><li><span data-ttu-id="e2b76-110">Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e2b76-110">If warnings are treated as errors, the app will fail to compile.</span></span></li></ul>|
|<span data-ttu-id="e2b76-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b76-111">Scope</span></span>|<span data-ttu-id="e2b76-112">Gering</span><span class="sxs-lookup"><span data-stu-id="e2b76-112">Minor</span></span>|
|<span data-ttu-id="e2b76-113">Version</span><span class="sxs-lookup"><span data-stu-id="e2b76-113">Version</span></span>|<span data-ttu-id="e2b76-114">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e2b76-114">4.5.1</span></span>|
|<span data-ttu-id="e2b76-115">Typ</span><span class="sxs-lookup"><span data-stu-id="e2b76-115">Type</span></span>|<span data-ttu-id="e2b76-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="e2b76-116">Retargeting</span></span>|
