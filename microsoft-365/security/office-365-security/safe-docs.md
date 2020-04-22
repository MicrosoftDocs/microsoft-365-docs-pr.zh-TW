---
title: Office 365 ATP 中的安全文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 深入瞭解 Office 365 ATP 中的安全檔。
ms.openlocfilehash: b70c7013ce038a3934b7ea5e62d1d0530f12e4e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634313"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Office 365 中的安全檔高級威脅防護

安全檔是 Office 365 高級威脅防護（ATP）中的一項功能，可使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)來掃描在[受保護的檢視](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 只有使用 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權的使用者才能使用此功能。

- 安全檔目前可用於公開預覽，可供屬於 office 版本為2002（12527.20092）或更高版本的[Office 預覽人員計畫](https://insider.office.com/en-us/join)中的使用者。 此功能預設為關閉，必須由安全性管理員啟用。

- 目前只有美國地區支援相容性檔案處理（所有檔案都會前往 US 地區進行掃描）。 對 UK/歐盟地區的支援計畫于未來的更新中。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派許可權，才能執行本主題中的程式。 若要啟用及設定安全檔，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全性 & 規範中心設定安全檔

1. 開啟安全性 & 規範中心，網址<https://protection.office.com>為。

2. 移至**威脅管理** \> **原則** \> **ATP 安全附件**。

3. 在 [**信任檔案以在 Office 應用程式中開啟受保護的檢視**] 區段中，在 [協助人員保持安全]] 中，設定下列其中一個設定：

   - **開啟 Office 用戶端的安全檔（檔案也會傳送至 Microsoft 雲端進行深入分析）**

   - **即使安全檔將檔案識別為惡意，允許人員按一下受保護的檢視**：我們建議您不要啟用此選項。

4. 完成後，按一下 [儲存]****。

![ATP 安全附件頁面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 設定安全檔

請使用下列語法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- _EnableSafeDocs_參數會啟用或停用整個組織的安全檔。

- _AllowSafeDocsOpen_參數可允許或防止使用者在檔已識別為惡意時，留下受保護的檢視（也就是開啟檔）。

本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

如需詳細的語法及參數資訊，請參閱[Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已啟用並設定安全檔，請執行下列任一步驟：

- 在安全性 & 合規性中心移至**威脅管理** \> **原則** \> **ATP 安全附件**，並確認**當信任檔案以在 Office 應用程式中開啟受保護的檢視時，協助**中的選項將保持安全。

- 在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
