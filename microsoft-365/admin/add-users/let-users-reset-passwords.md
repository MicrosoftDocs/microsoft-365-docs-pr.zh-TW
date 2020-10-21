---
title: 讓使用者重設自己的密碼
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 瞭解如何使用自助密碼重設工具來重設密碼。
ms.openlocfilehash: 7ecadaa42610e0b77dc1727c11140080bd7b1779
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646676"
---
# <a name="let-users-reset-their-own-passwords"></a>讓使用者重設自己的密碼

做為 Microsoft 365 系統管理員，您可以讓使用者使用 [自助密碼重設工具](https://go.microsoft.com/fwlink/p/?LinkId=522677) ，這樣您就不需要重設密碼。 這可為您分擔一些工作！
  
## <a name="before-you-begin"></a>開始之前
  
- 您可以使用任何 Microsoft 365 商務版、教育版或非 **盈利性的收費** 方案，為雲端使用者取得自助密碼重設。 它不會與 Microsoft 365 試用版搭配使用。

- 該工具會使用 Azure。 當您執行這些步驟時，您將會在 Azure 中自動 **免費** 取得此項功能。 如果您不使用其他的 Azure 功能，開啟自助密碼重設不會花費您任何費用。

- **如果您使用的是內部部署 Active Directory**，則不會套用上述兩個點。 相反地，您可以設定此設定，但 **需要使用 AZURE AD Premium 付費訂閱**。

本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。 若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。 [什麼是系統管理員帳戶？](../admin-overview/admin-overview.md)

您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。

## <a name="watch-let-users-reset-their-own-passwords"></a>觀賞：讓使用者重設自己的密碼

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="steps-let-people-reset-their-own-passwords"></a>步驟：讓使用者重設自己的密碼

下列步驟會針對公司中的所有人員開啟自助密碼重設。
  
::: moniker range="o365-worldwide"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>中，移至 [ **設定** > **組織設定** ] 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **設定** \> **安全性 &amp; 隱私權** ] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [**設定** \> **設定** \> **安全性 &amp; 隱私權**] 頁面。

::: moniker-end

2. 在 [ **組織設定** ] 頁面的頂端，選取 [ **安全性 & 隱私權** ] 索引標籤。
  
3. 選取 [ **自助密碼重設**]。

4. 在 [ **自助密碼重設**] 下，選取 **[移至 Azure 入口網站] 以開啟自助密碼重設**。

5. 在左功能窗格中，選取 [ **使用者**]，然後在 [ **使用者] | [所有使用者** ] 頁面上，選取 [ **密碼重設**]。
  
6. 在 [ **屬性** ] 頁面上，選取 [ **全部** ] 以針對您公司內的每個人啟用它，然後選取 [ **儲存**]。
  
7. 當您的使用者登入時，系統會提示他們輸入其他連絡人資訊，以協助他們日後重設其密碼。

## <a name="related-content"></a>相關內容

[設定組織的密碼到期原則](../manage/set-password-expiration-policy.md)

[設定個別使用者的密碼永不過期](set-password-to-never-expire.md)

[Microsoft 365 商務版訓練影片](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
