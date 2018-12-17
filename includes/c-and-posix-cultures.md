> [!NOTE]
> <span data-ttu-id="3d43b-101">**Ausführen von .NET Core nur auf Linux- und macOS-Systemen:** Beim Sortierungsverhalten für die C- und Posix-Kulturen ist immer die Groß-/Kleinschreibung zu beachten, weil diese Kulturen nicht die erwartete Unicode-Sortierreihenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d43b-101">**.NET Core running on Linux and macOS systems only:** The collation behavior for the C and Posix cultures is always case-sensitive because these cultures do not use the expected Unicode colation order.</span></span> <span data-ttu-id="3d43b-102">Bei der Durchführung kulturrelevanter Sortiervorgänge ohne Unterscheidung von Groß-/Kleinschreibung wird empfohlen, eine andere Kultur als C oder Posix zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d43b-102">We recommend that you use a culture other than C or Posix for performing culture-sensitive, case-insensitive sorting operations.</span></span>  