---
title: 移除離職員工-簡介
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
description: 遵循此方案中的步驟，從 Microsoft 365 中移除前任員工，並保護組織的資料。
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241733"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="bf674-103">概覽：移除前任員工和安全資料</span><span class="sxs-lookup"><span data-stu-id="bf674-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="bf674-104">我們常遇到的問題是：「我應該在員工離開組織時，應如何保護資料並保護存取？」</span><span class="sxs-lookup"><span data-stu-id="bf674-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="bf674-105">本文將說明如何封鎖 Microsoft 365 的存取，您應該採取的措施來保護您的資料，以及如何允許其他員工存取資料。</span><span class="sxs-lookup"><span data-stu-id="bf674-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="bf674-106">觀賞有關移除員工的簡短影片。</span><span class="sxs-lookup"><span data-stu-id="bf674-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="bf674-107">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="bf674-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="bf674-108">若要防止員工登入：</span><span class="sxs-lookup"><span data-stu-id="bf674-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="bf674-109">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="bf674-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="bf674-110">選取使用者名稱旁的方塊，然後選取 [ **重設密碼**]。</span><span class="sxs-lookup"><span data-stu-id="bf674-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="bf674-111">輸入新密碼，然後選取 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="bf674-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="bf674-112"> (不要將其傳送給他們。 ) </span><span class="sxs-lookup"><span data-stu-id="bf674-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="bf674-113">選取使用者的名稱以移至其屬性窗格，然後在 [ **帳戶** ] 索引標籤上，選取 [ **啟動登出**]。</span><span class="sxs-lookup"><span data-stu-id="bf674-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="bf674-114">您必須是全域系統管理員，才可啟動登出。</span><span class="sxs-lookup"><span data-stu-id="bf674-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="bf674-115">在一小時內，或在他們保留目前的 Microsoft 365 頁面時，系統會提示他們重新登入。</span><span class="sxs-lookup"><span data-stu-id="bf674-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="bf674-116">存取權杖適用于一個小時，所以時程表取決於該權杖所留下的時間，以及是否要流覽至目前的網頁。</span><span class="sxs-lookup"><span data-stu-id="bf674-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf674-117">雖然我們已編號此方案中的步驟，而且您不需要以完全順序完成此方案，我們建議您以這種方式執行步驟。</span><span class="sxs-lookup"><span data-stu-id="bf674-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bf674-118">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="bf674-118">Before you begin</span></span>

<span data-ttu-id="bf674-119">您必須是全域系統管理員，才可完成此方案中的步驟。</span><span class="sxs-lookup"><span data-stu-id="bf674-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bf674-120">**步驟**</span><span class="sxs-lookup"><span data-stu-id="bf674-120">**Step**</span></span> <br/> |<span data-ttu-id="bf674-121">**這樣做的原因**</span><span class="sxs-lookup"><span data-stu-id="bf674-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="bf674-122">步驟 1-防止離職員工登入並封鎖 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="bf674-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="bf674-123">這會封鎖您的離職員工 Microsoft 365，並防止人員存取 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="bf674-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="bf674-124">步驟 2-儲存離職員工信箱的內容</span><span class="sxs-lookup"><span data-stu-id="bf674-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="bf674-125">這適用于即將進行員工工作的人員，或是否有訴訟。</span><span class="sxs-lookup"><span data-stu-id="bf674-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="bf674-126">步驟 3-將離職員工的電子郵件轉寄給另一個員工或轉換成共用信箱</span><span class="sxs-lookup"><span data-stu-id="bf674-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="bf674-p104">這讓離職員工的電子郵件地址也能繼續保持有效。如果客戶或合作夥伴仍將電子郵件傳送到離職員工的地址，這樣做可讓他們與接掌工作的人員取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="bf674-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="bf674-129">步驟 4-授予另一個員工 OneDrive 和 Outlook 資料的存取權</span><span class="sxs-lookup"><span data-stu-id="bf674-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="bf674-130">如果您只移除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的內容將會保留，即使超過 30 天後仍可存取。</span><span class="sxs-lookup"><span data-stu-id="bf674-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="bf674-131">在您刪除帳戶之前，您應該授與其他使用者 OneDrive 和 Outlook 的存取權。</span><span class="sxs-lookup"><span data-stu-id="bf674-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="bf674-132">在您刪除員工的帳戶之後，其 OneDrive 和 Outlook 中的內容會保留 **30** 天。</span><span class="sxs-lookup"><span data-stu-id="bf674-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="bf674-133">不過，在此30天內，您可以還原使用者的帳戶，並取得其內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="bf674-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="bf674-134">如果您還原使用者的帳戶，OneDrive 和 Outlook 內容仍可供您在30天之後存取。</span><span class="sxs-lookup"><span data-stu-id="bf674-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="bf674-135">步驟 5-清除並封鎖離職員工的行動裝置</span><span class="sxs-lookup"><span data-stu-id="bf674-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="bf674-136">從手機或平板電腦中移除您的業務資料。</span><span class="sxs-lookup"><span data-stu-id="bf674-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="bf674-137">步驟 6-移除並刪除離職員工的 Microsoft 365 授權</span><span class="sxs-lookup"><span data-stu-id="bf674-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="bf674-p106">當您移除授權時，您可將授權指派給其他人員。或者，您也可以刪除授權，這樣就不必在雇用另一位人員之前繼續付費。</span><span class="sxs-lookup"><span data-stu-id="bf674-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="bf674-140">當您移除或刪除授權時，使用者的舊電子郵件、連絡人及行事曆會保留 **30 天**，然後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="bf674-140">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted.</span></span> <span data-ttu-id="bf674-141">如果您移除或刪除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的將會保留，即使超過 30 天後仍可存取。</span><span class="sxs-lookup"><span data-stu-id="bf674-141">If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span>  <br/> |
|[<span data-ttu-id="bf674-142">步驟 7-刪除離職員工的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bf674-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="bf674-143">這會從您的系統管理中心移除帳戶。</span><span class="sxs-lookup"><span data-stu-id="bf674-143">This removes the account from your admin center.</span></span> <span data-ttu-id="bf674-144">保持有條不紊。</span><span class="sxs-lookup"><span data-stu-id="bf674-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="bf674-145">相關文章</span><span class="sxs-lookup"><span data-stu-id="bf674-145">Related articles</span></span>

[<span data-ttu-id="bf674-146">還原使用者</span><span class="sxs-lookup"><span data-stu-id="bf674-146">Restore a user</span></span>](restore-user.md)
