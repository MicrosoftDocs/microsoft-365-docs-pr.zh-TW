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
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920773"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="1b535-103">監視 Microsoft 365 連線能力</span><span class="sxs-lookup"><span data-stu-id="1b535-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="1b535-104">一旦您部署 Microsoft 365，您可以使用下列一些工具和技術來維護 Microsoft 365 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="1b535-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="1b535-105">您將需要瞭解官方 [服務健康情況和持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 指導方針，以及 [在慢速網路上使用 Microsoft 365 的最佳作法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="1b535-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="1b535-106">您也會想要取得 [microsoft 365 管理應用程式](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) ，並為商務用書簽加入 [microsoft 365 for Business-系統管理](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)說明。</span><span class="sxs-lookup"><span data-stu-id="1b535-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="1b535-107">監控 Microsoft 365 連線能力</span><span class="sxs-lookup"><span data-stu-id="1b535-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1b535-108">**取得新 Microsoft 365 端點的通知**</span><span class="sxs-lookup"><span data-stu-id="1b535-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="1b535-109">如果您正在 [管理 Microsoft 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)，當我們發佈新的端點時，您將會收到通知，您可以使用您最愛的 rss 讀取器訂閱 rss 摘要。</span><span class="sxs-lookup"><span data-stu-id="1b535-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="1b535-110">以下說明如何透過 [Outlook 訂閱](https://go.microsoft.com/fwlink/p/?LinkId=532416) ，也可以 [讓 RSS 摘要更新您的電子郵件](https://go.microsoft.com/fwlink/p/?LinkId=532417)。</span><span class="sxs-lookup"><span data-stu-id="1b535-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="1b535-111">**使用 System Center 監視 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="1b535-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="1b535-112">如果您使用 Microsoft System Center，您可以下載適用于 [Office 365 的 System Center Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) ，立即開始監控 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1b535-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="1b535-113">如需詳細的指導，請參閱 management pack operations guide 或此博客文章 [Office365 Monitoring Using System 中心 Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b535-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="1b535-114">**監控 Azure ExpressRoute 的健康情況**</span><span class="sxs-lookup"><span data-stu-id="1b535-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="1b535-115">如果您是使用 Azure ExpressRoute Microsoft 365 來連線至 Microsoft 365，您會想要確定您同時使用的是 Microsoft 365 服務健康情況儀表板，以及 Azure 使用 [Azure 資源健康情況來減少疑難排解時間](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="1b535-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="1b535-116">**使用 Azure AD Connect Health 搭配 AD FS**</span><span class="sxs-lookup"><span data-stu-id="1b535-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="1b535-117">如果您使用 AD FS 進行單一 Sign-On 搭配 Microsoft 365，您將會想要開始 [使用 AZURE Ad Connect Health 來監視您的 AD FS 基礎結構](/azure/active-directory/hybrid/how-to-connect-health-adfs)。</span><span class="sxs-lookup"><span data-stu-id="1b535-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="1b535-118">**以程式設計方式監視 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="1b535-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="1b535-119">請參閱 [Microsoft 365 管理 API](/office/office-365-management-api/office-365-management-apis-overview)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="1b535-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="1b535-120">您可以使用下列短連結返回這裡：[https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="1b535-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b535-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b535-121">Related topics</span></span>

[<span data-ttu-id="1b535-122">設定 Microsoft 365 企業版服務和應用程式</span><span class="sxs-lookup"><span data-stu-id="1b535-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="1b535-123">讓您的組織準備好進行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1b535-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="1b535-124">Microsoft 365 的網路規劃和效能調整</span><span class="sxs-lookup"><span data-stu-id="1b535-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="1b535-125">Microsoft 365 與內部部署環境的整合</span><span class="sxs-lookup"><span data-stu-id="1b535-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="1b535-126">管理 Microsoft 365 端點</span><span class="sxs-lookup"><span data-stu-id="1b535-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)