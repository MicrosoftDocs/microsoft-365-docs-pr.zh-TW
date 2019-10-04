---
title: 步驟 5：最佳化用戶端和 Office 365 服務效能
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 設定 TCP 設定與 Office 365 服務以獲得更佳效能。
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370070"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="a2fcb-103">步驟 5：最佳化用戶端和 Office 365 服務效能</span><span class="sxs-lookup"><span data-stu-id="a2fcb-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="a2fcb-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a2fcb-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![階段 1 - 網路](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a2fcb-106">您可以透過微調傳輸控制通訊協定 (TCP) 在用戶端裝置與 Office 365 服務間的運作方式來增加效能。</span><span class="sxs-lookup"><span data-stu-id="a2fcb-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="a2fcb-107">針對用戶端裝置，您可以變更用戶端裝置上的下列 TCP 設定以最佳化 TCP 效能：</span><span class="sxs-lookup"><span data-stu-id="a2fcb-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="a2fcb-108">[TCP 視窗縮放](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/)，因此用戶端裝置可以傳送更多資料，再要求通知</span><span class="sxs-lookup"><span data-stu-id="a2fcb-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="a2fcb-109">[TCP 閒置時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/)，因此用戶端裝置可以更有效率地處理開啟的連線</span><span class="sxs-lookup"><span data-stu-id="a2fcb-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="a2fcb-110">[TCP 最大區段大小](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/)，所以用戶端裝置可以傳送封包中資料的最大區塊</span><span class="sxs-lookup"><span data-stu-id="a2fcb-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="a2fcb-111">[TCP 選擇性通知](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/)，因此用戶端裝置可以更有效率地認知接收資料</span><span class="sxs-lookup"><span data-stu-id="a2fcb-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="a2fcb-112">針對 Office 365 服務，請參閱這些額外的資源以最佳化效能：</span><span class="sxs-lookup"><span data-stu-id="a2fcb-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="a2fcb-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a2fcb-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="a2fcb-114">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="a2fcb-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="a2fcb-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2fcb-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="a2fcb-116">Project Web App for Project Online</span><span class="sxs-lookup"><span data-stu-id="a2fcb-116">Project Web App for Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="a2fcb-117">做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step5)。</span><span class="sxs-lookup"><span data-stu-id="a2fcb-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a2fcb-118">下一步</span><span class="sxs-lookup"><span data-stu-id="a2fcb-118">Next step</span></span>

[<span data-ttu-id="a2fcb-119">網路基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="a2fcb-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
