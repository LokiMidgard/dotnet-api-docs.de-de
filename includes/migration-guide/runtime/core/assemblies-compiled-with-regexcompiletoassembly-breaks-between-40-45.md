### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="13ffc-101">Mit der Regex.CompileToAssembly-Methode kompilierte Assemblys zwischen 4.0 und 4.5 werden unterbrochen</span><span class="sxs-lookup"><span data-stu-id="13ffc-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="13ffc-102">Details</span><span class="sxs-lookup"><span data-stu-id="13ffc-102">Details</span></span>|<span data-ttu-id="13ffc-103">Wenn eine Assembly aus kompilierten regulären Ausdrücken mit .NET Framework 4.5 erstellt wird und auf .NET Framework 4 ausgerichtet ist, wird bei dem Versuch, die regulären Ausdrücke in dieser Assembly auf einem System zu verwenden, auf dem .NET Framework 4 installiert ist, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="13ffc-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>|
|<span data-ttu-id="13ffc-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="13ffc-104">Suggestion</span></span>|<span data-ttu-id="13ffc-105">Um dieses Problem zu umgehen, haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="13ffc-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="13ffc-106">Erstellen Sie die Assembly, die die regulären Ausdrücke enthält, mit .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="13ffc-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="13ffc-107">Verwenden Sie einen interpretierten regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="13ffc-107">Use an interpreted regular expression.</span></span></li></ul>|
|<span data-ttu-id="13ffc-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="13ffc-108">Scope</span></span>|<span data-ttu-id="13ffc-109">Gering</span><span class="sxs-lookup"><span data-stu-id="13ffc-109">Minor</span></span>|
|<span data-ttu-id="13ffc-110">Version</span><span class="sxs-lookup"><span data-stu-id="13ffc-110">Version</span></span>|<span data-ttu-id="13ffc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="13ffc-111">4.5</span></span>|
|<span data-ttu-id="13ffc-112">Typ</span><span class="sxs-lookup"><span data-stu-id="13ffc-112">Type</span></span>|<span data-ttu-id="13ffc-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="13ffc-113">Runtime</span></span>|
|<span data-ttu-id="13ffc-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="13ffc-114">Affected APIs</span></span>|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
