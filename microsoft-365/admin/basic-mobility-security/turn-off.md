---
title: 關閉基本行動性和安全性
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 移除群組或原則，以關閉基本行動性和安全性。
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876837"
---
# <a name="turn-off-basic-mobility-and-security"></a>關閉基本行動性和安全性

若要有效關閉基本行動性和安全性，請從裝置管理原則移除安全性群組定義的人員群組，或自行移除原則。

- 從您已建立的裝置原則中移除使用者安全性群組，以移除使用者群組。

- 移除所有基本行動及安全性裝置原則，以停用所有使用者的基本行動性和安全性。

這些選項會移除組織中裝置的基本行動性和安全性強制執行。 不幸的是，在您設定後，您無法直接 "取消「取消」「基本行動性」和「安全性」。 

>[!IMPORTANT]
>當您移除原則中的使用者安全性群組或自行移除原則時，請注意使用者裝置的影響。 例如，電子郵件設定檔及快取的電子郵件可能會被移除，視裝置而定。 如需詳細資訊，請參閱  [當您刪除原則或移除原則中的使用者時，會發生什麼事？](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>從基本行動及安全性裝置原則中移除使用者安全性群組

1. 在您的瀏覽器類型：中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 選取裝置原則，然後選取 [ **編輯原則**]。 

3. 在 [  **部署**]   頁面上，選取 [ **移除**]。

4. 在 [  **群組**] 下，選取安全性群組。

5. 選取 [  **移除**]，然後選取 [ **儲存**]。

## <a name="remove-basic-mobility-and-security-device-policies"></a>移除基本行動及安全性裝置原則

1.  在您的瀏覽器類型：中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。 

2.  選取裝置原則，然後選取 [  **刪除原則**]。
    
3.  在警告對話方塊中，選取 **[是]**。

>[!NOTE]
>如需在組織裝置仍處於封鎖狀態時解除封鎖裝置的更多步驟，請參閱博客文章 [從 Office 365 移除行動裝置管理的存取控制](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)。
