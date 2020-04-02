---
title: 自動將敏感度標籤套用到內容
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
description: 建立敏感度標籤時，您可以自動為文件或電子郵件指派標籤，或者也可以提示使用者選取您建議的標籤。
ms.openlocfilehash: a087d142843ce74de3a930aea9286034b8617db6
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106069"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="bb8ed-103">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="bb8ed-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="bb8ed-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="bb8ed-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bb8ed-105">建立敏感度標籤時，您可以自動將該標籤指派給包含敏感性資訊的內容，或者也可以提示使用者套用您建議的標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-105">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="bb8ed-106">自動將敏感度標籤套用到內容很重要，因為：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="bb8ed-107">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-107">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="bb8ed-108">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="bb8ed-109">使用者不再需要了解原則，而是可以專心於工作。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="bb8ed-110">在 Windows 版 Office 應用程式中的自動標籤，是由 Azure 資訊保護整合標籤用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-110">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8ed-111">針對在 Office 應用程式中的內建標籤功能，在[某些應用程式為預覽](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-111">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="bb8ed-112">當您[建立或編輯敏感度標籤時，可使用適用於 Office 應用程式的自動加上標籤設定](create-sensitivity-labels.md)：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-112">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![敏感度標籤的自動標籤選項](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="bb8ed-114">如何設定適用於 Office 應用程式的自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="bb8ed-114">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="bb8ed-115">敏感度標籤最實用的功能之一，是將標籤自動套用至符合特定條件的內容。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-115">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches specific conditions.</span></span> <span data-ttu-id="bb8ed-116">在此情況下，貴組織中的人員不必親自套用敏感度標籤，Office 365 會完成相關作業。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-116">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="bb8ed-117">當內容包含特定類型的敏感資訊時，您可以選擇自動將敏感度標籤套用到內容。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-117">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="bb8ed-118">從敏感度資訊類型或分類器清單中選擇：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-118">Choose from a list of sensitive info types or classifers:</span></span>

