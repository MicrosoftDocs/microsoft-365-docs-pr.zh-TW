---
title: 回應 Office 365 中遭入侵的電子郵件帳戶
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何辨識及回應 Office 365 中遭入侵的電子郵件帳戶
ms.openlocfilehash: 76ce2cd9b942403f5d25b7f356740cce6c2acad7
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971503"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="44e1f-103">回應 Office 365 中遭入侵的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="44e1f-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="44e1f-104">**摘要** 了解如何辨識及回應 Office 365 中遭入侵的電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="44e1f-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="44e1f-105">什麼是 Office 365 中遭入侵的電子郵件帳戶？</span><span class="sxs-lookup"><span data-stu-id="44e1f-105">What is a Compromised Email Account in Office 365?</span></span>

<span data-ttu-id="44e1f-106">對 Office 365 信箱、資料和其他服務的存取，是透過使用使用者名稱和密碼或 PIN 之類的認證來控制。</span><span class="sxs-lookup"><span data-stu-id="44e1f-106">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="44e1f-107">當預期使用者以外的其他人竊取這些認證時，遭竊的認證會被視為遭入侵。</span><span class="sxs-lookup"><span data-stu-id="44e1f-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="44e1f-108">攻擊者可以使用這些認證以原始使用者身分登入，並執行非法動作。</span><span class="sxs-lookup"><span data-stu-id="44e1f-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="44e1f-109">攻擊者可以使用遭竊的認證來存取使用者的 Office 365 信箱、SharePoint 資料夾或使用者 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="44e1f-109">Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="44e1f-110">一個常見的動作是攻擊者以原始使用者的身分傳送電子郵件給組織內外的收件者。</span><span class="sxs-lookup"><span data-stu-id="44e1f-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="44e1f-111">當攻擊者以電子郵件寄送資料給外部收件者時，這稱為資料外流。</span><span class="sxs-lookup"><span data-stu-id="44e1f-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="44e1f-112">遭入侵的 Office 365 電子郵件帳戶症狀</span><span class="sxs-lookup"><span data-stu-id="44e1f-112">Symptoms of a Compromised Office 365 Email Account</span></span>

