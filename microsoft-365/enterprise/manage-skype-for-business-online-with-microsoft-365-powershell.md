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
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="1337b-103">使用 PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1337b-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="1337b-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="1337b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1337b-105">商務用 Skype Online 系統管理員負責管理原則。</span><span class="sxs-lookup"><span data-stu-id="1337b-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="1337b-106">雖然您可以在 Microsoft 365 系統管理中心中執行其中一些工作，但是使用 PowerShell 可以更輕鬆地完成其他工作。</span><span class="sxs-lookup"><span data-stu-id="1337b-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="1337b-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="1337b-107">Before you start</span></span>

> [!NOTE]
> <span data-ttu-id="1337b-108">商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="1337b-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1337b-109">如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="1337b-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

<span data-ttu-id="1337b-110">安裝[Teams PowerShell 模組安裝](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="1337b-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>

## <a name="connect-using-admin-credentials"></a><span data-ttu-id="1337b-111">使用系統管理員認證連線</span><span class="sxs-lookup"><span data-stu-id="1337b-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="1337b-112">開啟 Windows PowerShell 命令提示視窗，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1337b-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="1337b-113">在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入您的系統管理員帳戶名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1337b-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="1337b-114">使用具有多重要素驗證的系統管理員帳戶進行連線</span><span class="sxs-lookup"><span data-stu-id="1337b-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="1337b-115">開啟 Windows PowerShell 命令提示視頻，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1337b-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="1337b-116">出現提示時，請輸入您的商務用 Skype Online 系統管理員帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="1337b-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="1337b-117">在 **[登入您的帳戶]** 對話方塊中，輸入商務用 Skype Online 系統管理員密碼，然後選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="1337b-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="1337b-118">在 **[登入您的帳戶]** 對話方塊中依照指示，提供驗證資訊（例如驗證碼），然後選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1337b-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="1337b-119">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1337b-119">For more information, see:</span></span>

- [<span data-ttu-id="1337b-120">使用 PowerShell 管理商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="1337b-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [<span data-ttu-id="1337b-121">使用 PowerShell 指派個別使用者商務用 Skype Online 原則</span><span class="sxs-lookup"><span data-stu-id="1337b-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a><span data-ttu-id="1337b-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1337b-122">See also</span></span>

[<span data-ttu-id="1337b-123">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1337b-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="1337b-124">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1337b-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

<span data-ttu-id="1337b-125">[商務用 Skype PowerShell Cmdlet 參考](/powershell/module/skype/)(英文)</span><span class="sxs-lookup"><span data-stu-id="1337b-125">[Skype for Business PowerShell cmdlet references](/powershell/module/skype/)</span></span>
