---
title: 從 [受限使用者] 入口網站中移除封鎖的使用者
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 系統管理員可以從 Office 365 中的 [受限使用者] 入口網站瞭解如何移除使用者。 傳送輸出垃圾郵件 (通常是因為「帳戶洩露」) 的使用者會被新增至 [受限使用者] 入口網站。
ms.openlocfilehash: 1625046cefbe6a62beacacefdac0318b6c16f49b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634373"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="22bab-104">從 Office 365 中的 [受限使用者] 入口網站移除封鎖的使用者</span><span class="sxs-lookup"><span data-stu-id="22bab-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="22bab-105">如果使用者超過[服務限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[輸出垃圾郵件](configure-the-outbound-spam-policy.md)原則中所指定的輸出傳送限制之一，系統就會限制使用者傳送電子郵件，但他們仍可接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="22bab-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="22bab-106">使用者會被新增至安全性與合規性中心的 [受限使用者] 入口網站。</span><span class="sxs-lookup"><span data-stu-id="22bab-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="22bab-107">當他們嘗試傳送電子郵件時，系統會以未傳遞回報 (又稱為 NDR 或退回的郵件) 傳回郵件，並包含錯誤碼 [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和下列文字：</span><span class="sxs-lookup"><span data-stu-id="22bab-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="22bab-108">「因為您不是認可的有效寄件者，所以無法傳遞您的郵件。</span><span class="sxs-lookup"><span data-stu-id="22bab-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="22bab-109">最有可能發生此狀況的原因是您的電子郵件地址有傳送垃圾郵件的嫌疑，因此系統已不允許此電子郵件地址傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="22bab-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="22bab-110">請連絡您的電子郵件系統管理員以取得協助。</span><span class="sxs-lookup"><span data-stu-id="22bab-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="22bab-111">遠端伺服器傳回 ‘550 5.1.8 存取被拒，錯誤的外寄寄件者。’」</span><span class="sxs-lookup"><span data-stu-id="22bab-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="22bab-112">系統管理員可以從安全性與合規性中心移除使用者，或用 Exchange Online PowerShell 移除使用者。</span><span class="sxs-lookup"><span data-stu-id="22bab-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="22bab-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="22bab-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="22bab-114">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="22bab-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="22bab-115">若要直接移至 [受限使用者]\*\*\*\* 頁面，請使用 <https://protection.office.com/restrictedusers>。</span><span class="sxs-lookup"><span data-stu-id="22bab-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="22bab-116">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="22bab-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="22bab-117">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="22bab-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="22bab-118">若要移除 [受限使用者] 入口網站中的使用者，您必須是**組織管理**或**安全性系統管理員**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="22bab-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="22bab-119">若要以唯讀方式存取 [受限使用者] 入口網站，您必須是**安全性讀取者**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="22bab-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="22bab-120">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="22bab-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="22bab-121">超過輸出郵件限制的寄件者是帳戶洩露的指標。</span><span class="sxs-lookup"><span data-stu-id="22bab-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="22bab-122">從 [受限使用者] 入口網站移除使用者之前，請務必遵循所需的步驟重新取得該帳戶的控制權。</span><span class="sxs-lookup"><span data-stu-id="22bab-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="22bab-123">如需詳細資訊，請參閱[針對 Office 365 電子郵件帳戶洩露的對策](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="22bab-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="22bab-124">使用安全性與合規性中心移除 [受限使用者] 清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="22bab-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="22bab-125">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [檢閱]\*\*\*\* \> [受限使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="22bab-126">尋找並選取您要解除封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="22bab-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="22bab-127">在 [動作]\*\*\*\* 資料行中，按一下 [解除封鎖]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="22bab-128">隨即會出現飛出視窗，內含帳戶的傳送受到限制的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="22bab-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="22bab-129">您必須逐一查看建議，以確保帳戶實際上遭到入侵時，您會採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="22bab-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="22bab-130">完成時，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="22bab-131">下一個畫面提供建議來協助避免未來的入侵。</span><span class="sxs-lookup"><span data-stu-id="22bab-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="22bab-132">啟用多重要素驗證 (MFA)，並變更密碼，是很好的防禦方式。</span><span class="sxs-lookup"><span data-stu-id="22bab-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="22bab-133">完成時按一下 [解除封鎖使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="22bab-134">按一下 [是]\*\*\*\* 以確認變更。</span><span class="sxs-lookup"><span data-stu-id="22bab-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="22bab-135">可能需要 30 分鐘以上的時間，才能移除限制。</span><span class="sxs-lookup"><span data-stu-id="22bab-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="22bab-136">確認受限使用者的提醒設定</span><span class="sxs-lookup"><span data-stu-id="22bab-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="22bab-137">當系統封鎖使用者傳送電子郵件時，預設的警示原則**無法傳送電子郵件的受限使用者**會自動通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="22bab-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="22bab-138">您可以確認這些設定，並新增其他要通知的使用者。</span><span class="sxs-lookup"><span data-stu-id="22bab-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="22bab-139">如需有關警示原則的詳細資訊，請參閱[安全性與合規性中心中的警示原則](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="22bab-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22bab-140">若要讓警示運作，必須開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="22bab-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="22bab-141">如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="22bab-141">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="22bab-142">在安全性與合規性中心，移至 [警示]\*\*\*\* \> [警示原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="22bab-143">尋找並選取 [無法傳送電子郵件的受限使用者]\*\*\*\* 警示。</span><span class="sxs-lookup"><span data-stu-id="22bab-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="22bab-144">在隨即出現的飛出視窗中，確認或設定如下設定：</span><span class="sxs-lookup"><span data-stu-id="22bab-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="22bab-145">**狀態**：確認已開啟警示 ![打開](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)。</span><span class="sxs-lookup"><span data-stu-id="22bab-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="22bab-146">**電子郵件收件者**：按一下 [編輯]\*\*\*\*，在 [編輯收件者]\*\*\*\* 飛出視窗中確認或設定如下列設定：</span><span class="sxs-lookup"><span data-stu-id="22bab-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="22bab-147">**傳送電子郵件通知**：確認已選取核取方塊 ([開啟]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="22bab-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="22bab-148">**電子郵件收件者**：預設值是 **TenantAdmins** (表示 **全域系統管理員**成員)。</span><span class="sxs-lookup"><span data-stu-id="22bab-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="22bab-149">若要新增其他收件者，按一下方塊中的空白處。</span><span class="sxs-lookup"><span data-stu-id="22bab-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="22bab-150">收件者清單隨即顯示，您可以輸入名稱開始篩選，然後選取收件者。</span><span class="sxs-lookup"><span data-stu-id="22bab-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="22bab-151">若要移除方塊中的現有收件者，只要按一下其名稱旁的移除圖示![](../../media/scc-remove-icon.png)即可。</span><span class="sxs-lookup"><span data-stu-id="22bab-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="22bab-152">**每日通知限制**：預設值是 [無限制]\*\*\*\*，但您可以選取每天的通知數量上限。</span><span class="sxs-lookup"><span data-stu-id="22bab-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="22bab-153">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="22bab-154">返回 [限制使用者傳送電子郵件]\*\*\*\* 飛出視窗中，按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22bab-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="22bab-155">使用 Exchange Online PowerShell 杦檢視和移除受限使用者清單中的使用者</span><span class="sxs-lookup"><span data-stu-id="22bab-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="22bab-156">若要檢視限制傳送電子郵件的使用者清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="22bab-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="22bab-157">若要檢視特定使用者的詳細資料，請執行下列命令並以其電子郵件地址取代 \<emailaddress\>：</span><span class="sxs-lookup"><span data-stu-id="22bab-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="22bab-158">如需詳細的語法及參數資訊，請參閱 [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="22bab-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress).</span></span>

<span data-ttu-id="22bab-159">若要從 [受限使用者] 清單中移除使用者，請執行下列命令並以其電子郵件地址取代 \<emailaddress\>：</span><span class="sxs-lookup"><span data-stu-id="22bab-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="22bab-160">如需詳細的語法及參數資訊，請參閱 [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="22bab-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress).</span></span>
