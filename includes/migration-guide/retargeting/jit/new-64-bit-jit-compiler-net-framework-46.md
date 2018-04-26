### <a name="new-64-bit-jit-compiler-in-the-net-framework-46"></a><span data-ttu-id="ae649-101">Neuer 64-Bit-JIT-Compiler in .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="ae649-101">New 64-bit JIT compiler in the .NET Framework 4.6</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ae649-102">Details</span><span class="sxs-lookup"><span data-stu-id="ae649-102">Details</span></span>|<span data-ttu-id="ae649-103">Ab .NET Framework 4.6 wird ein neuer 64-Bit-JIT-Compiler für die Just-in-Time-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae649-103">Starting with the .NET Framework 4.6, a new 64-bit JIT compiler is used for just-in-time compilation.</span></span> <span data-ttu-id="ae649-104">In einigen Fällen wird eine unerwartete Ausnahme ausgelöst oder ein anderes Verhalten beobachtet als bei der Ausführung des 32-Bit-Compilers oder des älteren 64-Bit-JIT-Compilers.</span><span class="sxs-lookup"><span data-stu-id="ae649-104">In some cases, an unexpected exception is thrown or a different behavior is observed than if an app is run using the 32-bit compiler or the older 64-bit JIT compiler.</span></span> <span data-ttu-id="ae649-105">Diese Änderung wirkt sich nicht auf den 32-Bit-JIT-Compiler aus. Die bekannten Unterschiede umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ae649-105">This change does not affect the 32-bit JIT compiler.The known differences include the following:</span></span><ul><li><span data-ttu-id="ae649-106">Unter bestimmten Umständen kann ein Unboxingvorgang in Releasebuilds mit aktivierter Optimierung eine <xref:System.NullReferenceException>-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="ae649-106">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span></li><li><span data-ttu-id="ae649-107">In manchen Fällen kann bei der Ausführung von Produktionscode in einem großen Methodentext eine <xref:System.StackOverflowException>-Ausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ae649-107">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span></li><li><span data-ttu-id="ae649-108">Unter bestimmten Bedingungen werden in Releasebuilds an eine Methode übergebene Strukturen als Verweistypen statt als Werttypen behandelt.</span><span class="sxs-lookup"><span data-stu-id="ae649-108">Under certain conditions, structures passed to a method are treated as reference types rather than as value types in Release builds.</span></span> <span data-ttu-id="ae649-109">Eins der Anzeichen dieses Problems besteht darin, dass die einzelnen Elemente einer Sammlung in unerwarteter Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ae649-109">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span></li><li><span data-ttu-id="ae649-110">Unter bestimmten Bedingungen ist der Vergleich von <xref:System.UInt16>-Werten mit festgelegtem hohem Bit fehlerhaft, wenn Optimierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ae649-110">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span></li><li><span data-ttu-id="ae649-111">Unter bestimmten Umständen, insbesondere beim Initialisieren von Arraywerten, kann die Speicherinitialisierung durch die IL-Anweisung <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> mit einem falschen Wert erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ae649-111">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="ae649-112">Dies kann entweder zu einem Ausnahmefehler oder zu einer falschen Ausgabe führen.</span><span class="sxs-lookup"><span data-stu-id="ae649-112">This can result either in an unhandled exception or incorrect output.</span></span></li><li><span data-ttu-id="ae649-113">Unter bestimmten seltenen Bedingungen kann ein bedingter Bittest den falschen <xref:System.Boolean>-Wert zurückgeben oder eine Ausnahme auslösen, wenn Compileroptimierungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ae649-113">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span></li><li><span data-ttu-id="ae649-114">Wenn unter bestimmten Umständen eine <code>if</code>-Anweisung für die Prüfung auf eine Bedingung vor dem Eintritt in einen <code>try</code>-Block oder beim Verlassen eines <code>try</code>-Blocks erfolgt und die gleiche Bedingung im <code>catch</code>- oder <code>finally</code>-Block ausgewertet wird, entfernt der neue 64-Bit-JIT-Compiler beim Optimieren von Code die <code>if</code>-Bedingung aus dem <code>catch</code>- oder <code>finally</code>-Block.</span><span class="sxs-lookup"><span data-stu-id="ae649-114">Under certain conditions, if an <code>if</code> statement is used to test for a condition before entering  a <code>try</code> block and in the exit from the <code>try</code> block, and the same condition is evaluated in the <code>catch</code> or <code>finally</code> block, the new 64-bit JIT compiler removes the <code>if</code> condition from the <code>catch</code> or <code>finally</code> block when it optimizes code.</span></span> <span data-ttu-id="ae649-115">Daher wird Code innerhalb der <code>if</code>-Anweisung im <code>catch</code>- oder <code>finally</code>-Block ohne Bedingung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ae649-115">As a result, code inside the <code>if</code> statement in the <code>catch</code> or <code>finally</code> block is executed unconditionally.</span></span></li></ul>|
|<span data-ttu-id="ae649-116">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ae649-116">Suggestion</span></span>|<span data-ttu-id="ae649-117"><strong>Entschärfung bekannter Probleme</strong>: Wenn die oben aufgeführten Probleme bei Ihnen auftreten, können Sie darauf mit einer der folgenden Maßnahmen reagieren:</span><span class="sxs-lookup"><span data-stu-id="ae649-117"><strong>Mitigation of known issues</strong> If you encounter the issues listed above, you can address them by doing any of the following:</span></span><ul><li><span data-ttu-id="ae649-118">Ausführen eines Upgrades auf .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ae649-118">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="ae649-119">Der neue 64-Bit-Compiler, der in .NET Framework 4.6.2 enthalten ist, behebt jedes dieser bekannten Probleme.</span><span class="sxs-lookup"><span data-stu-id="ae649-119">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span></li><li><span data-ttu-id="ae649-120">Stellen Sie sicher, dass ihre Windows-Version auf dem aktuellen Stand ist, indem Sie Windows Update ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae649-120">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="ae649-121">Serviceupdates für .NET Framework 4.6 und 4.6.1 beheben jedes dieser Probleme, mit Ausnahme der <xref:System.NullReferenceException>-Ausnahme bei Unboxingvorgängen.</span><span class="sxs-lookup"><span data-stu-id="ae649-121">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span></li><li><span data-ttu-id="ae649-122">Kompilieren Sie mit dem älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ae649-122">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="ae649-123">Informationen zum Vorgehen dazu finden Sie unter <strong>Entschärfung anderer Probleme</strong>.</span><span class="sxs-lookup"><span data-stu-id="ae649-123">See the <strong>Mitigation of other issues</strong> section for more information on how to do this.</span></span></li></ul><span data-ttu-id="ae649-124"><strong>Entschärfung anderer Probleme</strong>: Wenn Sie andere Verhaltensunterschiede zwischen Code, der mit dem älteren 64-Bit-Compiler kompiliert wurde, und dem mit dem neuen 64-Bit-JIT-Compiler kompiliertem Code oder zwischen den Debug- und Releaseversionen Ihrer App feststellen, die beide mit dem neuen 64-Bit-JIT-Compiler kompiliert wurden, können Sie folgendermaßen vorgehen, um Ihre App mit dem älteren 64-Bit-JIT-Compiler zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="ae649-124"><strong>Mitigation of other issues</strong> If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span><ul><li><span data-ttu-id="ae649-125">Sie können der Konfigurationsdatei Ihrer Anwendung auf Anwendungsbasis das [\<useLegacyJit>](~/docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae649-125">On a per-application basis, you can add the [\<useLegacyJit>](~/docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="ae649-126">Die folgende Anweisung deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den 64-Bit-Legacy-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ae649-126">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span></li></ul><pre><code class="language-xml">&lt;?xml version =&quot;1.0&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;useLegacyJit enabled=&quot;1&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><ul><li><span data-ttu-id="ae649-127">Auf Benutzerbasis können Sie dem <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework</code>-Wert der Registrierung einen <code>REG_DWORD</code>-Wert mit dem Namen <code>useLegacyJit</code> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae649-127">On a per-user basis, you can add a <code>REG_DWORD</code> value named <code>useLegacyJit</code> to the <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework</code> key of the registry.</span></span> <span data-ttu-id="ae649-128">Der Wert 1 aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert 0 deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ae649-128">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span></li><li><span data-ttu-id="ae649-129">Auf Computerbasis können Sie dem <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework</code>-Schlüssel der Registrierung einen <code>REG_DWORD</code>-Wert mit dem Namen <code>useLegacyJit</code> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae649-129">On a per-machine basis, you can add a <code>REG_DWORD</code> value named <code>useLegacyJit</code> to the <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework</code> key of the registry.</span></span> <span data-ttu-id="ae649-130">Der Wert <code>1</code> aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert <code>0</code> deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ae649-130">A value of <code>1</code> enables the legacy 64-bit JIT compiler; a value of <code>0</code> disables it and enables the new 64-bit JIT compiler.</span></span></li></ul><span data-ttu-id="ae649-131">Ferner können Sie uns über das Problem informieren, indem Sie einen Bug auf [Microsoft Connect](https://connect.microsoft.com/VisualStudio) melden.</span><span class="sxs-lookup"><span data-stu-id="ae649-131">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>|
|<span data-ttu-id="ae649-132">Bereich</span><span class="sxs-lookup"><span data-stu-id="ae649-132">Scope</span></span>|<span data-ttu-id="ae649-133">Edge</span><span class="sxs-lookup"><span data-stu-id="ae649-133">Edge</span></span>|
|<span data-ttu-id="ae649-134">Version</span><span class="sxs-lookup"><span data-stu-id="ae649-134">Version</span></span>|<span data-ttu-id="ae649-135">4.6</span><span class="sxs-lookup"><span data-stu-id="ae649-135">4.6</span></span>|
|<span data-ttu-id="ae649-136">Typ</span><span class="sxs-lookup"><span data-stu-id="ae649-136">Type</span></span>|<span data-ttu-id="ae649-137">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="ae649-137">Retargeting</span></span>|
