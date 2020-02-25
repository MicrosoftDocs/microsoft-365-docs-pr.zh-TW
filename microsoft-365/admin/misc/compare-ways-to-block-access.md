---
title: 比較封鎖存取 Office 365 的方法
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 了解如何當員工離開組織時，封鎖 Office 365 存取權限。
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254328"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="c52db-103">比較封鎖存取 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="c52db-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="c52db-104">當員工離開組織，很好的字詞或損毀上, 您要封鎖其 Office 365 存取權。</span><span class="sxs-lookup"><span data-stu-id="c52db-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365.</span></span> <span data-ttu-id="c52db-105">以下是幾種方法，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="c52db-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="c52db-106">**若要封鎖存取的方式**</span><span class="sxs-lookup"><span data-stu-id="c52db-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="c52db-107">**定義**</span><span class="sxs-lookup"><span data-stu-id="c52db-107">**Definition**</span></span> <br/> |<span data-ttu-id="c52db-108">**最佳做法**</span><span class="sxs-lookup"><span data-stu-id="c52db-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="c52db-109">封鎖登入</span><span class="sxs-lookup"><span data-stu-id="c52db-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="c52db-110">封鎖使用者存取 Office 365 的一種方式是將他們登入的狀態變更為**登入封鎖**。</span><span class="sxs-lookup"><span data-stu-id="c52db-110">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="c52db-111">這會禁止使用者從他們的電腦登入 Office 365 和行動裝置但是他們仍然可以檢視先前下載或同步處理電子郵件和文件。</span><span class="sxs-lookup"><span data-stu-id="c52db-111">This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c52db-112">如果您正在使用 Blackberry 企業服務，您可以一併停用那里其存取。</span><span class="sxs-lookup"><span data-stu-id="c52db-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="c52db-113">當員工離開組織計劃或他們計劃要進行長期請假時使用。</span><span class="sxs-lookup"><span data-stu-id="c52db-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="c52db-114">重設使用者密碼</span><span class="sxs-lookup"><span data-stu-id="c52db-114">Reset user password</span></span>  <br/> |<span data-ttu-id="c52db-115">若要防止使用者存取 Office 365 的另一個方法是重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="c52db-115">Another way to prevent a user from accessing Office 365 is to reset their password.</span></span> <span data-ttu-id="c52db-116">這會防止他們使用自己的帳戶，但是他們仍然可以檢視先前已下載或同步處理的電子郵件和文件。</span><span class="sxs-lookup"><span data-stu-id="c52db-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c52db-117">您可以然後為他們登入，並將密碼變更為您所選擇的其中一個。</span><span class="sxs-lookup"><span data-stu-id="c52db-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="c52db-118">當員工離開突然和永久和您覺得有使用此連接器是商務資料的考量。</span><span class="sxs-lookup"><span data-stu-id="c52db-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="c52db-119">移除所有指派授權</span><span class="sxs-lookup"><span data-stu-id="c52db-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="c52db-120">另一個選項是要移除任何指派給使用者的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="c52db-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="c52db-121">這會防止它們使用的網頁伺服器、 Yammer 與 SharePoint Online 的應用程式和服務，例如 Office 套件、 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c52db-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="c52db-122">他們仍可以登入，但是不能使用這些服務。</span><span class="sxs-lookup"><span data-stu-id="c52db-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="c52db-123">當您認為這位使用者無法再使用此連接器必須在 Office 365 中的特定功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="c52db-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="c52db-124">**重要：** 當您移除授權時，將會 30 天內刪除使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="c52db-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="c52db-125">相關文章</span><span class="sxs-lookup"><span data-stu-id="c52db-125">Related articles</span></span>

[<span data-ttu-id="c52db-126">登出 Office 365 中的使用者</span><span class="sxs-lookup"><span data-stu-id="c52db-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="c52db-127">重設 Office 365 中的使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="c52db-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="c52db-128">在商務用 Office 365 中指派授權給使用者</span><span class="sxs-lookup"><span data-stu-id="c52db-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="c52db-129">在商務用 Office 365 中從使用者移除授權</span><span class="sxs-lookup"><span data-stu-id="c52db-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

