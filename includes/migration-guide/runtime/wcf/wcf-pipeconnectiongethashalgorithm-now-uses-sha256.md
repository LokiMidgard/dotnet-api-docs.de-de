### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="9c111-101">Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256</span><span class="sxs-lookup"><span data-stu-id="9c111-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9c111-102">Details</span><span class="sxs-lookup"><span data-stu-id="9c111-102">Details</span></span>|<span data-ttu-id="9c111-103">Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9c111-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="9c111-104">In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c111-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="9c111-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9c111-105">Suggestion</span></span>|<span data-ttu-id="9c111-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9c111-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="9c111-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="9c111-107">Scope</span></span>|<span data-ttu-id="9c111-108">Gering</span><span class="sxs-lookup"><span data-stu-id="9c111-108">Minor</span></span>|
|<span data-ttu-id="9c111-109">Version</span><span class="sxs-lookup"><span data-stu-id="9c111-109">Version</span></span>|<span data-ttu-id="9c111-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9c111-110">4.7.1</span></span>|
|<span data-ttu-id="9c111-111">Typ</span><span class="sxs-lookup"><span data-stu-id="9c111-111">Type</span></span>|<span data-ttu-id="9c111-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9c111-112">Runtime</span></span>|
