---
title: Office 365 ATP 中的安全文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 深入瞭解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全檔。
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949451"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全檔

安全檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的一項功能，可使用 [Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 來掃描在 [受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 12730 Office 版本2004的使用者通常可使用安全檔， () 或更高！ 此功能預設為關閉，必須由安全性管理員啟用。

- 此功能僅適用于使用 *Microsoft 365 e5* 或 *Microsoft 365 e5 安全性* 授權 (未包含在 Office 365 ATP 計畫) 中的使用者。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 如需詳細資訊，請 

- 您必須已獲指派許可權，才能執行本主題中的程式。 若要啟用及設定安全檔，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何處理您的資料？

為了讓您受到保護，安全檔會將檔案傳送至 [Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 雲端，以進行分析。

- 您可以在 [這裡](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)找到 Microsoft Defender 高級威脅防護如何處理資料的詳細資訊。
- 除了上述指導方針之外，安全檔所傳送的檔案不會保留在進行分析所需的時間（通常是小於24小時）。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全性 & 規範中心設定安全檔

1. 開啟安全性 & 規範中心，網址為 <https://protection.office.com> 。

2. 移至 **威脅管理** \> **原則** \> **ATP 安全附件**。

3. 在 [ **信任檔案以在 Office 應用程式中開啟受保護的檢視** ] 區段中，在 [協助人員保持安全]] 中，設定下列其中一個設定：

   - **開啟 Office 用戶端的安全檔**

   - **即使安全檔將檔案識別為惡意，允許人員按一下受保護的檢視**：我們建議您不要啟用此選項。

4. 完成後，按一下 [儲存]****。

![ATP 安全附件頁面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全檔

使用下列語法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_參數會啟用或停用整個組織的安全檔。

- _AllowSafeDocsOpen_參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。

本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已啟用並設定安全檔，請執行下列任一步驟：

- 在安全性 & 合規性中心移至 **威脅管理** \> **原則** \> **ATP 安全附件**，並確認 **當信任檔案以在 Office 應用程式中開啟受保護的檢視時，協助** 中的選項將保持安全。

- 在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
