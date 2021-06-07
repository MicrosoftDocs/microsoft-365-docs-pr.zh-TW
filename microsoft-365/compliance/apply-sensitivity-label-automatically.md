---
title: 自動將敏感性標籤套用到 Microsoft 365 中的內容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 建立敏感度標籤時，您可以自動為檔案和電子郵件指派標籤，或者也可以提示使用者選取您建議的標籤。
ms.openlocfilehash: 4c39e5895c3315d77d7bfc211f0ba3e65f06659b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769290"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="d76a2-103">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="d76a2-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="d76a2-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="d76a2-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="d76a2-105">如需在 Azure Purview (預覽) 中自動套用敏感度標籤的相關資訊，請參閱[在 Azure Purview 中自動為您的內容加上標籤](/azure/purview/create-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-105">For information about automatically applying a sensitivity label in Azure Purview (preview), see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

<span data-ttu-id="d76a2-106">當您建立敏感度標籤時，您可以在該標籤符合您指定的條件時，自動將其指派給檔案和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d76a2-106">When you create a sensitivity label, you can automatically assign that label to files and emails when it matches conditions that you specify.</span></span>

<span data-ttu-id="d76a2-107">能夠自動將敏感度標籤套用到內容很重要，因為：</span><span class="sxs-lookup"><span data-stu-id="d76a2-107">This ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="d76a2-108">您不需要訓練您的使用者使用各個分類的時機。</span><span class="sxs-lookup"><span data-stu-id="d76a2-108">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="d76a2-109">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="d76a2-109">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="d76a2-110">使用者不再需要了解原則，而是可以專心於工作。</span><span class="sxs-lookup"><span data-stu-id="d76a2-110">Users no longer need to know about your policies—they can instead focus on their work.</span></span>

<span data-ttu-id="d76a2-111">手動將內容套用標籤時，該標籤永遠不會被自動套用標籤取代。</span><span class="sxs-lookup"><span data-stu-id="d76a2-111">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="d76a2-112">不過，自動套用標籤可取代自動套用的[低優先順序標籤](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-112">However, automatic labeling can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was automatically applied.</span></span>

<span data-ttu-id="d76a2-113">對 Microsoft 365 中的內容自動套用敏感度標籤有兩種不同的方法：</span><span class="sxs-lookup"><span data-stu-id="d76a2-113">There are two different methods for automatically applying a sensitivity label to content in Microsoft 365:</span></span>

- <span data-ttu-id="d76a2-114">**使用者編輯文件或撰寫 (回覆或轉寄) 電子郵件時的用戶端套用標籤**：使用針對檔案和電子郵件 (包括 Word、Excel、PowerPoint 和 Outlook) 自動套用標籤所設定的標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-114">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for files and emails (includes Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="d76a2-115">此方法支援向使用者建議標籤，以及自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-115">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="d76a2-116">但是在這兩種情況下，使用者都會決定接受或拒絕標籤，以協助確保正確為內容套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-116">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="d76a2-117">此用戶端加標籤對於文件有最小延遲，因為您甚至可以在儲存文件之前套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-117">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="d76a2-118">不過，並非所有用戶端應用程式都支援自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-118">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="d76a2-119">這項功能受 Azure 資訊保護整合標籤用戶端和[部分 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)的支援。</span><span class="sxs-lookup"><span data-stu-id="d76a2-119">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="d76a2-120">如需設定指示，請參閱在此頁面上的[如何設定適用於 Office 應用程式的自動套用標籤](#how-to-configure-auto-labeling-for-office-apps)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-120">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="d76a2-121">**內容已儲存 (在 SharePoint 或 OneDrive 中) 或寄送電子郵件 (由 Exchange Online 處理) 時的服務端套用標籤**：使用自動套用標籤原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-121">**Service-side labeling when content is already saved (in SharePoint or OneDrive) or emailed (processed by Exchange Online)**: Use an auto-labeling policy.</span></span> 
    
    <span data-ttu-id="d76a2-p103">您可能也聽過此方法稱為待用資料 (SharePoint 和 OneDrive 中的文件) 以及傳輸中的資料 (由 Exchange 傳送或接收的電子郵件) 的自動套用標籤。若是 Exchange，則不會包括待用電子郵件 (信箱)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p103">You might also hear this method referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange). For Exchange, it doesn't include emails at rest (mailboxes).</span></span>
    
    <span data-ttu-id="d76a2-124">由於此標籤是由服務套用，而不是由應用程式套用，因此您不需要擔心使用者擁有哪些應用程式及其版本。</span><span class="sxs-lookup"><span data-stu-id="d76a2-124">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="d76a2-125">如此一來，您就能立即在整個組織中使用這項功能，並且適用於大規模套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-125">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="d76a2-126">自動套用標籤原則不支援建議的標籤，因為使用者不會與套用標籤程序進行互動。</span><span class="sxs-lookup"><span data-stu-id="d76a2-126">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="d76a2-127">相反地，系統管理員會在模擬模式中執行原則，以協助確保在實際套用標籤之前，內容正確套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-127">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="d76a2-128">如需設定指示，請參閱此頁面上的[如何設定 SharePoint、OneDrive 和 Exchange 的自動套用標籤原則](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-128">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="d76a2-129">SharePoint 和 OneDrive 自動套用標籤專屬限制：</span><span class="sxs-lookup"><span data-stu-id="d76a2-129">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="d76a2-p105">支援 Word、PowerPoint 和 Excel 等 Office 檔案。支援 Open XML 格式 (例如 .docx 和 .xlsx)，但不支援 Microsoft Office 97-2003 格式 (例如 .doc 和 .xls)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p105">Office files for Word, PowerPoint, and Excel are supported. Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls).</span></span>
        - <span data-ttu-id="d76a2-132">這些檔案可在建立自動套用標籤原則之前或之後，以靜止方式自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-132">These files can be auto-labeled at rest before or after the auto-labeling policies are created.</span></span> <span data-ttu-id="d76a2-133">請注意，如果檔案是開啟工作階段的一部分 (檔案已開啟) ，則無法自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-133">Note that files cannot be auto-labeled if they are part of an open session (the file is open).</span></span>
    - <span data-ttu-id="d76a2-134">租用戶中每日最多有 25,000 個自動套用標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="d76a2-134">Maximum of 25,000 automatically labeled files in your tenant per day.</span></span>
    - <span data-ttu-id="d76a2-135">每個租用戶最多 10 個自動套用標籤的原則，每個最多可用於 10 個網站（SharePoint 或 OneDrive）。</span><span class="sxs-lookup"><span data-stu-id="d76a2-135">Maximum of 10 auto-labeling policies per tenant, each targeting up to 10 sites (SharePoint or OneDrive).</span></span>
    - <span data-ttu-id="d76a2-136">自動標籤原則不會造成修改時間、修改者和日期的現有值變更 (對於兩個模擬模式和套用標籤時)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-136">Existing values for modified, modified by, and the date are not changed as a result of auto-labeling policies—for both simulation mode and when labels are applied.</span></span>
    - <span data-ttu-id="d76a2-137">當標籤套用加密時，[版權管理簽發者和版權管理擁有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)會是上次修改檔案的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d76a2-137">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the account that last modified the file.</span></span>

    <span data-ttu-id="d76a2-138">Exchange 自動套用標籤專屬限制：</span><span class="sxs-lookup"><span data-stu-id="d76a2-138">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="d76a2-p107">不同於 Office 應用程式的手動套用標籤或自動套用標籤，PDF 附件和 office 附件 (Word、Excel 和 PowerPoint 檔案) 也會針對您在自動套用標籤原則中指定的條件進行掃描。有相符項目時，電子郵件會套用標籤，但是附件不會。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p107">Unlike manual labeling or auto-labeling with Office apps, PDF attachments as well as Office attachments (Word, Excel, and PowerPoint files) are also scanned for the conditions you specify in your auto-labeling policy. When there is a match, the email is labeled but not the attachment.</span></span>
        - <span data-ttu-id="d76a2-141">對於 PDF 檔案，如果標籤套用加密，則當您的租用戶[啟用 PDF 附件](ome-faq.yml#are-pdf-file-attachments-supported-)時，這些檔案將被加密。</span><span class="sxs-lookup"><span data-stu-id="d76a2-141">For PDF files, if the label applies encryption, these files are encrypted when your tenant is [enabled for PDF attachments](ome-faq.yml#are-pdf-file-attachments-supported-).</span></span>
        - <span data-ttu-id="d76a2-p108">對於這些 Office 檔案，支援 Open XML 格式 (如 .docx 和 .xlsx)，但不支援 Microsoft Office 97-2003 格式 (如 .doc 和 .xls)。如果標籤套用加密，則這些檔案將被加密。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p108">For these Office files, Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls). If the label applies encryption, these files are encrypted.</span></span>
    - <span data-ttu-id="d76a2-144">如果您有套用 IRM 加密的 Exchange 郵件流程規則或資料外洩防護 (DLP) 原則：當內容由這些規則或原則和自動套用標籤原則識別時，則會套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-144">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="d76a2-145">如果該標籤套用加密，則會忽略 Exchange 郵件流程規則或 DLP 原則的 IRM 設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-145">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="d76a2-146">不過，如果該標籤並未套用加密，除了標籤以外，還會套用郵件流程規則或 DLP 原則的 IRM 設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-146">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="d76a2-147">當有一個相符項目使用自動套用標籤時，具有 IRM 加密而沒有標籤的電子郵件，將會由具有任何加密設定的標籤取代。</span><span class="sxs-lookup"><span data-stu-id="d76a2-147">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="d76a2-148">當有項目與您的自動套用標籤條件相符時，內送電子郵件會套用標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-148">Incoming email is labeled when there is a match with your auto-labeling conditions:</span></span>
        - <span data-ttu-id="d76a2-149">如果標籤針對 [加密](encryption-sensitivity-labels.md) 進行設定，則會套用加密。</span><span class="sxs-lookup"><span data-stu-id="d76a2-149">If the label is configured for [encryption](encryption-sensitivity-labels.md), that encryption is applied.</span></span> <span data-ttu-id="d76a2-150">不過，目前不支援此設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-150">However, this configuration isn't currently supported.</span></span>
        - <span data-ttu-id="d76a2-151">如果標籤設定為套用 [動態標記](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)，請注意，這可能導致人員名稱會在組織的外部。</span><span class="sxs-lookup"><span data-stu-id="d76a2-151">If the label is configured to apply [dynamic markings](sensitivity-labels-office-apps.md#dynamic-markings-with-variables), be aware that this can result in the names of people outside your organization.</span></span>
    - <span data-ttu-id="d76a2-152">當標籤套用加密時，[版權管理頒發者和版權管理擁有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)會是傳送電子郵件的人員。</span><span class="sxs-lookup"><span data-stu-id="d76a2-152">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the person who sends the email.</span></span> <span data-ttu-id="d76a2-153">目前無法為自動加密的所有內建電子郵件訊息，設定版權管理員擁有者。</span><span class="sxs-lookup"><span data-stu-id="d76a2-153">There currently isn't a way to set a Rights Manager owner for all incoming email messages that are automatically encrypted.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="d76a2-154">比較 Office 應用程式的自動套用標籤與自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="d76a2-154">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="d76a2-155">使用下表來協助您識別兩個互補自動套用標籤方法的行為差異：</span><span class="sxs-lookup"><span data-stu-id="d76a2-155">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="d76a2-156">功能或行為</span><span class="sxs-lookup"><span data-stu-id="d76a2-156">Feature or behavior</span></span>|<span data-ttu-id="d76a2-157">標籤設定：檔案和電子郵件的自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-157">Label setting: Auto-labeling for files and emails</span></span>  |<span data-ttu-id="d76a2-158">原則：自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-158">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d76a2-159">應用程式相依性</span><span class="sxs-lookup"><span data-stu-id="d76a2-159">App dependency</span></span>|[<span data-ttu-id="d76a2-160">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-160">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="d76a2-161">否\*</span><span class="sxs-lookup"><span data-stu-id="d76a2-161">No \*</span></span> |
|<span data-ttu-id="d76a2-162">依位置限制</span><span class="sxs-lookup"><span data-stu-id="d76a2-162">Restrict by location</span></span>|<span data-ttu-id="d76a2-163">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-163">No</span></span> |<span data-ttu-id="d76a2-164">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-164">Yes</span></span> |
|<span data-ttu-id="d76a2-165">條件：可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="d76a2-165">Conditions: Trainable classifiers</span></span>|<span data-ttu-id="d76a2-166">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-166">Yes</span></span> |<span data-ttu-id="d76a2-167">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-167">No</span></span> |
|<span data-ttu-id="d76a2-168">條件：共用選項和電子郵件的其他選項</span><span class="sxs-lookup"><span data-stu-id="d76a2-168">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="d76a2-169">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-169">No</span></span> |<span data-ttu-id="d76a2-170">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-170">Yes</span></span> |
|<span data-ttu-id="d76a2-171">建議、原則工具提示及使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="d76a2-171">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="d76a2-172">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-172">Yes</span></span> |<span data-ttu-id="d76a2-173">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-173">No</span></span> |
|<span data-ttu-id="d76a2-174">模擬模式</span><span class="sxs-lookup"><span data-stu-id="d76a2-174">Simulation mode</span></span>|<span data-ttu-id="d76a2-175">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-175">No</span></span> |<span data-ttu-id="d76a2-176">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-176">Yes</span></span> |
|<span data-ttu-id="d76a2-177">已針對條件檢查 Exchange 附件</span><span class="sxs-lookup"><span data-stu-id="d76a2-177">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="d76a2-178">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-178">No</span></span> | <span data-ttu-id="d76a2-179">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-179">Yes</span></span>|
|<span data-ttu-id="d76a2-180">套用視覺標記</span><span class="sxs-lookup"><span data-stu-id="d76a2-180">Apply visual markings</span></span> |<span data-ttu-id="d76a2-181">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-181">Yes</span></span> |<span data-ttu-id="d76a2-182">是 (僅限電子郵件)</span><span class="sxs-lookup"><span data-stu-id="d76a2-182">Yes (email only)</span></span> |
|<span data-ttu-id="d76a2-183">已套用覆寫 IRM 加密但沒有標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-183">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="d76a2-184">如果使用者只有匯出的最小使用權限，則為是。</span><span class="sxs-lookup"><span data-stu-id="d76a2-184">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="d76a2-185">是 (僅限電子郵件)</span><span class="sxs-lookup"><span data-stu-id="d76a2-185">Yes (email only)</span></span> |
|<span data-ttu-id="d76a2-186">將內送電子郵件套用標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-186">Label incoming email</span></span>|<span data-ttu-id="d76a2-187">否</span><span class="sxs-lookup"><span data-stu-id="d76a2-187">No</span></span> |<span data-ttu-id="d76a2-188">是</span><span class="sxs-lookup"><span data-stu-id="d76a2-188">Yes</span></span>|

<span data-ttu-id="d76a2-189">\* 目前並非所有地區都提供自動套用標籤功能。</span><span class="sxs-lookup"><span data-stu-id="d76a2-189">\* Auto-labeling isn't currently available in all regions.</span></span> <span data-ttu-id="d76a2-190">如果您的租用戶無法支援這項功能，[系統管理標籤中心] 就不會顯示 [自動套用標籤] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-190">If your tenant can't support this functionality, the Auto-labeling tab isn't visible in the admin labeling center.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="d76a2-191">將多個條件套用到多個標籤時的評估方式</span><span class="sxs-lookup"><span data-stu-id="d76a2-191">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="d76a2-p113">標籤會根據您在原則中指定的標籤位置，針對評估進行排序：位於第一個位置的標籤具有最低的位置 (敏感度最低)，而位於最後一個位置的標籤具有最高的位置 (敏感度最高)。如需有關原則的詳細資訊，請參閱[標籤優先順序 (排序事項)](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p113">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="d76a2-194">請勿設定將上層標籤設定為自動套用或建議選項</span><span class="sxs-lookup"><span data-stu-id="d76a2-194">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="d76a2-195">請記得，您無法將上層標籤 (具有子標籤的標籤) 套用至內容。</span><span class="sxs-lookup"><span data-stu-id="d76a2-195">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="d76a2-196">請確認您沒有設定在 Office 應用程式中自動套用或推薦的上層標籤，且沒有為自動標籤原則選取上層標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-196">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="d76a2-197">如果這麼做，系統就不會將上層標籤套用至內容。</span><span class="sxs-lookup"><span data-stu-id="d76a2-197">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="d76a2-198">若要搭配子標籤使用上層標籤標籤，請務必同時發佈上層標籤和子標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-198">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="d76a2-199">如需上層標籤和子標籤的詳細資訊，請參閱[子標籤 (分組標籤)](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-199">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="d76a2-200">如何設定適用於 Office 應用程式的自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-200">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="d76a2-201">在 Windows 版 Office 應用程式中的自動標籤，是由 Azure 資訊保護整合標籤用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="d76a2-201">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="d76a2-202">對於 Office 應用程式中的內建標籤，此功能 [ 對不同的應用程式，處於不同的可用性階段 ](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-202">For built-in labeling in Office apps, this capability is in [different stages of availability for different apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="d76a2-203">當您[建立或編輯敏感度標籤](create-sensitivity-labels.md)時，可使用適用於 Office 應用程式的自動套用標籤設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-203">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md).</span></span> <span data-ttu-id="d76a2-204">請確定已針對標籤的範圍選取 **[檔案和電子郵件]**：</span><span class="sxs-lookup"><span data-stu-id="d76a2-204">Make sure **Files & emails** is selected for the label's scope:</span></span> 

![檔案和電子郵件的敏感度標籤範圍選項](../media/filesandemails-scope-options-sensitivity-label.png)

<span data-ttu-id="d76a2-206">當您在精靈中移動時，您會看到 [檔案和電子郵件的自動套用標籤 **]** 頁面，您可以在其中從敏感性資訊類型或可訓練分類器清單中選擇：</span><span class="sxs-lookup"><span data-stu-id="d76a2-206">As you move through the wizard, you see the **Auto-labeling for files and emails** page where you can choose from a list of sensitive info types or trainable classifiers:</span></span>

![在 Office 應用程式中自動套用標籤的標籤條件](../media/sensitivity-labels-conditions.png)

<span data-ttu-id="d76a2-p117">自動套用此敏感度標籤時，使用者會在其 Office 應用程式中看到通知。例如：</span><span class="sxs-lookup"><span data-stu-id="d76a2-p117">When this sensitivity label is automatically applied, the user sees a notification in their Office app. For example:</span></span>

![文件已自動套用標籤的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="d76a2-211">設定標籤的敏感度資訊類型</span><span class="sxs-lookup"><span data-stu-id="d76a2-211">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="d76a2-212">當您選取 **[敏感度資訊類型]** 選項時，會看到與在建立資料外洩防護 (DLP) 原則時相同的敏感度資訊類型清單。</span><span class="sxs-lookup"><span data-stu-id="d76a2-212">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="d76a2-213">例如，您可以自動將 [高度機密] 標籤套用至任何包含客戶個人資訊的內容，例如信用卡號碼、社會安全碼或身分證號碼：</span><span class="sxs-lookup"><span data-stu-id="d76a2-213">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personal information, such as credit card numbers, social security numbers, or passport numbers:</span></span>

![在 Office 應用程式中自動套用標籤的敏感資訊類型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="d76a2-p119">同樣的，當您在設定 DLP 原則時，藉由改變執行個體計數及比對精確度，您可以精簡您的條件。例如：</span><span class="sxs-lookup"><span data-stu-id="d76a2-p119">Similarly to when you configure DLP policies, you can then refine your condition by changing the instance count and match accuracy. For example:</span></span>

![執行比對精確度和個體計數的選項](../media/sit-confidence-level.png)

<span data-ttu-id="d76a2-218">您可以從 DLP 檔案了解更多有關這些組態選項：[調整規則以讓它們更容易或更難符合](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-218">You can learn more about these configuration options from the DLP documentation: [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="d76a2-219">同時類似於 DLP 原則設定，您可以選擇條件是必須偵測所有敏感性資訊類型，還是只偵測其中一種。</span><span class="sxs-lookup"><span data-stu-id="d76a2-219">Also similarly to DLP policy configuration, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="d76a2-220">若要讓您的條件更靈活或更複雜，您可以新增 [群組，並使用群組間的邏輯運算子](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-220">And to make your conditions more flexible or complex, you can add [groups and use logical operators between the groups](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

### <a name="configuring-trainable-classifiers-for-a-label"></a><span data-ttu-id="d76a2-221">為標籤設定可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="d76a2-221">Configuring trainable classifiers for a label</span></span>

<span data-ttu-id="d76a2-222">此選項目前處於預覽。</span><span class="sxs-lookup"><span data-stu-id="d76a2-222">This option is currently in preview.</span></span> <span data-ttu-id="d76a2-223">如果您使用此選項，請確定您已在您的租用戶中發佈至少另一個其他敏感性標籤，其已設定為自動加標籤和[敏感性資訊類型選項](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-223">If you use this option, make sure you have published in your tenant at least one other sensitivity label that's configured for auto-labeling and the [sensitive info types option](#configuring-sensitive-info-types-for-a-label).</span></span>

<span data-ttu-id="d76a2-224">當您選取 **[可訓練分類器]** 選項時，請選取一或多個 Microsoft 內建可訓練分類器。</span><span class="sxs-lookup"><span data-stu-id="d76a2-224">When you select the **Trainable classifiers** option, select one or more of the built-in trainable classifiers from Microsoft.</span></span> <span data-ttu-id="d76a2-225">如果您已建立自己的自訂可訓練分類器，也可以選取這些分類器：</span><span class="sxs-lookup"><span data-stu-id="d76a2-225">If you've created your own custom trainable classifiers, these are also available to select:</span></span>

![可訓練分類器和敏感度標籤的選項](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> <span data-ttu-id="d76a2-227">我們正在淘汰 [粗穢言語] 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="d76a2-227">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="d76a2-228">請不要使用這個內建分類器，如果您目前正在使用此分類器，請將您的商務流程移開。</span><span class="sxs-lookup"><span data-stu-id="d76a2-228">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="d76a2-229">建議您改用 **[針對性騷擾]**、**[粗話]** 和 **[威脅]** 內建分類器。</span><span class="sxs-lookup"><span data-stu-id="d76a2-229">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="d76a2-230">如需這些分類器的詳細資訊，請參閱[深入了解可訓練分類器](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-230">For more information about these classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="d76a2-231">在此選項的預覽期間，下列應用程式支援敏感度標籤的可訓練分類器：</span><span class="sxs-lookup"><span data-stu-id="d76a2-231">During the preview period for this option, the following apps support trainable classifiers for sensitivity labels:</span></span>

- <span data-ttu-id="d76a2-232">適用於 Windows 的 Microsoft 365 Apps 企業版 (之前稱為 [Office 365 專業增強版](/deployoffice/name-change))，現已在版本 2006 和更新版本中的[目前通道](/deployoffice/overview-update-channels#current-channel-overview)推出：</span><span class="sxs-lookup"><span data-stu-id="d76a2-232">Microsoft 365 Apps for enterprise ([formerly Office 365 ProPlus](/deployoffice/name-change)) for Windows, now rolling out to the [Current Channel](/deployoffice/overview-update-channels#current-channel-overview) in version 2006 and later:</span></span>
    - <span data-ttu-id="d76a2-233">Word</span><span class="sxs-lookup"><span data-stu-id="d76a2-233">Word</span></span>
    - <span data-ttu-id="d76a2-234">Excel</span><span class="sxs-lookup"><span data-stu-id="d76a2-234">Excel</span></span>
    - <span data-ttu-id="d76a2-235">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d76a2-235">PowerPoint</span></span>

- <span data-ttu-id="d76a2-236">當您[在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)時的 Office 網頁版應用程式：</span><span class="sxs-lookup"><span data-stu-id="d76a2-236">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="d76a2-237">Word</span><span class="sxs-lookup"><span data-stu-id="d76a2-237">Word</span></span>
    - <span data-ttu-id="d76a2-238">Excel</span><span class="sxs-lookup"><span data-stu-id="d76a2-238">Excel</span></span>
    - <span data-ttu-id="d76a2-239">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d76a2-239">PowerPoint</span></span>
    - <span data-ttu-id="d76a2-240">Outlook</span><span class="sxs-lookup"><span data-stu-id="d76a2-240">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="d76a2-241">建議使用者套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d76a2-241">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="d76a2-p124">您可以視需要建議使用者套用標籤。如果您使用此選項，您的使用者就可以接受分類和任何相關的保護，或者當標籤不適合內容時，可以取消建議。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p124">If you prefer, you can recommend to your users that they apply the label. With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![向使用者建議敏感度標籤的選項](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="d76a2-p125">以下舉例說明當您設定條件而將套用標籤作為建議動作 (含自訂原則提示) 時，來自 Azure 資訊保護整合標籤用戶端的提示。您可以選擇要在原則提示中顯示的文字。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p125">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![套用建議標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="d76a2-248">當套用自動或建議標籤時</span><span class="sxs-lookup"><span data-stu-id="d76a2-248">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="d76a2-p126">是否會在 Office 應用程式中實作自動化的建議標籤功能，取決於您使用的是 Office 內建的標籤功能，還是 Azure 資訊保護的整合標籤用戶端。然而，在這兩種情况下：</span><span class="sxs-lookup"><span data-stu-id="d76a2-p126">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client. In both cases, however:</span></span>

- <span data-ttu-id="d76a2-p127">如果文件或電子郵件之前已手動套用標籤，或之前已使用較高敏感度自動套用標籤，則無法使用自動套用標籤功能。請切記，您只能將單一敏感度標籤套用到文件或電子郵件 (單一保留標籤也是如此)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p127">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity. Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="d76a2-p128">您無法針對之前已加上較高敏感性標籤的文件或電子郵件使用建議標籤。如果內容已加上較高敏感性標籤，使用者將不會看到含有建議和原則提示的提示。</span><span class="sxs-lookup"><span data-stu-id="d76a2-p128">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity. When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="d76a2-255">專用於內建標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-255">Specific to built-in labeling:</span></span>

- <span data-ttu-id="d76a2-256">並非所有的 Office 應用程式都支援自動化 (建議) 標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-256">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="d76a2-257">如需詳細資訊，請參閱[在應用程式中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-257">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="d76a2-258">若為電腦版 Word 中的建議標籤，系統會標示觸發了建議的敏感性內容，讓使用者可以檢閱和移除敏感性內容，而不是套用建議的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-258">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="d76a2-259">如需這些標籤在 Office 應用程式中的套用方式、範例螢幕擷取畫面，以及系統如何偵測到敏感性資訊的詳細資訊，請參閱[在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-259">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="d76a2-260">專用於 Azure 資訊保護的整合標籤用戶端：</span><span class="sxs-lookup"><span data-stu-id="d76a2-260">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="d76a2-261">自動化的建議標籤功能適用於您儲存文件時所使用的 Word、Excel 和 PowerPoint，以及傳送電子郵件時的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d76a2-261">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="d76a2-262">若要讓 Outlook 支援建議標籤，您必須先設定[進階原則設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-262">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="d76a2-263">系統可於文件和電子郵件的本文，以及頁首及頁尾中偵測到敏感性資訊，但無法在電子郵件的主旨列或附件中偵測到敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="d76a2-263">Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="d76a2-264">如何設定 SharePoint、OneDrive 和 Exchange 的自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="d76a2-264">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>

<span data-ttu-id="d76a2-265">設定自動套用標籤原則之前，請確認您已經知道先決條件。</span><span class="sxs-lookup"><span data-stu-id="d76a2-265">Make sure you're aware of the prerequisites before you configure auto-labeling policies.</span></span> 

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="d76a2-266">自動套用標籤原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="d76a2-266">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="d76a2-267">模擬模式：</span><span class="sxs-lookup"><span data-stu-id="d76a2-267">Simulation mode:</span></span>
    - <span data-ttu-id="d76a2-268">必須開啟 Microsoft 365 的稽核功能。</span><span class="sxs-lookup"><span data-stu-id="d76a2-268">Auditing for Microsoft 365 must be turned on.</span></span> <span data-ttu-id="d76a2-269">如果您需要開啟稽核，或者如果您不確定稽核是否開啟，請參閱[開啟或關閉稽核記錄搜尋](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-269">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
    - <span data-ttu-id="d76a2-270">若要在來源檢視中檢視檔案或電子郵件內容，您必須擁有 **內容總管內容檢視者** 角色。</span><span class="sxs-lookup"><span data-stu-id="d76a2-270">To view file or email contents in the source view, you must have the **Content Explorer Content Viewer** role.</span></span> <span data-ttu-id="d76a2-271">預設的全域系統管理員沒有這個角色。</span><span class="sxs-lookup"><span data-stu-id="d76a2-271">Global admins don't have this role by default.</span></span> <span data-ttu-id="d76a2-272">如果您沒有這個使用權限，當您從 **[相符的項目]** 索引標籤中選取項目時，就不會看到預覽窗格。</span><span class="sxs-lookup"><span data-stu-id="d76a2-272">If you don't have this permission, you don't see the preview pane when you select an item from the **Matched Items** tab.</span></span>

- <span data-ttu-id="d76a2-273">若要對 SharePoint 和 OneDrive 中的檔案自動套用標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-273">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="d76a2-274">您必須[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-274">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="d76a2-275">當自動套用標籤原則執行時，檔案不能由其他程序或使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="d76a2-275">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span> <span data-ttu-id="d76a2-276">簽出以編輯的檔案屬於這個類別。</span><span class="sxs-lookup"><span data-stu-id="d76a2-276">A file that's checked out for editing falls into this category.</span></span>

- <span data-ttu-id="d76a2-277">如果您計劃使用[自訂敏感性資訊類型](sensitive-information-type-learn-about.md)，而不是內建的敏感性類型：</span><span class="sxs-lookup"><span data-stu-id="d76a2-277">If you plan to use [custom sensitive information types](sensitive-information-type-learn-about.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="d76a2-278">針對在儲存自訂敏感度資訊類型之後新增至 SharePoint 或 OneDrive 的內容，會評估該內容的自訂敏感度資訊類型。</span><span class="sxs-lookup"><span data-stu-id="d76a2-278">Custom sensitivity information types are evaluated for content that is added to SharePoint or OneDrive after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="d76a2-279">若要測試新的自訂敏感性資訊類型，請在建立您的自動套用標籤原則之前建立，然後建立含有範例資料的新文件以進行測試。</span><span class="sxs-lookup"><span data-stu-id="d76a2-279">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="d76a2-280">一或多個敏感性標籤[已建立和已發佈](create-sensitivity-labels.md) (給至少一個使用者)，這些標籤可供您針對自動套用標籤原則選取。</span><span class="sxs-lookup"><span data-stu-id="d76a2-280">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="d76a2-281">針對這些標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-281">For these labels:</span></span>
    - <span data-ttu-id="d76a2-282">Office 應用程式中的自動套用標籤標籤設定開啟與否並不重要，因為該標籤設定是補充自動套用標籤原則，如簡介中的說明。</span><span class="sxs-lookup"><span data-stu-id="d76a2-282">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span>
    - <span data-ttu-id="d76a2-283">如果您想要用於自動套用標籤的標籤是設定為使用視覺標記 (頁首、頁尾、浮水印)，請注意，這些標籤不適用於文件。</span><span class="sxs-lookup"><span data-stu-id="d76a2-283">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="d76a2-284">若標籤套用 [加密](encryption-sensitivity-labels.md)：</span><span class="sxs-lookup"><span data-stu-id="d76a2-284">If the labels apply [encryption](encryption-sensitivity-labels.md):</span></span>
        - <span data-ttu-id="d76a2-285">當自動套用標籤原則包括了 Microsoft Office SharePoint Online 或 Microsoft OneDrive 的位置時，此標籤必須針對 **立即指派權限** 進行設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-285">When the auto-labeling policy includes locations for SharePoint or OneDrive, the label must be configured for the **Assign permissions now** setting.</span></span>
        - <span data-ttu-id="d76a2-286">當自動套用標籤原則只針對 Exchange Online，此標籤可針對 **立即指派權限** 或 **讓使用者指派權限** (適用於不可轉寄或僅加密選項) 進行設定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-286">When the auto-labeling policy is just for Exchange, the label can be configured for either **Assign permissions now** or **Let users assign permissions** (for the Do Not Forward or Encrypt-Only options).</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="d76a2-287">了解模擬模式</span><span class="sxs-lookup"><span data-stu-id="d76a2-287">Learn about simulation mode</span></span>

<span data-ttu-id="d76a2-288">模擬模式是自動套用標籤原則專屬，並且編寫到工作流程中。</span><span class="sxs-lookup"><span data-stu-id="d76a2-288">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="d76a2-289">在您的原則執行至少一個模擬之前，您無法對文件和電子郵件自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-289">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="d76a2-290">自動套用標籤原則的工作流程：</span><span class="sxs-lookup"><span data-stu-id="d76a2-290">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="d76a2-291">建立及設定自動套用標籤原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-291">Create and configure an auto-labeling policy.</span></span>

2. <span data-ttu-id="d76a2-292">在模擬模式中執行原則，這可能需要 48 小時的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="d76a2-292">Run the policy in simulation mode, which can take 48 hours to complete.</span></span>

3. <span data-ttu-id="d76a2-293">查看結果，並視需要調整您的原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-293">Review the results, and if necessary, refine your policy.</span></span> <span data-ttu-id="d76a2-294">重新執行模擬模式，並再次等待其完成。</span><span class="sxs-lookup"><span data-stu-id="d76a2-294">Rerun simulation mode and wait for it to complete again.</span></span>

4. <span data-ttu-id="d76a2-295">視需要重複步驟 3。</span><span class="sxs-lookup"><span data-stu-id="d76a2-295">Repeat step 3 as needed.</span></span>

5. <span data-ttu-id="d76a2-296">在生產環境中部署。</span><span class="sxs-lookup"><span data-stu-id="d76a2-296">Deploy in production.</span></span>

<span data-ttu-id="d76a2-297">模擬的部署執行方式類似 PowerShell 的 WhatIf 參數。</span><span class="sxs-lookup"><span data-stu-id="d76a2-297">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="d76a2-298">您會看到報告的結果，就像是自動套用標籤原則已使用您定義的規則套用您選取的標籤。</span><span class="sxs-lookup"><span data-stu-id="d76a2-298">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="d76a2-299">如果需要，您可以接著調整規則的精確度，並重新執行模擬。</span><span class="sxs-lookup"><span data-stu-id="d76a2-299">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="d76a2-300">不過，由於 Exchange 的自動套用標籤適用於傳送和接收的電子郵件，而不是儲存在信箱中的電子郵件，因此除非您能夠傳送及接收完全相同的電子郵件訊息，否則請不要預期模擬中的電子郵件結果會是一致的。</span><span class="sxs-lookup"><span data-stu-id="d76a2-300">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="d76a2-301">模擬模式也可讓您在部署之前逐漸增加自動套用標籤原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="d76a2-301">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="d76a2-302">例如，您可能會從單一位置 (例如 SharePoint 網站) 的單一文件庫開始使用。</span><span class="sxs-lookup"><span data-stu-id="d76a2-302">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="d76a2-303">接著，使用反覆變更將範圍增加至多個網站，然後增加至其他位置 (例如 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-303">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="d76a2-304">最後，您可以使用模擬模式來提供執行自動套用標籤原則所需時間的近似值，以協助您規劃並排程不使用模擬模式執行的時間。</span><span class="sxs-lookup"><span data-stu-id="d76a2-304">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="d76a2-305">建立自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="d76a2-305">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="d76a2-306">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-306">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="d76a2-307">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="d76a2-307">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="d76a2-308">如果您沒有立即看到這個選項，請先選取 [全部顯示]。</span><span class="sxs-lookup"><span data-stu-id="d76a2-308">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="d76a2-309">選取 **[自動套用標籤]** 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="d76a2-309">Select the **Auto-labeling** tab:</span></span>
    
    ![自動套用標籤](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > <span data-ttu-id="d76a2-311">如果您沒有看到 **[自動套用標籤]** 索引標籤，就代表您的區域目前無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d76a2-311">If you don't see the **Auto-labeling** tab, this functionality isn't currently available in your region.</span></span>

3. <span data-ttu-id="d76a2-312">選取 **+ 建立自動套用標籤原則**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-312">Select **+ Create auto-labeling policy**.</span></span> <span data-ttu-id="d76a2-313">這會啟動 [新原則] 精靈：</span><span class="sxs-lookup"><span data-stu-id="d76a2-313">This starts the New policy wizard:</span></span>
    
    ![<span data-ttu-id="d76a2-314">自動套用標籤的新原則精靈</span><span class="sxs-lookup"><span data-stu-id="d76a2-314">New policy wizard for auto-labeling</span></span> ](../media/auto-labeling-wizard.png)

4. <span data-ttu-id="d76a2-315">針對 **[選擇要套用此標籤的資訊]** 頁面：選取其中一個範本，例如 **財務** 或 **隱私權**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-315">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="d76a2-316">您可以使用 **[顯示下列內容的選項]** 下拉式清單來精簡搜尋。</span><span class="sxs-lookup"><span data-stu-id="d76a2-316">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="d76a2-317">或者，如果範本不符合您的需求，請選取 **[自訂原則]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-317">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="d76a2-318">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-318">Select **Next**.</span></span>

5. <span data-ttu-id="d76a2-319">針對 **[命名您的自動套用標籤原則]** 頁面：提供唯一名稱，以及選擇性提供說明，以協助識別自動套用的標籤、位置和可識別要套用標籤之內容的條件。</span><span class="sxs-lookup"><span data-stu-id="d76a2-319">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="d76a2-320">針對 **[選擇要套用此標籤的資訊]** 頁面：選取並指定 Exchange、SharePoint 網站和 OneDrive 的位置。</span><span class="sxs-lookup"><span data-stu-id="d76a2-320">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="d76a2-321">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-321">Then select **Next**.</span></span>
    
    ![<span data-ttu-id="d76a2-322">選擇位置頁面自動套用標籤精靈</span><span class="sxs-lookup"><span data-stu-id="d76a2-322">Choose locations page auto-labelingwizard</span></span> ](../media/locations-auto-labeling-wizard.png)
    
    <span data-ttu-id="d76a2-323">您必須指定個別的 SharePoint 網站和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="d76a2-323">You must specify individual SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="d76a2-324">若為 OneDrive，使用者 OneDrive 帳戶的 URL 會採用下列格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="d76a2-324">For OneDrive, the URL for a user's OneDrive account is in the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>
    
    <span data-ttu-id="d76a2-325">例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="d76a2-325">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>
    
    <span data-ttu-id="d76a2-326">若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](/onedrive/list-onedrive-urls) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-326">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

7. <span data-ttu-id="d76a2-327">針對 **設定常用或進階規則** 頁面：保留 **常用規則** 的預設以定義可識別要在您所選取所有位置之間套用標籤之內容的規則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-327">For the **Set up common or advanced rules** page: Keep the default of **Common rules** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="d76a2-328">如果您在每個位置都需要不同的規則，請選取 **[進階規則]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-328">If you need different rules per location, select **Advanced rules**.</span></span> <span data-ttu-id="d76a2-329">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-329">Then select **Next**.</span></span>
    
    <span data-ttu-id="d76a2-330">規則會使用條件，其中包括敏感性資訊類型和共用選項：</span><span class="sxs-lookup"><span data-stu-id="d76a2-330">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="d76a2-331">針對敏感性資訊類型，您可以選取內建和自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="d76a2-331">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="d76a2-332">針對共用選項，您可以選擇 **[僅與我組織內部的人員]** 或 **[與我組織外部的人員]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-332">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="d76a2-333">如果您唯一的位置是 **[Exchange]**，或如果您選取 **[進階規則]**，則還可以選取其他條件：</span><span class="sxs-lookup"><span data-stu-id="d76a2-333">If your only location is **Exchange**, or if you select **Advanced rules**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="d76a2-334">寄件者 IP 位址為</span><span class="sxs-lookup"><span data-stu-id="d76a2-334">Sender IP address is</span></span>
    - <span data-ttu-id="d76a2-335">收件者網域為</span><span class="sxs-lookup"><span data-stu-id="d76a2-335">Recipient domain is</span></span>
    - <span data-ttu-id="d76a2-336">收件者為</span><span class="sxs-lookup"><span data-stu-id="d76a2-336">Recipient is</span></span>
    - <span data-ttu-id="d76a2-337">附件的副檔名為</span><span class="sxs-lookup"><span data-stu-id="d76a2-337">Attachment's file extension is</span></span>
    - <span data-ttu-id="d76a2-338">附件受密碼保護</span><span class="sxs-lookup"><span data-stu-id="d76a2-338">Attachment is password protected</span></span>
    - <span data-ttu-id="d76a2-339">無法掃描任何電子郵件附件的內容</span><span class="sxs-lookup"><span data-stu-id="d76a2-339">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="d76a2-340">未完成掃描任何電子郵件附件的內容</span><span class="sxs-lookup"><span data-stu-id="d76a2-340">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="d76a2-341">根據您先前的選擇，您現在有機會使用條件和例外建立新的規則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-341">Depending on your previous choices, you'll now have an opportunity to create new rules by using conditions and exceptions.</span></span>
    
    <span data-ttu-id="d76a2-342">敏感性資訊類型的設定選項，和您針對 Office 應用程式的自動套用標籤所選取的設定選項相同。</span><span class="sxs-lookup"><span data-stu-id="d76a2-342">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="d76a2-343">如需詳細資訊，請參閱[設定標籤的敏感性資訊類型](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-343">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>
    
    <span data-ttu-id="d76a2-344">當您已定義所有需要的規則，並確認其狀態為開啟時，請選取 **[下一步]** 以繼續選擇標籤以自動套用。</span><span class="sxs-lookup"><span data-stu-id="d76a2-344">When you have defined all the rules you need, and confirmed their status is on, select **Next** to move on to choosing a label to auto-apply.</span></span>

11. <span data-ttu-id="d76a2-345">針對 **[選擇要自動套用的標籤]** 頁面：選取 **[+ 選擇標籤]**，從 **[選擇敏感度標籤]** 窗格中選取標籤，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-345">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="d76a2-346">針對 **決定立即或稍後測試原則** 頁面：如果您已準備好立即在模擬模式中執行自動套用標籤原則，請選取 **[在模擬模式中執行原則]** 。</span><span class="sxs-lookup"><span data-stu-id="d76a2-346">For the **Decide if you want to test out the policy now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="d76a2-347">否則，請選取 **[將原則關閉]**。</span><span class="sxs-lookup"><span data-stu-id="d76a2-347">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="d76a2-348">選取 **[下一步]**:</span><span class="sxs-lookup"><span data-stu-id="d76a2-348">Select **Next**:</span></span> 
    
    ![測試原則自動套用標籤精靈](../media/simulation-mode-auto-labeling-wizard.png)

13. <span data-ttu-id="d76a2-350">針對 **[摘要]** 頁面：檢閱您的自動套用標籤原則設定，視需要進行任何變更，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="d76a2-350">For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>

<span data-ttu-id="d76a2-351">現在，在 **[資訊保護]** > **[自動套用標籤]** 頁面，您會在 **[模擬]** 或 **[關閉]** 區段中看到自動套用標籤原則 (視您是否選擇要在模擬模式中執行) 而定。</span><span class="sxs-lookup"><span data-stu-id="d76a2-351">Now on the **Information protection** > **Auto-labeling** page, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="d76a2-352">選取您的原則，以查看設定和狀態的詳細資料 (例如，**仍在執行中的原則模擬**)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-352">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="d76a2-353">針對模擬模式中的原則，選取 **[相符的項目]** 索引標籤，以查看哪些電子郵件或文件符合您指定的規則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-353">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="d76a2-354">您可以直接從這個介面修改您的原則：</span><span class="sxs-lookup"><span data-stu-id="d76a2-354">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="d76a2-355">針對 **[關閉]** 區段中的原則，選取 **[編輯原則]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d76a2-355">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="d76a2-356">針對 **[模擬]** 區段中的原則，從任一索引標籤中選取頁面頂端的 **[編輯原則]** 選項：</span><span class="sxs-lookup"><span data-stu-id="d76a2-356">For policy in the **Simulation** section, select the **Edit policy** option at the top of the page, from either tab:</span></span>
    
    ![編輯自動套用標籤原則選項](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="d76a2-358">當您準備好執行原則而不進行模擬時，請選取 **[開啟原則]** 選項。</span><span class="sxs-lookup"><span data-stu-id="d76a2-358">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="d76a2-359">您的自動原則會持續執行，直到刪除為止。</span><span class="sxs-lookup"><span data-stu-id="d76a2-359">Your auto-policies run continuously until they are deleted.</span></span> <span data-ttu-id="d76a2-360">例如，新的和修改過的文件會包含在目前的原則設定中。</span><span class="sxs-lookup"><span data-stu-id="d76a2-360">For example, new and modified documents will be included with the current policy settings.</span></span>

<span data-ttu-id="d76a2-361">具有適當[權限](data-classification-content-explorer.md#permissions)時，您也可以藉由使用[內容總管](data-classification-content-explorer.md)，來查看自動套用標籤原則的結果：</span><span class="sxs-lookup"><span data-stu-id="d76a2-361">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="d76a2-362">**內容總管清單檢視器** 可讓您查看檔案的標籤，但是無法查看檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="d76a2-362">**Content Explorer List Viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="d76a2-363">**內容總管內容檢視器** 可讓您查看檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="d76a2-363">**Content Explorer Content Viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="d76a2-364">您也可以使用內容總管來識別包含包含敏感性資訊、但尚未套用標籤的的文件位置。</span><span class="sxs-lookup"><span data-stu-id="d76a2-364">You can also use content explorer to identify locations that have documents with sensitive information, but are unlabeled.</span></span> <span data-ttu-id="d76a2-365">利用此資訊，請考量將這些位置新增到您的自動套用標籤原則，並納入已識別的敏感性資訊類型作為規則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-365">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

### <a name="use-powershell-for-auto-labeling-policies"></a><span data-ttu-id="d76a2-366">將 PowerShell 用於自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="d76a2-366">Use PowerShell for auto-labeling policies</span></span>

<span data-ttu-id="d76a2-367">您可以使用[安全性與合規性中心 PowerShell](/powershell/exchange/scc-powershell) 來建立及設定自動套用標籤原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-367">You can use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure auto-labeling policies.</span></span> <span data-ttu-id="d76a2-368">這表示您可以完整編寫建立和維護自動套用標籤原則的指令碼，這也提供您一個更有效方式，可為 OneDrive 和 SharePoint 位置指定多個 URL。</span><span class="sxs-lookup"><span data-stu-id="d76a2-368">This means you can fully script the creation and maintenance of your auto-labeling policies, which also provides a more efficient method of specifying multiple URLs for OneDrive and SharePoint locations.</span></span>

<span data-ttu-id="d76a2-369">在 PowerShell 中執行命令之前，您必須先[連線至安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-369">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="d76a2-370">若要建立新的自動套用標籤原則：</span><span class="sxs-lookup"><span data-stu-id="d76a2-370">To create a new auto-labeling policy:</span></span> 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
<span data-ttu-id="d76a2-371">此命令會為您指定的 SharePoint 網站建立自動套用標籤原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-371">This command creates an auto-labeling policy for a SharePoint site that you specify.</span></span> <span data-ttu-id="d76a2-372">若為 OneDrive 位置，請改用 *OneDriveLocation* 參數。</span><span class="sxs-lookup"><span data-stu-id="d76a2-372">For a OneDrive location, use the *OneDriveLocation* parameter, instead.</span></span> 

<span data-ttu-id="d76a2-373">若要新增其他網站至現有的自動套用標籤原則：</span><span class="sxs-lookup"><span data-stu-id="d76a2-373">To add additional sites to an existing auto-labeling policy:</span></span>

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

<span data-ttu-id="d76a2-374">此命令會在變數中指定其他 SharePoint URL，然後將該變數新增至現有的自動套用標籤原則。</span><span class="sxs-lookup"><span data-stu-id="d76a2-374">This command specifies the additional SharePoint URLs in a variable that is then added to an existing auto-labeling policy.</span></span> <span data-ttu-id="d76a2-375">若要改為新增 OneDrive 位置，請使用 *AddOneDriveLocation* 參數搭配不同的變數，例如 *$OneDriveLocations*。</span><span class="sxs-lookup"><span data-stu-id="d76a2-375">To add OneDrive locations instead, use the *AddOneDriveLocation* parameter with a different variable, such as *$OneDriveLocations*.</span></span>

<span data-ttu-id="d76a2-376">若要建立新的自動套用標籤原則規則：</span><span class="sxs-lookup"><span data-stu-id="d76a2-376">To create a new auto-labeling policy rule:</span></span>

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

<span data-ttu-id="d76a2-377">針對現有的自動套用標籤原則，此命令會建立新的原則規則，以偵測 **美國社會安全編號 (SSN)** 的敏感性資訊類型，其具有實體識別碼 a44669fe-0d48-453d-a9b1-2cc83f2cba77。</span><span class="sxs-lookup"><span data-stu-id="d76a2-377">For an existing auto-labeling policy, this command creates a new policy rule to detect the sensitive information type of **U.S. social security number (SSN)**, which has an entity ID of a44669fe-0d48-453d-a9b1-2cc83f2cba77.</span></span> <span data-ttu-id="d76a2-378">若要尋找其他敏感性資訊類型的實體識別碼，請參閱[敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="d76a2-378">To find the entity IDs for other sensitive information types, refer to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="d76a2-379">如需有關支援自動套用標籤原則的 PowerShell Cmdlet 的詳細資訊、其可用參數和一些範例，請參閱下列 Cmdlet 說明：</span><span class="sxs-lookup"><span data-stu-id="d76a2-379">For more information about the PowerShell cmdlets that support auto-labeling policies, their available parameters and some examples, see the following cmdlet help:</span></span>

- [<span data-ttu-id="d76a2-380">Get-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="d76a2-380">Get-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [<span data-ttu-id="d76a2-381">New-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="d76a2-381">New-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [<span data-ttu-id="d76a2-382">New-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="d76a2-382">New-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/new-autosensitivitylabelrule)
- [<span data-ttu-id="d76a2-383">Remove-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="d76a2-383">Remove-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [<span data-ttu-id="d76a2-384">Remove-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="d76a2-384">Remove-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [<span data-ttu-id="d76a2-385">Set-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="d76a2-385">Set-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [<span data-ttu-id="d76a2-386">Set-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="d76a2-386">Set-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/set-autosensitivitylabelrule)