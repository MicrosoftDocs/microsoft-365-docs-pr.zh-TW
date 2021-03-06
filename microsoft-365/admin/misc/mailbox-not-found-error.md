---
title: 收到在 Outlook 網頁版中找不到信箱的錯誤
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ms.custom: AdminTemplateSet
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: '**找不到信箱** 錯誤表示您用於連結至 Outlook 網頁版的帳戶沒有 Exchange Online 授權。'
ms.openlocfilehash: 48e47d279f540693a874c4de2ced535cfbbd753d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391276"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>是否收到在 Outlook 網頁版中找不到信箱的錯誤？

如果您正在使用網頁版 Outlook 並收到 **找不到信箱** 錯誤，表示您用於連結至網頁版 Outlook 的帳戶沒有 Exchange Online 的授權，因此，沒有與此帳戶相關聯的信箱。 

## <a name="assign-a-license-to-your-account"></a>指派授權至您的帳戶

您的系統管理員可以指派授權至您的帳戶，依照下列步驟進行：

1. 開啟 [Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home#/homepage) 並移至 **使用者** 章節底下的 **作用中的使用者**，選取看到此錯誤的使用者。
1. 在開啟的使用者頁面中，移至 **授權與應用程式** 章節，選取正確的 **位置** 值，並指派包含 Exchange Online 的授權 (展開授權以查看詳細資料)。 
1. 完成後，按一下 [儲存變更 **]**。

## <a name="related-content"></a>相關內容

[為使用者新增其他電子郵件別名](../email/add-another-email-alias-for-a-user.md) (文章)
[在 Microsoft 365 中設定電子郵件轉寄](../email/configure-email-forwarding.md) (文章)
[建立共用信箱](../email/create-a-shared-mailbox.md) (文章)