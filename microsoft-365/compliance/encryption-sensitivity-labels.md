---
title: 使用敏感度標籤來套用加密以限制存取內容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。敏感度標籤可以使用加密來保護內容。
ms.openlocfilehash: ccbdc5651751c9ee83fa7791f1146108afe9492e
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43900727"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a><span data-ttu-id="8036c-104">使用敏感度標籤來套用加密以限制存取內容</span><span class="sxs-lookup"><span data-stu-id="8036c-104">Restrict access to content by using sensitivity labels to apply encryption</span></span> 

><span data-ttu-id="8036c-105">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8036c-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8036c-p102">當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。例如，使用敏感度標籤的加密設定，您可以保護內容，以便：</span><span class="sxs-lookup"><span data-stu-id="8036c-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="8036c-108">僅您組織內的使用者才能開啟機密文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-108">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="8036c-109">僅行銷部門中的使用者才能編輯和列印促銷公告文件或電子郵件，而您組織中的所有其他使用者則只能讀取它。</span><span class="sxs-lookup"><span data-stu-id="8036c-109">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="8036c-110">使用者無法轉寄電子郵件，或從中複製包含內部組織相關消息的資訊。</span><span class="sxs-lookup"><span data-stu-id="8036c-110">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="8036c-111">在指定日期之後，無法開啟傳送給商業夥伴的目前價格清單。</span><span class="sxs-lookup"><span data-stu-id="8036c-111">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="8036c-112">加密文件或電子郵件時，內容的存取會受到限制，以便：</span><span class="sxs-lookup"><span data-stu-id="8036c-112">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="8036c-113">只有標籤加密設定授權的使用者才能將其解密。</span><span class="sxs-lookup"><span data-stu-id="8036c-113">Can be decrypted only by users authorized by the label's encryption settings.</span></span>
- <span data-ttu-id="8036c-114">即使檔案重新命名，無論其位於您組織內部或外部，仍會保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="8036c-114">Remains encrypted no matter where it resides, inside or outside your organization, even if the file's renamed.</span></span>
- <span data-ttu-id="8036c-115">同時進行靜態加密 (例如，在 OneDrive 帳戶中) 及傳輸中加密 (例如，已傳送的電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="8036c-115">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="8036c-116">最後，身為系統管理員的您，在設定一個敏感度標籤來套用加密時，可以選擇以下兩者之一：</span><span class="sxs-lookup"><span data-stu-id="8036c-116">Finally, as an admin, when you configure a sensitivity label to apply encryption, you can choose either to:</span></span>

- <span data-ttu-id="8036c-117">**立即指派權限**，這樣您就能確實決定哪個使用者能夠存取該標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="8036c-117">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="8036c-118">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="8036c-118">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="8036c-119">如此一來，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="8036c-119">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="8036c-120">當您在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或是安全性與合規性中心中[建立敏感性標籤](create-sensitivity-labels.md)時，可以使用加密設定。</span><span class="sxs-lookup"><span data-stu-id="8036c-120">The encryption settings are available when you [create a sensitivity label](create-sensitivity-labels.md) in the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span>

## <a name="understand-how-the-encryption-works"></a><span data-ttu-id="8036c-121">了解加密的運作方式</span><span class="sxs-lookup"><span data-stu-id="8036c-121">Understand how the encryption works</span></span>

<span data-ttu-id="8036c-122">加密使用來自 Azure 資訊保護的 Azure 版權管理服務 (Azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="8036c-122">Encryption uses the Azure Rights Management service (Azure RMS) from Azure Information Protection.</span></span> <span data-ttu-id="8036c-123">此保護解決方案使用加密、身分識別及授權原則。</span><span class="sxs-lookup"><span data-stu-id="8036c-123">This protection solution uses encryption, identity, and authorization policies.</span></span> <span data-ttu-id="8036c-124">若要深入了解，請參閱 Azure 資訊保護文件中的[什麼是 Azure 版權管理？](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="8036c-124">To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) from the Azure Information Protection documentation.</span></span> 

<span data-ttu-id="8036c-125">使用此加密解決方案時，**超級使用者**功能可確保獲授權的人員和服務一律可以讀取和檢查已為組織加密的資料。</span><span class="sxs-lookup"><span data-stu-id="8036c-125">When you use this encryption solution, the **super user** feature ensures that authorized people and services can always read and inspect the data that has been encrypted for your organization.</span></span> <span data-ttu-id="8036c-126">如有需要，您可以接著將加密移除或變更。</span><span class="sxs-lookup"><span data-stu-id="8036c-126">If necessary, the encryption can then be removed or changed.</span></span> <span data-ttu-id="8036c-127">如需詳細資訊，請參閱[為 Azure 資訊保護和探索服務或資料復原設定超級使用者](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="8036c-127">For more information, see [Configuring super users for Azure Information Protection and discovery services or data recovery](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

## <a name="how-to-configure-a-label-for-encryption"></a><span data-ttu-id="8036c-128">如何設定用於加密的標籤</span><span class="sxs-lookup"><span data-stu-id="8036c-128">How to configure a label for encryption</span></span>

<span data-ttu-id="8036c-129">[建立或編輯敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，並在精靈的 [加密]\*\*\*\* 頁面上選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8036c-129">[Create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels), and on the **Encryption** page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="8036c-130">**無**：新標籤的預設設定。</span><span class="sxs-lookup"><span data-stu-id="8036c-130">**None**: The default setting for a new label.</span></span> <span data-ttu-id="8036c-131">不會套用新的加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-131">No new encryption is applied.</span></span>
- <span data-ttu-id="8036c-132">**套用**：開啟加密，然後指定加密設定。</span><span class="sxs-lookup"><span data-stu-id="8036c-132">**Apply**: Turns on encryption, and you then specify encryption settings.</span></span>
- <span data-ttu-id="8036c-133">**移除**：如果文件或電子郵件已加密，則會移除加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-133">**Remove**: Removes encryption if the document or email is encrypted.</span></span>

> [!NOTE]
> <span data-ttu-id="8036c-134">只有 Azure 資訊保護整合標籤用戶端才支援 [移除]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="8036c-134">The **Remove** option is supported by the Azure Information Protection unified labeling client only.</span></span> <span data-ttu-id="8036c-135">當您使用內建標籤時，具有此選項的標籤會在 Office 應用程式和服務中顯示，並且若已選取該選項，則加密行為會與 [無]\*\*\*\* 相同。</span><span class="sxs-lookup"><span data-stu-id="8036c-135">When you use built-in labeling, a label with this option is visible in Office apps and services and if selected, the encryption behavior is the same as **None**.</span></span>

<span data-ttu-id="8036c-136">設定加密選項：</span><span class="sxs-lookup"><span data-stu-id="8036c-136">Configuring the encryption options:</span></span>

![用於加密的敏感度標籤選項](../media/encrytion-options-sensitivity-label.png)


### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="8036c-138">套用標籤時，現有的加密會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="8036c-138">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="8036c-139">如果您將敏感度標籤套用到未加密的內容，您可以選取的加密選項結果會一目了然。</span><span class="sxs-lookup"><span data-stu-id="8036c-139">If a sensitivity label is applied to unencrypted content, the outcome of the encryption options you can select is self-explanatory.</span></span> <span data-ttu-id="8036c-140">例如，如果將加密設定為 [無]\*\*\*\*，則內容會保持未加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-140">For example, if encryption is set to **None**, the content remains unencrypted.</span></span>

<span data-ttu-id="8036c-141">不過，內容可能已加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-141">However, the content might be already encrypted.</span></span> <span data-ttu-id="8036c-142">例如，其他使用者可能已套用：</span><span class="sxs-lookup"><span data-stu-id="8036c-142">For example, another user might have applied:</span></span>

- <span data-ttu-id="8036c-143">其自己的權限，其中包括標籤提示時的使用者定義權限、Azure 資訊保護用戶端的自訂權限，以及來自 Office 應用程式內的**限制存取**文件保護。</span><span class="sxs-lookup"><span data-stu-id="8036c-143">Their own permissions, which include user-defined permissions when prompted by a label, custom permissions by the Azure Information Protection client, and the **Restricted Access** document protection from within an Office app.</span></span>
- <span data-ttu-id="8036c-144">Azure 版權管理保護範本可獨立於標籤將內容加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-144">An Azure Rights Management protection template that encrypts the content independently from a label.</span></span> <span data-ttu-id="8036c-145">此類別包括使用版權保護來套用加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="8036c-145">This category includes mail flow rules that apply encryption by using rights protection.</span></span>
- <span data-ttu-id="8036c-146">以系統管理員指派的權限套用加密的標籤。</span><span class="sxs-lookup"><span data-stu-id="8036c-146">A label that applies encryption with permissions assigned by the administrator.</span></span>

<span data-ttu-id="8036c-147">下表說明對該內容套用敏感度標籤時，現有的加密會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="8036c-147">The following table identifies what happens to existing encryption when a sensitivity label is applied to that content:</span></span>

| |<span data-ttu-id="8036c-148">**加密：無**</span><span class="sxs-lookup"><span data-stu-id="8036c-148">**Encryption: None**</span></span>|<span data-ttu-id="8036c-149">**加密：套用**</span><span class="sxs-lookup"><span data-stu-id="8036c-149">**Encryption: Apply**</span></span>|<span data-ttu-id="8036c-150">**加密：移除**</span><span class="sxs-lookup"><span data-stu-id="8036c-150">**Encryption: Remove**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8036c-151">**使用者指定的權限**</span><span class="sxs-lookup"><span data-stu-id="8036c-151">**Permissions specified by a user**</span></span>|<span data-ttu-id="8036c-152">原始加密已保留</span><span class="sxs-lookup"><span data-stu-id="8036c-152">Original encryption is preserved</span></span>|<span data-ttu-id="8036c-153">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="8036c-153">New label encryption is applied</span></span>|<span data-ttu-id="8036c-154">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="8036c-154">Original encryption is removed</span></span>|
|<span data-ttu-id="8036c-155">**保護範本**</span><span class="sxs-lookup"><span data-stu-id="8036c-155">**Protection template**</span></span>|<span data-ttu-id="8036c-156">原始加密已保留</span><span class="sxs-lookup"><span data-stu-id="8036c-156">Original encryption is preserved</span></span>|<span data-ttu-id="8036c-157">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="8036c-157">New label encryption is applied</span></span>|<span data-ttu-id="8036c-158">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="8036c-158">Original encryption is removed</span></span>|
|<span data-ttu-id="8036c-159">**具有系統管理員定義權限的標籤**</span><span class="sxs-lookup"><span data-stu-id="8036c-159">**Label with administator-defined permissions**</span></span>|<span data-ttu-id="8036c-160">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="8036c-160">Original encryption is removed</span></span>|<span data-ttu-id="8036c-161">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="8036c-161">New label encryption is applied</span></span>|<span data-ttu-id="8036c-162">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="8036c-162">Original encryption is removed</span></span>|

<span data-ttu-id="8036c-163">請注意，在套用新標籤加密或移除原始加密的情況下，只有在套用標籤的使用者有支援此動作的使用權利或角色時，才會發生這種情況：</span><span class="sxs-lookup"><span data-stu-id="8036c-163">Note that in the cases where the new label encryption is applied or the original encryption is removed, this happens only if the user applying the label has a usage right or role that supports this action:</span></span>
- <span data-ttu-id="8036c-164">[使用權限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)匯出或完全控制。</span><span class="sxs-lookup"><span data-stu-id="8036c-164">The [usage right](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export or Full Control.</span></span>
- <span data-ttu-id="8036c-165">[版權管理簽發者或版權管理擁有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)的角色，或[超級使用者](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="8036c-165">The role of [Rights Management issuer or Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), or [super user](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

<span data-ttu-id="8036c-166">如果使用者沒有這些權限或角色中的一個，就無法套用標籤，因此會保留原始加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-166">If the user doesn't have one of these rights or roles, the label can't be applied and so the original encryption is preserved.</span></span> <span data-ttu-id="8036c-167">使用者會看到下列訊息：**您沒有對敏感度標籤進行變更所需的權限。請連絡內容的擁有者。**</span><span class="sxs-lookup"><span data-stu-id="8036c-167">The user sees the following message: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.**</span></span>

<span data-ttu-id="8036c-168">例如，對電子郵件訊息套用 [不可轉寄] 的人員，可以將該對話重新標記，以取代加密或移除它，因為他們是該電子郵件的版權管理擁有者。</span><span class="sxs-lookup"><span data-stu-id="8036c-168">For example, the person who applies Do Not Forward to an email message can relabel the thread to replace the encryption or remove it, because they are the Rights Management owner for the email.</span></span> <span data-ttu-id="8036c-169">但除了超級使用者之外，此電子郵件的收件者無法重新標記它，因為他們沒有所需的使用權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-169">But with the exception of super users, recipients of this email can't relabel it because they don't have the required usage rights.</span></span>

#### <a name="email-attachments-for-encrypted-email-messages"></a><span data-ttu-id="8036c-170">已加密電子郵件的電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="8036c-170">Email attachments for encrypted email messages</span></span>

<span data-ttu-id="8036c-171">當電子郵件以任何方法加密時，任何附加至電子郵件的未加密 Office 文件都會自動繼承相同的加密設定。</span><span class="sxs-lookup"><span data-stu-id="8036c-171">When an email message is encrypted by any method, any unencrypted Office documents that are attached to the email automatically inherit the same encryption settings.</span></span>

<span data-ttu-id="8036c-172">已加密然後新增為附件的文件，一律會保留其原始加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-172">Documents that are already encrypted and then added as attachments always preserve their original encryption.</span></span> 

## <a name="configure-encryption-settings"></a><span data-ttu-id="8036c-173">設定加密設定</span><span class="sxs-lookup"><span data-stu-id="8036c-173">Configure encryption settings</span></span>

<span data-ttu-id="8036c-174">當您在精靈的 [加密]\*\*\*\* 頁面上選取 [套用]\*\*\*\* 來建立或編輯敏感度標籤時，請選擇是否要：</span><span class="sxs-lookup"><span data-stu-id="8036c-174">When you select **Apply** on the **Encryption** page of the wizard to create or edit a sensitivity label, choose whether to:</span></span>

- <span data-ttu-id="8036c-175">**立即指派權限**，這樣您就能決定哪些使用者確切能取得已套用標籤內容的權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-175">**Assign permissions now**, so that you can determine exactly which users get which permissions to content that has the label applied.</span></span> <span data-ttu-id="8036c-176">如需詳細資訊，請參閱下一節的[立即指派權限](#assign-permissions-now)。</span><span class="sxs-lookup"><span data-stu-id="8036c-176">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="8036c-177">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="8036c-177">**Let users assign permissions** when your users apply the label to content.</span></span> <span data-ttu-id="8036c-178">利用此選項，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="8036c-178">With this option, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="8036c-179">如需詳細資訊，請本頁的[讓使用者指派權限](#let-users-assign-permissions)章節。</span><span class="sxs-lookup"><span data-stu-id="8036c-179">For more information, see the [Let users assign permissions](#let-users-assign-permissions) section on this page.</span></span>

<span data-ttu-id="8036c-180">例如，如果您有一個名為 [高度機密] \*\*\*\* 的敏感度標籤，該標籤將套用至最敏感的內容，則您可能會希望立即決定誰能取得該內容的何種權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-180">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you might want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="8036c-181">或者，如果您有一個名為 [商業合約]\*\*\*\* 的敏感度標籤，並且貴組織的工作流程要求人員隨機與不同人員共同處理此內容，則您可能會希望讓使用者在指派標籤時決定可存取的人員。</span><span class="sxs-lookup"><span data-stu-id="8036c-181">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you might want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="8036c-182">這種靈活性既可以幫助您提高使用者的工作效率，又可以減少管理員更新或建立新敏感度標籤以滿足特定案例的要求。</span><span class="sxs-lookup"><span data-stu-id="8036c-182">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

<span data-ttu-id="8036c-183">選擇 [立即指派權限] 或 [讓使用者指派權限]：</span><span class="sxs-lookup"><span data-stu-id="8036c-183">Choosing whether to assign permissions now or let users assign permissions:</span></span> 

![新增使用者或系統管理員定義權限的選項](../media/sensitivity-label-user-or-admin-defined-permissions.png)


## <a name="assign-permissions-now"></a><span data-ttu-id="8036c-185">立即指派權限</span><span class="sxs-lookup"><span data-stu-id="8036c-185">Assign permissions now</span></span>

<span data-ttu-id="8036c-186">使用下列選項來控制誰可以存取套用此標籤的電子郵件或文件。</span><span class="sxs-lookup"><span data-stu-id="8036c-186">Use the following options to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="8036c-187">您可以：</span><span class="sxs-lookup"><span data-stu-id="8036c-187">You can:</span></span>

1. <span data-ttu-id="8036c-p117">在特定日期，或是在套用標籤之後的特定天數之後**允許具有標籤的內容的存取權到期**。在此時間後，使用者將無法開啟具有標籤的項目。如果指定日期，則會在目前時區中，該日期的午夜開始生效。(請注意，某些電子郵件用戶端可能因為其快取機制而無法強制執行到期，而顯示超過期限的電子郵件。)</span><span class="sxs-lookup"><span data-stu-id="8036c-p117">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won't be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients might not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

2. <span data-ttu-id="8036c-p118">在套用標籤之後**允許離線存取**可為從不、一律或特定天數。如果您將離線存取限制為從不或天數，則達到該閾值時，必須重新驗證使用者，並記錄其存取。如需詳細資訊，請參閱關於 Rights Management 使用授權的下一節。</span><span class="sxs-lookup"><span data-stu-id="8036c-p118">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

<span data-ttu-id="8036c-195">已加密內容的存取控制設定：</span><span class="sxs-lookup"><span data-stu-id="8036c-195">Settings for access control for encrypted content:</span></span>

![系統管理員定義權限的設定](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="8036c-197">用於離線存取的 Rights Management 使用授權</span><span class="sxs-lookup"><span data-stu-id="8036c-197">Rights Management use license for offline access</span></span>

<span data-ttu-id="8036c-198">當使用者開啟以來自 Azure Rights Management 服務的加密保護的文件或電子郵件時，Azure Rights Management 會將該內容的使用授權授與給該使用者。</span><span class="sxs-lookup"><span data-stu-id="8036c-198">When a user opens a document or email that's been protected by encryption from the Azure Rights Management service, an Azure Rights Management use license for that content is granted to the user.</span></span> <span data-ttu-id="8036c-199">使用授權是一項憑證，其中包含使用者對於文件或電子郵件使用權限，以及用來加密內容的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="8036c-199">This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content.</span></span> <span data-ttu-id="8036c-200">如果已設定，則使用授權也會包含到期日，以及該使用授權的有效期。</span><span class="sxs-lookup"><span data-stu-id="8036c-200">The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="8036c-p120">如果未設定到期日，則租用戶的預設使用授權有效期間為 30 天。在這段期間，不會針對內容重新驗證或重新授權使用者。這個程序可讓使用者在沒有網際網路連線的情況下繼續開啟受保護文件或電子郵件。使用授權有效期間到期時，下次使用者存取受保護文件或電子郵件時，則必須重新驗證和重新授權使用者。</span><span class="sxs-lookup"><span data-stu-id="8036c-p120">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This process lets the user continue to open the protected document or email without an internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="8036c-205">除了重新驗證外，還會重新評估原則和使用者群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="8036c-205">In addition to reauthentication, the encryption settings and user group membership is reevaluated.</span></span> <span data-ttu-id="8036c-206">這表示，如果上次使用者存取內容後，加密設定或群組成員資格發生變更，則這些使用者可能遇到相同的文件或電子郵件，卻有不同的存取結果。</span><span class="sxs-lookup"><span data-stu-id="8036c-206">This means that users could experience different access results for the same document or email if there are changes in the encryption settings or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="8036c-207">若要了解如何變更預設的 30 天設定，請參閱 [Rights Management 使用授權](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="8036c-207">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="8036c-208">將權限指派給特定使用者或群組</span><span class="sxs-lookup"><span data-stu-id="8036c-208">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="8036c-209">您可以將權限授與特定人員，以便只有他們可與標籤內容互動：</span><span class="sxs-lookup"><span data-stu-id="8036c-209">You can grant permissions to specific people so that only they can interact with the labeled content:</span></span>

1. <span data-ttu-id="8036c-210">首先，新增將獲指派標籤內容之權限的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="8036c-210">First, add users or groups that will be assigned permissions to the labeled content.</span></span>

2. <span data-ttu-id="8036c-211">接著，選擇那些使用者應對標籤內容具有的權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-211">Then, choose which permissions those users should have for the labeled content.</span></span>

<span data-ttu-id="8036c-212">指派權限：</span><span class="sxs-lookup"><span data-stu-id="8036c-212">Assigning permissions:</span></span>

![將權限指派給使用者的選項](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="8036c-214">新增使用者或群組</span><span class="sxs-lookup"><span data-stu-id="8036c-214">Add users or groups</span></span>

<span data-ttu-id="8036c-215">指派權限時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="8036c-215">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="8036c-p122">組織中的所有人 (所有租用戶成員)。此設定會排除來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="8036c-p122">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>

- <span data-ttu-id="8036c-218">任何已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="8036c-218">Any authenticated users.</span></span> <span data-ttu-id="8036c-219">選取此選項之前，請先確認您了解此設定的[需求與限制](#requirements-and-limitations-for-add-any-authenticated-users)。</span><span class="sxs-lookup"><span data-stu-id="8036c-219">Make sure you understand the [requirements and limitations](#requirements-and-limitations-for-add-any-authenticated-users) of this setting before selecting it.</span></span>

- <span data-ttu-id="8036c-220">Azure AD 中特定使用者或啟用電子郵件功能的安全性群組、通訊群組或 Microsoft 365 群組 ([先前的 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))。</span><span class="sxs-lookup"><span data-stu-id="8036c-220">Any specific user or email-enabled security group, distribution group, or Microsoft 365 group ([formerly Office 365 group](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) in Azure AD.</span></span> <span data-ttu-id="8036c-221">Microsoft 365 群組可以有靜態或[動態的成員資格](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)。</span><span class="sxs-lookup"><span data-stu-id="8036c-221">The Microsoft 365 group can have static or [dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="8036c-222">請注意，您無法使用 [Exchange 的 動態通訊群組](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups?view=exchserver-2019) (部分機器翻譯)，因為此群組類型不會同步處理到 Azure AD，且您無法使用未啟用電子郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="8036c-222">Note that you can't use a [dynamic distribution group from Exchange](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups?view=exchserver-2019) because this group type isn't synchronized to Azure AD, and you can't use a security group that isn't email-enabled.</span></span>

- <span data-ttu-id="8036c-223">任何電子郵件地址或網域。</span><span class="sxs-lookup"><span data-stu-id="8036c-223">Any email address or domain.</span></span> <span data-ttu-id="8036c-224">使用此選項來指定另一個組織中使用 Azure AD 的所有使用者，方法是輸入來自該組織的任何網域名稱。</span><span class="sxs-lookup"><span data-stu-id="8036c-224">Use this option to specify all users in another organization who uses Azure AD, by entering any domain name from that organization.</span></span> <span data-ttu-id="8036c-225">您也可以針對社交提供者使用此選項，方法是輸入其網域名稱，例如 **gmail.com**、**hotmail.com** 或 **outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="8036c-225">You can also use this option for social providers, by entering their domain name such as **gmail.com**, **hotmail.com**, or **outlook.com**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8036c-226">如果您指定的網域來自使用 Azure AD 的組織，則無法限制對該特定網域的存取。</span><span class="sxs-lookup"><span data-stu-id="8036c-226">If you specify a domain from an organization that uses Azure AD, you can't restrict access to that specific domain.</span></span> <span data-ttu-id="8036c-227">相反地，系統會為擁有您指定網域名稱的租用戶自動包含 Azure AD 中的所有經驗證網域。</span><span class="sxs-lookup"><span data-stu-id="8036c-227">Instead, all verified domains in Azure AD are automatically included for the tenant that owns the domain name you specify.</span></span>

<span data-ttu-id="8036c-228">當您選擇所有租用戶成員或瀏覽目錄時，使用者或群組必須具有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8036c-228">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="8036c-p127">最佳做法是使用群組，而非使用者。此策略可讓您保持更簡單的組態。</span><span class="sxs-lookup"><span data-stu-id="8036c-p127">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a><span data-ttu-id="8036c-231">**新增任何已驗證使用者**的需求與限制</span><span class="sxs-lookup"><span data-stu-id="8036c-231">Requirements and limitations for **Add any authenticated users**</span></span>

<span data-ttu-id="8036c-232">此設定不會限制能夠存取標籤所加密內容的人員，同時仍會加密內容，並提供限制內容使用方式 (權限) 和存取方式 (到期和離線存取) 的選項。</span><span class="sxs-lookup"><span data-stu-id="8036c-232">This setting doesn't restrict who can access the content that the label encrypts, while still encrypting the content and providing you with options to restrict how the content can be used (permissions), and accessed (expiry and offline access).</span></span> <span data-ttu-id="8036c-233">不過，開啟加密內容的應用程式必須能夠支援所使用的驗證。</span><span class="sxs-lookup"><span data-stu-id="8036c-233">However, the application opening the encrypted content must be able to support the authentication being used.</span></span> <span data-ttu-id="8036c-234">因此，同盟社交提供者 (例如 Google) 和一次性密碼驗證僅對電子郵件有效，且僅在您使用 Exchange Online 時才有效。</span><span class="sxs-lookup"><span data-stu-id="8036c-234">For this reason, federated social providers such as Google, and onetime passcode authentication work for email only, and only when you use Exchange Online.</span></span> <span data-ttu-id="8036c-235">您可以將 Microsoft 帳戶與 Office 365 應用程式和 [Azure 資訊保護檢視器](https://portal.azurerms.com/#/download)搭配使用。</span><span class="sxs-lookup"><span data-stu-id="8036c-235">Microsoft accounts can be used with Office 365 apps and the [Azure Information Protection viewer](https://portal.azurerms.com/#/download).</span></span>

<span data-ttu-id="8036c-236">任何已驗證使用者設定的一些典型案例如下：</span><span class="sxs-lookup"><span data-stu-id="8036c-236">Some typical scenarios for the any authenticated users setting:</span></span>
- <span data-ttu-id="8036c-237">您不在意檢視內容的是誰，但想要限制其使用方式。</span><span class="sxs-lookup"><span data-stu-id="8036c-237">You don't mind who views the content, but you want to restrict how it is used.</span></span> <span data-ttu-id="8036c-238">例如，您不希望編輯、複製或列印內容。</span><span class="sxs-lookup"><span data-stu-id="8036c-238">For example, you don't want the content to be edited, copied, or printed.</span></span>
- <span data-ttu-id="8036c-239">您不需要限制存取內容的是誰，但想要能夠確認誰開啟了該內容。</span><span class="sxs-lookup"><span data-stu-id="8036c-239">You don't need to restrict who accesses the content, but you want to be able to confirm who opens it.</span></span>
- <span data-ttu-id="8036c-240">您必須將靜態內容和在傳輸中的內容加密，但不要求存取控制。</span><span class="sxs-lookup"><span data-stu-id="8036c-240">You have a requirement that the content must be encrypted at rest and in transit, but it doesn't require access controls.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="8036c-241">選擇權限</span><span class="sxs-lookup"><span data-stu-id="8036c-241">Choose permissions</span></span>

<span data-ttu-id="8036c-242">當您選擇要對那些使用者或群組允許的權限時，您可以選取下列任一項：</span><span class="sxs-lookup"><span data-stu-id="8036c-242">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="8036c-243">[預先定義的權限層級](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，其中有一組預設的權限，例如共同作者或檢閱者。</span><span class="sxs-lookup"><span data-stu-id="8036c-243">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="8036c-244">自訂權限，您可在此選擇一或多個使用權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-244">Custom permissions, where you choose one or more usage rights.</span></span>

<span data-ttu-id="8036c-245">如需可協助您選取適當權限的詳細資訊，請參閱[使用權限和描述](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="8036c-245">For more information to help you select the appropriate permissions, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![選擇預設或自訂權限的選項](../media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="8036c-p130">請注意，相同標籤可將不同的權限授與不同的使用者。例如，單一標籤可將某些使用者指派為檢閱者，並將不同的使用者指派為共同作者，如以下螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="8036c-p130">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown in the following screenshot.</span></span>

<span data-ttu-id="8036c-p131">若要這麼做，請新增使用者或群組、將權限指派給他們，並儲存這些設定。然後，重複這些步驟、新增使用者並將權限指派給他們，每次完成後儲存設定。您可以視需要經常重複此設定，為不同的使用者定義不同的權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-p131">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can repeat this configuration as often as necessary, to define different permissions for different users.</span></span>

![具有不同權限的不同使用者](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="8036c-253">Rights Management 簽發者 (套用敏感度標籤的使用者) 一律具有完全控制權</span><span class="sxs-lookup"><span data-stu-id="8036c-253">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="8036c-254">敏感度標籤的加密使用來自 Azure 資訊保護的 Azure 版權管理服務。</span><span class="sxs-lookup"><span data-stu-id="8036c-254">Encryption for a sensitivity label uses the Azure Rights Management service from Azure Information Protection.</span></span> <span data-ttu-id="8036c-255">當使用者套用敏感度標籤以使用加密保護文件或電子郵件時，該使用者就會變成該內容的版權管理簽發者。</span><span class="sxs-lookup"><span data-stu-id="8036c-255">When a user applies a sensitivity label to protect a document or email by using encryption, that user becomes the Rights Management issuer for that content.</span></span>

<span data-ttu-id="8036c-256">版權管理簽發者一律會被授與文件或電子郵件的完全控制權限，此外：</span><span class="sxs-lookup"><span data-stu-id="8036c-256">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="8036c-257">如果加密設定包括到期日，則版權管理簽發者仍然可在該日期之後開啟和編輯文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-257">If the encryption settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="8036c-258">Rights Management 簽發者一律可以離線存取文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-258">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="8036c-259">Rights Management 簽發者仍可以開啟撤銷後的文件。</span><span class="sxs-lookup"><span data-stu-id="8036c-259">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="8036c-260">如需詳細資訊，請參閱 [Rights Management 簽發者和 Rights Management 擁有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="8036c-260">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="8036c-261">讓使用者指派權限</span><span class="sxs-lookup"><span data-stu-id="8036c-261">Let users assign permissions</span></span>

<span data-ttu-id="8036c-262">您可以使用這些選項讓使用者在手動將敏感度標籤套用至內容時指派權限：</span><span class="sxs-lookup"><span data-stu-id="8036c-262">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="8036c-263">在 Outlook 中，使用者可以針對所選的收件者選取等同於[不可轉寄](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails)選項的限制。</span><span class="sxs-lookup"><span data-stu-id="8036c-263">In Outlook, a user can select restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option for their chosen recipients.</span></span>

- <span data-ttu-id="8036c-264">在 Word、PowerPoint 和 Excel 中，系統會提示使用者為特定使用者、群組或組織選取其自己的權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-264">In Word, PowerPoint, and Excel, a user is prompted to select their own permissions for specific users, groups, or organizations.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="8036c-265">適用於 Word、PowerPoint 和 Excel 的此選項，是由 Azure 資訊保護整合標籤用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="8036c-265">This option for Word, PowerPoint, and Excel is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="8036c-266">針對使用內建標籤的應用程式，目前在 [Windows 版和 Mac 版預覽](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)中都提供支援。</span><span class="sxs-lookup"><span data-stu-id="8036c-266">For apps that use built-in labeling, support is currently in [preview for Windows and Mac](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span></span> 
    > 
    > <span data-ttu-id="8036c-267">如果已選取此選項，但使用者的應用程式不支援此選項，表示該標籤未顯示給使用者，或 (目前正在 iOS 和 Android 版預覽中推出) 為求一致，系統會顯示標籤，但無法在套用時為使用者提供說明訊息。</span><span class="sxs-lookup"><span data-stu-id="8036c-267">If this option is selected but isn't supported for a user's app, either that label doesn't display to the user, or (currently rolling out in preview for iOS and Android) the label displays for consistency, but it can't be applied with an explanation message to users.</span></span>

<span data-ttu-id="8036c-268">支援這些選項時，請使用下表來識別使用者何時可看到敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="8036c-268">When the options are supported, use the following table to identify when users see the sensitivity label:</span></span>

|<span data-ttu-id="8036c-269">設定</span><span class="sxs-lookup"><span data-stu-id="8036c-269">Setting</span></span> |<span data-ttu-id="8036c-270">標籤在 Outlook 中顯示</span><span class="sxs-lookup"><span data-stu-id="8036c-270">Label visible in Outlook</span></span>|<span data-ttu-id="8036c-271">標籤在 Word、Excel、PowerPoint 中顯示</span><span class="sxs-lookup"><span data-stu-id="8036c-271">Label visible in Word, Excel, PowerPoint</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8036c-272">**在 Outlook 中，強制執行限制等同於 [不可轉寄] 選項**</span><span class="sxs-lookup"><span data-stu-id="8036c-272">**In Outlook, enforce restrictions equivalent to the Do Not Forward option**</span></span>|<span data-ttu-id="8036c-273">是</span><span class="sxs-lookup"><span data-stu-id="8036c-273">Yes</span></span> |<span data-ttu-id="8036c-274">否</span><span class="sxs-lookup"><span data-stu-id="8036c-274">No</span></span> |
|<span data-ttu-id="8036c-275">**在 Word、PowerPoint 與 Excel 中提示使用者指定權限**</span><span class="sxs-lookup"><span data-stu-id="8036c-275">**In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>|<span data-ttu-id="8036c-276">否</span><span class="sxs-lookup"><span data-stu-id="8036c-276">No</span></span> |<span data-ttu-id="8036c-277">是</span><span class="sxs-lookup"><span data-stu-id="8036c-277">Yes</span></span>|

<span data-ttu-id="8036c-278">同時選取這兩個設定時，標籤會因此同時在 Outlook 和 Word、Excel 和 PowerPoint 中顯示。</span><span class="sxs-lookup"><span data-stu-id="8036c-278">When both settings are selected, the label is therefore visible in both Outlook and in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="8036c-279">可讓使用者指派權限的敏感度標籤只能透過使用者手動來套用至內容；它不能自動套用，也不能作為推薦標籤。</span><span class="sxs-lookup"><span data-stu-id="8036c-279">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

<span data-ttu-id="8036c-280">設定使用者指派的權限：</span><span class="sxs-lookup"><span data-stu-id="8036c-280">Configuring the user-assigned permissions:</span></span>

![使用者定義權限的加密設定](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="8036c-282">Outlook 限制</span><span class="sxs-lookup"><span data-stu-id="8036c-282">Outlook restrictions</span></span>

<span data-ttu-id="8036c-283">在 Outlook 中，當使用者套用的敏感標籤可允許他們指派郵件的權限時，限制與 [不可轉寄] 選項相同。</span><span class="sxs-lookup"><span data-stu-id="8036c-283">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="8036c-284">使用者會在郵件頂端看到標籤名稱和描述，指出內容已受到保護。</span><span class="sxs-lookup"><span data-stu-id="8036c-284">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="8036c-285">與 Word、PowerPoint 和 Excel 不同的是 (請參閱[下一節](#word-powerpoint-and-excel-permissions))，使用者不會收到選取特定權限的提示。</span><span class="sxs-lookup"><span data-stu-id="8036c-285">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![套用至 Outlook 郵件的敏感度標籤](../media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="8036c-287">將 [不可轉寄] 選項套用到電子郵件時，電子郵件會加密而且收件者必須經過驗證。</span><span class="sxs-lookup"><span data-stu-id="8036c-287">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="8036c-288">收件者無法轉寄、列印或複製該電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-288">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="8036c-289">例如，在 Outlook 用戶端中，無法使用 [轉寄] 按鈕、[另存新檔] 和 [列印] 功能表選項，且您無法在 [收件人]、[副本] 或 [密件副本] 方塊中新增或變更收件者。</span><span class="sxs-lookup"><span data-stu-id="8036c-289">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="8036c-290">附加到電子郵件的未加密 Office 文件會自動繼承相同的限制。</span><span class="sxs-lookup"><span data-stu-id="8036c-290">Unencrypted Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="8036c-291">套用至這些文件的使用權限是 [編輯內容]、[編輯]；[儲存]；[檢視]、[開啟]、[讀取]；和 [允許巨集]。</span><span class="sxs-lookup"><span data-stu-id="8036c-291">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="8036c-292">如果使用者想要不同的附件使用權限，或者附件不是支援此繼承保護的 Office 文件，則使用者需要在將文件附加到電子郵件之前保護該檔案。</span><span class="sxs-lookup"><span data-stu-id="8036c-292">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="8036c-293">Word、PowerPoint 和 Excel 權限</span><span class="sxs-lookup"><span data-stu-id="8036c-293">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="8036c-294">在 Word、PowerPoint 和 Excel 中，當使用者套用可讓他們對文件指派權限的敏感度標籤時，系統會提示他們指定套用加密時的所選使用者和權限。</span><span class="sxs-lookup"><span data-stu-id="8036c-294">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to specify their choice of users and permissions when the encryption is applied.</span></span>

<span data-ttu-id="8036c-295">例如，利用 Azure 資訊保護整合標籤用戶端，使用者可以：</span><span class="sxs-lookup"><span data-stu-id="8036c-295">For example, with the Azure Information Protection unified labeling client, users can:</span></span>

- <span data-ttu-id="8036c-296">選取權限等級，例如檢視者 (指派 [僅檢視] 權限) 或共同作者 (指派 [檢視]、[編輯]、[複製] 和 [列印] 權限)。</span><span class="sxs-lookup"><span data-stu-id="8036c-296">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="8036c-297">選取使用者、群組或組織。</span><span class="sxs-lookup"><span data-stu-id="8036c-297">Select users, groups, or organizations.</span></span> <span data-ttu-id="8036c-298">這可能包括組織內部或外部的人員。</span><span class="sxs-lookup"><span data-stu-id="8036c-298">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="8036c-299">設定到期日，到期之後所選使用者就無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="8036c-299">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="8036c-300">如需詳細資訊, 請參閱前一節的[用於離線存取的 Rights Management 使用授權](#rights-management-use-license-for-offline-access)。</span><span class="sxs-lookup"><span data-stu-id="8036c-300">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![讓使用者以自訂權限進行保護的選項](../media/sensitivity-aip-custom-permissions-dialog.png)

<span data-ttu-id="8036c-302">針對內建標籤，使用者會在選取下列項目時看到相同的對話方塊：</span><span class="sxs-lookup"><span data-stu-id="8036c-302">For built-in labeling, users see the same dialog box if they select the following:</span></span>

- <span data-ttu-id="8036c-303">Windows：[檔案]\*\*\*\* 索引標籤 > [資訊]\*\*\*\*  >  [保護文件]\*\*\*\*  >  [限制存取]\*\*\*\*  >  [限制存取]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8036c-303">Windows: **File** tab > **Info** > **Protect Document** > **Restrict Access** > **Restricted Access**</span></span>

- <span data-ttu-id="8036c-304">MacOS：[校閱]\*\*\*\* 索引標籤 > [保護]\*\*\*\*  >  [權限]\*\*\*\*  >  [限制存取]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8036c-304">MacOS: **Review** tab > **Protection** > **Permissions** > **Restricted Access**</span></span>


## <a name="example-configurations-for-the-encryption-settings"></a><span data-ttu-id="8036c-305">加密設定的範例組態</span><span class="sxs-lookup"><span data-stu-id="8036c-305">Example configurations for the encryption settings</span></span>

<span data-ttu-id="8036c-306">針對後續的各個範例，當您[建立或編輯敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)時，請從精靈的 **[加密]** 頁面執行組態。</span><span class="sxs-lookup"><span data-stu-id="8036c-306">For each example that follows, do the configuration from the **Encryption** page of the wizard when you [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span> <span data-ttu-id="8036c-307">首先，請確認 **[加密]** 設定為 **[套用]**：</span><span class="sxs-lookup"><span data-stu-id="8036c-307">First make sure that the **Encryption** is set to **Apply**:</span></span>

![敏感度標籤精靈中的套用加密選項](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a><span data-ttu-id="8036c-309">範例 1：套用 [不可轉寄] 標籤，以傳送加密的電子郵件傳送至 Gmail 帳戶</span><span class="sxs-lookup"><span data-stu-id="8036c-309">Example 1: Label that applies Do Not Forward to send an encrypted email to a Gmail account</span></span>

<span data-ttu-id="8036c-310">此標籤只會在 Outlook 和 Outlook 網頁版中顯示，因此您必須使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="8036c-310">This label displays only in Outlook and Outlook on the web, and you must use Exchange Online.</span></span> <span data-ttu-id="8036c-311">當使用者需要傳送加密的電子郵件給使用 Gmail 帳戶 (或您組織外部的任何其他電子郵件帳戶)的人員時，指示使用者選取此標籤。</span><span class="sxs-lookup"><span data-stu-id="8036c-311">Instruct users to select this label when they need to send an encrypted email to people using a Gmail account (or any other email account outside your organization).</span></span> 

<span data-ttu-id="8036c-312">您的使用者在 **[收件者]** 方塊中輸入 Gmail 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8036c-312">Your users type the Gmail email address in the **To** box.</span></span>  <span data-ttu-id="8036c-313">然後選取標籤，而 [不可轉寄] 選項會自動新增至電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="8036c-313">Then, they select the label and the Do Not Forward option is automatically added to the email.</span></span> <span data-ttu-id="8036c-314">結果會是收件者無法轉寄電子郵件、列印它、複製其內容，或使用 **[另存新檔]** 選項將電子郵件儲存在信箱外部。</span><span class="sxs-lookup"><span data-stu-id="8036c-314">The result is that recipients cannot forward the email, or print it, copy from it, or save the email outside their mailbox by using the **Save As** option.</span></span> 

1. <span data-ttu-id="8036c-315">在 **[加密]** 頁面上：針對 **[立即指派權限，或讓使用者決定?]**，選取 **[當使用者套用標籤時，讓他們指派權限]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-315">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Let users assign permissions when they apply the label**.</span></span>

3. <span data-ttu-id="8036c-316">選取核取方塊：**[在 Outlook 中，強制限制等於 [不可轉寄] 選項]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-316">Select the checkbox: **In Outlook, enforce restrictions equivalent to the Do Not Forward option**.</span></span>

4. <span data-ttu-id="8036c-317">如果已選取，請清除此核取方塊：**[在 Word、PowerPoint 與 Excel 中提示使用者指定權限]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-317">If selected, clear the checkbox: **In Word, PowerPoint, and Excel, prompt users to specify permissions**.</span></span>

5. <span data-ttu-id="8036c-318">選取 **[下一步]** 並完成精靈。</span><span class="sxs-lookup"><span data-stu-id="8036c-318">Select **Next** and complete the wizard.</span></span>


### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a><span data-ttu-id="8036c-319">範例 2：會對其他組織中的所有使用者限制唯讀權限的標籤</span><span class="sxs-lookup"><span data-stu-id="8036c-319">Example 2: Label that restricts read-only permission to all users in another organization</span></span>

<span data-ttu-id="8036c-320">此標籤適用於以唯讀方式共用的非常敏感文件，以及一律需要網際網路連線才能檢視的文件。</span><span class="sxs-lookup"><span data-stu-id="8036c-320">This label is suitable for sharing very sensitive documents as read-only, and the documents always require an internet connection to view them.</span></span>

<span data-ttu-id="8036c-321">此標籤不適合用於電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-321">This label is not suitable for emails.</span></span>

1. <span data-ttu-id="8036c-322">在 **[加密]** 頁面上：針對 **[立即指派權限，或讓使用者決定?]**，選取 **[立即指派權限]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-322">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Assign permissions now**.</span></span>

3. <span data-ttu-id="8036c-323">針對 **[允許離線存取]**，選取 **[從不]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-323">For **Allow offline access**, select **Never**.</span></span>

4. <span data-ttu-id="8036c-324">選取 [指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-324">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="8036c-325">在 **[指派權限]** 窗格中，選取 **[新增這些電子郵件地址或網域]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-325">On the **Assign permissions** pane, select **Add these email address or domains**.</span></span>

4. <span data-ttu-id="8036c-326">在文字方塊中，輸入來自另一個組織的網域名稱，例如，**fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="8036c-326">In the text box, enter the name of a domain from the other organization, for example, **fabrikam.com**.</span></span> <span data-ttu-id="8036c-327">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-327">Then select **Add**.</span></span>

5. <span data-ttu-id="8036c-328">選取 [從現有或自訂權限中選擇權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-328">Select **Choose permissions from present or custom**.</span></span>

6. <span data-ttu-id="8036c-329">在 **[從現有或自訂權限中選擇權限]** 窗格中，選取下拉式方塊，選取 **[檢視器]**，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-329">On the **Choose permissions from present or custom** pane, select the dropdown box, select **Viewer**, and then select **Save**.</span></span>

6. <span data-ttu-id="8036c-330">回到 **[指派權限]** 窗格，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-330">Back on the **Assign Permissions** pane, select **Save**.</span></span>

7. <span data-ttu-id="8036c-331">在 **[加密]** 頁面上，選取 **[下一步]** 並完成精靈。</span><span class="sxs-lookup"><span data-stu-id="8036c-331">On the **Encryption** page, select **Next** and complete the wizard.</span></span>


### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a><span data-ttu-id="8036c-332">範例 3：將外部使用者新增至可加密內容的現有標籤</span><span class="sxs-lookup"><span data-stu-id="8036c-332">Example 3: Add external users to an existing label that encrypts content</span></span>

<span data-ttu-id="8036c-333">您新增的新使用者將能夠開啟已使用此標籤保護的文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-333">The new users that you add will be able open documents and emails that have already been protected with this label.</span></span> <span data-ttu-id="8036c-334">您授與這些使用者的權限可以與現有使用者所擁有的權限不同。</span><span class="sxs-lookup"><span data-stu-id="8036c-334">The permissions that you grant these users can be different from the permissions that the existing users have.</span></span>

1. <span data-ttu-id="8036c-335">在 [加密]\*\*\*\* 頁面上：針對 [立即指派權限，或讓使用者決定?]\*\*\*\*，確定已選取 [立即指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-335">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="8036c-336">選取 [指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-336">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="8036c-337">在 **[指派權限]** 窗格中，選取 **[新增這些電子郵件地址或網域]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-337">On the **Assign permissions** pane, select **Add these email address or domains**.</span></span>

4. <span data-ttu-id="8036c-338">在文字方塊中，輸入要新增的第一個使用者 (或群組) 的電子郵件地址，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-338">In the text box, enter the email address of the first user (or group) to add, and then select **Add**.</span></span>

5. <span data-ttu-id="8036c-339">選取 [從現有或自訂權限中選擇權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-339">Select **Choose permissions from present or custom**.</span></span>

6. <span data-ttu-id="8036c-340">在 **[從現有或自訂權限中選擇權限]** 窗格中，選取此使用者 (或群組) 的權限，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-340">On the **Choose permissions from present or custom** pane, select the permissions for this user (or group), and then select **Save**.</span></span>

7. <span data-ttu-id="8036c-341">回到 **[指派權限]** 窗格，針對您要新增至此標籤的每個使用者 (或群組) 重複步驟 3 到 6。</span><span class="sxs-lookup"><span data-stu-id="8036c-341">Back on the **Assign Permissions** pane, repeat steps 3 through 6 for each user (or group) that you want to add to this label.</span></span> <span data-ttu-id="8036c-342">然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-342">Then click **Save**.</span></span>

8. <span data-ttu-id="8036c-343">在 **[加密]** 頁面上，選取 **[下一步]** 並完成精靈。</span><span class="sxs-lookup"><span data-stu-id="8036c-343">On the **Encryption** page, select **Next** and complete the wizard.</span></span>


### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a><span data-ttu-id="8036c-344">範例 4：加密內容但不會限制能夠存取內容人員的標籤</span><span class="sxs-lookup"><span data-stu-id="8036c-344">Example 4: Label that encrypts content but doesn't restrict who can access it</span></span>

<span data-ttu-id="8036c-345">此組態的優點在於您不需要指定使用者、群組或網域來加密電子郵件或文件。</span><span class="sxs-lookup"><span data-stu-id="8036c-345">This configuration has the advantage that you don't need to specify users, groups, or domains to encrypt an email or document.</span></span> <span data-ttu-id="8036c-346">內容仍會加密，您仍然可以指定使用權限、到期日期和離線存取。</span><span class="sxs-lookup"><span data-stu-id="8036c-346">The content will still be encrypted and you can still specify usage rights, an expiry date, and offline access.</span></span> 

<span data-ttu-id="8036c-347">僅當您不需要限制能開啟受保護文件或電子郵件的人員時，才使用此組態。</span><span class="sxs-lookup"><span data-stu-id="8036c-347">Use this configuration only when you do not need to restrict who can open the protected document or email.</span></span> [<span data-ttu-id="8036c-348">此設定的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8036c-348">More information about this setting</span></span>](#requirements-and-limitations-for-add-any-authenticated-users)

1. <span data-ttu-id="8036c-349">在 [加密]\*\*\*\* 頁面上：針對 [立即指派權限，或讓使用者決定?]\*\*\*\*，確定已選取 [立即指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-349">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="8036c-350">視需要設定 **[使用者存取內容的期限]** 和 **[允許離線存取]** 設定。</span><span class="sxs-lookup"><span data-stu-id="8036c-350">Configure settings for **User access to content expires** and **Allow offline access** as required.</span></span>

3. <span data-ttu-id="8036c-351">選取 [指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-351">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="8036c-352">在 **[指派權限]** 窗格中，選取 **[新增所有經過驗證的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-352">On the **Assign permissions** pane, select **Add any authenticated users**.</span></span> 
    
    <span data-ttu-id="8036c-353">針對 **[使用者和群組]**，您會看到 **AuthenticatedUsers** 已自動新增。</span><span class="sxs-lookup"><span data-stu-id="8036c-353">For **Users and groups**, you see **AuthenticatedUsers** automatically added.</span></span> <span data-ttu-id="8036c-354">您無法變更此值，只能刪除它，這會取消 **[新增所有經過驗證的使用者]** 選取範圍。</span><span class="sxs-lookup"><span data-stu-id="8036c-354">You can't change this value, only delete it, which cancels the **Add any authenticated users** selection.</span></span>

5. <span data-ttu-id="8036c-355">選取 [從現有或自訂權限中選擇權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-355">Select **Choose permissions from present or custom**.</span></span>

6. <span data-ttu-id="8036c-356">在 **[從現有或自訂權限中選擇權限]** 窗格中，選取下拉式方塊，選取您要的 **[檢視器]** 權限，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-356">On the **Choose permissions from present or custom** pane, select the dropdown box, select **Viewer**permissions you want, and then select **Save**.</span></span>

7. <span data-ttu-id="8036c-357">回到 **[指派權限]** 窗格，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8036c-357">Back on the **Assign Permissions** pane, select **Save**.</span></span>

8. <span data-ttu-id="8036c-358">在 **[加密]** 頁面上，選取 **[下一步]** 並完成精靈。</span><span class="sxs-lookup"><span data-stu-id="8036c-358">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

## <a name="considerations-for-encrypted-content"></a><span data-ttu-id="8036c-359">加密內容的考量事項</span><span class="sxs-lookup"><span data-stu-id="8036c-359">Considerations for encrypted content</span></span>

<span data-ttu-id="8036c-360">加密您最機密的文件和電子郵件，可協助確保只有獲授權的人員可以存取此資料。</span><span class="sxs-lookup"><span data-stu-id="8036c-360">Encrypting your most sensitive documents and emails helps to ensure that only authorized people can access this data.</span></span> <span data-ttu-id="8036c-361">不過，有一些事項需要納入考量：</span><span class="sxs-lookup"><span data-stu-id="8036c-361">However, there are some considerations to take into account:</span></span>

- <span data-ttu-id="8036c-362">如果您的組織尚未[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)：</span><span class="sxs-lookup"><span data-stu-id="8036c-362">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    
    - <span data-ttu-id="8036c-363">搜尋、電子文件探索和 Delve 對加密的檔案將不適用。</span><span class="sxs-lookup"><span data-stu-id="8036c-363">Search, eDiscovery, and Delve will not work for encrypted files.</span></span> 
    - <span data-ttu-id="8036c-364">DLP 原則對這些加密檔案的中繼資料 (包括保留標籤資訊) 有效，但對這些檔案的內容 (例如檔案中的信用卡號碼) 沒有效用。</span><span class="sxs-lookup"><span data-stu-id="8036c-364">DLP policies work for the metadata of these encrypted files (including retention label information) but not the content of these files (such as credit card numbers within files).</span></span>
    - <span data-ttu-id="8036c-365">使用者無法使用 Office 網頁版開啟加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="8036c-365">Users can't open encrypted files using Office on the web.</span></span> <span data-ttu-id="8036c-366">啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤時，使用者可以使用 Office 網頁版來開啟加密的檔案，但有一些[限制](sensitivity-labels-sharepoint-onedrive-files.md#limitations)，其中包括已使用內部部署金鑰 (稱為「保存您自己的金鑰」或 HYOK) 套用的加密，以及已獨立於敏感度標籤套用的加密。</span><span class="sxs-lookup"><span data-stu-id="8036c-366">When sensitivity labels for Office files in SharePoint and OneDrive is enabled, users can use Office on the web to open encrypted files, with some [limitations](sensitivity-labels-sharepoint-onedrive-files.md#limitations) that include encryption that has been applied with an on-premises key (known as "hold your own key", or HYOK), and encryption that has been applied independently from a sensitivity label.</span></span>

- <span data-ttu-id="8036c-367">若要讓多個使用者同時編輯加密的檔案，他們都必須使用 Office 網頁版。</span><span class="sxs-lookup"><span data-stu-id="8036c-367">For multiple users to edit an encrypted file at the same time, they must all be using Office for the web.</span></span> <span data-ttu-id="8036c-368">如果未這麼做，而且檔案已經開啟：</span><span class="sxs-lookup"><span data-stu-id="8036c-368">If this isn't the case, and the file is already open:</span></span>
    
    - <span data-ttu-id="8036c-369">在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中，使用者會看到 [檔案使用中]\*\*\*\* 訊息，其中包含已簽出檔案的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="8036c-369">In Office apps (Windows, Mac, Android, and iOS), users see a **File In Use** message with the name of the person who has checked out the file.</span></span> <span data-ttu-id="8036c-370">然後，他們可以檢視唯讀複本，或儲存並編輯檔案的複本，並在檔案可用時收到通知。</span><span class="sxs-lookup"><span data-stu-id="8036c-370">They can then view a read-only copy or save and edit a copy of the file, and receive notification when the file is available.</span></span>
    - <span data-ttu-id="8036c-371">在 Office 網頁版中，使用者會看到錯誤訊息，指出他們無法與其他人一起編輯該文件。</span><span class="sxs-lookup"><span data-stu-id="8036c-371">In Office for the web, users see an error message that they can't edit the document with other people.</span></span> <span data-ttu-id="8036c-372">然後他們可以選取 [在閱讀檢視中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8036c-372">They can then select **Open in Reading View**.</span></span>

- <span data-ttu-id="8036c-373">Office 應用程式 (Windows、Mac、Android 和 iOS) 中的[自動儲存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)功能已對加密的檔案停用。</span><span class="sxs-lookup"><span data-stu-id="8036c-373">The [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality in Office apps (Windows, Mac, Android, and iOS) is disabled for encrypted files.</span></span> <span data-ttu-id="8036c-374">使用者會看到一則訊息，指出檔案具有必須移除的權限限制，之後才可以開啟「自動儲存」。</span><span class="sxs-lookup"><span data-stu-id="8036c-374">Users see a message that the file has restricted permissions that must be removed before AutoSave can be turned on.</span></span>

- <span data-ttu-id="8036c-375">在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中開啟加密的檔案可能需要較長的時間才能開啟。</span><span class="sxs-lookup"><span data-stu-id="8036c-375">Encrypted files might take longer to open in Office apps (Windows, Mac, Android, and iOS).</span></span>

- <span data-ttu-id="8036c-376">用於已加密檔案的下列動作在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中不受支援，因此使用者會看到錯誤訊息，指出發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="8036c-376">The following actions for encrypted files aren't supported from Office apps (Windows, Mac, Android, and iOS), and users see an error message that something went wrong.</span></span> <span data-ttu-id="8036c-377">不過，您可以使用 SharePoint 功能做為替代：</span><span class="sxs-lookup"><span data-stu-id="8036c-377">However, SharePoint functionality can be used as an alternative:</span></span>
    
    - <span data-ttu-id="8036c-378">檢視、還原和儲存舊版的複本。</span><span class="sxs-lookup"><span data-stu-id="8036c-378">View, restore, and save copies of previous versions.</span></span> <span data-ttu-id="8036c-379">或者，當您[為清單或文件庫啟用和設定版本設定](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37)時，使用者可以使用 Office 網頁版執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="8036c-379">As an alternative, users can do these actions using Office on the web when you [enable and configure versioning for a list or library](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).</span></span> 
    - <span data-ttu-id="8036c-380">變更檔案的名稱或位置。</span><span class="sxs-lookup"><span data-stu-id="8036c-380">Change the name or location of files.</span></span> <span data-ttu-id="8036c-381">或者，使用者可以在 SharePoint 中[重新命名文件庫中的檔案、資料夾或連結](https://support.office.com/article/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185)。</span><span class="sxs-lookup"><span data-stu-id="8036c-381">As an alternative, users can [rename a file, folder, or link in a document library](https://support.office.com/article/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) in SharePoint.</span></span>

<span data-ttu-id="8036c-382">若要獲得使用敏感度標籤加密之檔案的最佳共同作業體驗，建議您[為 SharePoint 和 OneDrive 中的 Office 檔案中使用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)和 Office 網頁版。</span><span class="sxs-lookup"><span data-stu-id="8036c-382">For the best collaboration experience for files that are encrypted by a sensitivity label, we recommend you use [sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) and Office for the web.</span></span> 

## <a name="important-prerequisites"></a><span data-ttu-id="8036c-383">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="8036c-383">Important prerequisites</span></span>

<span data-ttu-id="8036c-384">在您可以使用加密之前，您可能需要執行一些組態工作。</span><span class="sxs-lookup"><span data-stu-id="8036c-384">Before you can use encryption, you might need to do some configuration tasks.</span></span>

### <a name="activate-protection-from-azure-information-protection"></a><span data-ttu-id="8036c-385">啟用來自 Azure 資訊保護的保護</span><span class="sxs-lookup"><span data-stu-id="8036c-385">Activate protection from Azure Information Protection</span></span>

<span data-ttu-id="8036c-386">若要讓敏感度標籤套用加密，必須為您的租用戶啟用來自 Azure 資訊保護的保護服務 (Azure 版權管理)。</span><span class="sxs-lookup"><span data-stu-id="8036c-386">For sensitivity labels to apply encryption, the protection service (Azure Rights Management) from Azure Information Protection must be activated for your tenant.</span></span> <span data-ttu-id="8036c-387">在較新的租用戶中，這是預設設定，但您可能需要手動啟用該服務。</span><span class="sxs-lookup"><span data-stu-id="8036c-387">In newer tenants, this is the default setting, but you might need to manually activate the service.</span></span> <span data-ttu-id="8036c-388">如需詳細資訊，請參閱[啟用來自 Azure 資訊保護的保護服務](https://docs.microsoft.com/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="8036c-388">For more information, see [Activating the protection service from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="8036c-389">設定 Exchange 進行 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="8036c-389">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="8036c-390">不需要先設定 Exchange 來使用 Azure 資訊保護，使用者就能在 Outlook 中套用標籤來加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8036c-390">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to encrypt their emails.</span></span> <span data-ttu-id="8036c-391">不過，在設定 Exchange 使用 Azure 資訊保護之前，您無法獲得使用 Exchange 的 Azure 版權管理保護的完整功能。</span><span class="sxs-lookup"><span data-stu-id="8036c-391">However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="8036c-392">例如，使用者無法在行動電話或 Outlook 網頁版上檢視加密的電子郵件，無法為加密的電子郵件編製索引供搜尋，而且您無法設定 Exchange Online DLP 使用版權管理保護。</span><span class="sxs-lookup"><span data-stu-id="8036c-392">For example, users cannot view encrypted emails on mobile phones or with Outlook on the web, encrypted emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="8036c-393">若要確保 Exchange 可以支援這些額外情節，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="8036c-393">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="8036c-394">針對 Exchange Online，請參閱 [Exchange Online：IRM 設定](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)的指示。</span><span class="sxs-lookup"><span data-stu-id="8036c-394">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
- <span data-ttu-id="8036c-395">針對 Exchange 內部部署，您必須部署 [RMS 連接器和設定您的 Exchange Server](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="8036c-395">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span> 
