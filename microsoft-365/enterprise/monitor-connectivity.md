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
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688272"
---
# <a name="monitor-microsoft-365-connectivity"></a>監視 Microsoft 365 連線能力

一旦您部署 Microsoft 365，您可以使用下列一些工具和技術來維護 Microsoft 365 的連線能力。 您將需要瞭解官方 [服務健康情況和持續性](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 指導方針，以及 [在慢速網路上使用 Microsoft 365 的最佳作法](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 您也會想要取得 [microsoft 365 管理應用程式](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) ，並為商務用書簽加入 [microsoft 365 for Business-系統管理](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)說明。
  
## <a name="monitoring-microsoft-365-connectivity"></a>監控 Microsoft 365 連線能力

|||
|:-----|:-----|
|**取得新 Microsoft 365 端點的通知** <br/> |如果您正在 [管理 Microsoft 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)，當我們發佈新的端點時，您將會收到通知，您可以使用您最愛的 rss 讀取器訂閱 rss 摘要。 以下說明如何透過 [Outlook 訂閱](https://go.microsoft.com/fwlink/p/?LinkId=532416) ，也可以 [讓 RSS 摘要更新您的電子郵件](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**使用 System Center 監視 Microsoft 365** <br/> |如果您使用 Microsoft System Center，您可以下載適用于 [Office 365 的 System Center Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) ，立即開始監控 Microsoft 365。 如需詳細的指導，請參閱 management pack operations guide 或此博客文章 [Office365 Monitoring Using System 中心 Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**監控 Azure ExpressRoute 的健康情況** <br/> |如果您是使用 Azure ExpressRoute Microsoft 365 來連線至 Microsoft 365，您會想要確定您同時使用的是 Microsoft 365 服務健康情況儀表板，以及 Azure 使用 [Azure 資源健康情況來減少疑難排解時間](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**使用 Azure AD Connect Health 搭配 AD FS** <br/> |如果您使用 AD FS 進行單一 Sign-On 搭配 Microsoft 365，您將會想要開始 [使用 AZURE Ad Connect Health 來監視您的 AD FS 基礎結構](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)。  <br/> |
|**以程式設計方式監視 Microsoft 365** <br/> |請參閱 [Microsoft 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)的指導方針。  <br/> |

您可以使用下列短連結返回這裡：[https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft 365 企業版服務和應用程式](configure-services-and-applications.md)
  
[讓您的組織準備好進行 Microsoft 365 企業版](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)
  
[Microsoft 365 與內部部署環境的整合](microsoft-365-integration.md)
  
[管理 Microsoft 365 端點](managing-office-365-endpoints.md)
