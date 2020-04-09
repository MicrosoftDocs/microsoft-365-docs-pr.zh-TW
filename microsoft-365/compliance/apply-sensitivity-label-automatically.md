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
ms.openlocfilehash: 7bbfb85746c114fa277f28a87c04194bd290c1fd
ms.sourcegitcommit: d1909d34ac0cddeb776ff5eb8414bfc9707d5ac1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43163873"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="80c3c-103">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="80c3c-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="80c3c-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="80c3c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="80c3c-105">當您建立敏感度標籤時，您可以在該標籤符合您指定的條件時，自動將其指派給內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="80c3c-106">自動將敏感度標籤套用到內容很重要，因為：</span><span class="sxs-lookup"><span data-stu-id="80c3c-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="80c3c-107">您不需要訓練您的使用者使用各個分類的時機。</span><span class="sxs-lookup"><span data-stu-id="80c3c-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="80c3c-108">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="80c3c-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="80c3c-109">使用者不再需要了解原則，而是可以專心於工作。</span><span class="sxs-lookup"><span data-stu-id="80c3c-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="80c3c-110">自動套用敏感度標籤有兩種不同的方法：</span><span class="sxs-lookup"><span data-stu-id="80c3c-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="80c3c-111">**使用者編輯文件或撰寫 (回覆或轉寄) 電子郵件時的用戶端加上標籤**：使用針對 Office 應用程式 (Word、Excel、PowerPoint 和 Outlook) 自動加上標籤所設定的標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="80c3c-112">此方法支援向使用者建議標籤，以及自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="80c3c-113">但是在這兩種情況下，使用者都會決定接受或拒絕標籤，以協助確保正確的內容標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="80c3c-114">此用戶端加上標籤對於文件有最小延遲，因為您甚至可以在文件儲存之前套用標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="80c3c-115">不過，並非所有用戶端應用程式都支援自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="80c3c-116">這項功能受 Azure 資訊保護整合式標籤用戶端和[部分 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)的支援。</span><span class="sxs-lookup"><span data-stu-id="80c3c-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="80c3c-117">如需設定指示，請參閱在此頁面上的[如何設定適用於 Office 應用程式的自動加上標籤](#how-to-configure-auto-labeling-for-office-apps)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="80c3c-118">**內容已儲存 (在 SharePoint Online 或商務用 OneDrive 中) 或寄送電子郵件 (由 Exchange Online 處理) 時的服務端加上標籤**：使用自動加上標籤原則 - 目前為預覽階段。</span><span class="sxs-lookup"><span data-stu-id="80c3c-118">**Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="80c3c-119">請參閱預覽公告、[宣告 Microsoft 365 服務中使用敏感度標籤自動分類的公開預覽](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961) (英文)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-119">See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).</span></span>
    
    <span data-ttu-id="80c3c-120">此方法稱為使用敏感度標籤自動分類。</span><span class="sxs-lookup"><span data-stu-id="80c3c-120">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="80c3c-121">您可能也聽過其稱為待用資料 (SharePoint 和 OneDrive 中的文件) 以及傳輸中資料 (由 Exchange 傳送或接收的電子郵件) 的自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-121">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="80c3c-122">若是 Exchange，不會包含待用電子郵件 (信箱)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-122">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="80c3c-123">由於此標籤是由服務套用，而不是由應用程式套用，因此您不需要擔心使用者擁有哪些應用程式及其版本。</span><span class="sxs-lookup"><span data-stu-id="80c3c-123">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="80c3c-124">如此一來，您就能立即在整個組織中使用這項功能，並且適用於大規模加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-124">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="80c3c-125">自動加上標籤原則不支援建議的標籤，因為使用者不會與加上標籤程序進行互動。</span><span class="sxs-lookup"><span data-stu-id="80c3c-125">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="80c3c-126">相反地，系統管理員會在模擬模式中執行原則，以協助確保在實際套用標籤之前，內容正確加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-126">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="80c3c-127">如需設定指示，請參閱此頁面上的[如何設定 SharePoint、OneDrive 和 Exchange 的自動加上標籤原則](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-127">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="80c3c-128">SharePoint 和 OneDrive 自動加上標籤專屬限制：</span><span class="sxs-lookup"><span data-stu-id="80c3c-128">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="80c3c-129">在您的租用戶中每天 25000 個檔案的數量上限 (Word、PowerPoint 或 Excel)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-129">Maximum number of 25,000 files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
    - <span data-ttu-id="80c3c-130">所有原則之間 10 個網站集合的數量上限</span><span class="sxs-lookup"><span data-stu-id="80c3c-130">Maximum number of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="80c3c-131">在您的租用戶之間 10 個原則的數量上限</span><span class="sxs-lookup"><span data-stu-id="80c3c-131">Maximum number of 10 policies across your tenant</span></span>

    <span data-ttu-id="80c3c-132">Exchange 自動加上標籤專屬限制：</span><span class="sxs-lookup"><span data-stu-id="80c3c-132">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="80c3c-133">不同於 Office 應用程式的手動加上標籤或自動加上標籤，Office 附件也會針對您在自動加上標籤原則中指定的條件進行掃描。</span><span class="sxs-lookup"><span data-stu-id="80c3c-133">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="80c3c-134">有相符項目時，電子郵件會加上標籤，但是附件不會加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-134">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="80c3c-135">如果您有套用 IRM 加密的 Exchange 郵件流程規則或資料外洩防護 (DLP) 原則：當內容由這些規則或原則和自動加上標籤原則識別時，則會套用標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-135">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="80c3c-136">如果該標籤套用加密，則會忽略 Exchange 郵件流程規則或 DLP 原則的 IRM 設定。</span><span class="sxs-lookup"><span data-stu-id="80c3c-136">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="80c3c-137">不過，如果該標籤並未套用加密，除了標籤以外，還會套用郵件流程規則或 DLP 原則的 IRM 設定。</span><span class="sxs-lookup"><span data-stu-id="80c3c-137">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="80c3c-138">當有一個相符項目使用自動加上標籤時，具有 IRM 加密而沒有標籤的電子郵件，將會由具有任何加密設定的標籤取代。</span><span class="sxs-lookup"><span data-stu-id="80c3c-138">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="80c3c-139">當有項目與您的自動加上標籤條件相符時，內送電子郵件會加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-139">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="80c3c-140">不過，如果標籤針對加密進行設定，則不會套用加密。</span><span class="sxs-lookup"><span data-stu-id="80c3c-140">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="80c3c-141">比較 Office 應用程式的自動加上標籤與自動加上標籤原則</span><span class="sxs-lookup"><span data-stu-id="80c3c-141">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="80c3c-142">使用下表來協助您識別兩個互補自動加上標籤方法的行為差異：</span><span class="sxs-lookup"><span data-stu-id="80c3c-142">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="80c3c-143">功能或行為</span><span class="sxs-lookup"><span data-stu-id="80c3c-143">Feature or behavior</span></span>|<span data-ttu-id="80c3c-144">標籤設定：Office 應用程式的自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="80c3c-144">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="80c3c-145">原則：自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="80c3c-145">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80c3c-146">應用程式相依性</span><span class="sxs-lookup"><span data-stu-id="80c3c-146">App dependency</span></span>|[<span data-ttu-id="80c3c-147">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-147">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="80c3c-148">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-148">No</span></span> |
|<span data-ttu-id="80c3c-149">依位置限制</span><span class="sxs-lookup"><span data-stu-id="80c3c-149">Restrict by location</span></span>|<span data-ttu-id="80c3c-150">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-150">No</span></span> |<span data-ttu-id="80c3c-151">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-151">Yes</span></span> |
|<span data-ttu-id="80c3c-152">條件：可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="80c3c-152">Conditions: Trainable classifers</span></span>|<span data-ttu-id="80c3c-153">是 (限制預覽)</span><span class="sxs-lookup"><span data-stu-id="80c3c-153">Yes (limited preview)</span></span> |<span data-ttu-id="80c3c-154">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-154">No</span></span> |
|<span data-ttu-id="80c3c-155">條件：共用選項和電子郵件的其他選項</span><span class="sxs-lookup"><span data-stu-id="80c3c-155">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="80c3c-156">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-156">No</span></span> |<span data-ttu-id="80c3c-157">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-157">Yes</span></span> |
|<span data-ttu-id="80c3c-158">建議、原則工具提示及使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="80c3c-158">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="80c3c-159">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-159">Yes</span></span> |<span data-ttu-id="80c3c-160">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-160">No</span></span> |
|<span data-ttu-id="80c3c-161">模擬模式</span><span class="sxs-lookup"><span data-stu-id="80c3c-161">Simulation mode</span></span>|<span data-ttu-id="80c3c-162">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-162">No</span></span> |<span data-ttu-id="80c3c-163">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-163">Yes</span></span> |
|<span data-ttu-id="80c3c-164">已針對條件檢查 Exchange 附件</span><span class="sxs-lookup"><span data-stu-id="80c3c-164">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="80c3c-165">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-165">No</span></span> | <span data-ttu-id="80c3c-166">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-166">Yes</span></span>|
|<span data-ttu-id="80c3c-167">套用視覺標記</span><span class="sxs-lookup"><span data-stu-id="80c3c-167">Apply visual markings</span></span> |<span data-ttu-id="80c3c-168">是</span><span class="sxs-lookup"><span data-stu-id="80c3c-168">Yes</span></span> |<span data-ttu-id="80c3c-169">是 (僅限電子郵件)</span><span class="sxs-lookup"><span data-stu-id="80c3c-169">Yes (email only)</span></span> |
|<span data-ttu-id="80c3c-170">覆寫沒有標籤的已套用 IRM 加密</span><span class="sxs-lookup"><span data-stu-id="80c3c-170">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="80c3c-171">如果使用者只有「匯出」的最小使用權限，則為「是」。</span><span class="sxs-lookup"><span data-stu-id="80c3c-171">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="80c3c-172">是 (僅限電子郵件)</span><span class="sxs-lookup"><span data-stu-id="80c3c-172">Yes (email only)</span></span> |
|<span data-ttu-id="80c3c-173">將內送電子郵件加上標籤</span><span class="sxs-lookup"><span data-stu-id="80c3c-173">Label incoming email</span></span>|<span data-ttu-id="80c3c-174">否</span><span class="sxs-lookup"><span data-stu-id="80c3c-174">No</span></span> |<span data-ttu-id="80c3c-175">是 (未套用加密)</span><span class="sxs-lookup"><span data-stu-id="80c3c-175">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="80c3c-176">手動將內容加上標籤時，該標籤永遠不會被自動加上標籤取代。</span><span class="sxs-lookup"><span data-stu-id="80c3c-176">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="80c3c-177">不過，自動加上標籤原則可取代使用 Office 應用程式自動加上標籤所套用的[低優先順序標籤](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-177">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="80c3c-178">將多個條件套用到多個標籤時的評估方式</span><span class="sxs-lookup"><span data-stu-id="80c3c-178">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="80c3c-p108">標籤會根據您在原則中指定的標籤位置，針對評估進行排序：位於第一個位置的標籤具有最低的位置 (敏感度最低)，而位於最後一個位置的標籤具有最高的位置 (敏感度最高)。如需有關原則的詳細資訊，請參閱[標籤優先順序 (排序事項)](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="80c3c-181">請勿設定將上層標籤設定為自動套用或建議選項</span><span class="sxs-lookup"><span data-stu-id="80c3c-181">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="80c3c-182">請記得，您無法將上層標籤 (具有子標籤的標籤) 套用至內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-182">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="80c3c-183">請確定未將上層標籤設定為自動套用或建議選項，因為上層標籤無法套用到使用 Azure 資訊保護統一標籤用戶端的 Office 應用程式中的內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-183">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="80c3c-184">如需上層標籤和子標籤的詳細資訊，請參閱[子標籤 (分組標籤)](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-184">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="80c3c-185">如何設定適用於 Office 應用程式的自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="80c3c-185">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="80c3c-186">在 Windows 版 Office 應用程式中的自動標籤，是由 Azure 資訊保護整合標籤用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="80c3c-186">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="80c3c-187">針對在 Office 應用程式中的內建標籤功能，在[某些應用程式為預覽](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-187">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="80c3c-188">當您[建立或編輯敏感度標籤時，可使用適用於 Office 應用程式的自動加上標籤設定](create-sensitivity-labels.md)：</span><span class="sxs-lookup"><span data-stu-id="80c3c-188">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![敏感度標籤的自動標籤選項](../media/sensitivity-labels-auto-labeling-options.png)

<span data-ttu-id="80c3c-190">當內容包含特定類型的敏感資訊時，您可以選擇自動將敏感度標籤套用到內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-190">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="80c3c-191">從敏感度資訊類型或分類器清單中選擇：</span><span class="sxs-lookup"><span data-stu-id="80c3c-191">Choose from a list of sensitive info types or classifers:</span></span>

![在 Office 應用程式中自動加上標籤的標籤條件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="80c3c-193">目前，[分類器]\*\*\*\* 的選項在限制預覽中，您必須將表單提交給 Microsoft，才能為您的租用戶啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="80c3c-193">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="80c3c-194">如需詳細資訊，請參閱[宣佈在 Office 應用程式中使用內建分類器自動加上標籤 - 限制預覽](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889) (英文)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-194">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="80c3c-195">自動套用此敏感度標籤時，使用者會在其 Office 應用程式中看到通知。</span><span class="sxs-lookup"><span data-stu-id="80c3c-195">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="80c3c-196">例如：</span><span class="sxs-lookup"><span data-stu-id="80c3c-196">For example:</span></span>

![文件已自動套用標籤的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="80c3c-198">設定標籤的敏感度資訊類型</span><span class="sxs-lookup"><span data-stu-id="80c3c-198">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="80c3c-199">當您選取 [敏感度資訊類型]\*\*\*\* 選項時，會看到與在建立資料外洩防護 (DLP) 原則時相同的敏感度資訊類型清單。</span><span class="sxs-lookup"><span data-stu-id="80c3c-199">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="80c3c-200">例如，您可以自動將 [高度機密] 標籤套用至任何包含客戶個人身分識別資訊 (PII) 的內容，例如信用卡號碼或身分證號碼：</span><span class="sxs-lookup"><span data-stu-id="80c3c-200">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![在 Office 應用程式中自動加上標記的敏感資訊類型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="80c3c-202">選取敏感度資訊類型之後，您可以變更執行個體計數或比對精確度來調整條件。</span><span class="sxs-lookup"><span data-stu-id="80c3c-202">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="80c3c-203">如需詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-203">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="80c3c-204">此外，您可以選擇條件是必須偵測所有敏感性資訊類型，還是只偵測其中一種。</span><span class="sxs-lookup"><span data-stu-id="80c3c-204">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="80c3c-205">若要讓您的條件更靈活或更複雜，您可以新增群組，並使用群組之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="80c3c-205">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="80c3c-206">如需詳細資訊，請參閱[群組和邏輯運算子](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-206">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![執行個體計數和比對精確度的選項](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="80c3c-208">為標籤設定分類器</span><span class="sxs-lookup"><span data-stu-id="80c3c-208">Configuring classifers for a label</span></span>

<span data-ttu-id="80c3c-209">當您選取 [分類器]\*\*\*\* 選項時，請選取一或多個內建分類器：</span><span class="sxs-lookup"><span data-stu-id="80c3c-209">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分類器和敏感度標籤的選項](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="80c3c-211">如需這些分類器的詳細資訊，請參閱[開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-211">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="80c3c-212">在預覽期間，下列應用程式支援靈敏度標籤的分類器：</span><span class="sxs-lookup"><span data-stu-id="80c3c-212">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="80c3c-213">來自 [Office 測試人員](https://office.com/insider)的 Windows 版 Office 365 專業增強版傳統型應用程式：</span><span class="sxs-lookup"><span data-stu-id="80c3c-213">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="80c3c-214">Word</span><span class="sxs-lookup"><span data-stu-id="80c3c-214">Word</span></span>
    - <span data-ttu-id="80c3c-215">Excel</span><span class="sxs-lookup"><span data-stu-id="80c3c-215">Excel</span></span>
    - <span data-ttu-id="80c3c-216">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="80c3c-216">PowerPoint</span></span>

- <span data-ttu-id="80c3c-217">當您[在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) 時的 Office Web 應用程式：</span><span class="sxs-lookup"><span data-stu-id="80c3c-217">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="80c3c-218">Word</span><span class="sxs-lookup"><span data-stu-id="80c3c-218">Word</span></span>
    - <span data-ttu-id="80c3c-219">Excel</span><span class="sxs-lookup"><span data-stu-id="80c3c-219">Excel</span></span>
    - <span data-ttu-id="80c3c-220">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="80c3c-220">PowerPoint</span></span>
    - <span data-ttu-id="80c3c-221">Outlook</span><span class="sxs-lookup"><span data-stu-id="80c3c-221">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label-in-office-apps"></a><span data-ttu-id="80c3c-222">建議使用者在 Office 應用程式中套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="80c3c-222">Recommend that the user applies a sensitivity label in Office apps</span></span>

<span data-ttu-id="80c3c-223">您可以視需要建議使用者套用標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-223">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="80c3c-224">如果您使用此選項，您的使用者就可以接受分類和任何相關的保護，或者當標籤不適合內容時，可以取消建議。</span><span class="sxs-lookup"><span data-stu-id="80c3c-224">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![向使用者建議敏感度標籤的選項](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="80c3c-226">以下舉例說明當您設定條件而將套用標籤作為建議動作 (含自訂原則提示) 時，來自 Azure 資訊保護整合標籤用戶端的提示。</span><span class="sxs-lookup"><span data-stu-id="80c3c-226">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="80c3c-227">您可以選擇要在原則提示中顯示的文字。</span><span class="sxs-lookup"><span data-stu-id="80c3c-227">You can choose what text is displayed in the policy tip.</span></span>

![套用建議標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied-in-office-apps"></a><span data-ttu-id="80c3c-229">在 Office 應用程式中套用自動或建議標籤的時機</span><span class="sxs-lookup"><span data-stu-id="80c3c-229">When automatic or recommended labels are applied in Office apps</span></span>

<span data-ttu-id="80c3c-230">是否會在 Office 應用程式中實作自動化的建議標籤功能，取決於您使用的是 Office 內建的標籤功能，還是 Azure 資訊保護的整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="80c3c-230">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="80c3c-231">不過，在這兩種情況下：</span><span class="sxs-lookup"><span data-stu-id="80c3c-231">In both cases, however:</span></span>

- <span data-ttu-id="80c3c-232">您不能對之前已手動加上標籤，或之前已自動加上較高敏感性標籤的文件和電子郵件，自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-232">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="80c3c-233">請記住，您只能將單一敏感度標籤套用至文件或電子郵件 (除了單一保留標籤之外)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-233">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="80c3c-234">您無法針對之前已加上較高敏感性標籤的文件或電子郵件使用建議標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-234">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="80c3c-235">如果內容已加上較高敏感性標籤，使用者將不會看到含有建議和原則提示的提示。</span><span class="sxs-lookup"><span data-stu-id="80c3c-235">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="80c3c-236">專用於內建標籤：</span><span class="sxs-lookup"><span data-stu-id="80c3c-236">Specific to built-in labeling:</span></span>

- <span data-ttu-id="80c3c-237">並非所有的 Office 應用程式都支援自動化 (建議) 標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-237">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="80c3c-238">如需詳細資訊，請參閱[在應用程式中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-238">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="80c3c-239">若為電腦版 Word 中的建議標籤，系統會標示觸發了建議的敏感性內容，讓使用者可以檢閱和移除敏感性內容，而不是套用建議的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-239">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="80c3c-240">如需這些標籤在 Office 應用程式中的套用方式、範例螢幕擷取畫面，以及系統如何偵測到敏感性資訊的詳細資訊，請參閱[在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-240">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="80c3c-241">專用於 Azure 資訊保護的整合標籤用戶端：</span><span class="sxs-lookup"><span data-stu-id="80c3c-241">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="80c3c-242">自動化的建議標籤功能適用於您儲存文件時所使用的 Word、Excel 和 PowerPoint，以及傳送電子郵件時的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="80c3c-242">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="80c3c-243">若要讓 Outlook 支援建議標籤，您必須先設定[進階原則設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-243">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="80c3c-244">系統可於文件和電子郵件的本文，以及頁首及頁尾中偵測到敏感性資訊，但無法在電子郵件的主旨列或附件中偵測到敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="80c3c-244">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="80c3c-245">如何設定 SharePoint、OneDrive 和 Exchange 的自動加上標籤原則</span><span class="sxs-lookup"><span data-stu-id="80c3c-245">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>
> [!NOTE]
> <span data-ttu-id="80c3c-246">自動加上標籤原則會在公開預覽階段逐漸推出給租用戶，可能有變更。</span><span class="sxs-lookup"><span data-stu-id="80c3c-246">Auto-labeling policies are gradually rolling out to tenants in public preview and subject to change.</span></span>

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="80c3c-247">自動加上標籤原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="80c3c-247">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="80c3c-248">必須對模擬模式開啟針對 Office 365 稽核。</span><span class="sxs-lookup"><span data-stu-id="80c3c-248">Auditing for Office 365 must be turned on for simulation mode.</span></span> <span data-ttu-id="80c3c-249">如果您需要開啟稽核，或者如果您不確定稽核是否開啟，請參閱[開啟或關閉 Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-249">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="80c3c-250">若要對 SharePoint 和 OneDrive 中的檔案自動加上標籤：</span><span class="sxs-lookup"><span data-stu-id="80c3c-250">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="80c3c-251">您必須[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-251">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="80c3c-252">當自動加上標籤原則執行時，檔案不能由其他程序或使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="80c3c-252">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="80c3c-253">如果您打算使用[自訂敏感性資訊類型](custom-sensitive-info-types.md)，而不是內建的敏感性類型：</span><span class="sxs-lookup"><span data-stu-id="80c3c-253">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="80c3c-254">針對在自訂敏感性資訊類型儲存之後所建立的內容，會評估自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="80c3c-254">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="80c3c-255">若要測試新的自訂敏感性資訊類型，請在建立您的自動加上標籤原則之前建立，然後建立含有範例資料的新文件以進行測試。</span><span class="sxs-lookup"><span data-stu-id="80c3c-255">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="80c3c-256">[已建立和已發佈](create-sensitivity-labels.md) (給至少一個使用者) 一或多個敏感性標籤，您可以針對您的自動加上標籤原則進行選取。</span><span class="sxs-lookup"><span data-stu-id="80c3c-256">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policy.</span></span> <span data-ttu-id="80c3c-257">針對這些標籤：</span><span class="sxs-lookup"><span data-stu-id="80c3c-257">For these labels:</span></span>
    - <span data-ttu-id="80c3c-258">Office 應用程式中的自動加上標籤標籤設定開啟與否並不重要，因為該標籤設定是補充自動加上標籤原則，如簡介中的說明。</span><span class="sxs-lookup"><span data-stu-id="80c3c-258">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="80c3c-259">如果您想要用於自動加上標籤的標籤是設定為使用視覺標記 (頁首、頁尾、浮水印)，請注意，這些標籤不適用於文件。</span><span class="sxs-lookup"><span data-stu-id="80c3c-259">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="80c3c-260">了解模擬模式</span><span class="sxs-lookup"><span data-stu-id="80c3c-260">Learn about simulation mode</span></span>

<span data-ttu-id="80c3c-261">模擬模式是自動加上標籤原則專屬的，並且編寫到工作流程中。</span><span class="sxs-lookup"><span data-stu-id="80c3c-261">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="80c3c-262">在您的原則執行至少一個模擬之前，您無法對文件和電子郵件自動加上標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-262">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="80c3c-263">自動加上標籤原則的工作流程：</span><span class="sxs-lookup"><span data-stu-id="80c3c-263">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="80c3c-264">建立及設定自動加上標籤原則</span><span class="sxs-lookup"><span data-stu-id="80c3c-264">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="80c3c-265">在模擬模式中執行原則，並至少等待 24 小時</span><span class="sxs-lookup"><span data-stu-id="80c3c-265">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="80c3c-266">檢閱結果，並視需要調整原則，重新執行模擬模式，並等待至少 24 小時</span><span class="sxs-lookup"><span data-stu-id="80c3c-266">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="80c3c-267">視需要重複步驟 3</span><span class="sxs-lookup"><span data-stu-id="80c3c-267">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="80c3c-268">在生產環境中部署</span><span class="sxs-lookup"><span data-stu-id="80c3c-268">Deploy in production</span></span>

<span data-ttu-id="80c3c-269">模擬的部署執行方式類似 PowerShell 的 WhatIf 參數。</span><span class="sxs-lookup"><span data-stu-id="80c3c-269">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="80c3c-270">您會看到結果，報告就像是自動加上標籤原則已使用您定義的規則，套用您選取的標籤。</span><span class="sxs-lookup"><span data-stu-id="80c3c-270">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="80c3c-271">如果需要，您可以接著調整規則的精確度，並重新執行模擬。</span><span class="sxs-lookup"><span data-stu-id="80c3c-271">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="80c3c-272">不過，由於 Exchange 的自動加上標籤適用於傳送和接收的電子郵件，而不是儲存在信箱中的電子郵件，因此除非您能夠傳送及接收完全相同的電子郵件訊息，否則請不要預期模擬中的電子郵件結果一致。</span><span class="sxs-lookup"><span data-stu-id="80c3c-272">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="80c3c-273">模擬模式也可讓您在部署之前逐漸增加自動加上標籤原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="80c3c-273">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="80c3c-274">例如，您可能會從單一位置 (例如具有單一文件庫的 SharePoint 網站) 開始使用。</span><span class="sxs-lookup"><span data-stu-id="80c3c-274">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="80c3c-275">接著，使用反覆變更將範圍增加到多個網站，然後增加至其他位置 (例如 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-275">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="80c3c-276">最後，您可以使用模擬模式來提供執行自動加上標籤原則所需時間的近似值，以協助您規劃並排程不使用模擬模式執行的時間。</span><span class="sxs-lookup"><span data-stu-id="80c3c-276">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="80c3c-277">建立自動加上標籤原則</span><span class="sxs-lookup"><span data-stu-id="80c3c-277">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="80c3c-278">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="80c3c-278">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="80c3c-279">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="80c3c-279">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="80c3c-280">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-280">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="80c3c-281">選取 [自動加上標籤 (預覽)]\*\*\*\* 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="80c3c-281">Select the **Auto-labeling (preview)** tab:</span></span>
    
    ![自動加上標籤 (預覽) 索引標籤](../media/auto-labeling-tab.png)

3. <span data-ttu-id="80c3c-283">選取 [+ 建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-283">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="80c3c-284">針對 [選擇您要套用此標籤的資訊]\*\*\*\* 頁面：選取其中一個範本，例如 [財務]\*\*\*\* 或 [隱私權]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-284">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="80c3c-285">您可以使用 [顯示選項]\*\*\*\* 下拉式清單來精簡搜尋。</span><span class="sxs-lookup"><span data-stu-id="80c3c-285">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="80c3c-286">或者，如果範本不符合您的需求，請選取 [自訂原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-286">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="80c3c-287">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-287">Select **Next**.</span></span>

5. <span data-ttu-id="80c3c-288">針對 [為您的自動加上標籤原則命名]\*\*\*\* 頁面：提供唯一名稱，以及選擇性提供說明，以協助識別自動套用的標籤、位置和條件，以上項目可識別加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-288">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="80c3c-289">針對 [選擇您要套用標籤的位置]\*\*\*\* 頁面：選取並指定 Exchange、SharePoint 網站和 OneDrive 的位置。</span><span class="sxs-lookup"><span data-stu-id="80c3c-289">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="80c3c-290">接著，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-290">Then select **Next**.</span></span>

7. <span data-ttu-id="80c3c-291">針對 [定義原則設定]\*\*\*\* 頁面：保留預設值 [尋找包含的內容]\*\*\*\* 以定義規則，可識別在您所選取所有位置之間要加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-291">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="80c3c-292">如果您在每個位置都需要不同的規則，請選取 [進階設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-292">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="80c3c-293">接著，選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-293">Then select **Next**.</span></span>
    
    <span data-ttu-id="80c3c-294">規則會使用條件，其中包括敏感性資訊類型和共用選項：</span><span class="sxs-lookup"><span data-stu-id="80c3c-294">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="80c3c-295">針對敏感性資訊類型，您可以選取內建和自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="80c3c-295">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="80c3c-296">針對共用選項，您可以選擇 [僅與我組織內部的人員]\*\*\*\* 或 [與我組織外部的人員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-296">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="80c3c-297">如果您唯一的位置是 **Exchange**，或如果您選取 [進階設定]\*\*\*\*，您還可以選取其他條件：</span><span class="sxs-lookup"><span data-stu-id="80c3c-297">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="80c3c-298">寄件者 IP 位址為</span><span class="sxs-lookup"><span data-stu-id="80c3c-298">Sender IP address is</span></span>
    - <span data-ttu-id="80c3c-299">收件者網域為</span><span class="sxs-lookup"><span data-stu-id="80c3c-299">Recipient domain is</span></span>
    - <span data-ttu-id="80c3c-300">收件者為</span><span class="sxs-lookup"><span data-stu-id="80c3c-300">Recipient is</span></span>
    - <span data-ttu-id="80c3c-301">附件的副檔名為</span><span class="sxs-lookup"><span data-stu-id="80c3c-301">Attachment's file extension is</span></span>
    - <span data-ttu-id="80c3c-302">附件受密碼保護</span><span class="sxs-lookup"><span data-stu-id="80c3c-302">Attachment is password protected</span></span>
    - <span data-ttu-id="80c3c-303">文件屬性為</span><span class="sxs-lookup"><span data-stu-id="80c3c-303">Document property is</span></span>
    - <span data-ttu-id="80c3c-304">無法掃描的任何電子郵件附件內容</span><span class="sxs-lookup"><span data-stu-id="80c3c-304">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="80c3c-305">未完成掃描的任何電子郵件附件內容</span><span class="sxs-lookup"><span data-stu-id="80c3c-305">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="80c3c-306">針對 [設定規則來定義要對哪個內容加上標籤]\*\*\*\* 頁面：選取 [+ 建立規則]\*\*\*\* 然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-306">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="80c3c-307">在 [建立規則]\*\*\*\* 頁面上，使用敏感性資訊類型或共用選項來為您的規則命名和加以定義，然後選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-307">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="80c3c-308">敏感性資訊類型的設定選項，和您針對 Office 應用程式的自動加上標籤所選取的設定選項相同。</span><span class="sxs-lookup"><span data-stu-id="80c3c-308">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="80c3c-309">如需詳細資訊，請參閱[設定標籤的敏感性資訊類型](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-309">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="80c3c-310">回到 [設定規則來定義要對哪個內容加上標籤]\*\*\*\* 頁面：如果您需要另一個規則來識別要加上標籤的內容，請選取 [+ 建立規則]\*\*\*\*，然後重複上一個步驟。</span><span class="sxs-lookup"><span data-stu-id="80c3c-310">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="80c3c-311">當您已定義所有需要的規則，並確認其狀態為開啟時，請選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-311">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="80c3c-312">針對 [選擇要自動套用的標籤]\*\*\*\* 頁面：選取 [+ 選擇標籤]\*\*\*\*，從 [選擇敏感度標籤]\*\*\*\* 窗格中選取標籤，然後選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-312">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="80c3c-313">針對 [選擇原則的模式]\*\*\*\* 頁面：如果您現在已準備好在模擬模式中執行自動加上標籤原則，請選取 [測試]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-313">For the **Choose a mode for the policy** page: Select **Test it out** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="80c3c-314">否則，請選取 [保持關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-314">Otherwise, select **Leave it turned off**.</span></span> <span data-ttu-id="80c3c-315">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c3c-315">Select **Next**.</span></span> 

13. <span data-ttu-id="80c3c-316">針對 [摘要]\*\*\*\* 頁面：檢閱您的自動加上標籤原則設定，視需要進行任何變更，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="80c3c-316">For the **Summary** page: Review the configuration of the your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="80c3c-317">不同於 Office 應用程式的自動加上標籤，沒有個別發佈選項。</span><span class="sxs-lookup"><span data-stu-id="80c3c-317">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="80c3c-318">不過，發佈標籤時，自動加上標籤原則最多有 24 小時可以在您的整個組織中複寫。</span><span class="sxs-lookup"><span data-stu-id="80c3c-318">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="80c3c-319">現在在 [資訊保護]\*\*\*\* 頁面的 [自動加上標籤 (預覽)]\*\*\*\* 索引標籤上，您會在 [測試]\*\*\*\* 區段中看到您的自動加上標籤原則。</span><span class="sxs-lookup"><span data-stu-id="80c3c-319">Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Testing** section.</span></span> <span data-ttu-id="80c3c-320">選取您的原則，以查看設定和狀態的詳細資料 (例如，仍在測試中或測試完成)。</span><span class="sxs-lookup"><span data-stu-id="80c3c-320">Select your policy to see the details of the configuration and status (for example, still testing or test complete).</span></span> <span data-ttu-id="80c3c-321">選取 [相符項目]\*\*\*\* 索引標籤，以查看哪些電子郵件或文件符合您指定的規則。</span><span class="sxs-lookup"><span data-stu-id="80c3c-321">Select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="80c3c-322">您可以藉由選取頁面頂端的 [編輯]\*\*\*\* 選項，直接從此介面修改您的原則。</span><span class="sxs-lookup"><span data-stu-id="80c3c-322">You can modify your policy directly from this interface by selecting the **Edit** option at the top of the page.</span></span>

<span data-ttu-id="80c3c-323">當您準備好不透過模擬來執行原則時，請選取 [開啟]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="80c3c-323">When you're ready to run the policy without simulation, select the **Turn On** option.</span></span>

<span data-ttu-id="80c3c-324">您也可以在您具有適當[權限](data-classification-content-explorer.md#permissions)時藉由使用[內容總管](data-classification-content-explorer.md)，查看您自動加上標籤原則的結果：</span><span class="sxs-lookup"><span data-stu-id="80c3c-324">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="80c3c-325">**內容總管清單檢視器**可讓您查看檔案的標籤，但是無法查看檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-325">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="80c3c-326">**內容總管內容檢視器**可讓您查看檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="80c3c-326">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="80c3c-327">您也可以使用內容總管來識別具有未加上標籤文件 (包含敏感性資訊) 的位置。</span><span class="sxs-lookup"><span data-stu-id="80c3c-327">You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information.</span></span> <span data-ttu-id="80c3c-328">使用這項資訊，請考量將這些位置新增到您的自動加上標籤原則，並納入已識別的敏感性資訊類型作為規則。</span><span class="sxs-lookup"><span data-stu-id="80c3c-328">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>


