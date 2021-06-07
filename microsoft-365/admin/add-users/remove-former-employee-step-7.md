---
title: 步驟 7-刪除離職員工的使用者帳戶
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
description: 請遵循下列步驟來刪除離職員工的使用者帳戶。
ms.openlocfilehash: e9f87f68650394a81c735346db929bf592e91d18
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779828"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="8d8de-103">步驟 7-刪除離職員工的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8d8de-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="8d8de-104">儲存並存取離職員工的所有使用者資料後，您可以刪除離職員工的帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d8de-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d8de-p101">如果您已經設定電子郵件轉寄功能或將它轉換為共用信箱的話，請不要刪除該帳戶。這兩者都需要該帳戶做為轉寄或共用信箱功能的錨點。</span><span class="sxs-lookup"><span data-stu-id="8d8de-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="8d8de-107">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8d8de-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8d8de-108">選取您要刪除的員工名稱。</span><span class="sxs-lookup"><span data-stu-id="8d8de-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="8d8de-109">在使用者的名稱下，選取 [ **刪除使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8d8de-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="8d8de-110">為此使用者選擇您想要的選項，然後選取 [ **刪除使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8d8de-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="8d8de-111">如果您已有其他使用者存取此使用者的電子郵件和 OneDrive，您不需要在這裡重新執行。</span><span class="sxs-lookup"><span data-stu-id="8d8de-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="8d8de-p103">當您刪除使用者時，帳戶會變成非作用中的狀態並持續大約 30 天。在這段期間內，您可以還原該帳戶，但 30 天一過，就會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8d8de-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>

## <a name="watch-delete-a-former-employees-user-account"></a><span data-ttu-id="8d8de-114">觀賞：刪除離職員工的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8d8de-114">Watch: Delete a former employee's user account</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

<span data-ttu-id="8d8de-115">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="8d8de-115">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="8d8de-116">貴組織是否使用 Active Directory？</span><span class="sxs-lookup"><span data-stu-id="8d8de-116">Does your organization use Active Directory?</span></span>

<span data-ttu-id="8d8de-117">如果您的組織同步處理使用者帳戶以從本機 active directory 環境 Microsoft 365，您必須在本機 active directory 服務中刪除及還原這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d8de-117">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="8d8de-118">您不能在 Office 365 刪除或還原使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d8de-118">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="8d8de-119">若要瞭解如何在 Active Directory 中刪除及還原使用者帳戶，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="8d8de-119">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="8d8de-120">如果您使用的是 Azure Active Directory，請參閱[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d8de-120">If you're using Azure Active Directory, see the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="8d8de-121">終止員工的電子郵件工作階段所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="8d8de-121">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="8d8de-122">以下是如何讓員工退出電子郵件 (Exchange) 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8d8de-122">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d8de-123">**您可以執行的作業**</span><span class="sxs-lookup"><span data-stu-id="8d8de-123">**What you can do**</span></span> <br/> |<span data-ttu-id="8d8de-124">**做法**</span><span class="sxs-lookup"><span data-stu-id="8d8de-124">**How you do it**</span></span> <br/> |
|<span data-ttu-id="8d8de-125">終止工作階段 (例如 Outlook 網頁版、Outlook、Exchange Active Sync 等等)，並強制開啟新工作階段</span><span class="sxs-lookup"><span data-stu-id="8d8de-125">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="8d8de-126">重設密碼</span><span class="sxs-lookup"><span data-stu-id="8d8de-126">Reset password</span></span>  <br/> |
|<span data-ttu-id="8d8de-127">終止工作階段並封鎖對日後工作階段的存取 (針對所有通訊協定)</span><span class="sxs-lookup"><span data-stu-id="8d8de-127">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="8d8de-128">停用帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d8de-128">Disable the account.</span></span> <span data-ttu-id="8d8de-129">例如，在 Exchange 系統管理中心或使用 PowerShell) 中 (：</span><span class="sxs-lookup"><span data-stu-id="8d8de-129">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="8d8de-130">終止特定通訊協定的工作階段 (例如 ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="8d8de-130">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="8d8de-131">停用通訊協定。</span><span class="sxs-lookup"><span data-stu-id="8d8de-131">Disable the protocol.</span></span> <span data-ttu-id="8d8de-132">例如，在 Exchange 系統管理中心或使用 PowerShell) 中 (：</span><span class="sxs-lookup"><span data-stu-id="8d8de-132">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="8d8de-133">您可以在三個位置完成上述作業：</span><span class="sxs-lookup"><span data-stu-id="8d8de-133">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d8de-134">**如果您在此處終止工作階段**</span><span class="sxs-lookup"><span data-stu-id="8d8de-134">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="8d8de-135">**需要多久時間**</span><span class="sxs-lookup"><span data-stu-id="8d8de-135">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="8d8de-136">在 Exchange 系統管理中心或使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d8de-136">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="8d8de-137">預期的延遲是 30 分鐘內</span><span class="sxs-lookup"><span data-stu-id="8d8de-137">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="8d8de-138">在 Azure Active Directory 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8d8de-138">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="8d8de-139">預期的延遲是 60 分鐘</span><span class="sxs-lookup"><span data-stu-id="8d8de-139">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="8d8de-140">在內部部署環境</span><span class="sxs-lookup"><span data-stu-id="8d8de-140">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="8d8de-141">預期的延遲是 3 小時或更多</span><span class="sxs-lookup"><span data-stu-id="8d8de-141">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="8d8de-142">如何以最快速度取得帳戶終止的回應</span><span class="sxs-lookup"><span data-stu-id="8d8de-142">How to get fastest response for account termination</span></span>

 <span data-ttu-id="8d8de-143">**最快**：使用 Exchange 系統管理中心 (使用 PowerShell) 或 Azure Active Directory 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="8d8de-143">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center.</span></span> <span data-ttu-id="8d8de-144">在內部部署環境中，透過 DirSync 同步處理變更可能會花費數小時。</span><span class="sxs-lookup"><span data-stu-id="8d8de-144">In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="8d8de-145">使用 **內部部署和 Exchange Datacenter 中目前狀態的使用者最快**：使用 Azure Active Directory 系統管理中心或 Exchange 的系統管理中心終止會話，並在內部部署環境中也進行變更。</span><span class="sxs-lookup"><span data-stu-id="8d8de-145">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well.</span></span> <span data-ttu-id="8d8de-146">若不採取此做法，在 Azure Active Directory 系統管理中心或 Exchange 系統管理中心進行的變更將被 DirSync 覆寫。</span><span class="sxs-lookup"><span data-stu-id="8d8de-146">Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8d8de-147">相關文章</span><span class="sxs-lookup"><span data-stu-id="8d8de-147">Related articles</span></span>

[<span data-ttu-id="8d8de-148">還原使用者</span><span class="sxs-lookup"><span data-stu-id="8d8de-148">Restore a user</span></span>](restore-user.md)

[<span data-ttu-id="8d8de-149">重設密碼</span><span class="sxs-lookup"><span data-stu-id="8d8de-149">Reset passwords</span></span>](reset-passwords.md)
