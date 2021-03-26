---
title: 重新傳送使用者的密碼 - 系統管理說明
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b838071-94aa-4b8e-8d84-d17ece1ee951
description: 瞭解如何重設密碼，並將電子郵件傳送至新的 Microsoft 365 使用者。
ms.openlocfilehash: 2b2c8657a4bbd4745a3fee34fc259244b83640d3
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222096"
---
# <a name="resend-a-users-password---admin-help"></a><span data-ttu-id="2b222-103">重新傳送使用者的密碼 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="2b222-103">Resend a user's password - Admin Help</span></span>

<span data-ttu-id="2b222-104">本文說明如何將通知電子郵件重新傳送給 Office 365 中的新使用者。</span><span class="sxs-lookup"><span data-stu-id="2b222-104">This article explains how to resend the notification email to a new user in Office 365.</span></span> <span data-ttu-id="2b222-105">這可能會在您建立新的使用者時出現，而且不會收到具有新密碼的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2b222-105">This can happen when you create a new user and they don't get an email with their new password.</span></span> <span data-ttu-id="2b222-106">若要執行此動作，請重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="2b222-106">You do this by resetting the user's password.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2b222-107">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="2b222-107">Before you begin</span></span>

<span data-ttu-id="2b222-108">本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。</span><span class="sxs-lookup"><span data-stu-id="2b222-108">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="2b222-109">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="2b222-109">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="2b222-110">[何謂系統管理員帳戶?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)</span><span class="sxs-lookup"><span data-stu-id="2b222-110">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span>

<span data-ttu-id="2b222-111">您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="2b222-111">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="resend-user-password"></a><span data-ttu-id="2b222-112">重新傳送使用者密碼</span><span class="sxs-lookup"><span data-stu-id="2b222-112">Resend user password</span></span>
  
::: moniker range="o365-worldwide"  
  
1. <span data-ttu-id="2b222-113">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="2b222-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2b222-114">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="2b222-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2b222-115">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="2b222-115">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

::: moniker-end

2. <span data-ttu-id="2b222-116">在 [作用中 **使用者** ] 頁面上，選取使用者，然後選取 [ **重設密碼**]。</span><span class="sxs-lookup"><span data-stu-id="2b222-116">On the **Active users** page, select the user and then select **Reset password**.</span></span>

3. <span data-ttu-id="2b222-117">依照「 **重設密碼** 」頁面上的指示，為使用者自動產生新密碼或為使用者建立新密碼，然後選取 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="2b222-117">Follow the instructions on the **Reset password** page to auto-generate a new password for the user or create one for them, and then select **Reset**.</span></span>  

4. <span data-ttu-id="2b222-118">輸入使用者可以取得的電子郵件地址，讓他們接收新密碼，並追蹤以確保他們知道。</span><span class="sxs-lookup"><span data-stu-id="2b222-118">Enter an email address the user can get to so they receive the new password, and follow up with them to make sure they got it.</span></span>

## <a name="related-content"></a><span data-ttu-id="2b222-119">相關內容</span><span class="sxs-lookup"><span data-stu-id="2b222-119">Related content</span></span>

[<span data-ttu-id="2b222-120">讓使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="2b222-120">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="2b222-121">重設密碼</span><span class="sxs-lookup"><span data-stu-id="2b222-121">Reset passwords</span></span>](../add-users/reset-passwords.md)