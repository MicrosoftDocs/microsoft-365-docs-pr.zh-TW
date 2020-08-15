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
description: 摘要︰使用適用於 Microsoft 365 的 PowerShell 來管理商務用 Skype Online 原則、每一個使用者原則和會議的設定。
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688709"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>使用 PowerShell 管理商務用 Skype Online

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

任何一個商務用 Skype Online 系統管理員的主要工作之一就是管理原則。 雖然您可以在 Microsoft 365 系統管理中心中完成其中一些工作，但是使用 PowerShell 可以更快速、更輕鬆地完成其他工作。 

## <a name="before-you-start"></a>開始之前

下載並安裝[商務用 Skype Online 連接器模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後重新啟動電腦。


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a>使用商務用 Skype Online 系統管理員帳戶名稱和密碼進行連線

1. 開啟 Windows PowerShell 命令提示字元，然後執行下列命令： 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. 在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼，然後按一下 **[確定]**。


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a>使用具有多重要素驗證的商務用 Skype Online 系統管理員帳戶進行連線

1. 開啟 Windows PowerShell 命令提示字元，然後執行下列命令：

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. 當出現 **New-CsOnlineSession** 命令提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱。

3. 在 **[登入您的帳戶]** 對話方塊中，輸入商務用 Skype Online 系統管理員密碼，然後按一下 **[登入]**。

4. 請依照 **[登入您的帳戶]** 對話方塊中的指示，提供其他驗證資訊（例如驗證碼），然後按一下 **[驗證]**。

如需詳細資訊，請參閱下列主題：
  
- [使用 PowerShell 管理商務用 Skype Online 原則](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [使用 PowerShell 指派個別使用者商務用 Skype Online 原則](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>另請參閱

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)

[商務用 Skype PowerShell Cmdlet 參考](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)(英文)

