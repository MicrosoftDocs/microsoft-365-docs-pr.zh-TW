<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="e31c5-101">必要：Microsoft 365 企業版可以使用您的網路</span><span class="sxs-lookup"><span data-stu-id="e31c5-101">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="e31c5-102">您的辦公室有足夠的網際網路頻寬，可容納 Microsoft 365 流量，包括 Office 365、Microsoft Intune 以及 Windows 10 企業版安裝和更新。</span><span class="sxs-lookup"><span data-stu-id="e31c5-102">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="e31c5-103">您的整體網路對應至 [Office 365 參考架構](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)。</span><span class="sxs-lookup"><span data-stu-id="e31c5-103">Your overall network maps to an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="e31c5-104">您的網路變更已經過試驗和測試，並符合您的流量延遲需求。</span><span class="sxs-lookup"><span data-stu-id="e31c5-104">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="e31c5-105">如有需要，[步驟 1](../networking-provide-bandwidth-cloud-services.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="e31c5-105">If needed, [Step 1](../networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="e31c5-106">必要：您的當地辦公室具備當地網際網路連線和名稱解析</span><span class="sxs-lookup"><span data-stu-id="e31c5-106">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="e31c5-p101">您已設定每個當地辦公室可透過當地 ISP 存取網際網路，而 ISP 的 DNS 伺服器會使用當地公用 IP 位址來識別它們在網際網路上的位置。這可確保存取 Microsoft 365 雲端服務的使用者獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="e31c5-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="e31c5-109">如果您的分公司不是使用當地 ISP，效能可能會變差，因為網路流量必須通過組織的骨幹，或是資料要求會交由遠處的前端伺服器處理。</span><span class="sxs-lookup"><span data-stu-id="e31c5-109">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="e31c5-110">如何測試</span><span class="sxs-lookup"><span data-stu-id="e31c5-110">How to test</span></span>
<span data-ttu-id="e31c5-p102">在辦公室內的裝置上使用工具或網站來判斷 Proxy 伺服器所使用的公用 IP 位址。例如，使用 [What Is My IP Address](https://www.whatismypublicip.com/) (我的 IP 位址是什麼) 網頁。此公用 IP 位址由 ISP 指派，應該是地理區域性的。不應該來自總公司公用 IP 位址範圍或雲端型網路安全性廠商。</span><span class="sxs-lookup"><span data-stu-id="e31c5-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="e31c5-115">如有需要，[步驟 2](../networking-dns-resolution-same-location.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="e31c5-115">If needed, [Step 2](../networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
### <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="e31c5-116">選用：已移除不需要的網路 Hairpin</span><span class="sxs-lookup"><span data-stu-id="e31c5-116">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="e31c5-p103">您已檢查網路 Hairpin，並判斷出其對您的所有辦公室之效能的影響。您已移除可能的網路 Hairpin，或與協力廠商網路或安全性提供者合作，為其網路實作最佳化的 Microsoft 365 對等。</span><span class="sxs-lookup"><span data-stu-id="e31c5-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="e31c5-119">如有需要，[步驟 3](../networking-avoid-network-hairpins.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e31c5-119">If needed, [Step 3](../networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="e31c5-120">選用：已在您的網際網路瀏覽器和邊緣裝置上設定流量旁路</span><span class="sxs-lookup"><span data-stu-id="e31c5-120">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="e31c5-121">已將最新的 PAC 檔案部署至內部部署網際網路瀏覽器，以便送至 Microsoft 365 DNS 網域名稱的流量可以略過 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e31c5-121">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="e31c5-122">已設定您的網路周邊裝置 (例如防火牆、SSL 中斷和檢查，以及封包檢查裝置) 來使用流量旁路，或最低限度地處理送至 Microsoft 365 端點之最佳化和允許類別的流量。</span><span class="sxs-lookup"><span data-stu-id="e31c5-122">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


#### <a name="how-to-test"></a><span data-ttu-id="e31c5-123">如何測試</span><span class="sxs-lookup"><span data-stu-id="e31c5-123">How to test</span></span>

<span data-ttu-id="e31c5-124">在網路周邊裝置上使用記錄工具，以確保送至 Microsoft 365 的流量沒有經過檢查、解密或其他形式妨礙。</span><span class="sxs-lookup"><span data-stu-id="e31c5-124">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="e31c5-125">如有需要，[步驟 4](../networking-configure-proxies-firewalls.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e31c5-125">If needed, [Step 4](../networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="e31c5-126">選用：設定用戶端和 Office 365 應用程式達到最佳效能</span><span class="sxs-lookup"><span data-stu-id="e31c5-126">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="e31c5-127">您已在用戶端裝置上針對 Exchange Online、商務用 Skype Online、SharePoint Online 和 Project Online 服務最佳化傳輸控制通訊協定 (TCP) 設定。</span><span class="sxs-lookup"><span data-stu-id="e31c5-127">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="e31c5-128">如有需要，[步驟 5](../networking-optimize-tcp-performance.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e31c5-128">If needed, [Step 5](../networking-optimize-tcp-performance.md) can help you with this option.</span></span>
