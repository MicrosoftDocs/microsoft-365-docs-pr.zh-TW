---
title: 傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
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
description: 如果使用者持續從 Office 365 傳送被歸類為垃圾郵件的電子郵件，使用者將遭到限制而無法再傳送任何郵件。
ms.openlocfilehash: 7d900e154e60b49b3fcfe63552b6ad3288adfc82
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871739"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="537bf-103">傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者</span><span class="sxs-lookup"><span data-stu-id="537bf-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="537bf-104">如果使用者持續從 Office 365 傳送被歸類為垃圾郵件的電子郵件，使用者將遭到限制而無法傳送任何電子郵件，但仍可以收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="537bf-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="537bf-105">使用者會列在服務中，做為錯誤的外寄寄件者，並將會收到未傳遞回報 (NDR)，指出：</span><span class="sxs-lookup"><span data-stu-id="537bf-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="537bf-106">「因為您不是認可的有效寄件者，所以無法傳遞您的郵件。</span><span class="sxs-lookup"><span data-stu-id="537bf-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="537bf-107">最有可能發生此狀況的原因是您的電子郵件地址有傳送垃圾郵件的嫌疑，因此系統已不允許此電子郵件地址傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="537bf-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="537bf-108">請連絡您的電子郵件系統管理員以取得協助。</span><span class="sxs-lookup"><span data-stu-id="537bf-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="537bf-109">遠端伺服器傳回「550 5.1.8 存取被拒，錯誤的外寄寄件者。」</span><span class="sxs-lookup"><span data-stu-id="537bf-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="537bf-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="537bf-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="537bf-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="537bf-111"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="537bf-112">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="537bf-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="537bf-113">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="537bf-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="537bf-114">若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主題中的＜反垃圾郵件＞項目。</span><span class="sxs-lookup"><span data-stu-id="537bf-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

