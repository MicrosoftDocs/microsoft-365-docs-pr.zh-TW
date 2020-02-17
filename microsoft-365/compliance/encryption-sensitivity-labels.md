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
ms.openlocfilehash: 17cea4f80ac1dee75c10c2beef63be06141c89d5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074606"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a><span data-ttu-id="cb964-104">使用敏感度標籤來套用加密以限制存取內容</span><span class="sxs-lookup"><span data-stu-id="cb964-104">Restrict access to content by using sensitivity labels to apply encryption</span></span> 

<span data-ttu-id="cb964-p102">當建立敏感度標籤時，您可以限制標籤將套用至其中之內容的存取。例如，使用敏感度標籤的加密設定，您可以保護內容，以便：</span><span class="sxs-lookup"><span data-stu-id="cb964-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="cb964-107">僅您組織內的使用者才能開啟機密文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb964-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="cb964-108">僅行銷部門中的使用者才能編輯和列印促銷公告文件或電子郵件，而您組織中的所有其他使用者則只能讀取它。</span><span class="sxs-lookup"><span data-stu-id="cb964-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="cb964-109">使用者無法轉寄電子郵件，或從中複製包含內部組織相關消息的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb964-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="cb964-110">在指定日期之後，無法開啟傳送給商業夥伴的目前價格清單。</span><span class="sxs-lookup"><span data-stu-id="cb964-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="cb964-111">加密文件或電子郵件時，內容的存取會受到限制，以便：</span><span class="sxs-lookup"><span data-stu-id="cb964-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="cb964-112">只有標籤加密設定授權的使用者才能將其解密。</span><span class="sxs-lookup"><span data-stu-id="cb964-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="cb964-113">即使檔案重新命名，無論其位於您組織內部或外部，仍保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="cb964-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="cb964-114">同時進行靜態加密 (例如，在 OneDrive 帳戶中) 及傳輸中加密 (例如，已傳送的電子郵件)。</span><span class="sxs-lookup"><span data-stu-id="cb964-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="cb964-115">最後，身為系統管理員的您，在設定一個敏感度標籤來套用加密時，可以選擇以下兩者之一：</span><span class="sxs-lookup"><span data-stu-id="cb964-115">Finally, as an admin, when you configure a sensitivity label to apply encryption, you can choose either to:</span></span>

- <span data-ttu-id="cb964-116">**立即指派權限**，這樣您就能確實決定哪個使用者能夠存取該標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="cb964-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="cb964-117">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="cb964-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="cb964-118">如此一來，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="cb964-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="cb964-119">當您在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或是 Office 365 安全性與合規性中心中[建立敏感性標籤](create-sensitivity-labels.md)時，可以使用加密設定。</span><span class="sxs-lookup"><span data-stu-id="cb964-119">The encryption settings are available when you [create a sensitivity label](create-sensitivity-labels.md) in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="cb964-120">加密的運作方式</span><span class="sxs-lookup"><span data-stu-id="cb964-120">How encryption works</span></span>

