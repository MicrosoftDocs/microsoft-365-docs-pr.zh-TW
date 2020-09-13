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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430031"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="f6b3a-103">使用 PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="f6b3a-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="f6b3a-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="f6b3a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f6b3a-105">商務用 Skype Online 系統管理員負責管理原則。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="f6b3a-106">雖然您可以在 Microsoft 365 系統管理中心中執行其中一些工作，但是使用 PowerShell 可以更輕鬆地完成其他工作。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f6b3a-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="f6b3a-107">Before you start</span></span>

<span data-ttu-id="f6b3a-108">下載並安裝[商務用 Skype Online Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="f6b3a-109">使用商務用 Skype Online 的系統管理員認證連線</span><span class="sxs-lookup"><span data-stu-id="f6b3a-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="f6b3a-110">開啟 Windows PowerShell 命令提示視窗，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f6b3a-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="f6b3a-111">在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="f6b3a-112">使用具有多重要素驗證的系統管理員帳戶進行連線</span><span class="sxs-lookup"><span data-stu-id="f6b3a-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="f6b3a-113">開啟 Windows PowerShell 命令提示視頻，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f6b3a-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="f6b3a-114">當出現 **New-CsOnlineSession** 命令提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="f6b3a-115">在 **[登入您的帳戶]** 對話方塊中，輸入商務用 Skype Online 系統管理員密碼，然後選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="f6b3a-116">在 **[登入您的帳戶]** 對話方塊中依照指示，提供驗證資訊（例如驗證碼），然後選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="f6b3a-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="f6b3a-117">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="f6b3a-117">For more information, see:</span></span>
  
- [<span data-ttu-id="f6b3a-118">使用 PowerShell 管理商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="f6b3a-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="f6b3a-119">使用 PowerShell 指派個別使用者商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="f6b3a-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="f6b3a-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f6b3a-120">See also</span></span>

[<span data-ttu-id="f6b3a-121">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6b3a-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f6b3a-122">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6b3a-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

<span data-ttu-id="f6b3a-123">[商務用 Skype PowerShell Cmdlet 參考](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)(英文)</span><span class="sxs-lookup"><span data-stu-id="f6b3a-123">[Skype for Business PowerShell cmdlet references](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)</span></span>
