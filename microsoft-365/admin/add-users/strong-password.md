---
title: 關閉使用者的強式密碼需求
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
ms.openlocfilehash: e2300e3c94de53cd04d0c1726538fdb8a86a1ccf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903533"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="82b3e-103">關閉使用者的強式密碼需求</span><span class="sxs-lookup"><span data-stu-id="82b3e-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="82b3e-104">本文說明如何為您的使用者關閉強式密碼需求。</span><span class="sxs-lookup"><span data-stu-id="82b3e-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="82b3e-105">在您的 Microsoft 365 for business 組織中，預設會開啟強式密碼需求。</span><span class="sxs-lookup"><span data-stu-id="82b3e-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="82b3e-106">您的組織可能會有停用強式密碼的需求。</span><span class="sxs-lookup"><span data-stu-id="82b3e-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="82b3e-107">請遵循下列步驟關閉強式密碼需求。</span><span class="sxs-lookup"><span data-stu-id="82b3e-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="82b3e-108">您必須使用 PowerShell 來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="82b3e-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82b3e-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="82b3e-109">Before you begin</span></span>

<span data-ttu-id="82b3e-110">本文適用于管理企業、學校或非盈利性密碼原則的人員。</span><span class="sxs-lookup"><span data-stu-id="82b3e-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="82b3e-111">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="82b3e-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="82b3e-112">什麼是系統管理員帳戶？</span><span class="sxs-lookup"><span data-stu-id="82b3e-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="82b3e-113">您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="82b3e-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="82b3e-114">您也必須使用 PowerShell 連接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="82b3e-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="82b3e-115">設定強式密碼</span><span class="sxs-lookup"><span data-stu-id="82b3e-115">Set strong passwords</span></span>

1. <span data-ttu-id="82b3e-116">[使用 PowerShell 連接至 Microsoft 365](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="82b3e-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="82b3e-117">使用 PowerShell，您可以使用下列命令，為所有使用者關閉強式密碼需求：</span><span class="sxs-lookup"><span data-stu-id="82b3e-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="82b3e-118">UserPrincipalName 必須是網際網路樣式的登入格式，其中使用者名稱後面接 @ 符號 ( @ ) 和功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="82b3e-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="82b3e-119">例如： user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="82b3e-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="82b3e-120">相關內容</span><span class="sxs-lookup"><span data-stu-id="82b3e-120">Related content</span></span>

[<span data-ttu-id="82b3e-121">如何使用 PowerShell 連接至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82b3e-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="82b3e-122">PowerShell Get-msoluser 命令的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="82b3e-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="82b3e-123">密碼原則的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="82b3e-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)