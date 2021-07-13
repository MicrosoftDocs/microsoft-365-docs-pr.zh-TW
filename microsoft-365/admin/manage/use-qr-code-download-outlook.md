---
title: 使用 QR 碼來登入 Outlook 行動應用程式
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: 瞭解如何使用 QR 碼來驗證和下載 Outlook 行動裝置。
ms.openlocfilehash: c13fbeabd320c64925165ba16797d5a3471961ad
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391336"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 碼來登入 Outlook 行動應用程式

> [!IMPORTANT]
> 此功能僅適用于已在 Microsoft 365 系統管理中心中開啟目標版本的組織。 若要開啟目標版本並深入瞭解其運作方式，請參閱 [設定標準或目標發行選項](release-options-in-office-365.md)。 我們將透過公開預覽，將更多組織擴充至未來的幾周。 公開預覽提供了 Microsoft 365 功能的早期存取權。

Microsoft 365 系統管理員可以讓您的使用者在其行動裝置上登入 Outlook for Android 或 iOS 應用程式，而不必輸入其使用者名稱和密碼。 透過掃描 QR 碼，使用者可以安全地驗證和登入 Outlook 行動。

在 Outlook 網頁版或其他桌面 Outlook 應用程式中，使用者可能會看到通知，告知他們可以在行動裝置上使用 Outlook。 系統管理員可以使用 Exchange Powershell 來管理這些通知。 如果使用者選擇傳送自己的 SMS 文字訊息，以在其行動裝置上下載應用程式，則其電腦上會出現 QR 碼。 他們將可以掃描 QR 碼，以登入至其電話或平板電腦上的 Outlook。 此 QR 碼是一種簡短的存留期權杖，只能兌換一次。

> [!NOTE]
> 在某些情況下，您的使用者必須在其電腦上重新驗證，以產生 QR 碼。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

這項功能預設為啟用。 若要停用此功能，請遵循下列步驟。

1. [連線 Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
2. 您可以使用 PowerShell 停用通知，通知使用者有關 Outlook 行動應用程式的通知。 這也會防止 QR 程式碼登入流向顯示。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>相關內容

[設定標準或目標版本選項](release-options-in-office-365.md) (文章) \
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (文章) 