<span data-ttu-id="44e1f-113">使用者可能會注意到並報告其 Office 365 信箱中的異常活動。</span><span class="sxs-lookup"><span data-stu-id="44e1f-113">Users might notice and report unusual activity in their Office 365 mailboxes.</span></span> <span data-ttu-id="44e1f-114">以下是一些常見的症狀：</span><span class="sxs-lookup"><span data-stu-id="44e1f-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="44e1f-115">可疑的活動，例如遺失或刪除的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="44e1f-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="44e1f-116">其他使用者可能會收到來自遭入侵帳戶的電子郵件，該帳戶寄件者的 [寄件備份]\*\*\*\* 資料夾中不存在對應的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="44e1f-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="44e1f-117">出現不是由預期使用者或系統管理員所建立的收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="44e1f-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="44e1f-118">這些規則可能會自動將電子郵件轉寄到未知的地址，或將電子郵件移到 [記事]\*\*\*\*、[垃圾郵件]\*\*\*\* 或 [RSS 訂閱]\*\*\*\* 資料夾。</span><span class="sxs-lookup"><span data-stu-id="44e1f-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="44e1f-119">全域通訊清單中使用者的顯示名稱可能會變更。</span><span class="sxs-lookup"><span data-stu-id="44e1f-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="44e1f-120">使用者的信箱遭封鎖而無法傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="44e1f-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="44e1f-121">在 Microsoft Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 中的 [寄件備份] 或 [刪除的郵件] 資料夾包含常見遭入侵帳戶的郵件，例如「我卡在倫敦了，給我錢」。</span><span class="sxs-lookup"><span data-stu-id="44e1f-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="44e1f-122">異常的個人資料變更，例如名稱、電話號碼或郵遞區號已更新。</span><span class="sxs-lookup"><span data-stu-id="44e1f-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="44e1f-123">異常的認證變更，例如要求變更密碼多次。</span><span class="sxs-lookup"><span data-stu-id="44e1f-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="44e1f-124">最近新增郵件轉寄。</span><span class="sxs-lookup"><span data-stu-id="44e1f-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="44e1f-125">最近新增異常的簽章，例如假銀行簽章或處方藥簽章。</span><span class="sxs-lookup"><span data-stu-id="44e1f-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="44e1f-126">如果使用者報告上述的任何症狀，則應該執行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="44e1f-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="44e1f-127">Microsoft 365 安全性與合規性中心和 Azure 入口網站會提供工具，以協助您調查您懷疑可能遭入侵之使用者帳戶的活動。</span><span class="sxs-lookup"><span data-stu-id="44e1f-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="44e1f-128">安全性與合規性中心的 Office 365 整合稽核記錄 - 檢閱可疑帳戶的所有活動，方法是篩選日期範圍自發生可疑活動之前到目前日期的結果。</span><span class="sxs-lookup"><span data-stu-id="44e1f-128">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="44e1f-129">請勿在搜尋期間篩選活動。</span><span class="sxs-lookup"><span data-stu-id="44e1f-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="44e1f-130">使用 Azure AD 入口網站中提供的 Azure AD 登入記錄檔及其他風險報告。</span><span class="sxs-lookup"><span data-stu-id="44e1f-130">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal.</span></span> <span data-ttu-id="44e1f-131">檢查這些欄中的值：</span><span class="sxs-lookup"><span data-stu-id="44e1f-131">Examine the values in these columns:</span></span>

  - <span data-ttu-id="44e1f-132">檢閱 IP 位址</span><span class="sxs-lookup"><span data-stu-id="44e1f-132">Review IP address</span></span>

  - <span data-ttu-id="44e1f-133">登入位置</span><span class="sxs-lookup"><span data-stu-id="44e1f-133">sign-in locations</span></span>

  - <span data-ttu-id="44e1f-134">登入時間</span><span class="sxs-lookup"><span data-stu-id="44e1f-134">sign-in times</span></span>

  - <span data-ttu-id="44e1f-135">登入成功或失敗</span><span class="sxs-lookup"><span data-stu-id="44e1f-135">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="44e1f-136">如何保護並將電子郵件功能還原到可疑的遭入侵 Office 365 帳戶和信箱</span><span class="sxs-lookup"><span data-stu-id="44e1f-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="44e1f-137">即使是在您重新取得帳戶的存取權之後，攻擊者可能已新增後門程式項目，使得攻擊者得以繼續控制該帳戶。</span><span class="sxs-lookup"><span data-stu-id="44e1f-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="44e1f-138">您必須執行下列所有步驟來重新取得帳戶的存取權，愈快愈好，以確保劫持者不會繼續控制您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="44e1f-138">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="44e1f-139">這些步驟可協助您移除劫持者可能已新增至您的帳戶的任何後門程式項目。</span><span class="sxs-lookup"><span data-stu-id="44e1f-139">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="44e1f-140">在您執行這些步驟之後，建議您執行病毒掃描，以確認您的電腦未遭入侵。</span><span class="sxs-lookup"><span data-stu-id="44e1f-140">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="44e1f-141">步驟 1 重設使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="44e1f-141">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="44e1f-142">請勿透過電子郵件傳送新密碼給預期的使用者，因為攻擊者此時仍可能對信箱具有存取權。</span><span class="sxs-lookup"><span data-stu-id="44e1f-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="44e1f-143">遵循[重設 Office 365 商務版密碼](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)中為其他人重設 Office 365 商務版密碼的程序</span><span class="sxs-lookup"><span data-stu-id="44e1f-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="44e1f-144">**附註**：</span><span class="sxs-lookup"><span data-stu-id="44e1f-144">**Notes**:</span></span>

