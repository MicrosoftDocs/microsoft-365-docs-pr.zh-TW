---
title: 自動將敏感度標籤套用到內容
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 建立敏感度標籤時，您可以自動為文件或電子郵件指派標籤，或者也可以提示使用者選取您建議的標籤。
ms.openlocfilehash: 5bd20abdf85fa66057bb9336ca2af715125f4622
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076717"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="451f2-103">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="451f2-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="451f2-104">建立敏感度標籤時，您可以自動將該標籤指派給包含敏感性資訊的內容，或者也可以提示使用者套用您建議的標籤。</span><span class="sxs-lookup"><span data-stu-id="451f2-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="451f2-105">自動將敏感度標籤套用到內容很重要，因為：</span><span class="sxs-lookup"><span data-stu-id="451f2-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="451f2-106">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="451f2-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="451f2-107">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="451f2-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="451f2-108">使用者不再需要了解原則，就可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="451f2-108">Users no longer need to know about your policies - they can instead focus on their work.</span></span>

> [!NOTE]
> <span data-ttu-id="451f2-p101">自動套用標籤的功能需要有 Azure 資訊保護 P2 訂閱。若要使用此功能，您必須[下載並安裝 Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/zh-TW/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。我們正在努力在 Office App 中提供此功能的原生支援，讓此功能不需要 Azure 資訊保護統一標籤用戶端。此外，統一標籤用戶端只能在 Windows 上執行，因此 Mac、iOS 和 Android 尚未支援此功能。</span><span class="sxs-lookup"><span data-stu-id="451f2-p101">The capability to apply labels automatically requires an Azure Information Protection P2 subscription. To use this feature, you must [Download and install the Azure Information Protection unified labeling client](https://docs.microsoft.com/zh-TW/azure/information-protection/rms-client/install-unifiedlabelingclient-app). We're working on native support for this feature in Office apps, so that it won't require the Azure Information Protection unified labeling client. Also, the unified labeling client runs only on Windows, so this feature is not yet supported on Mac, iOS, and Android.</span></span>

<span data-ttu-id="451f2-113">當您在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或是 Office 365 安全性與合規性中心底下的 [分類]\*\*\*\* >  [敏感度標籤]\*\*\*\* 建立敏感度標籤時，可以使用自動標籤設定。</span><span class="sxs-lookup"><span data-stu-id="451f2-113">The encryption settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span>

![敏感度標籤的自動標籤選項](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="451f2-115">根據條件自動套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="451f2-115">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="451f2-p102">敏感度標籤最強大的功能之一，是能夠自動套用至符合特定條件的內容。在此情況下，貴組織中的人員不需要套用敏感度標籤，Office 365 會替他們做這些事。</span><span class="sxs-lookup"><span data-stu-id="451f2-p102">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the sensitivity labels - Office 365 does the work for them.</span></span>
   
<span data-ttu-id="451f2-p103">您可以選擇在內容包含特定類型的敏感性資訊時，自動將敏感度標籤套用到該內容。當您設定自動套用敏感度標籤時，您會看到建立資料外洩防護 (DLP) 原則時的同一份敏感性資訊類型清單。因此，舉例來說，您可以自動將高度機密性標籤套用到包含客戶個人識別資訊 (PII) 的任何內容，例如信用卡號碼或社會安全號碼。</span><span class="sxs-lookup"><span data-stu-id="451f2-p103">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span> 

![執行個體計數和比對精確度的選項](media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="451f2-p104">選擇敏感性資訊類型之後，您可以變更執行個體計數或精確度來精簡條件。如需詳細資訊，請參閱[調整規則以讓它們更容易或更難符合](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="451f2-p104">After you choose your sensitive informaton types, you can refine your condition by changing the instance count or match accuracy. For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="451f2-p105">此外，您可以選擇條件是否必須偵測所有敏感性資訊類型，或只偵測其中一種。若要讓條件更具彈性或更複雜，您可以在群組之間新增群組並使用邏輯運算子。如需詳細資訊，請參閱[群組和邏輯運算子](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="451f2-p105">Further, you can choose whether a condition must detect all of the sensitive infromation types, or just one of them. And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups. For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="451f2-p106">自動套用敏感度標籤時，使用者會在其 Office App 中看到通知。使用者可以選擇 [確定]\*\*\*\* 來關閉通知。</span><span class="sxs-lookup"><span data-stu-id="451f2-p106">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![文件已自動套用標籤的通知](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="451f2-130">建議使用者套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="451f2-130">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="451f2-p107">您可以視需要建議使用者套用標籤，而不自動將敏感度標籤套用到內容。此選項可讓使用者享有接受分類和任何關聯保護的彈性，或在標籤不適用於其文件或電子郵件時關閉建議。</span><span class="sxs-lookup"><span data-stu-id="451f2-p107">If you prefer, instead of applying a sensitivity label automatically to content, you can recommend to your users that they apply the label. This option provides your users the flexibility of accepting the classification and any associated protection, or dismissing the recommendation if the label is not suitable for their document or email.</span></span>

<span data-ttu-id="451f2-p108">請注意，Word、PowerPoint 和 Excel 可支援建議標籤功能 (但必須安裝 Azure 資訊保護統一標籤用戶端)。我們正在努力在 Outlook 中提供建議標籤支援。</span><span class="sxs-lookup"><span data-stu-id="451f2-p108">Note that recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed). We're working on support for recommended labels in Outlook.</span></span>

![向使用者建議敏感度標籤的選項](media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="451f2-p109">以下是設定條件以將標籤套用為建議動作並顯示自訂原則提示的提示範例。您可以選擇要在原則提示中顯示的文字內容。</span><span class="sxs-lookup"><span data-stu-id="451f2-p109">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![套用建議標籤的提示](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="451f2-139">如何套用自動或建議標籤</span><span class="sxs-lookup"><span data-stu-id="451f2-139">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="451f2-p110">自動標籤可在儲存文件時套用到 Word、Excel 和 PowerPoint，並在傳送電子郵件時套用到 Outlook。這些條件會偵測文件本文和電子郵件內文以及頁首和頁尾中的敏感性資訊，但不會偵測主旨列或電子郵件附件中的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="451f2-p110">Automatic labeling applies to Word, Excel, and PowerPoint when documents are saved, and to Outlook when emails are sent. These conditions detect sensitive information in the body text in documents and emails, and to headers and footers -- but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="451f2-p111">如果文件或電子郵件之前已手動標示，或之前已使用較高分類自動標示，則無法使用自動分類功能。請切記，您只能將單一敏感度標籤套用到文件或電子郵件 (單一保留標籤也是如此)。</span><span class="sxs-lookup"><span data-stu-id="451f2-p111">You cannot use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification. Remember, a document or email can have only a single sensitivity label applied to it (in addition to a single retention label).</span></span>

- <span data-ttu-id="451f2-p112">建議分類可在儲存文件時套用到 Word、Excel 和 PowerPoint。我們正在努力在 Outlook 中提供建議標籤支援。</span><span class="sxs-lookup"><span data-stu-id="451f2-p112">Recommended classification applies to Word, Excel, and PowerPoint when documents are saved. We're working on support for recommended labeling in Outlook.</span></span>

- <span data-ttu-id="451f2-p113">如果文件之前已使用較高分類標示，則無法使用建議分類功能。在此情況下，當內容已使用較高分類標示時，使用者將無法看到含有建議和原則提示的提示。</span><span class="sxs-lookup"><span data-stu-id="451f2-p113">You cannot use recommended classification for documents that were previously labeled with a higher classification. In this case, when the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="451f2-148">將多個條件套用到多個標籤時的評估方式</span><span class="sxs-lookup"><span data-stu-id="451f2-148">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="451f2-p114">標籤會根據您在原則中指定的標籤位置，針對評估進行排序：位於第一個位置的標籤具有最低的位置 (敏感度最低)，而位於最後一個位置的標籤具有最高的位置 (敏感度最高)。如需有關原則的詳細資訊，請參閱[標籤優先順序 (排序事項)](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="451f2-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="451f2-151">請勿設定將上層標籤設定為自動套用或建議選項</span><span class="sxs-lookup"><span data-stu-id="451f2-151">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="451f2-152">請記得，無法將上層標籤 (具有子標籤的標籤) 套用至內容。</span><span class="sxs-lookup"><span data-stu-id="451f2-152">Remember, a parent label (a label with sublabels) can't be applied to content.</span></span> <span data-ttu-id="451f2-153">請確定未將上層標籤設定為自動套用或建議選項，因為上層標籤無法套用到使用 Azure 資訊保護統一標籤用戶端的 Office 應用程式中的內容。</span><span class="sxs-lookup"><span data-stu-id="451f2-153">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="451f2-154">如需上層標籤和子標籤的詳細資訊，請參閱[子標籤 (分組標籤)](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="451f2-154">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
