---
title: 使用 PowerShell 管理商務用 Skype Online
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: 使用適用於 Microsoft 365 的 PowerShell 來管理商務用 Skype Online 原則、每一個使用者原則和會議的設定。
ms.openlocfilehash: 4ea4858e4ca334cdb0268312e69bef77bc9bbd86
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288980"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>使用 PowerShell 管理商務用 Skype Online

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

商務用 Skype Online 系統管理員負責管理原則。 雖然您可以在 Microsoft 365 系統管理中心中執行其中一些工作，但是使用 PowerShell 可以更輕鬆地完成其他工作。

## <a name="before-you-start"></a>開始之前

> [!NOTE]
> 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。

安裝[Teams PowerShell 模組安裝](/microsoftteams/teams-powershell-install)。

## <a name="connect-using-admin-credentials"></a>使用系統管理員認證連線

1. 開啟 Windows PowerShell 命令提示視窗，然後執行下列命令：

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. 在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入您的系統管理員帳戶名稱和密碼，然後選取 **[確定]**。

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>使用具有多重要素驗證的系統管理員帳戶進行連線

1. 開啟 Windows PowerShell 命令提示視頻，然後執行下列命令：

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. 出現提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱。

3. 在 **[登入您的帳戶]** 對話方塊中，輸入商務用 Skype Online 系統管理員密碼，然後選取 **[登入]**。

4. 在 **[登入您的帳戶]** 對話方塊中依照指示，提供驗證資訊（例如驗證碼），然後選取 **[驗證]**。

如需詳細資訊，請參閱：

- [使用 PowerShell 管理商務用 Skype Online 原則](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [使用 PowerShell 指派個別使用者商務用 Skype Online 原則](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a>另請參閱

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)

[商務用 Skype PowerShell Cmdlet 參考](/powershell/module/skype/)(英文)
