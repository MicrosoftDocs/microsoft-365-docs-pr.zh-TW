---
title: 步驟 1-停止員工登入 Microsoft 365
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 封鎖離職員工的登入，並封鎖 Microsoft 365 服務的存取權。
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177114"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="cad44-103">步驟 1-防止離職員工登入並封鎖 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="cad44-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="cad44-104">如果您需要立即避免使用者登入存取，您應該重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="cad44-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="cad44-105">在此步驟中，請從 Microsoft 365 中強制登出使用者。</span><span class="sxs-lookup"><span data-stu-id="cad44-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="cad44-106">您必須是全域系統管理員，才能啟動其他系統管理員的登出。</span><span class="sxs-lookup"><span data-stu-id="cad44-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="cad44-107">若為非系統管理員的使用者，您可以使用使用者系統管理員或服務台管理員使用者來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cad44-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="cad44-108">深入瞭解系統管理角色</span><span class="sxs-lookup"><span data-stu-id="cad44-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="cad44-109">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cad44-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cad44-110">選取使用者名稱旁的方塊，然後選取 [ **重設密碼**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="cad44-111">輸入新密碼，然後選取 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="cad44-112"> (不要將其傳送給他們。 ) </span><span class="sxs-lookup"><span data-stu-id="cad44-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="cad44-113">選取使用者的名稱以移至其屬性窗格，然後在 [ **帳戶** ] 索引標籤上，選取 [登出 **所有會話**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="cad44-114">在一小時內，或在他們保留目前的 Microsoft 365 頁面時，系統會提示他們重新登入。</span><span class="sxs-lookup"><span data-stu-id="cad44-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="cad44-115">存取權杖適用于一個小時，所以時程表取決於該權杖所留下的時間，以及是否要流覽至目前的網頁。</span><span class="sxs-lookup"><span data-stu-id="cad44-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cad44-116">如果使用者在 Outlook 網頁版，只要在其信箱中按一下滑鼠，就不會立即將其彈出。</span><span class="sxs-lookup"><span data-stu-id="cad44-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="cad44-117">當他們選取不同的麻將牌（例如 OneDrive，或重新整理其瀏覽器）時，就會啟動登出。</span><span class="sxs-lookup"><span data-stu-id="cad44-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="cad44-118">若要使用 PowerShell 立即登出使用者，請參閱 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cad44-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="cad44-119">如需花費多久時間以將某人退出電子郵件的詳細資訊，請參閱[終止員工的電子郵件工作階段所需注意的事項](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。</span><span class="sxs-lookup"><span data-stu-id="cad44-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="cad44-120">封鎖離職員工的 Microsoft 365 服務存取權</span><span class="sxs-lookup"><span data-stu-id="cad44-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="cad44-121">封鎖帳戶最多可能需要24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="cad44-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="cad44-122">如果您需要立即避免使用者登入存取，請依照上述步驟進行，然後重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="cad44-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="cad44-123">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cad44-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cad44-124">選取您要封鎖的員工名稱，在使用者的名稱下，選取 [ **封鎖此使用者** 的符號]。</span><span class="sxs-lookup"><span data-stu-id="cad44-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="cad44-125">選取 [ **封鎖使用者登入**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="cad44-126">封鎖離職員工的電子郵件存取權 (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="cad44-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="cad44-127">如果您的 Microsoft 365 訂閱中包含電子郵件，請登入 Exchange 系統管理中心，然後遵循下列步驟，封鎖您的離職員工存取其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cad44-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="cad44-128">移至 <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="cad44-128">Go to the <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="cad44-129">在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="cad44-130">按兩下使用者並前往 [**電子郵件應用程式**] 下的 [**管理電子郵件應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="cad44-130">Double-click the user and go to **Manage email apps settings** under **Email apps**.</span></span> <span data-ttu-id="cad44-131">**關閉** 所有選項的滑塊;行動裝置 **(Exchange ActiveSync)**、 **Outlook 網頁版**、 **Outlook 桌面 (MAPI)**、 **Exchange web 服務**、 **POP3** 和 **IMAP**。</span><span class="sxs-lookup"><span data-stu-id="cad44-131">Turn **Off** the slider for all the options; **Mobile (Exchange ActiveSync)**, **Outlook on the web**, **Outlook desktop (MAPI)**, **Exchange web services**, **POP3**, and **IMAP**.</span></span>
4. <span data-ttu-id="cad44-132">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="cad44-132">Select **Save**.</span></span>
