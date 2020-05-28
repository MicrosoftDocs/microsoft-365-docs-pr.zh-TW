---
title: 比較封鎖存取的方式
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 瞭解如何在員工離開組織時，封鎖 Microsoft 365 的存取權。
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399431"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="e38c7-103">比較封鎖存取的方式</span><span class="sxs-lookup"><span data-stu-id="e38c7-103">Compare ways to block access</span></span>

<span data-ttu-id="e38c7-104">當員工休假或損毀時，您必須封鎖他們對 Microsoft 365 的存取。</span><span class="sxs-lookup"><span data-stu-id="e38c7-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="e38c7-105">以下是一些您可以執行這項作業的方法。</span><span class="sxs-lookup"><span data-stu-id="e38c7-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="e38c7-106">**封鎖存取的方式**</span><span class="sxs-lookup"><span data-stu-id="e38c7-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="e38c7-107">**定義**</span><span class="sxs-lookup"><span data-stu-id="e38c7-107">**Definition**</span></span> <br/> |<span data-ttu-id="e38c7-108">**最佳做法**</span><span class="sxs-lookup"><span data-stu-id="e38c7-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="e38c7-109">封鎖登入</span><span class="sxs-lookup"><span data-stu-id="e38c7-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="e38c7-110">封鎖使用者存取 Microsoft 365 的一種方式，就是將其登入狀態變更為 [已**封鎖登入**]。</span><span class="sxs-lookup"><span data-stu-id="e38c7-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="e38c7-111">這可防止使用者從其電腦和行動裝置登入 Microsoft 365，但他們仍可查看先前下載或同步處理的電子郵件和檔。</span><span class="sxs-lookup"><span data-stu-id="e38c7-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="e38c7-112">如果您使用 Blackberry Enterprise 服務，您也可以停用其存取權。</span><span class="sxs-lookup"><span data-stu-id="e38c7-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="e38c7-113">當員工計畫離開組織或打算進行長期請假時使用。</span><span class="sxs-lookup"><span data-stu-id="e38c7-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="e38c7-114">重設使用者密碼</span><span class="sxs-lookup"><span data-stu-id="e38c7-114">Reset user password</span></span>  <br/> |<span data-ttu-id="e38c7-115">防止使用者存取 Microsoft 365 的另一種方式是重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="e38c7-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="e38c7-116">這樣做可以防止使用者使用他們的帳戶，但是他們仍然可以查看先前下載或同步處理的電子郵件和檔。</span><span class="sxs-lookup"><span data-stu-id="e38c7-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="e38c7-117">您可以接著登入，並將密碼變更為您所選擇的其中一個。</span><span class="sxs-lookup"><span data-stu-id="e38c7-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="e38c7-118">當員工突然且永久離職時使用，而您覺得商務資料有問題。</span><span class="sxs-lookup"><span data-stu-id="e38c7-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="e38c7-119">移除所有指派的授權</span><span class="sxs-lookup"><span data-stu-id="e38c7-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="e38c7-120">另一個選項是移除所有指派給使用者的 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="e38c7-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="e38c7-121">這可防止使用者使用應用程式和服務，例如 Office 套件、web 的 Office 應用程式、Yammer 及 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="e38c7-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="e38c7-122">他們仍可登入，但無法使用這些服務。</span><span class="sxs-lookup"><span data-stu-id="e38c7-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="e38c7-123">當您感覺此使用者不再需要存取 Microsoft 365 中的特定功能時，請使用此功能。</span><span class="sxs-lookup"><span data-stu-id="e38c7-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="e38c7-124">**重要：** 當您移除授權時，使用者的信箱將會在30天內刪除。</span><span class="sxs-lookup"><span data-stu-id="e38c7-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="e38c7-125">相關文章</span><span class="sxs-lookup"><span data-stu-id="e38c7-125">Related articles</span></span>

[<span data-ttu-id="e38c7-126">從 Microsoft 365 下架使用者</span><span class="sxs-lookup"><span data-stu-id="e38c7-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="e38c7-127">在 Microsoft 365 中重設使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="e38c7-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="e38c7-128">將授權指派給 Microsoft 365 for business 中的使用者</span><span class="sxs-lookup"><span data-stu-id="e38c7-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="e38c7-129">從 Microsoft 365 for business 中的使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="e38c7-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