- <span data-ttu-id="44e1f-145">請確定密碼為強式密碼，且包含大寫和小寫字母、至少一個數字，以及至少一個特殊字元。</span><span class="sxs-lookup"><span data-stu-id="44e1f-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="44e1f-146">請勿重複使用最後五個密碼。</span><span class="sxs-lookup"><span data-stu-id="44e1f-146">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="44e1f-147">即使密碼歷程記錄需求可讓您重複使用較新的密碼，您也應該選取攻擊者無法猜測的項目。</span><span class="sxs-lookup"><span data-stu-id="44e1f-147">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="44e1f-148">如果您的內部部署身分識別與 Office 365 同盟，則必須變更您的內部部署密碼，然後必須通知您的系統管理員相關入侵。</span><span class="sxs-lookup"><span data-stu-id="44e1f-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="44e1f-149">強烈建議您啟用多重要素驗證 (MFA)，以防止入侵，特別是具有系統管理權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="44e1f-149">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="44e1f-150">您可以在[這裡](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)深入了解。</span><span class="sxs-lookup"><span data-stu-id="44e1f-150">You can learn more [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="44e1f-151">步驟 2 移除可疑的電子郵件轉寄地址</span><span class="sxs-lookup"><span data-stu-id="44e1f-151">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="44e1f-152">開啟 [Microsoft 365 系統管理中心] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-152">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="44e1f-153">找出有問題的使用者帳戶，並展開 [郵件設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-153">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="44e1f-154">針對 [電子郵件轉寄]\*\*\*\*，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-154">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="44e1f-155">移除任何可疑的轉寄地址。</span><span class="sxs-lookup"><span data-stu-id="44e1f-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="44e1f-156">步驟 3 停用任何可疑的收件匣規則</span><span class="sxs-lookup"><span data-stu-id="44e1f-156">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="44e1f-157">使用 Outlook 網頁版登入使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="44e1f-157">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="44e1f-158">按一下齒輪圖示並按一下 [郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-158">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="44e1f-159">按一下 [收件匣和整理規則]\*\*\*\* 並檢閱規則。</span><span class="sxs-lookup"><span data-stu-id="44e1f-159">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="44e1f-160">停用或刪除可疑的規則。</span><span class="sxs-lookup"><span data-stu-id="44e1f-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="44e1f-161">步驟 4 解除封鎖使用者，使其可以傳送郵件</span><span class="sxs-lookup"><span data-stu-id="44e1f-161">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="44e1f-162">如果懷疑遭入侵的信箱被非法用來傳送垃圾郵件，則可能是該信箱已被封鎖無法傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="44e1f-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="44e1f-163">若要解除封鎖信箱，使其可以傳送郵件，請遵循[傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者](removing-user-from-restricted-users-portal-after-spam.md)中的程序。</span><span class="sxs-lookup"><span data-stu-id="44e1f-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="44e1f-164">步驟 5 選用：封鎖使用者帳戶，使其無法登入</span><span class="sxs-lookup"><span data-stu-id="44e1f-164">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44e1f-165">您可以封鎖懷疑遭入侵的帳戶，使該帳戶無法登入，直到您認為可以安全地重新啟用存取權為止。</span><span class="sxs-lookup"><span data-stu-id="44e1f-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="44e1f-166">移至 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="44e1f-166">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="44e1f-167">在 Microsoft 365 系統管理中心，選取 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-167">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="44e1f-168">選取要封鎖的員工，然後在使用者窗格中選擇 [登入狀態]\*\*\*\* 旁邊的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>

4. <span data-ttu-id="44e1f-169">在 [登入狀態]\*\*\*\* 窗格上，選擇 [封鎖登入]\*\*\*\*，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="44e1f-170">在系統管理中心的左下方瀏覽窗格中，展開 [系統管理中心]\*\*\*\*，然後選取 [Exchange]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-170">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="44e1f-171">在 Exchange 系統管理中心中，瀏覽到 [收件者] > [信箱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="44e1f-172">選取使用者，然後在使用者屬性頁面的 [行動裝置]\*\*\*\* 底下，按一下 [停用 Exchange ActiveSync]\*\*\*\* 和 [停用裝置用 OWA]\*\*\*\*，並且對這兩個選項都回答 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="44e1f-173">在 [電子郵件連線]\*\*\*\* 底下，按一下 [停用]\*\*\*\*，然後回答 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="44e1f-174">步驟 6 選用：從所有系統管理角色群組移除懷疑遭入侵的帳戶</span><span class="sxs-lookup"><span data-stu-id="44e1f-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="44e1f-175">保護的帳戶之後，就可以還原系統管理角色群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="44e1f-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="44e1f-176">使用全域系統管理員帳戶登入 Microsoft 365 系統管理中心，然後開啟 [作用中使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-176">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="44e1f-177">找出懷疑遭入侵的帳戶，並手動檢查以查看是否有對給該帳戶指派任何系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="44e1f-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="44e1f-178">開啟 [安全性與合規性中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-178">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="44e1f-179">按一下 [權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-179">Click **Permissions**.</span></span>

5. <span data-ttu-id="44e1f-180">手動檢查角色群組，以查看懷疑遭入侵的帳戶是否為任何群組的成員。</span><span class="sxs-lookup"><span data-stu-id="44e1f-180">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="44e1f-181">如果是：</span><span class="sxs-lookup"><span data-stu-id="44e1f-181">If it is: a.</span></span>

   <span data-ttu-id="44e1f-182">a.</span><span class="sxs-lookup"><span data-stu-id="44e1f-182">a.</span></span> <span data-ttu-id="44e1f-183">按一下角色群組，然後按一下 [編輯角色群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-183">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="44e1f-184">b.</span><span class="sxs-lookup"><span data-stu-id="44e1f-184">b.</span></span> <span data-ttu-id="44e1f-185">按一下 [選擇成員]\*\*\*\* 和 [編輯]\*\*\*\*，從角色群組移除使用者。</span><span class="sxs-lookup"><span data-stu-id="44e1f-185">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="44e1f-186">開啟 [Exchange 系統管理中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-186">Open the **Exchange admin center**</span></span>

7. <span data-ttu-id="44e1f-187">按一下 [權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-187">Click **Permissions**.</span></span>

8. <span data-ttu-id="44e1f-188">手動檢查角色群組，以查看懷疑遭入侵的帳戶是否為任何群組的成員。</span><span class="sxs-lookup"><span data-stu-id="44e1f-188">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="44e1f-189">如果是：</span><span class="sxs-lookup"><span data-stu-id="44e1f-189">If it is: a.</span></span>

   <span data-ttu-id="44e1f-190">a.</span><span class="sxs-lookup"><span data-stu-id="44e1f-190">a.</span></span> <span data-ttu-id="44e1f-191">按一下角色群組，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e1f-191">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="44e1f-192">b.</span><span class="sxs-lookup"><span data-stu-id="44e1f-192">b.</span></span> <span data-ttu-id="44e1f-193">使用 [成員]\*\*\*\* 區段，從角色群組移除該使用者。</span><span class="sxs-lookup"><span data-stu-id="44e1f-193">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="44e1f-194">步驟 7 選用：額外的預防步驟</span><span class="sxs-lookup"><span data-stu-id="44e1f-194">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="44e1f-195">務必確認您所傳送的項目。</span><span class="sxs-lookup"><span data-stu-id="44e1f-195">Make sure that you verify your sent items.</span></span> <span data-ttu-id="44e1f-196">您可能需要通知您的連絡人清單上的人員，您的帳戶已遭入侵。</span><span class="sxs-lookup"><span data-stu-id="44e1f-196">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="44e1f-197">攻擊者可能會要求他們給予金錢，比方說騙他們說您滯留在不同國家/地區因而缺錢，或是攻擊者也可能傳送病毒給他們來劫持電腦。</span><span class="sxs-lookup"><span data-stu-id="44e1f-197">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="44e1f-198">使用此 Exchange 帳戶作為其備用電子郵件帳戶的任何其他服務可能已遭入侵。</span><span class="sxs-lookup"><span data-stu-id="44e1f-198">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="44e1f-199">先為您的 Office 365 訂閱執行下列步驟，然後再為您的其他帳戶執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="44e1f-199">First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="44e1f-200">確認您的連絡資訊，例如電話號碼及地址，是正確的。</span><span class="sxs-lookup"><span data-stu-id="44e1f-200">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="44e1f-201">像網路安全專業人員一般保護 Office 365</span><span class="sxs-lookup"><span data-stu-id="44e1f-201">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="44e1f-202">您的 Office 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="44e1f-202">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="44e1f-203">使用 [Office 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高頂級順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Office 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="44e1f-203">Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="44e1f-204">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="44e1f-204">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="44e1f-205">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="44e1f-205">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="44e1f-206">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="44e1f-206">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="44e1f-207">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="44e1f-207">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="44e1f-208">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="44e1f-208">Beyond 90 days.</span></span> <span data-ttu-id="44e1f-209">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="44e1f-209">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="44e1f-210">另請參閱</span><span class="sxs-lookup"><span data-stu-id="44e1f-210">See also</span></span>

- [<span data-ttu-id="44e1f-211">偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊</span><span class="sxs-lookup"><span data-stu-id="44e1f-211">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="44e1f-212">網際網路犯罪客訴中心</span><span class="sxs-lookup"><span data-stu-id="44e1f-212">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="44e1f-213">美國證券交易委員會 -「網路釣魚」詐騙</span><span class="sxs-lookup"><span data-stu-id="44e1f-213">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="44e1f-214">若要直接向 Microsoft 和您的系統管理員檢舉垃圾郵件，[請使用檢舉訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="44e1f-214">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
