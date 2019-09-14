---
title: 步驟 4：設定流量旁路
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並為信任的 Office 365 位置的流量旁路設定 Web 瀏覽器和邊緣裝置。
ms.openlocfilehash: 416c93fd3f44e1cd9edba52a9d6117ac6d133760
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982784"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="a74cd-103">步驟 4：設定流量旁路</span><span class="sxs-lookup"><span data-stu-id="a74cd-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="a74cd-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a74cd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a74cd-p101">因為一般網際網路流量可能會有風險，所以一般組織網路會使用邊緣裝置 (例如 Proxy 伺服器、SSL 中斷和檢查，以及封包檢查裝置) 和資料外洩防護系統來加強安全性。請閱讀「在 Office 365 流量上使用協力廠商網路裝置或解決方案」中一些與網路攔截裝置有關的問題。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="a74cd-p102">不過，Microsoft 365 雲端型服務所使用的 DNS 網域名稱與 IP 位址 是眾所周知的。此外，流量和服務本身會受到許多安全性功能保護。因為此安全性和保護已經到位，所以您的邊緣裝置需要複製它。Microsoft 365 流量的中繼目的地和複製安全性處理會大幅降低效能。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="a74cd-p103">消除中繼目的地及複製安全性處理的第一個步驟是識別 Microsoft 365 流量。Microsoft 已定義下列類型的 DNS 網域名稱和 IP 位址範圍，稱為端點：</span><span class="sxs-lookup"><span data-stu-id="a74cd-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="a74cd-113">**最佳化** - 連線至每個 Office 365 服務所需的動作，並代表超過 75% 的 Microsoft 365 頻寬、連線和資料量。</span><span class="sxs-lookup"><span data-stu-id="a74cd-113">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="a74cd-114">這些端點代表對網路效能、延遲和可用性最敏感的 Microsoft 365 情節。</span><span class="sxs-lookup"><span data-stu-id="a74cd-114">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="a74cd-115">**允許** - 連線至特定 Microsoft 365 服務與功能所需的動作，但對網路效能和延遲不如最佳化類別中的項目敏感。</span><span class="sxs-lookup"><span data-stu-id="a74cd-115">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="a74cd-116">**預設** - 代表不需要任何最佳化的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="a74cd-116">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="a74cd-117">您可以將預設類別端點視為正常網際網路流量。</span><span class="sxs-lookup"><span data-stu-id="a74cd-117">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="a74cd-118">您可以在 [ https://aka.ms/o365endpoints ](https://aka.ms/o365endpoints) 找到 DNS 網域名稱及 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="a74cd-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="a74cd-119">Microsoft 建議您：</span><span class="sxs-lookup"><span data-stu-id="a74cd-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="a74cd-p106">在內部部署電腦的網際網路瀏覽器上使用 Proxy 自動設定 (PAC) 指令碼，對 Microsoft 365 雲端型服務的 DNS 網域名稱略過 Proxy 伺服器。如需最新的 Microsoft 365 PAC 指令碼，請參閱 [Get-Pacfile PowerShell 指令碼](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- 
- <span data-ttu-id="a74cd-p107">分析您的邊緣裝置來判定複製處理，然後設定它們以將流量轉送至最佳化及允許端點。這稱為流量旁路。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="a74cd-p108">邊緣裝置包含防火牆、SSL 中斷和檢查、封包檢查裝置，以及資料外洩防護系統。若要設定並更新邊緣裝置的組態，您可以使用指令碼或 REST 呼叫，以使用來自 Office 365 端點 Web 服務的結構化端點清單。如需詳細資訊，請參閱[Office 365 IP 位址和 URL Web 服務](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="a74cd-p109">請注意，您只對 Microsoft 365 最佳化和允許類別端點的流量略過一般 Proxy 和網路安全性處理。所有其他一般網際網路流量將會透過 Proxy 進行，並受制於您的現有網路安全性處理。</span><span class="sxs-lookup"><span data-stu-id="a74cd-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="a74cd-129">作為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step4)。</span><span class="sxs-lookup"><span data-stu-id="a74cd-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a74cd-130">下一步</span><span class="sxs-lookup"><span data-stu-id="a74cd-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="a74cd-131">最佳化用戶端和 Office 365 服務效能</span><span class="sxs-lookup"><span data-stu-id="a74cd-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



