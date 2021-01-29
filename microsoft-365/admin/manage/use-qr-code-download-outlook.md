---
title: 使用 QR 碼登錄 Outlook 行動應用程式
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
description: 瞭解如何使用 QR 碼來驗證和下載 Outlook mobile。
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050769"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 碼登錄 Outlook 行動應用程式

> [!IMPORTANT]
> 此 Microsoft 365 功能位於公開預覽中。 公開預覽可讓您及早存取 Microsoft 365 的功能。

做為 Microsoft 365 系統管理員，您可以讓您的使用者在其行動裝置上登入 Outlook for Android 或 iOS 應用程式，而不必輸入他們的使用者名稱和密碼。 透過掃描 QR 碼，使用者就可以安全地驗證和登入 Outlook mobile。

在 Outlook 網頁版或其他的桌面 Outlook 應用程式中，使用者可能會看到通知，通知他們可以在行動裝置上使用 Outlook。 系統管理員可以使用 Exchange Powershell 來管理這些通知。 如果使用者選擇傳送自己的 SMS 文字訊息，以在其行動裝置上下載應用程式，則其電腦上會出現 QR 碼。 他們將可以掃描 QR 碼，以登入在其電話或平板電腦上的 Outlook。 此 QR 碼是一種簡短的存留期權杖，只能兌換一次。

> [!NOTE]
> 在某些情況下，您的使用者將必須在其電腦上重新驗證，以產生 QR 碼。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

此體驗預設為開啟。 若要停用此功能，請遵循下列步驟。

1. [連接至 Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。
2. 您可以使用 PowerShell 來停用通知，告知使用者 Outlook 行動應用程式的相關資訊。 這也會使 QR 碼無法顯示登入流程。

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

相關主題

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)