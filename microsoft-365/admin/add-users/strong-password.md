---
title: 為使用者設定強式密碼需求
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用 Windows PowerShell 為使用者設定強式密碼需求。
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626140"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="c1c56-103">為使用者設定強式密碼需求</span><span class="sxs-lookup"><span data-stu-id="c1c56-103">Set strong password requirement for users</span></span>

<span data-ttu-id="c1c56-104">本文說明如何為使用者設定強式密碼需求。</span><span class="sxs-lookup"><span data-stu-id="c1c56-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="c1c56-105">您必須使用 PowerShell 來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="c1c56-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c1c56-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="c1c56-106">Before you begin</span></span>

<span data-ttu-id="c1c56-107">本文適用于管理企業、學校或非盈利性密碼原則的人員。</span><span class="sxs-lookup"><span data-stu-id="c1c56-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="c1c56-108">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c1c56-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="c1c56-109">[何謂系統管理員帳戶?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1c56-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="c1c56-110">您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="c1c56-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="c1c56-111">您也必須使用 PowerShell 連接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c1c56-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="c1c56-112">設定強式密碼</span><span class="sxs-lookup"><span data-stu-id="c1c56-112">Set strong passwords</span></span>

1. <span data-ttu-id="c1c56-113">[使用 PowerShell 連接至 Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c1c56-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="c1c56-114">使用 PowerShell，您可以使用下列命令為所有使用者開啟強式密碼需求：</span><span class="sxs-lookup"><span data-stu-id="c1c56-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="c1c56-115">UserPrincipalName 必須是網際網路樣式的登入格式，其中使用者名稱後面接 @ 符號 ( @ ) 和功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c1c56-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="c1c56-116">例如： user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c1c56-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="c1c56-117">相關內容</span><span class="sxs-lookup"><span data-stu-id="c1c56-117">Related content</span></span>

[<span data-ttu-id="c1c56-118">如何使用 PowerShell 連接至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1c56-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="c1c56-119">PowerShell Get-msoluser 命令的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c1c56-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="c1c56-120">密碼原則的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c1c56-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)