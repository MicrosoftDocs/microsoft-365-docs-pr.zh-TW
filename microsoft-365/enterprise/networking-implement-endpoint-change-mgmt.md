---
title: 步驟 4：規劃 URL 和 IP 位址變更
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 44990dcfd09e5cc2a44666da43fdeeaffd59da7d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866109"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="dff81-102">步驟 4：規劃 URL 和 IP 位址變更</span><span class="sxs-lookup"><span data-stu-id="dff81-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="dff81-103">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="dff81-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="dff81-p101">此步驟需完成[步驟 3](networking-configure-proxies-firewalls.md)。如果尚未完成步驟 3，您可以跳到[步驟 5](networking-optimize-tcp-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="dff81-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="dff81-p102">由 Microsoft 365 全域網路使用的 URL 和 IP 位址會隨時間變更，因此請務必規劃這些端點的更新。比方說，您可能需要重新設定安全性周邊裝置：</span><span class="sxs-lookup"><span data-stu-id="dff81-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="dff81-108">需要不受阻礙的處理之新服務的新 URL</span><span class="sxs-lookup"><span data-stu-id="dff81-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="dff81-109">為已停用的服務移除 URL</span><span class="sxs-lookup"><span data-stu-id="dff81-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="dff81-110">Microsoft 的新網路位置及網際網路上的伺服器之新的 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="dff81-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="dff81-111">不同服務的 IP 位址範圍變更</span><span class="sxs-lookup"><span data-stu-id="dff81-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="dff81-112">如需針對端點變更建立執行計劃的詳細資訊，其中包含對變更的通知，請參閱[管理 Office 365 端點-整合](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration)和[管理 Office 365 端點-Proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)。</span><span class="sxs-lookup"><span data-stu-id="dff81-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="dff81-113">作為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step4)。</span><span class="sxs-lookup"><span data-stu-id="dff81-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="dff81-114">下一步</span><span class="sxs-lookup"><span data-stu-id="dff81-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="dff81-115">最佳化用戶端和 Office 365 服務效能</span><span class="sxs-lookup"><span data-stu-id="dff81-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
