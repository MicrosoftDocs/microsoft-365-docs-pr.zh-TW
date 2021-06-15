---
title: 監視 Microsoft 365 連線能力
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: 在本文中，您將瞭解可用於監視及維護 Microsoft 365 連線的工具和技術。
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924196"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="39abe-103">監視 Microsoft 365 連線能力</span><span class="sxs-lookup"><span data-stu-id="39abe-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="39abe-104">在您部署 Microsoft 365 後，您可以使用下列一些工具和技術，維持 Microsoft 365 連線能力。</span><span class="sxs-lookup"><span data-stu-id="39abe-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="39abe-105">您需要瞭解官方[服務健康情況和持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)指導方針，以及[在慢速網路上使用 Microsoft 365 的最佳作法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="39abe-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="39abe-106">您也想要抓取 Microsoft 365 的系統[管理應用程式](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)，並[為商務用 Microsoft 365 書簽-系統管理](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)說明。</span><span class="sxs-lookup"><span data-stu-id="39abe-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="39abe-107">監控 Microsoft 365 連線能力</span><span class="sxs-lookup"><span data-stu-id="39abe-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="39abe-108">監控類型</span><span class="sxs-lookup"><span data-stu-id="39abe-108">Type of monitoring</span></span> |<span data-ttu-id="39abe-109">描述</span><span class="sxs-lookup"><span data-stu-id="39abe-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="39abe-110">**取得新 Microsoft 365 端點的通知**</span><span class="sxs-lookup"><span data-stu-id="39abe-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="39abe-111">如果您正在[管理 Microsoft 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)，當我們發佈新的端點時，您將會收到通知，您可以使用您最愛的 rss 讀取器訂閱 rss 摘要。</span><span class="sxs-lookup"><span data-stu-id="39abe-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="39abe-112">以下是如何透過[Outlook 訂閱](https://go.microsoft.com/fwlink/p/?LinkId=532416)，也可以[讓 RSS 摘要更新以電子郵件傳送給您](https://go.microsoft.com/fwlink/p/?LinkId=532417)。</span><span class="sxs-lookup"><span data-stu-id="39abe-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="39abe-113">**使用 System Center 監視 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="39abe-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="39abe-114">如果您使用的是 Microsoft System Center，您可以下載[System Center 管理元件，以供 Office 365](https://www.microsoft.com/download/details.aspx?id=43708)開始監視 Microsoft 365 今天。</span><span class="sxs-lookup"><span data-stu-id="39abe-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="39abe-115">如需詳細的指導，請參閱管理元件作業指南。</span><span class="sxs-lookup"><span data-stu-id="39abe-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="39abe-116">**監控 Azure ExpressRoute 的健康情況**</span><span class="sxs-lookup"><span data-stu-id="39abe-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="39abe-117">如果您是使用 azure ExpressRoute Microsoft 365 來連線至 Microsoft 365，您會想要確定您同時使用 Microsoft 365 服務健康情況儀表板，以及 azure 使用[azure 資源健康情況來減少疑難排解時間](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="39abe-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="39abe-118">**使用 Azure AD Connect Health 搭配 AD FS**</span><span class="sxs-lookup"><span data-stu-id="39abe-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="39abe-119">如果您使用 AD fs 來處理具有 Microsoft 365 的單一 Sign-On，您會想要開始[使用 Azure ad 連線狀況來監視您的 AD FS 基礎結構](/azure/active-directory/hybrid/how-to-connect-health-adfs)。</span><span class="sxs-lookup"><span data-stu-id="39abe-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="39abe-120">**以程式設計方式監視 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="39abe-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="39abe-121">請參閱我們[Microsoft 365 管理 API](/office/office-365-management-api/office-365-management-apis-overview)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="39abe-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="39abe-122">您可以使用下列短連結返回這裡：[https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="39abe-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="39abe-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="39abe-123">Related topics</span></span>

[<span data-ttu-id="39abe-124">設定 Microsoft 365 企業版服務和應用程式</span><span class="sxs-lookup"><span data-stu-id="39abe-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="39abe-125">準備 Microsoft 365 企業版的組織</span><span class="sxs-lookup"><span data-stu-id="39abe-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="39abe-126">Microsoft 365 的網路規劃和效能調整</span><span class="sxs-lookup"><span data-stu-id="39abe-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="39abe-127">與內部部署環境的整合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39abe-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="39abe-128">管理 Microsoft 365 端點</span><span class="sxs-lookup"><span data-stu-id="39abe-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