<span data-ttu-id="537bf-115">下列程序也可以透過遠端 PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="537bf-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="537bf-116">使用 Get-BlockedSenderAddress Cmdlet 來取得受限制使用者的清單，以及使用 Remove-BlockedSenderAddress 來移除限制。</span><span class="sxs-lookup"><span data-stu-id="537bf-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="537bf-117">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="537bf-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="537bf-118">移除封鎖的 Office 365 電子郵件帳戶的限制</span><span class="sxs-lookup"><span data-stu-id="537bf-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="537bf-119">您可以在安全性與合規性中心 (SCC) 完成此工作。</span><span class="sxs-lookup"><span data-stu-id="537bf-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="537bf-120">如需 SCC 的詳細資訊，請[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="537bf-120">[Go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="537bf-121">您必須在**組織管理**或**安全性系統管理員**角色群組，才能執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="537bf-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="537bf-122">如需 SCC 角色群組的詳細資訊，請[移至安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="537bf-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="537bf-123">使用具備 Office 365 全域系統管理員權限的公司或學校帳戶登入 Office 365 安全性與合規性中心，並在左側清單中，展開 [威脅管理]\*\*\*\*，選擇 [檢閱]\*\*\*\*，然後選擇 [限制的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="537bf-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="537bf-124">若要直接前往安全性與合規性中心中的 [限制的使用者]\*\*\*\* 頁面 (先前稱為重要訊息中心)，請使用此 URL：> [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="537bf-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="537bf-125">此頁面會包含已遭封鎖而無法傳送電子郵件的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="537bf-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="537bf-126">尋找您想要移除限制的使用者，並選取 [解除封鎖]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="537bf-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="537bf-127">隨即會出現飛出視窗，內含帳戶的傳送受到限制的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="537bf-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="537bf-128">您必須逐一查看建議，以確保帳戶實際上遭到入侵時，您會採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="537bf-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="537bf-129">完成時，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="537bf-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="537bf-130">下一個畫面提供建議來協助避免未來的入侵。</span><span class="sxs-lookup"><span data-stu-id="537bf-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="537bf-131">啟用多重要素驗證 (MFA)，並變更密碼，是很好的防禦方式。</span><span class="sxs-lookup"><span data-stu-id="537bf-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="537bf-132">完成時按一下 [解除封鎖使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="537bf-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="537bf-133">按一下 [是]\*\*\*\* 以確認變更。</span><span class="sxs-lookup"><span data-stu-id="537bf-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="537bf-134">可能需要 30 分鐘以上的時間，才能移除限制。</span><span class="sxs-lookup"><span data-stu-id="537bf-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="537bf-135">確認發生此情況時系統管理員會收到警示</span><span class="sxs-lookup"><span data-stu-id="537bf-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="537bf-136">「無法傳送電子郵件的受限制使用者」警示以原則的形式於 [Office 365 安全性與合規性警示] 原則頁面下提供。</span><span class="sxs-lookup"><span data-stu-id="537bf-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="537bf-137">這原先是輸出垃圾郵件原則，但現在是 Office 365 警示平台的原生部分。</span><span class="sxs-lookup"><span data-stu-id="537bf-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="537bf-138">如需警示的詳細資訊，請移至[安全性與合規性中心的警示原則](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="537bf-138">Go to [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="537bf-139">若要讓警示運作，必須開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="537bf-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="537bf-140">如需詳細資訊，請參閱[開啟或關閉 Office 365 稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="537bf-140">See how to [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="537bf-141">此警示的原則是預設值，都每個 Office 365 租用戶都會隨附，因此不需要進行設定。</span><span class="sxs-lookup"><span data-stu-id="537bf-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="537bf-142">它會被視為高嚴重性警示，並且會每次使用者遭限制無法傳送郵件而引發警示時，寄送電子郵件給所設定的 TenantAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="537bf-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="537bf-143">系統管理員可以更新發生此警示所通知的群組，方法是移至警示，其位於 SCC 入口網站 > [警示] > [警示原則] > [使用者受限制無法傳送電子郵件]。</span><span class="sxs-lookup"><span data-stu-id="537bf-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="537bf-144">您可以編輯警示，以便：</span><span class="sxs-lookup"><span data-stu-id="537bf-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="537bf-145">開啟/關閉電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="537bf-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="537bf-146">傳送電子郵件給需要的收件者</span><span class="sxs-lookup"><span data-stu-id="537bf-146">Email the required recipients</span></span>
- <span data-ttu-id="537bf-147">限制您每天收到的通知</span><span class="sxs-lookup"><span data-stu-id="537bf-147">Limit the notifications you get per day</span></span>

## <a name="checking-for-and-removing-restrictions-using-powershell"></a><span data-ttu-id="537bf-148">使用 PowerShell 檢查並移除限制</span><span class="sxs-lookup"><span data-stu-id="537bf-148">Checking for and removing restrictions using PowerShell</span></span>
<span data-ttu-id="537bf-149">用於限制的使用者的 PowerShell 命令為：</span><span class="sxs-lookup"><span data-stu-id="537bf-149">The PowerShell commands for Restricted Users are:</span></span>
- <span data-ttu-id="537bf-150">`Get-BlockedSenderAddress`：執行可擷取受限制而無法傳送電子郵件的使用者清單</span><span class="sxs-lookup"><span data-stu-id="537bf-150">`Get-BlockedSenderAddress`: Run to retreive the list of users that are restricted from sending email</span></span>
- <span data-ttu-id="537bf-151">`Remove-BlockedSenderAddress`：執行可從限制中移除使用者</span><span class="sxs-lookup"><span data-stu-id="537bf-151">`Remove-BlockedSenderAddress`: Run to remove user(s) from being restricted</span></span>

## <a name="for-more-information"></a><span data-ttu-id="537bf-152">相關資訊</span><span class="sxs-lookup"><span data-stu-id="537bf-152">For more information</span></span>

[<span data-ttu-id="537bf-153">回應遭入侵的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="537bf-153">Responding to a compromised email account</span></span>](../../compliance/responding-to-a-compromised-email-account.md)

[<span data-ttu-id="537bf-154">了解「無法傳送電子郵件的受限制使用者」警示</span><span class="sxs-lookup"><span data-stu-id="537bf-154">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[<span data-ttu-id="537bf-155">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="537bf-155">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="537bf-156">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="537bf-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="537bf-157">安全性與合規性中心的警示原則</span><span class="sxs-lookup"><span data-stu-id="537bf-157">Alert policies in the Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
