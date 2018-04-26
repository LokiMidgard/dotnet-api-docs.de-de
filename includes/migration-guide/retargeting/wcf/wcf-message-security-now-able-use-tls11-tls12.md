### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="32e0e-101">WCF-Nachrichtensicherheit kann jetzt TLS1.1 und TLS1.2 verwenden</span><span class="sxs-lookup"><span data-stu-id="32e0e-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="32e0e-102">Details</span><span class="sxs-lookup"><span data-stu-id="32e0e-102">Details</span></span>|<span data-ttu-id="32e0e-103">Ab .NET Framework 4.7 können Kunden über die Anwendungskonfigurationseinstellungen neben SSL3.0 und TLS1.0 entweder TLS1.1 oder TLS1.2 in WCF-Nachrichtensicherheit konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32e0e-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="32e0e-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="32e0e-104">Suggestion</span></span>|<span data-ttu-id="32e0e-105">In .NET Framework 4.7 werden TLS1.1 und TLS1.2 in WCF-Nachrichtensicherheit standardmäßig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="32e0e-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="32e0e-106">Sie können die Unterstützung aktivieren, indem Sie die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config- oder der web.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="32e0e-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="32e0e-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="32e0e-107">Scope</span></span>|<span data-ttu-id="32e0e-108">Edge</span><span class="sxs-lookup"><span data-stu-id="32e0e-108">Edge</span></span>|
|<span data-ttu-id="32e0e-109">Version</span><span class="sxs-lookup"><span data-stu-id="32e0e-109">Version</span></span>|<span data-ttu-id="32e0e-110">4.7</span><span class="sxs-lookup"><span data-stu-id="32e0e-110">4.7</span></span>|
|<span data-ttu-id="32e0e-111">Typ</span><span class="sxs-lookup"><span data-stu-id="32e0e-111">Type</span></span>|<span data-ttu-id="32e0e-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="32e0e-112">Retargeting</span></span>|
