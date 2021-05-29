---
title: 停止自動轉寄電子郵件
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何建立郵件流程規則以避免盜竊專有資訊，以停止自動轉寄電子郵件。
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706471"
---
# <a name="stop-email-auto-forward"></a>停止電子郵件自動轉寄

## <a name="watch-stop-auto-forwarding-emails"></a>觀賞：停止自動轉送電子郵件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

如果駭客取得使用者信箱的存取權，他們就可以將使用者的電子郵件自動轉寄到外部地址，並竊取專有資訊。 您可以建立郵件流程規則來停止這種情況。

## <a name="try-it"></a>試試看吧！

1. 從 Microsoft 365 系統管理中心，選取 [ **Exchange**，**郵件流程**]，然後在 [**規則**] 索引標籤上，選取加號，然後選擇 [**建立新規則**]。
1. 選取 [ **更多選項**]。 為您的新規則命名。
1. 然後開啟下拉清單以套用 **此規則如果** 是，請選取 **寄件者**，然後 **是外部內部**。
1. 選取 **組織內**，然後按一下 **[確定]**。
1. 選擇 [ **新增條件**]，開啟下拉式清單，選取 **郵件** 內容，然後 **加入郵件類型**。
1. 開啟 [ **選取郵件類型** ] 下拉式清單，選擇 [ **自動轉寄**]，然後選擇 **[確定]**。
1. 開啟 [ **執行下列** 下拉式清單]，選取 [ **封鎖郵件**]，然後 **拒絕郵件，並包含說明**。
1. 輸入您的說明的訊息文字，然後選取 **[確定]**。
1. 向下並選取 [ **儲存**]。

    您的規則已經建立，駭客也無法再自動轉寄郵件。

## <a name="related-content"></a>相關內容

[為使用者新增其他電子郵件別名](../admin/email/add-another-email-alias-for-a-user.md) (文章)
[在 Microsoft 365 中設定電子郵件轉寄](../admin/email/configure-email-forwarding.md) (文章)
[尋找並修正電子郵件傳遞問題，以 Office 365 商務系統管理員](/exchange/troubleshoot/email-delivery/email-delivery-issues) (文章) 