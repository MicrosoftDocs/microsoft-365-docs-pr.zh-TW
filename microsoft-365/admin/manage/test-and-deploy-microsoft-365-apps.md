---
title: 測試及部署 Microsoft 365 應用程式
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 針對組織中的使用者和群組，從 Microsoft 365 系統管理中心的整合式應用程式入口網站，尋找、測試及部署 Microsoft 和 Microsoft 合作夥伴應用程式。
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790187"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 admin center 中測試及部署 Microsoft 365 應用程式

Microsoft 365 系統管理中心可讓您靈活地從單一位置部署 Microsoft 和 Microsoft 合作夥伴應用程式。 由 Microsoft 和 Microsoft 合作夥伴從整合的應用程式入口網站進行購買及授權的應用程式，可提供您組織所需的便利性和優點，以保持業務服務定期更新並有效地運作。  

如需購買及授權組織的 Microsoft 365 應用程式的詳細資訊，請參閱博客文章，該文章稱為「管理」， [並從 microsoft 365 系統管理中心部署 microsoft 365 應用程式](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>在整合式應用程式入口網站中管理應用程式

透過選擇 Microsoft 365 系統管理中心的整合式應用程式，您可以管理已購買及已授權的 Microsoft 和 Microsoft 合作夥伴應用程式的測試和部署。 

1. 在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。 

2. 選擇 [**可供** 使用的應用程式]**狀態** 的應用程式。

3. 在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。

    某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。

    a. 選取 [ **新增使用者**]，選擇 [ **完整部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組**]。

    特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。

    如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。

    b. 選取 [**更新**，**完成**]，現在您可以在 [**一覽表**] 索引標籤上選取 [**部署**]。  

4. 查看應用程式資訊，然後選取 [ **部署**]。 

5. 在 [**部署完成**] 頁面上選取 [**完成**]。 

    在 [ **概覽** ] 索引標籤上，查看測試或完整部署的詳細資料。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>尋找已發佈的應用程式進行測試和完整部署 

您可以在 [整合式應用程式] 頁面上，找出未出現在清單中的已發佈應用程式，並加以測試及完全部署。 透過從系統管理中心購買及授權應用程式，您可以從單一位置將 Microsoft 和 Microsoft 合作夥伴應用程式新增至您的清單。

1. 在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。 

2. 選取 [在應用程式清單上方 **取得應用程式** ]。

3. 在 [ **Microsoft 365 應用程式** 發佈的應用程式] 頁面上，選擇您想要部署的應用程式，請選擇 [ **立即取得**]。

4. 接受許可權，然後選取 [ **繼續**]。

5. 在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。

    某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。

    a. 選取 [ **新增使用者**]，選擇 [ **完整部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組**]。

    特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。

    如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。

    b. 選取 [**更新**，**完成**]，現在您可以選取 [**簡介**] 索引標籤上的 [**部署**]。  

6. 查看應用程式資訊，然後選取 [ **部署**]。 

7. 在 [**部署完成**] 頁面上選取 [**完成**]。 

    在 [ **概覽** ] 索引標籤上，查看測試或完整部署的詳細資料。

在 Microsoft 365 系統管理中心中，每個部署的應用程式 **狀態****都是「** **測試部署**」、「**完全部署**」或「**自訂**」**部署類型**，以及您部署應用程式的日期。

> [!NOTE]
> 若應用程式先前部署自整合的應用程式入口網站，則 **部署類型** 是 **自訂的。**

## <a name="unsupported-scenarios"></a>不支援的案例

下列案例目前不支援從整合應用入口網站進行部署：

- 應用程式或增益集連結到一個以上的軟體作為服務 (SaaS) 提供。
- SaaS 應用程式連結到應用程式和增益集，但沒有相關聯的 AADid。
- 兩個 SaaS 的應用程式共用相同的 AADid，且兩者都連結到應用程式或增益集。
  