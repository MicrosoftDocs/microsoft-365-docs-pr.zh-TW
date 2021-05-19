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
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538804"
---
# <a name="monitor-microsoft-365-connectivity"></a>監視 Microsoft 365 連線能力

在您部署 Microsoft 365 後，您可以使用下列一些工具和技術，維持 Microsoft 365 連線能力。 您需要瞭解官方[服務健康情況和持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)指導方針，以及[在慢速網路上使用 Microsoft 365 的最佳作法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 您也想要抓取 Microsoft 365 的系統[管理應用程式](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)，並[為商務用 Microsoft 365 書簽-系統管理](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)說明。
  
## <a name="monitoring-microsoft-365-connectivity"></a>監控 Microsoft 365 連線能力

|||
|:-----|:-----|
|**取得新 Microsoft 365 端點的通知** <br/> |如果您正在[管理 Microsoft 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)，當我們發佈新的端點時，您將會收到通知，您可以使用您最愛的 rss 讀取器訂閱 rss 摘要。 以下是如何透過[Outlook 訂閱](https://go.microsoft.com/fwlink/p/?LinkId=532416)，也可以[讓 RSS 摘要更新以電子郵件傳送給您](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**使用 System Center 監視 Microsoft 365** <br/> |如果您使用的是 Microsoft System Center，您可以下載[System Center 管理元件，以供 Office 365](https://www.microsoft.com/download/details.aspx?id=43708)開始監視 Microsoft 365 今天。 如需詳細的指導，請參閱管理元件作業指南。 <br/> |
|**監控 Azure ExpressRoute 的健康情況** <br/> |如果您是使用 azure ExpressRoute Microsoft 365 來連線至 Microsoft 365，您會想要確定您同時使用 Microsoft 365 服務健康情況儀表板，以及 azure 使用[azure 資源健康情況來減少疑難排解時間](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**使用 Azure AD Connect Health 搭配 AD FS** <br/> |如果您使用 AD fs 來處理具有 Microsoft 365 的單一 Sign-On，您會想要開始[使用 Azure ad 連線狀況來監視您的 AD FS 基礎結構](/azure/active-directory/hybrid/how-to-connect-health-adfs)。  <br/> |
|**以程式設計方式監視 Microsoft 365** <br/> |請參閱我們[Microsoft 365 管理 API](/office/office-365-management-api/office-365-management-apis-overview)的指導方針。  <br/> |

您可以使用下列短連結返回這裡：[https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft 365 企業版服務和應用程式](configure-services-and-applications.md)
  
[準備 Microsoft 365 企業版的組織](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)
  
[與內部部署環境的整合 Microsoft 365](microsoft-365-integration.md)
  
[管理 Microsoft 365 端點](managing-office-365-endpoints.md)
