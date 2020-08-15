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
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="e46f8-103">使用 PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e46f8-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="e46f8-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="e46f8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e46f8-105">任何一個商務用 Skype Online 系統管理員的主要工作之一就是管理原則。</span><span class="sxs-lookup"><span data-stu-id="e46f8-105">One of the primary tasks of any Skype for Business Online administrator is managing policies.</span></span> <span data-ttu-id="e46f8-106">雖然您可以在 Microsoft 365 系統管理中心中完成其中一些工作，但是使用 PowerShell 可以更快速、更輕鬆地完成其他工作。</span><span class="sxs-lookup"><span data-stu-id="e46f8-106">Although you can accomplish some of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier in PowerShell.</span></span> 

## <a name="before-you-start"></a><span data-ttu-id="e46f8-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="e46f8-107">Before you start</span></span>

<span data-ttu-id="e46f8-108">下載並安裝[商務用 Skype Online 連接器模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="e46f8-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a><span data-ttu-id="e46f8-109">使用商務用 Skype Online 系統管理員帳戶名稱和密碼進行連線</span><span class="sxs-lookup"><span data-stu-id="e46f8-109">Connect using a Skype for Business Online administrator account name and password</span></span>

1. <span data-ttu-id="e46f8-110">開啟 Windows PowerShell 命令提示字元，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e46f8-110">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="e46f8-111">在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入您的商務用 Skype Online 系統管理員帳戶名稱和密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e46f8-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then click **OK**.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a><span data-ttu-id="e46f8-112">使用具有多重要素驗證的商務用 Skype Online 系統管理員帳戶進行連線</span><span class="sxs-lookup"><span data-stu-id="e46f8-112">Connect using a Skype for Business Online administrator account with multi-factor authentication</span></span>

1. <span data-ttu-id="e46f8-113">開啟 Windows PowerShell 命令提示字元，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e46f8-113">Open a Windows PowerShell command prompt and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="e46f8-114">當出現 **New-CsOnlineSession** 命令提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="e46f8-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="e46f8-115">在 **[登入您的帳戶]** 對話方塊中，輸入商務用 Skype Online 系統管理員密碼，然後按一下 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="e46f8-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password, and then click **Sign in**.</span></span>

4. <span data-ttu-id="e46f8-116">請依照 **[登入您的帳戶]** 對話方塊中的指示，提供其他驗證資訊（例如驗證碼），然後按一下 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="e46f8-116">Follow the instructions in the **Sign in to your account** dialog box to provide additional authentication information, such as a verification code, and then click **Verify**.</span></span>

<span data-ttu-id="e46f8-117">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="e46f8-117">For more information, see the following topics:</span></span>
  
- [<span data-ttu-id="e46f8-118">使用 PowerShell 管理商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="e46f8-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="e46f8-119">使用 PowerShell 指派個別使用者商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="e46f8-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="e46f8-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e46f8-120">See also</span></span>

[<span data-ttu-id="e46f8-121">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e46f8-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e46f8-122">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e46f8-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

<span data-ttu-id="e46f8-123">[商務用 Skype PowerShell Cmdlet 參考](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)(英文)</span><span class="sxs-lookup"><span data-stu-id="e46f8-123">[Skype for Business PowerShell cmdlet references](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)</span></span>