![在 Office 應用程式中自動加上標籤的標籤條件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="bb8ed-120">目前，[分類器]\*\*\*\* 的選項在限制預覽中，您必須將表單提交給 Microsoft，才能為您的租用戶啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-120">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="bb8ed-121">如需詳細資訊，請參閱[宣佈在 Office 應用程式中使用內建分類器自動加上標籤 - 限制預覽](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889) (英文)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-121">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="bb8ed-122">自動套用此敏感度標籤時，使用者會在其 Office 應用程式中看到通知。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-122">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="bb8ed-123">例如：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-123">For example:</span></span>

![文件已自動套用標籤的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="bb8ed-125">設定標籤的敏感度資訊類型</span><span class="sxs-lookup"><span data-stu-id="bb8ed-125">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="bb8ed-126">當您選取 [敏感度資訊類型]\*\*\*\* 選項時，會看到與在建立資料外洩防護 (DLP) 原則時相同的敏感度資訊類型清單。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-126">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="bb8ed-127">例如，您可以自動將 [高度機密] 標籤套用至任何包含客戶個人身分識別資訊 (PII) 的內容，例如信用卡號碼或身分證號碼：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-127">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![在 Office 應用程式中自動加上標記的敏感資訊類型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="bb8ed-129">選取敏感度資訊類型之後，您可以變更執行個體計數或比對精確度來調整條件。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-129">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="bb8ed-130">如需詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-130">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="bb8ed-131">此外，您可以選擇條件是必須偵測所有敏感性資訊類型，還是只偵測其中一種。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-131">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="bb8ed-132">若要讓您的條件更靈活或更複雜，您可以新增群組，並使用群組之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-132">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="bb8ed-133">如需詳細資訊，請參閱[群組和邏輯運算子](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-133">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![執行個體計數和比對精確度的選項](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="bb8ed-135">為標籤設定分類器</span><span class="sxs-lookup"><span data-stu-id="bb8ed-135">Configuring classifers for a label</span></span>

<span data-ttu-id="bb8ed-136">當您選取 [分類器]\*\*\*\* 選項時，請選取一或多個內建分類器：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-136">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分類器和敏感度標籤的選項](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="bb8ed-138">如需這些分類器的詳細資訊，請參閱[開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-138">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="bb8ed-139">在預覽期間，下列應用程式支援靈敏度標籤的分類器：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-139">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="bb8ed-140">來自 [Office 測試人員](https://office.com/insider)的 Windows 版 Office 365 專業增強版傳統型應用程式：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-140">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="bb8ed-141">Word</span><span class="sxs-lookup"><span data-stu-id="bb8ed-141">Word</span></span>
    - <span data-ttu-id="bb8ed-142">Excel</span><span class="sxs-lookup"><span data-stu-id="bb8ed-142">Excel</span></span>
    - <span data-ttu-id="bb8ed-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bb8ed-143">PowerPoint</span></span>

- <span data-ttu-id="bb8ed-144">當您[在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) 時的 Office Web 應用程式：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-144">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="bb8ed-145">Word</span><span class="sxs-lookup"><span data-stu-id="bb8ed-145">Word</span></span>
    - <span data-ttu-id="bb8ed-146">Excel</span><span class="sxs-lookup"><span data-stu-id="bb8ed-146">Excel</span></span>
    - <span data-ttu-id="bb8ed-147">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bb8ed-147">PowerPoint</span></span>
    - <span data-ttu-id="bb8ed-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="bb8ed-148">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="bb8ed-149">建議使用者套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="bb8ed-149">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="bb8ed-150">您可以視需要建議使用者套用標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-150">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="bb8ed-151">如果您使用此選項，您的使用者就可以接受分類和任何相關的保護，或者當標籤不適合內容時，可以取消建議。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-151">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![向使用者建議敏感度標籤的選項](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="bb8ed-153">以下舉例說明當您設定條件而將套用標籤作為建議動作 (含自訂原則提示) 時，來自 Azure 資訊保護整合標籤用戶端的提示。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-153">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="bb8ed-154">您可以選擇要在原則提示中顯示的文字。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-154">You can choose what text is displayed in the policy tip.</span></span>

![套用建議標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="bb8ed-156">如何套用自動或建議標籤</span><span class="sxs-lookup"><span data-stu-id="bb8ed-156">How automatic or recommended labels are applied</span></span>

<span data-ttu-id="bb8ed-157">是否會在 Office 應用程式中實作自動化的建議標籤功能，取決於您使用的是 Office 內建的標籤功能，還是 Azure 資訊保護的整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-157">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8ed-158">不過，在這兩種情況下：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-158">In both cases, however:</span></span>

- <span data-ttu-id="bb8ed-159">您不能對之前已手動加上標籤，或之前已自動加上較高敏感性標籤的文件和電子郵件，自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="bb8ed-160">請記住，您只能將單一敏感度標籤套用至文件或電子郵件 (除了單一保留標籤之外)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="bb8ed-161">您無法針對之前已加上較高敏感性標籤的文件或電子郵件使用建議標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-161">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="bb8ed-162">如果內容已加上較高敏感性標籤，使用者將不會看到含有建議和原則提示的提示。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-162">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="bb8ed-163">專用於內建標籤：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-163">Specific to built-in labeling:</span></span>

- <span data-ttu-id="bb8ed-164">並非所有的 Office 應用程式都支援自動化 (建議) 標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-164">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="bb8ed-165">如需詳細資訊，請參閱[在應用程式中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-165">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="bb8ed-166">若為電腦版 Word 中的建議標籤，系統會標示觸發了建議的敏感性內容，讓使用者可以檢閱和移除敏感性內容，而不是套用建議的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-166">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="bb8ed-167">如需這些標籤在 Office 應用程式中的套用方式、範例螢幕擷取畫面，以及系統如何偵測到敏感性資訊的詳細資訊，請參閱[在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-167">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="bb8ed-168">專用於 Azure 資訊保護的整合標籤用戶端：</span><span class="sxs-lookup"><span data-stu-id="bb8ed-168">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="bb8ed-169">自動化的建議標籤功能適用於您儲存文件時所使用的 Word、Excel 和 PowerPoint，以及傳送電子郵件時的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-169">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="bb8ed-170">若要讓 Outlook 支援建議標籤，您必須先設定[進階原則設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-170">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="bb8ed-171">系統可於文件和電子郵件的本文，以及頁首及頁尾中偵測到敏感性資訊，但無法在電子郵件的主旨列或附件中偵測到敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-171">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="bb8ed-172">將多個條件套用到多個標籤時的評估方式</span><span class="sxs-lookup"><span data-stu-id="bb8ed-172">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="bb8ed-p115">標籤會根據您在原則中指定的標籤位置，針對評估進行排序：位於第一個位置的標籤具有最低的位置 (敏感度最低)，而位於最後一個位置的標籤具有最高的位置 (敏感度最高)。如需有關原則的詳細資訊，請參閱[標籤優先順序 (排序事項)](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-p115">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="bb8ed-175">請勿設定將上層標籤設定為自動套用或建議選項</span><span class="sxs-lookup"><span data-stu-id="bb8ed-175">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="bb8ed-176">請記得，您無法將上層標籤 (具有子標籤的標籤) 套用至內容。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-176">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="bb8ed-177">請確定未將上層標籤設定為自動套用或建議選項，因為上層標籤無法套用到使用 Azure 資訊保護統一標籤用戶端的 Office 應用程式中的內容。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-177">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bb8ed-178">如需上層標籤和子標籤的詳細資訊，請參閱[子標籤 (分組標籤)](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="bb8ed-178">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