<span data-ttu-id="cb964-121">加密使用來自 Azure 資訊保護的 Azure 版權管理服務 (Azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="cb964-121">Encryption uses the Azure Rights Management service (Azure RMS) from Azure Information Protection.</span></span> <span data-ttu-id="cb964-122">此保護解決方案使用加密、身分識別及授權原則。</span><span class="sxs-lookup"><span data-stu-id="cb964-122">This protection solution uses encryption, identity, and authorization policies.</span></span> <span data-ttu-id="cb964-123">若要深入了解，請參閱 Azure 資訊保護文件中的[什麼是 Azure 版權管理？](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="cb964-123">To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) from the Azure Information Protection documentation.</span></span> 

<span data-ttu-id="cb964-124">使用此加密解決方案時，**超級使用者**功能可確保獲授權的人員和服務一律可以讀取和檢查已為組織加密的資料。</span><span class="sxs-lookup"><span data-stu-id="cb964-124">When you use this encryption solution, the **super user** feature ensures that authorized people and services can always read and inspect the data that has been encrypted for your organization.</span></span> <span data-ttu-id="cb964-125">如有需要，您可以接著將加密移除或變更。</span><span class="sxs-lookup"><span data-stu-id="cb964-125">If necessary, the encryption can then be removed or changed.</span></span> <span data-ttu-id="cb964-126">如需詳細資訊，請參閱[為 Azure 資訊保護和探索服務或資料復原設定超級使用者](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="cb964-126">For more information, see [Configuring super users for Azure Information Protection and discovery services or data recovery](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

## <a name="configuring-a-label-for-encryption"></a><span data-ttu-id="cb964-127">設定用於加密的標籤</span><span class="sxs-lookup"><span data-stu-id="cb964-127">Configuring a label for encryption</span></span>

<span data-ttu-id="cb964-128">當您[建立或編輯敏感度標籤時](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，可以在精靈的 [加密]\*\*\*\* 頁面上選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cb964-128">When you [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels), on the **Encryption** page of the wizard, you can select one of the following options:</span></span>

- <span data-ttu-id="cb964-129">**無**：新標籤的預設設定。</span><span class="sxs-lookup"><span data-stu-id="cb964-129">**None**: The default setting for a new label.</span></span> <span data-ttu-id="cb964-130">不會套用新的加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-130">No new encryption is applied.</span></span>
- <span data-ttu-id="cb964-131">**套用**：開啟加密，然後指定加密設定。</span><span class="sxs-lookup"><span data-stu-id="cb964-131">**Apply**: Turns on encryption, and you then specify encryption settings.</span></span>
- <span data-ttu-id="cb964-132">**移除**：如果文件或電子郵件已加密，則會移除加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-132">**Remove**: Removes encryption if the document or email is encrypted.</span></span>

> [!NOTE]
> <span data-ttu-id="cb964-133">只有 Azure 資訊保護整合標籤用戶端才支援 [移除]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="cb964-133">The **Remove** option is supported by the Azure Information Protection unified labeling client only.</span></span> <span data-ttu-id="cb964-134">當您使用內建的標籤時，具有此選項的標籤會在 Office 應用程式中顯示，並且若已選取該選項，則加密行為會與 [無]\*\*\*\* 相同。</span><span class="sxs-lookup"><span data-stu-id="cb964-134">When you use built-in labeling, a label with this option is visible in Office apps and if selected, the encryption behavior is the same as **None**.</span></span>

<span data-ttu-id="cb964-135">設定加密選項：</span><span class="sxs-lookup"><span data-stu-id="cb964-135">Configuring the encryption options:</span></span>

![用於加密的敏感度標籤選項](../media/encrytion-options-sensitivity-label.png)


### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="cb964-137">套用標籤時，現有的加密會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="cb964-137">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="cb964-138">如果您將敏感度標籤套用到未加密的內容，您可以選取的加密選項結果會一目了然。</span><span class="sxs-lookup"><span data-stu-id="cb964-138">If a sensitivity label is applied to unencrypted content, the outcome of the encryption options you can select is self-explanatory.</span></span> <span data-ttu-id="cb964-139">例如，如果將加密設定為 [無]\*\*\*\*，則內容會保持未加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-139">For example, if encryption is set to **None**, the content remains unencrypted.</span></span>

<span data-ttu-id="cb964-140">不過，內容可能已加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-140">However, the content might be already encrypted.</span></span> <span data-ttu-id="cb964-141">例如，其他使用者可能已套用：</span><span class="sxs-lookup"><span data-stu-id="cb964-141">For example, another user might have applied:</span></span>

- <span data-ttu-id="cb964-142">其自己的權限，其中包括標籤提示時的使用者定義權限、Azure 資訊保護用戶端的自訂權限，以及來自 Office 應用程式內的**限制存取**文件保護。</span><span class="sxs-lookup"><span data-stu-id="cb964-142">Their own permissions, which include user-defined permissions when prompted by a label, custom permissions by the Azure Information Protection client, and the **Restricted Access** document protection from within an Office app.</span></span>
- <span data-ttu-id="cb964-143">Azure 版權管理保護範本可獨立於標籤將內容加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-143">An Azure Rights Management protection template that encrypts the content independently from a label.</span></span> <span data-ttu-id="cb964-144">此類別包括使用版權保護來套用加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="cb964-144">This category includes mail flow rules that apply encryption by using rights protection.</span></span>
- <span data-ttu-id="cb964-145">以系統管理員指派的權限套用加密的標籤。</span><span class="sxs-lookup"><span data-stu-id="cb964-145">A label that applies encryption with permissions assigned by the administrator.</span></span>

<span data-ttu-id="cb964-146">下表說明對該內容套用敏感度標籤時，現有的加密會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="cb964-146">The following table identifies what happens to existing encryption when a sensitivity label is applied to that content:</span></span>

| |<span data-ttu-id="cb964-147">**加密：無**</span><span class="sxs-lookup"><span data-stu-id="cb964-147">**Encryption: None**</span></span>|<span data-ttu-id="cb964-148">**加密：套用**</span><span class="sxs-lookup"><span data-stu-id="cb964-148">**Encryption: Apply**</span></span>|<span data-ttu-id="cb964-149">**加密：移除**</span><span class="sxs-lookup"><span data-stu-id="cb964-149">**Encryption: Remove**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb964-150">**使用者指定的權限**</span><span class="sxs-lookup"><span data-stu-id="cb964-150">**Permissions specified by a user**</span></span>|<span data-ttu-id="cb964-151">原始加密已保留</span><span class="sxs-lookup"><span data-stu-id="cb964-151">Original encryption is preserved</span></span>|<span data-ttu-id="cb964-152">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="cb964-152">New label encryption is applied</span></span>|<span data-ttu-id="cb964-153">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="cb964-153">Original encryption is removed</span></span>|
|<span data-ttu-id="cb964-154">**保護範本**</span><span class="sxs-lookup"><span data-stu-id="cb964-154">**Protection template**</span></span>|<span data-ttu-id="cb964-155">原始加密已保留</span><span class="sxs-lookup"><span data-stu-id="cb964-155">Original encryption is preserved</span></span>|<span data-ttu-id="cb964-156">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="cb964-156">New label encryption is applied</span></span>|<span data-ttu-id="cb964-157">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="cb964-157">Original encryption is removed</span></span>|
|<span data-ttu-id="cb964-158">**具有系統管理員定義權限的標籤**</span><span class="sxs-lookup"><span data-stu-id="cb964-158">**Label with administator-defined permissions**</span></span>|<span data-ttu-id="cb964-159">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="cb964-159">Original encryption is removed</span></span>|<span data-ttu-id="cb964-160">新標籤加密已套用</span><span class="sxs-lookup"><span data-stu-id="cb964-160">New label encryption is applied</span></span>|<span data-ttu-id="cb964-161">原始加密已移除</span><span class="sxs-lookup"><span data-stu-id="cb964-161">Original encryption is removed</span></span>|

<span data-ttu-id="cb964-162">請注意，在套用新標籤加密或移除原始加密的情況下，只有在套用標籤的使用者有支援此動作的使用權利或角色時，才會發生這種情況：</span><span class="sxs-lookup"><span data-stu-id="cb964-162">Note that in the cases where the new label encryption is applied or the original encryption is removed, this happens only if the user applying the label has a usage right or role that supports this action:</span></span>
- <span data-ttu-id="cb964-163">[使用權限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights.md#usage-rights-and-descriptions)匯出或完全控制。</span><span class="sxs-lookup"><span data-stu-id="cb964-163">The [usage right](https://docs.microsoft.com/azure/information-protection/configure-usage-rights.md#usage-rights-and-descriptions) Export or Full Control.</span></span>
- <span data-ttu-id="cb964-164">[版權管理簽發者或版權管理擁有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)的角色，或[超級使用者](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="cb964-164">The role of [Rights Management issuer or Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), or [super user](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

<span data-ttu-id="cb964-165">如果使用者沒有這些權限或角色中的一個，就無法套用標籤，因此會保留原始加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-165">If the user doesn't have one of these rights or roles, the label can't be applied and so the original encryption is preserved.</span></span> <span data-ttu-id="cb964-166">使用者會看到下列訊息：**您沒有對敏感度標籤進行變更所需的權限。請連絡內容的擁有者。**</span><span class="sxs-lookup"><span data-stu-id="cb964-166">The user sees the following message: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.**</span></span>

<span data-ttu-id="cb964-167">例如，對電子郵件訊息套用 [不可轉寄] 的人員，可以將該對話重新標記，以取代加密或移除它，因為他們是該電子郵件的版權管理擁有者。</span><span class="sxs-lookup"><span data-stu-id="cb964-167">For example, the person who applies Do Not Forward to an email message can relabel the thread to replace the encryption or remove it, because they are the Rights Management owner for the email.</span></span> <span data-ttu-id="cb964-168">但除了超級使用者之外，此電子郵件的收件者無法重新標記它，因為他們沒有所需的使用權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-168">But with the exception of super users, recipients of this email can't relabel it because they don't have the required usage rights.</span></span>

#### <a name="email-attachments-for-encrypted-email-messages"></a><span data-ttu-id="cb964-169">已加密電子郵件的電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="cb964-169">Email attachments for encrypted email messages</span></span>

<span data-ttu-id="cb964-170">當電子郵件以任何方法加密時，任何附加至電子郵件的未加密 Office 文件都會自動繼承相同的加密設定。</span><span class="sxs-lookup"><span data-stu-id="cb964-170">When an email message is encrypted by any method, any unencrypted Office documents that are attached to the email automatically inherit the same encryption settings.</span></span>

<span data-ttu-id="cb964-171">已加密然後新增為附件的文件，一律會保留其原始加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-171">Documents that are already encrypted and then added as attachments always preserve their original encryption.</span></span> 

## <a name="how-to-configure-encryption-settings-for-a-sensitivity-label"></a><span data-ttu-id="cb964-172">如何設定敏感度標籤的加密設定</span><span class="sxs-lookup"><span data-stu-id="cb964-172">How to configure encryption settings for a sensitivity label</span></span>

<span data-ttu-id="cb964-173">當您在精靈的 [加密]\*\*\*\* 頁面上選取 [套用]\*\*\*\* 來建立或編輯敏感度標籤時，請選擇是否要：</span><span class="sxs-lookup"><span data-stu-id="cb964-173">When you select **Apply** on the **Encryption** page of the wizard to create or edit a sensitivity label, choose whether to:</span></span>

- <span data-ttu-id="cb964-174">**立即指派權限**，這樣您就能決定哪些使用者確切能取得已套用標籤內容的權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-174">**Assign permissions now**, so that you can determine exactly which users get which permissions to content that has the label applied.</span></span> <span data-ttu-id="cb964-175">如需詳細資訊，請參閱下一節的[立即指派權限](#assign-permissions-now)。</span><span class="sxs-lookup"><span data-stu-id="cb964-175">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="cb964-176">當使用者將標籤套用到內容時，**讓使用者指派權限**。</span><span class="sxs-lookup"><span data-stu-id="cb964-176">**Let users assign permissions** when your users apply the label to content.</span></span> <span data-ttu-id="cb964-177">利用此選項，您就可以讓組織中的人員靈活地共同作業並完成工作。</span><span class="sxs-lookup"><span data-stu-id="cb964-177">With this option, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="cb964-178">如需詳細資訊，請本頁的[讓使用者指派權限](#let-users-assign-permissions)章節。</span><span class="sxs-lookup"><span data-stu-id="cb964-178">For more information, see the [Let users assign permissions](#let-users-assign-permissions) section on this page.</span></span>

<span data-ttu-id="cb964-179">例如，如果您有一個名為 [高度機密] \*\*\*\* 的敏感度標籤，該標籤將套用至最敏感的內容，則您可能會希望立即決定誰能取得該內容的何種權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-179">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you might want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="cb964-180">或者，如果您有一個名為 [商業合約]\*\*\*\* 的敏感度標籤，並且貴組織的工作流程要求人員隨機與不同人員共同處理此內容，則您可能會希望讓使用者在指派標籤時決定可存取的人員。</span><span class="sxs-lookup"><span data-stu-id="cb964-180">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you might want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="cb964-181">這種靈活性既可以幫助您提高使用者的工作效率，又可以減少管理員更新或建立新敏感度標籤以滿足特定案例的要求。</span><span class="sxs-lookup"><span data-stu-id="cb964-181">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

<span data-ttu-id="cb964-182">選擇 [立即指派權限] 或 [讓使用者指派權限]：</span><span class="sxs-lookup"><span data-stu-id="cb964-182">Choosing whether to assign permissions now or let users assign permissions:</span></span> 

![新增使用者或系統管理員定義權限的選項](../media/sensitivity-label-user-or-admin-defined-permissions.png)


## <a name="assign-permissions-now"></a><span data-ttu-id="cb964-184">立即指派權限</span><span class="sxs-lookup"><span data-stu-id="cb964-184">Assign permissions now</span></span>

<span data-ttu-id="cb964-185">使用下列選項來控制誰可以存取套用此標籤的電子郵件或文件。</span><span class="sxs-lookup"><span data-stu-id="cb964-185">Use the following options to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="cb964-186">您可以：</span><span class="sxs-lookup"><span data-stu-id="cb964-186">You can:</span></span>

1. <span data-ttu-id="cb964-p117">在特定日期，或是在套用標籤之後的特定天數之後**允許具有標籤的內容的存取權到期**。在此時間後，使用者將無法開啟具有標籤的項目。如果指定日期，則會在目前時區中，該日期的午夜開始生效。(請注意，某些電子郵件用戶端可能因為其快取機制而無法強制執行到期，而顯示超過期限的電子郵件。)</span><span class="sxs-lookup"><span data-stu-id="cb964-p117">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients might not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

2. <span data-ttu-id="cb964-p118">在套用標籤之後**允許離線存取**可為從不、一律或特定天數。如果您將離線存取限制為從不或天數，則達到該閾值時，必須重新驗證使用者，並記錄其存取。如需詳細資訊，請參閱關於 Rights Management 使用授權的下一節。</span><span class="sxs-lookup"><span data-stu-id="cb964-p118">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

<span data-ttu-id="cb964-194">已加密內容的存取控制設定：</span><span class="sxs-lookup"><span data-stu-id="cb964-194">Settings for access control for encrypted content:</span></span>

![系統管理員定義權限的設定](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="cb964-196">用於離線存取的 Rights Management 使用授權</span><span class="sxs-lookup"><span data-stu-id="cb964-196">Rights Management use license for offline access</span></span>

<span data-ttu-id="cb964-197">當使用者開啟以來自 Azure 版權管理服務的加密保護的文件或電子郵件時，Azure 版權管理會將該內容的使用授權授與給該使用者。</span><span class="sxs-lookup"><span data-stu-id="cb964-197">When a user opens a document or email that’s been protected by encryption from the Azure Rights Management service, an Azure Rights Management use license for that content is granted to the user.</span></span> <span data-ttu-id="cb964-198">使用授權是一項憑證，其中包含使用者對於文件或電子郵件使用權限，以及用來加密內容的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="cb964-198">This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content.</span></span> <span data-ttu-id="cb964-199">如果已設定，則使用授權也會包含到期日，以及該使用授權的有效期。</span><span class="sxs-lookup"><span data-stu-id="cb964-199">The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="cb964-p120">如果未設定到期日，則租用戶的預設使用授權有效期間為 30 天。在這段期間，不會針對內容重新驗證或重新授權使用者。這個程序可讓使用者在沒有網際網路連線的情況下繼續開啟受保護文件或電子郵件。使用授權有效期間到期時，下次使用者存取受保護文件或電子郵件時，則必須重新驗證和重新授權使用者。</span><span class="sxs-lookup"><span data-stu-id="cb964-p120">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This process lets the user continue to open the protected document or email without an internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="cb964-204">除了重新驗證外，還會重新評估原則和使用者群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="cb964-204">In addition to reauthentication, the encryption settings and user group membership is reevaluated.</span></span> <span data-ttu-id="cb964-205">這表示，如果上次使用者存取內容後，加密設定或群組成員資格發生變更，則這些使用者可能遇到相同的文件或電子郵件，卻有不同的存取結果。</span><span class="sxs-lookup"><span data-stu-id="cb964-205">This means that users could experience different access results for the same document or email if there are changes in the encryption settings or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="cb964-206">若要了解如何變更預設的 30 天設定，請參閱 [Rights Management 使用授權](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="cb964-206">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="cb964-207">將權限指派給特定使用者或群組</span><span class="sxs-lookup"><span data-stu-id="cb964-207">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="cb964-208">您可以將權限授與特定人員，以便只有他們可與標籤內容互動：</span><span class="sxs-lookup"><span data-stu-id="cb964-208">You can grant permissions to specific people so that only they can interact with the labeled content:</span></span>

1. <span data-ttu-id="cb964-209">首先，新增將獲指派標籤內容之權限的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="cb964-209">First, add users or groups that will be assigned permissions to the labeled content.</span></span>

2. <span data-ttu-id="cb964-210">接著，選擇那些使用者應對標籤內容具有的權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-210">Then, choose which permissions those users should have for the labeled content.</span></span>

<span data-ttu-id="cb964-211">指派權限：</span><span class="sxs-lookup"><span data-stu-id="cb964-211">Assigning permissions:</span></span>

![將權限指派給使用者的選項](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="cb964-213">新增使用者或群組</span><span class="sxs-lookup"><span data-stu-id="cb964-213">Add users or groups</span></span>

<span data-ttu-id="cb964-214">指派權限時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="cb964-214">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="cb964-p122">組織中的所有人 (所有租用戶成員)。此設定會排除來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="cb964-p122">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="cb964-217">任何已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="cb964-217">Any authenticated users.</span></span> <span data-ttu-id="cb964-218">選取此選項之前，請先確認您了解此設定的[需求與限制](#requirements-and-limitations-for-add-any-authenticated-users)。</span><span class="sxs-lookup"><span data-stu-id="cb964-218">Make sure you understand the [requirements and limitations](#requirements-and-limitations-for-add-any-authenticated-users) of this setting before selecting it.</span></span>
- <span data-ttu-id="cb964-219">任何特定使用者或啟用電子郵件功能的安全性群組、通訊群組、Office 365 群組或動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="cb964-219">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="cb964-220">組織外的任何電子郵件地址或網域，例如 gmail.com、hotmail.com 或 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cb964-220">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span> 

<span data-ttu-id="cb964-221">當您選擇所有租用戶成員或瀏覽目錄時，使用者或群組必須具有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cb964-221">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="cb964-p124">最佳做法是使用群組，而非使用者。此策略可讓您保持更簡單的組態。</span><span class="sxs-lookup"><span data-stu-id="cb964-p124">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a><span data-ttu-id="cb964-224">**新增任何已驗證使用者**的需求與限制</span><span class="sxs-lookup"><span data-stu-id="cb964-224">Requirements and limitations for **Add any authenticated users**</span></span>

<span data-ttu-id="cb964-225">此設定不會限制能夠存取標籤所加密內容的人員，同時仍會加密內容，並提供限制內容使用方式 (權限) 和存取方式 (到期和離線存取) 的選項。</span><span class="sxs-lookup"><span data-stu-id="cb964-225">This setting doesn't restrict who can access the content that the label encrypts, while still encrypting the content and providing you with options to restrict how the content can be used (permissions), and accessed (expiry and offline access).</span></span> <span data-ttu-id="cb964-226">不過，開啟加密內容的應用程式必須能夠支援所使用的驗證。</span><span class="sxs-lookup"><span data-stu-id="cb964-226">However, the application opening the encrypted content must be able to support the authentication being used.</span></span> <span data-ttu-id="cb964-227">因此，同盟社交提供者 (例如 Google) 和一次性密碼驗證僅對電子郵件有效，且僅在您使用 Exchange Online 和來自 Office 365 訊息加密的新功能時才有效。</span><span class="sxs-lookup"><span data-stu-id="cb964-227">For this reason, federated social providers such as Google, and onetime passcode authentication work for email only, and only when you use Exchange Online and the new capabilities from Office 365 Message Encryption.</span></span> <span data-ttu-id="cb964-228">您可以將 Microsoft 帳戶與 Office 365 應用程式和 [Azure 資訊保護檢視器](https://portal.azurerms.com/#/download)搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cb964-228">Microsoft accounts can be used with Office 365 apps and the [Azure Information Protection viewer](https://portal.azurerms.com/#/download).</span></span>

<span data-ttu-id="cb964-229">任何已驗證使用者設定的一些典型案例如下：</span><span class="sxs-lookup"><span data-stu-id="cb964-229">Some typical scenarios for the any authenticated users setting:</span></span>
- <span data-ttu-id="cb964-230">您不在意檢視內容的是誰，但想要限制其使用方式。</span><span class="sxs-lookup"><span data-stu-id="cb964-230">You don't mind who views the content, but you want to restrict how it is used.</span></span> <span data-ttu-id="cb964-231">例如，您不希望編輯、複製或列印內容。</span><span class="sxs-lookup"><span data-stu-id="cb964-231">For example, you don't want the content to be edited, copied, or printed.</span></span>
- <span data-ttu-id="cb964-232">您不需要限制存取內容的是誰，但想要能夠確認誰開啟了該內容。</span><span class="sxs-lookup"><span data-stu-id="cb964-232">You don't need to restrict who accesses the content, but you want to be able to confirm who opens it.</span></span>
- <span data-ttu-id="cb964-233">您必須將靜態內容和在傳輸中的內容加密，但不要求存取控制。</span><span class="sxs-lookup"><span data-stu-id="cb964-233">You have a requirement that the content must be encrypted at rest and in transit, but it doesn't require access controls.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="cb964-234">選擇權限</span><span class="sxs-lookup"><span data-stu-id="cb964-234">Choose permissions</span></span>

<span data-ttu-id="cb964-235">當您選擇要對那些使用者或群組允許的權限時，您可以選取下列任一項：</span><span class="sxs-lookup"><span data-stu-id="cb964-235">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="cb964-236">[預先定義的權限層級](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，其中有一組預設的權限，例如共同作者或檢閱者。</span><span class="sxs-lookup"><span data-stu-id="cb964-236">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="cb964-237">一組自訂的權限，您可在其中選擇任何您想要的權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-237">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="cb964-238">如需每一個特定權限的詳細資訊，請參閱[使用權限和描述](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="cb964-238">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![選擇預設或自訂權限的選項](../media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="cb964-p127">請注意，相同標籤可將不同的權限授與不同的使用者。例如，單一標籤可將某些使用者指派為檢閱者，並將不同的使用者指派為共同作者，如以下螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="cb964-p127">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown in the following screenshot.</span></span>

<span data-ttu-id="cb964-p128">若要這麼做，請新增使用者或群組、將權限指派給他們，並儲存這些設定。然後，重複這些步驟、新增使用者並將權限指派給他們，每次完成後儲存設定。您可以視需要經常重複此設定，為不同的使用者定義不同的權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-p128">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can repeat this configuration as often as necessary, to define different permissions for different users.</span></span>

![具有不同權限的不同使用者](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="cb964-246">Rights Management 簽發者 (套用敏感度標籤的使用者) 一律具有完全控制權</span><span class="sxs-lookup"><span data-stu-id="cb964-246">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="cb964-247">敏感度標籤的加密使用來自 Azure 資訊保護的 Azure 版權管理服務。</span><span class="sxs-lookup"><span data-stu-id="cb964-247">Encryption for a sensitivity label uses the Azure Rights Management service from Azure Information Protection.</span></span> <span data-ttu-id="cb964-248">當使用者套用敏感度標籤以使用加密保護文件或電子郵件時，該使用者就會變成該內容的版權管理簽發者。</span><span class="sxs-lookup"><span data-stu-id="cb964-248">When a user applies a sensitivity label to protect a document or email by using encryption, that user becomes the Rights Management issuer for that content.</span></span>

<span data-ttu-id="cb964-249">版權管理簽發者一律會被授與文件或電子郵件的完全控制權限，此外：</span><span class="sxs-lookup"><span data-stu-id="cb964-249">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="cb964-250">如果加密設定包括到期日，則版權管理簽發者仍然可在該日期之後開啟和編輯文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb964-250">If the encryption settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="cb964-251">Rights Management 簽發者一律可以離線存取文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb964-251">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="cb964-252">Rights Management 簽發者仍可以開啟撤銷後的文件。</span><span class="sxs-lookup"><span data-stu-id="cb964-252">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="cb964-253">如需詳細資訊，請參閱 [Rights Management 簽發者和 Rights Management 擁有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="cb964-253">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="cb964-254">讓使用者指派權限</span><span class="sxs-lookup"><span data-stu-id="cb964-254">Let users assign permissions</span></span>

<span data-ttu-id="cb964-255">您可以使用這些選項讓使用者在手動將敏感度標籤套用至內容時指派權限：</span><span class="sxs-lookup"><span data-stu-id="cb964-255">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="cb964-256">在 Outlook 中，使用者可以針對所選的收件者選取等同於[不可轉寄](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails)選項的限制。</span><span class="sxs-lookup"><span data-stu-id="cb964-256">In Outlook, a user can select restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option for their chosen recipients.</span></span>

- <span data-ttu-id="cb964-257">在 Word、PowerPoint 和 Excel 中，系統會提示使用者為特定使用者、群組或組織選取其自己的權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-257">In Word, PowerPoint, and Excel, a user is prompted to select their own permissions for specific users, groups, or organizations.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="cb964-258">適用於 Word、PowerPoint 和 Excel 的此選項，是由 Azure 資訊保護整合標籤用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="cb964-258">This option for Word, PowerPoint, and Excel is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="cb964-259">針對使用內建標籤的應用程式，目前在 [Windows 版和 Mac 版預覽](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)中都提供支援。</span><span class="sxs-lookup"><span data-stu-id="cb964-259">For apps that use built-in labeling, support is currently in [preview for Windows and Mac](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span></span> 
    > 
    > <span data-ttu-id="cb964-260">如果已選取此選項，但使用者的應用程式不支援此選項，表示該標籤未顯示給使用者，或 (目前正在 iOS 和 Android 版預覽中推出) 為求一致，系統會顯示標籤，但無法在套用時為使用者提供說明訊息。</span><span class="sxs-lookup"><span data-stu-id="cb964-260">If this option is selected but isn't supported for a user's app, either that label doesn't display to the user, or (currently rolling out in preview for iOS and Android) the label displays for consistency, but it can't be applied with an explanation message to users.</span></span>

<span data-ttu-id="cb964-261">支援這些選項時，請使用下表來識別使用者何時可看到敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="cb964-261">When the options are supported, use the following table to identify when users see the sensitivity label:</span></span>

|<span data-ttu-id="cb964-262">設定</span><span class="sxs-lookup"><span data-stu-id="cb964-262">Setting</span></span> |<span data-ttu-id="cb964-263">標籤在 Outlook 中顯示</span><span class="sxs-lookup"><span data-stu-id="cb964-263">Label visible in Outlook</span></span>|<span data-ttu-id="cb964-264">標籤在 Word、Excel、PowerPoint 中顯示</span><span class="sxs-lookup"><span data-stu-id="cb964-264">Label visible in Word, Excel, PowerPoint</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb964-265">**在 Outlook 中，強制執行限制等同於 [不可轉寄] 選項**</span><span class="sxs-lookup"><span data-stu-id="cb964-265">**In Outlook, enforce restrictions equivalent to the Do Not Forward option**</span></span>|<span data-ttu-id="cb964-266">是</span><span class="sxs-lookup"><span data-stu-id="cb964-266">Yes</span></span> |<span data-ttu-id="cb964-267">否</span><span class="sxs-lookup"><span data-stu-id="cb964-267">No</span></span> |
|<span data-ttu-id="cb964-268">**在 Word、PowerPoint 與 Excel 中提示使用者指定權限**</span><span class="sxs-lookup"><span data-stu-id="cb964-268">**In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>|<span data-ttu-id="cb964-269">否</span><span class="sxs-lookup"><span data-stu-id="cb964-269">No</span></span> |<span data-ttu-id="cb964-270">是</span><span class="sxs-lookup"><span data-stu-id="cb964-270">Yes</span></span>|

<span data-ttu-id="cb964-271">同時選取這兩個設定時，標籤會因此同時在 Outlook 和 Word、Excel 和 PowerPoint 中顯示。</span><span class="sxs-lookup"><span data-stu-id="cb964-271">When both settings are selected, the label is therefore visible in both Outlook and in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="cb964-272">可讓使用者指派權限的敏感度標籤只能透過使用者手動來套用至內容；它不能自動套用，也不能作為推薦標籤。</span><span class="sxs-lookup"><span data-stu-id="cb964-272">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

<span data-ttu-id="cb964-273">設定使用者指派的權限：</span><span class="sxs-lookup"><span data-stu-id="cb964-273">Configuring the user-assigned permissions:</span></span>

![使用者定義權限的加密設定](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="cb964-275">Outlook 限制</span><span class="sxs-lookup"><span data-stu-id="cb964-275">Outlook restrictions</span></span>

<span data-ttu-id="cb964-276">在 Outlook 中，當使用者套用的敏感標籤可允許他們指派郵件的權限時，限制與 [不可轉寄] 選項相同。</span><span class="sxs-lookup"><span data-stu-id="cb964-276">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="cb964-277">使用者會在郵件頂端看到標籤名稱和描述，指出內容已受到保護。</span><span class="sxs-lookup"><span data-stu-id="cb964-277">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="cb964-278">與 Word、PowerPoint 和 Excel 不同的是 (請參閱[下一節](#word-powerpoint-and-excel-permissions))，使用者不會收到選取特定權限的提示。</span><span class="sxs-lookup"><span data-stu-id="cb964-278">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![套用至 Outlook 郵件的敏感度標籤](../media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="cb964-280">將 [不可轉寄] 選項套用到電子郵件時，電子郵件會加密而且收件者必須經過驗證。</span><span class="sxs-lookup"><span data-stu-id="cb964-280">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="cb964-281">收件者無法轉寄、列印或複製該電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb964-281">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="cb964-282">例如，在 Outlook 用戶端中，無法使用 [轉寄] 按鈕、[另存新檔] 和 [列印] 功能表選項，且您無法在 [收件人]、[副本] 或 [密件副本] 方塊中新增或變更收件者。</span><span class="sxs-lookup"><span data-stu-id="cb964-282">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="cb964-283">附加到電子郵件的未加密 Office 文件會自動繼承相同的限制。</span><span class="sxs-lookup"><span data-stu-id="cb964-283">Unencrypted Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="cb964-284">套用至這些文件的使用權限是 [編輯內容]、[編輯]；[儲存]；[檢視]、[開啟]、[讀取]；和 [允許巨集]。</span><span class="sxs-lookup"><span data-stu-id="cb964-284">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="cb964-285">如果使用者想要不同的附件使用權限，或者附件不是支援此繼承保護的 Office 文件，則使用者需要在將文件附加到電子郵件之前保護該檔案。</span><span class="sxs-lookup"><span data-stu-id="cb964-285">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="cb964-286">Word、PowerPoint 和 Excel 權限</span><span class="sxs-lookup"><span data-stu-id="cb964-286">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="cb964-287">在 Word、PowerPoint 和 Excel 中，當使用者套用可讓他們對文件指派權限的敏感度標籤時，系統會提示他們指定套用加密時的所選使用者和權限。</span><span class="sxs-lookup"><span data-stu-id="cb964-287">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to specify their choice of users and permissions when the encryption is applied.</span></span>

<span data-ttu-id="cb964-288">例如，利用 Azure 資訊保護整合標籤用戶端，使用者可以：</span><span class="sxs-lookup"><span data-stu-id="cb964-288">For example, with the Azure Information Protection unified labeling client, users can:</span></span>

- <span data-ttu-id="cb964-289">選取權限等級，例如檢視者 (指派 [僅檢視] 權限) 或共同作者 (指派 [檢視]、[編輯]、[複製] 和 [列印] 權限)。</span><span class="sxs-lookup"><span data-stu-id="cb964-289">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="cb964-290">選取使用者、群組或組織。</span><span class="sxs-lookup"><span data-stu-id="cb964-290">Select users, groups, or organizations.</span></span> <span data-ttu-id="cb964-291">這可能包括組織內部或外部的人員。</span><span class="sxs-lookup"><span data-stu-id="cb964-291">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="cb964-292">設定到期日，到期之後所選使用者就無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="cb964-292">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="cb964-293">如需詳細資訊, 請參閱前一節的[用於離線存取的 Rights Management 使用授權](#rights-management-use-license-for-offline-access)。</span><span class="sxs-lookup"><span data-stu-id="cb964-293">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![讓使用者以自訂權限進行保護的選項](../media/sensitivity-aip-custom-permissions-dialog.png)

<span data-ttu-id="cb964-295">針對內建標籤，使用者會在選取下列項目時看到相同的對話方塊：</span><span class="sxs-lookup"><span data-stu-id="cb964-295">For built-in labeling, users see the same dialog box if they select the following:</span></span>

- <span data-ttu-id="cb964-296">Windows：[檔案]\*\*\*\* 索引標籤 > [資訊]\*\*\*\*  >  [保護文件]\*\*\*\*  >  [限制存取]\*\*\*\*  >  [限制存取]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb964-296">Windows: **File** tab > **Info** > **Protect Document** > **Restrict Access** > **Restricted Access**</span></span>

- <span data-ttu-id="cb964-297">MacOS：[校閱]\*\*\*\* 索引標籤 > [保護]\*\*\*\*  >  [權限]\*\*\*\*  >  [限制存取]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb964-297">MacOS: **Review** tab > **Protection** > **Permissions** > **Restricted Access**</span></span>


## <a name="considerations-for-encrypted-content"></a><span data-ttu-id="cb964-298">加密內容的考量事項</span><span class="sxs-lookup"><span data-stu-id="cb964-298">Considerations for encrypted content</span></span>

<span data-ttu-id="cb964-299">加密您最機密的文件和電子郵件，可協助確保只有獲授權的人員可以存取此資料。</span><span class="sxs-lookup"><span data-stu-id="cb964-299">Encrypting your most sensitive documents and emails helps to ensure that only authorized people can access this data.</span></span> <span data-ttu-id="cb964-300">不過，有一些事項需要納入考量：</span><span class="sxs-lookup"><span data-stu-id="cb964-300">However, there are some considerations to take into account:</span></span>

- <span data-ttu-id="cb964-301">如果您的組織尚未[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)：</span><span class="sxs-lookup"><span data-stu-id="cb964-301">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    
    - <span data-ttu-id="cb964-302">搜尋、電子文件探索和 Delve 對加密的檔案將不適用。</span><span class="sxs-lookup"><span data-stu-id="cb964-302">Search, eDiscovery, and Delve will not work for encrypted files.</span></span> 
    - <span data-ttu-id="cb964-303">DLP 原則對這些加密檔案的中繼資料 (包括保留標籤資訊) 有效，但對這些檔案的內容 (例如檔案中的信用卡號碼) 沒有效用。</span><span class="sxs-lookup"><span data-stu-id="cb964-303">DLP policies work for the metadata of these encrypted files (including retention label information) but not the content of these files (such as credit card numbers within files).</span></span>
    - <span data-ttu-id="cb964-304">使用者無法使用 Office 網頁版開啟加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="cb964-304">Users can't open encrypted files using Office on the web.</span></span> <span data-ttu-id="cb964-305">啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤時，使用者可以使用 Office 網頁版來開啟加密的檔案，但有一些[限制](sensitivity-labels-sharepoint-onedrive-files.md#limitations)，其中包括已使用內部部署金鑰 (稱為「保存您自己的金鑰」或 HYOK) 套用的加密，以及已獨立於敏感度標籤套用的加密。</span><span class="sxs-lookup"><span data-stu-id="cb964-305">When sensitivity labels for Office files in SharePoint and OneDrive is enabled, users can use Office on the web to open encrypted files, with some [limitations](sensitivity-labels-sharepoint-onedrive-files.md#limitations) that include encryption that has been applied with an on-premises key (known as "hold your own key", or HYOK), and encryption that has been applied independently from a sensitivity label.</span></span>

- <span data-ttu-id="cb964-306">若要讓多個使用者同時編輯加密的檔案，他們都必須使用 Office 網頁版。</span><span class="sxs-lookup"><span data-stu-id="cb964-306">For multiple users to edit an encrypted file at the same time, they must all be using Office for the web.</span></span> <span data-ttu-id="cb964-307">如果未這麼做，而且檔案已經開啟：</span><span class="sxs-lookup"><span data-stu-id="cb964-307">If this isn't the case, and the file is already open:</span></span>
    
    - <span data-ttu-id="cb964-308">在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中，使用者會看到 [檔案使用中]\*\*\*\* 訊息，其中包含已簽出檔案的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="cb964-308">In Office apps (Windows, Mac, Android, and iOS), users see a **File In Use** message with the name of the person who has checked out the file.</span></span> <span data-ttu-id="cb964-309">然後，他們可以檢視唯讀複本，或儲存並編輯檔案的複本，並在檔案可用時收到通知。</span><span class="sxs-lookup"><span data-stu-id="cb964-309">They can then view a read-only copy or save and edit a copy of the file, and receive notification when the file is available.</span></span>
    - <span data-ttu-id="cb964-310">在 Office 網頁版中，使用者會看到錯誤訊息，指出他們無法與其他人一起編輯該文件。</span><span class="sxs-lookup"><span data-stu-id="cb964-310">In Office for the web, users see an error message that they can't edit the document with other people.</span></span> <span data-ttu-id="cb964-311">然後他們可以選取 [在閱讀檢視中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb964-311">They can then select **Open in Reading View**.</span></span>

- <span data-ttu-id="cb964-312">Office 應用程式 (Windows、Mac、Android 和 iOS) 中的[自動儲存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)功能已對加密的檔案停用。</span><span class="sxs-lookup"><span data-stu-id="cb964-312">The [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality in Office apps (Windows, Mac, Android, and iOS) is disabled for encrypted files.</span></span> <span data-ttu-id="cb964-313">使用者會看到一則訊息，指出檔案具有必須移除的權限限制，之後才可以開啟「自動儲存」。</span><span class="sxs-lookup"><span data-stu-id="cb964-313">Users see a message that the file has restricted permissions that must be removed before AutoSave can be turned on.</span></span>

- <span data-ttu-id="cb964-314">在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中開啟加密的檔案可能需要較長的時間才能開啟。</span><span class="sxs-lookup"><span data-stu-id="cb964-314">Encrypted files might take longer to open in Office apps (Windows, Mac, Android, and iOS).</span></span>

- <span data-ttu-id="cb964-315">用於已加密檔案的下列動作在 Office 應用程式 (Windows、Mac、Android 和 iOS) 中不受支援，因此使用者會看到錯誤訊息，指出發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="cb964-315">The following actions for encrypted files aren't supported from Office apps (Windows, Mac, Android, and iOS), and users see an error message that something went wrong.</span></span> <span data-ttu-id="cb964-316">不過，您可以使用 SharePoint 功能做為替代：</span><span class="sxs-lookup"><span data-stu-id="cb964-316">However, SharePoint functionality can be used as an alternative:</span></span>
    
    - <span data-ttu-id="cb964-317">檢視、還原和儲存舊版的複本。</span><span class="sxs-lookup"><span data-stu-id="cb964-317">View, restore, and save copies of previous versions.</span></span> <span data-ttu-id="cb964-318">或者，當您[為清單或文件庫啟用和設定版本設定](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37)時，使用者可以使用 Office 網頁版執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="cb964-318">As an alternative, users can do these actions using Office on the web when you [enable and configure versioning for a list or library](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).</span></span> 
    - <span data-ttu-id="cb964-319">變更檔案的名稱或位置。</span><span class="sxs-lookup"><span data-stu-id="cb964-319">Change the name or location of files.</span></span> <span data-ttu-id="cb964-320">或者，使用者可以在 SharePoint 中[重新命名文件庫中的檔案、資料夾或連結](https://support.office.com/article/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185)。</span><span class="sxs-lookup"><span data-stu-id="cb964-320">As an alternative, users can [rename a file, folder, or link in a document library](https://support.office.com/article/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) in SharePoint.</span></span>

<span data-ttu-id="cb964-321">若要獲得使用敏感度標籤加密之檔案的最佳共同作業體驗，建議您[為 SharePoint 和 OneDrive 中的 Office 檔案中使用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)和 Office 網頁版。</span><span class="sxs-lookup"><span data-stu-id="cb964-321">For the best collaboration experience for files that are encrypted by a sensitivity label, we recommend you use [sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) and Office for the web.</span></span> 

## <a name="important-prerequisites"></a><span data-ttu-id="cb964-322">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="cb964-322">Important prerequisites</span></span>

<span data-ttu-id="cb964-323">在您可以使用加密之前，您可能需要執行一些組態工作。</span><span class="sxs-lookup"><span data-stu-id="cb964-323">Before you can use encryption, you might need to do some configuration tasks.</span></span>

### <a name="activate-protection-from-azure-information-protection"></a><span data-ttu-id="cb964-324">啟用來自 Azure 資訊保護的保護</span><span class="sxs-lookup"><span data-stu-id="cb964-324">Activate protection from Azure Information Protection</span></span>

<span data-ttu-id="cb964-325">若要讓敏感度標籤套用加密，必須為您的租用戶啟用來自 Azure 資訊保護的保護服務 (Azure 版權管理)。</span><span class="sxs-lookup"><span data-stu-id="cb964-325">For sensitivity labels to apply encryption, the protection service (Azure Rights Management) from Azure Information Protection must be activated for your tenant.</span></span> <span data-ttu-id="cb964-326">在較新的租用戶中，這是預設設定，但您可能需要手動啟用該服務。</span><span class="sxs-lookup"><span data-stu-id="cb964-326">In newer tenants, this is the default setting, but you might need to manually activate the service.</span></span> <span data-ttu-id="cb964-327">如需詳細資訊，請參閱[啟用來自 Azure 資訊保護的保護服務](https://docs.microsoft.com/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="cb964-327">For more information, see [Activating the protection service from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="cb964-328">設定 Exchange 進行 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="cb964-328">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="cb964-p146">在使用者可在 Outlook 中套用標籤以保護其電子郵件之前，不必設定 Exchange 進行 Azure 資訊保護。不過，直到設定 Exchange 進行 Azure 資訊保護前，您都無法取得使用 Azure Rights Management 保護與 Exchange 搭配的完整功能。</span><span class="sxs-lookup"><span data-stu-id="cb964-p146">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="cb964-331">例如，使用者無法在行動電話或 Outlook 網頁版上檢視受保護的電子郵件，無法為受保護的電子郵件編製索引進行搜尋，而且您無法設定 Exchange Online DLP 進行 Rights Management 保護。</span><span class="sxs-lookup"><span data-stu-id="cb964-331">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="cb964-332">若要確保 Exchange 可以支援這些額外情節，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="cb964-332">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="cb964-333">針對 Exchange Online，請參閱 [Exchange Online：IRM 設定](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)的指示。</span><span class="sxs-lookup"><span data-stu-id="cb964-333">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
- <span data-ttu-id="cb964-334">針對 Exchange 內部部署，您必須部署 [RMS 連接器和設定您的 Exchange Server](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="cb964-334">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span> 
