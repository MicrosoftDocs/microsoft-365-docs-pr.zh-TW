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
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535947"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="418ab-103">步驟 1-防止離職員工登入並封鎖 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="418ab-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="418ab-104">如果您需要立即避免使用者登入存取，您應該重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="418ab-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="418ab-105">在此步驟中，請從 Microsoft 365 中強制登出使用者。</span><span class="sxs-lookup"><span data-stu-id="418ab-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="418ab-106">您必須是全域系統管理員，才可啟動登出。</span><span class="sxs-lookup"><span data-stu-id="418ab-106">You need to be a global administrator to initiate sign-out.</span></span>

1. <span data-ttu-id="418ab-107">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="418ab-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="418ab-108">選取使用者名稱旁的方塊，然後選取 [ **重設密碼**]。</span><span class="sxs-lookup"><span data-stu-id="418ab-108">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="418ab-109">輸入新密碼，然後選取 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="418ab-109">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="418ab-110"> (不要將其傳送給他們。 ) </span><span class="sxs-lookup"><span data-stu-id="418ab-110">(Don't send it to them.)</span></span>
4. <span data-ttu-id="418ab-111">選取使用者的名稱以移至其屬性窗格，然後在 [ **帳戶** ] 索引標籤上，選取 [ **啟動登出**]。</span><span class="sxs-lookup"><span data-stu-id="418ab-111">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="418ab-112">在一小時內，或在他們保留目前的 Microsoft 365 頁面時，系統會提示他們重新登入。</span><span class="sxs-lookup"><span data-stu-id="418ab-112">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="418ab-113">存取權杖適用于一個小時，所以時程表取決於該權杖所留下的時間，以及是否要流覽至目前的網頁。</span><span class="sxs-lookup"><span data-stu-id="418ab-113">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="418ab-114">如果使用者是在網頁上的 Outlook，只要在其信箱中按一下 [流覽]，就不會立即啟用。</span><span class="sxs-lookup"><span data-stu-id="418ab-114">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="418ab-115">當他們選取不同的麻將牌（例如 OneDrive，或重新整理其瀏覽器）時，就會啟動登出。</span><span class="sxs-lookup"><span data-stu-id="418ab-115">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="418ab-116">若要使用 PowerShell 立即登出使用者，請參閱 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="418ab-116">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="418ab-117">如需花費多久時間以將某人退出電子郵件的詳細資訊，請參閱[終止員工的電子郵件工作階段所需注意的事項](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。</span><span class="sxs-lookup"><span data-stu-id="418ab-117">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="418ab-118">封鎖離職員工的 Microsoft 365 服務存取權</span><span class="sxs-lookup"><span data-stu-id="418ab-118">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="418ab-119">封鎖帳戶最多可能需要24小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="418ab-119">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="418ab-120">如果您需要立即避免使用者登入存取，請依照上述步驟進行，然後重設其密碼。</span><span class="sxs-lookup"><span data-stu-id="418ab-120">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="418ab-121">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="418ab-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="418ab-122">選取您要封鎖的員工名稱，在使用者的名稱下，選取 [ **封鎖此使用者** 的符號]。</span><span class="sxs-lookup"><span data-stu-id="418ab-122">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="418ab-123">選取 [ **封鎖使用者登入**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="418ab-123">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="418ab-124">封鎖離職員工的電子郵件存取權 (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="418ab-124">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="418ab-125">如果您的 Microsoft 365 訂閱中包含電子郵件，請登入 Exchange 系統管理中心，然後遵循下列步驟，封鎖您的離職員工存取其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="418ab-125">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="418ab-126">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="418ab-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="418ab-127">在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="418ab-127">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="418ab-128">按兩下使用者並移至 [ **信箱功能** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="418ab-128">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="418ab-129">在 [行動 **裝置**] 下，選取 [**停用 Exchange ActiveSync** ] 和 [**停用裝置的 OWA]，** 然後在出現提示時回答 **[是]**</span><span class="sxs-lookup"><span data-stu-id="418ab-129">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="418ab-130">在 [ **電子郵件** 連線] 下，選取 [ **停** 用並在提示時回答 **Yes]** 。</span><span class="sxs-lookup"><span data-stu-id="418ab-130">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
