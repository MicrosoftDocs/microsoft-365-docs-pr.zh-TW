---
title: 使用 PowerShell 管理密碼
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: 瞭解如何使用 PowerShell 來管理密碼。
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073189"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="b92a8-103">使用 PowerShell 管理密碼</span><span class="sxs-lookup"><span data-stu-id="b92a8-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="b92a8-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="b92a8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b92a8-105">您可以使用 Microsoft 365 的 PowerShell 作為 Microsoft 365 系統管理中心的替代方法，以在 Microsoft 365 中管理密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="b92a8-106">當本文中的命令區塊要求您指定變數值時，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="b92a8-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="b92a8-107">將命令區塊複製到 [剪貼簿]，然後將它貼到 [記事本] 或 PowerShell 整合型腳本環境 (ISE) 。</span><span class="sxs-lookup"><span data-stu-id="b92a8-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="b92a8-108">填入變數值，並移除 "<" 和 ">" 字元。</span><span class="sxs-lookup"><span data-stu-id="b92a8-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="b92a8-109">在 PowerShell] 視窗或 PowerShell ISE 中執行命令。</span><span class="sxs-lookup"><span data-stu-id="b92a8-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b92a8-110">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="b92a8-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b92a8-111">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="b92a8-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="b92a8-112">設定密碼</span><span class="sxs-lookup"><span data-stu-id="b92a8-112">Set a password</span></span>

<span data-ttu-id="b92a8-113">使用下列命令指定使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="b92a8-114">強制使用者變更其密碼</span><span class="sxs-lookup"><span data-stu-id="b92a8-114">Force a user to change their password</span></span>

<span data-ttu-id="b92a8-115">使用這些命令來設定密碼，並強制使用者變更其新密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="b92a8-116">使用這些命令設定密碼，並強制使用者在下次登入時變更其新密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b92a8-117">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="b92a8-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b92a8-118">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b92a8-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="b92a8-119">設定密碼</span><span class="sxs-lookup"><span data-stu-id="b92a8-119">Set a password</span></span>

<span data-ttu-id="b92a8-120">使用下列命令指定使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="b92a8-121">強制使用者變更其密碼</span><span class="sxs-lookup"><span data-stu-id="b92a8-121">Force a user to change their password</span></span>

<span data-ttu-id="b92a8-122">使用這些命令可強制使用者變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="b92a8-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="b92a8-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="b92a8-123">See also</span></span>

[<span data-ttu-id="b92a8-124">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="b92a8-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b92a8-125">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b92a8-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b92a8-126">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b92a8-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

