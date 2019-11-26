---
title: 套用或移除網站的文件刪除原則
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: 組織通常會受限於合規性、 法律或其他法規，需要一段時間保留文件。 但是，將文件保留超過要求時間，可能會讓組織暴露在法律風險下。 基於這個理由，您的組織可能已建立您網站的文件刪除原則 — 例如，一般商業文件可能需要刪除五年之後建立它們。
ms.openlocfilehash: 2eaa864cda726e6e36625f81358da76856db7db4
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256760"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="7282c-105">套用或移除網站的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="7282c-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="7282c-106">組織通常會受限於合規性、 法律或其他法規，需要一段時間保留文件。</span><span class="sxs-lookup"><span data-stu-id="7282c-106">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="7282c-107">但是，將文件保留超過要求時間，可能會讓組織暴露在法律風險下。</span><span class="sxs-lookup"><span data-stu-id="7282c-107">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="7282c-108">基於這個理由，您的組織可能已建立您網站的文件刪除原則&mdash;，例如，一般商業文件可能就需要刪除五年之後建立它們。</span><span class="sxs-lookup"><span data-stu-id="7282c-108">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="7282c-109">有些組織可能使用文件刪除原則：</span><span class="sxs-lookup"><span data-stu-id="7282c-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="7282c-110">**強制**網站擁有人無法選擇不採用強制原則，自動套用至網站。</span><span class="sxs-lookup"><span data-stu-id="7282c-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="7282c-111">**預設值**預設原則會自動套用至網站，但網站擁有者可以：</span><span class="sxs-lookup"><span data-stu-id="7282c-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="7282c-112">如果有的話，請選擇其他原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="7282c-113">退出原則，完全如果它不是相關網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="7282c-113">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="7282c-114">**既非強制，也不預設**在此情況下，沒有原則會自動套用至網站和網站擁有者必須自行套用原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="7282c-115">文件刪除原則可能包含多個規則&mdash;，例如一個規則可能會說刪除文件之後，他們所建立，但另一個規則可能會說刪除文件之後他們上次修改的一年的一年。</span><span class="sxs-lookup"><span data-stu-id="7282c-115">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="7282c-116">如果原則包含多個規則，您可以選取最佳適用於您網站的規則。</span><span class="sxs-lookup"><span data-stu-id="7282c-116">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="7282c-117">刪除規則會套用至站台內的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="7282c-117">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="7282c-118">只能將一個原則和一個規則可以為作用中的網站一次。</span><span class="sxs-lookup"><span data-stu-id="7282c-118">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="7282c-119">一個原則，例如規則可以設定為預設值，使其在套用原則時就會自動套用。</span><span class="sxs-lookup"><span data-stu-id="7282c-119">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="7282c-120">最後，會繼承文件刪除原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-120">Finally, document deletion policies are inherited.</span></span> <span data-ttu-id="7282c-121">當您選取的原則或規則您的網站，選取範圍繼承而來的所有子網站，雖然子網站的擁有者，可以選取不同的原則或規則來中斷繼承。</span><span class="sxs-lookup"><span data-stu-id="7282c-121">When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule.</span></span> <span data-ttu-id="7282c-122">當您選取的原則或規則時，請考慮您網站下任何子網站的內容。</span><span class="sxs-lookup"><span data-stu-id="7282c-122">When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="7282c-123">檢視網站集合中可用的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="7282c-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="7282c-124">您的組織可能會將不同的原則指派給不同的網站集合。</span><span class="sxs-lookup"><span data-stu-id="7282c-124">Your organization may assign different policies to different site collections.</span></span> <span data-ttu-id="7282c-125">在網站集合層級，網站集合擁有者可以檢視所有可用來該網站集合的文件刪除原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-125">At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection.</span></span> <span data-ttu-id="7282c-126">原則可能已可使用的網站集合範本 （並因此所有網站集合建立此範本中） 或此特定網站集合。</span><span class="sxs-lookup"><span data-stu-id="7282c-126">The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="7282c-127">最上層網站中的網站集合，在右上角，選擇 [**設定**[齒輪圖示] \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="7282c-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="7282c-128">在 [**網站集合管理**] 下\>**文件刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="7282c-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7282c-129">只有在原則指派至網站集合後，才會出現 **[文件刪除原則]** 連結。</span><span class="sxs-lookup"><span data-stu-id="7282c-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="7282c-130">此外，連結不會出現原則已指派至網站之後，立即 — 可能需要 24 小時的時間從時原則指派給時顯示**文件刪除原則**的連結。</span><span class="sxs-lookup"><span data-stu-id="7282c-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="7282c-131">在此頁面上，您可以檢視：</span><span class="sxs-lookup"><span data-stu-id="7282c-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="7282c-132">目前指派的原則和相關聯的規則。</span><span class="sxs-lookup"><span data-stu-id="7282c-132">The currently assigned policies and the associated rules.</span></span> <span data-ttu-id="7282c-133">選取要檢視的規則在右窗格中的原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-133">Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="7282c-134">預設原則，如果有的話，會顯示 **[是]** [**預設**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="7282c-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="7282c-135">如果原則已被指派為 [**強制**] 清單下方會顯示訊息。</span><span class="sxs-lookup"><span data-stu-id="7282c-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="7282c-136">這份清單可僅，檢視網站集合擁有者若要查看所有可用的原則和規則。</span><span class="sxs-lookup"><span data-stu-id="7282c-136">This list is view only, for the site collection owner to see all of the available policies and rules.</span></span> <span data-ttu-id="7282c-137">若要套用原則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="7282c-137">To apply a policy, see the next section.</span></span>
  
![指派給網站集合的文件刪除原則檢視](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="7282c-139">套用或移除網站的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="7282c-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="7282c-140">為網站擁有人或網站集合擁有者，您的組織可能已建立的原則，您可以套用至您的網站，或選擇退出完全。</span><span class="sxs-lookup"><span data-stu-id="7282c-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="7282c-141">在右上角，選擇 [**設定**[齒輪圖示] \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="7282c-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="7282c-142">在 [**網站管理**] 下\>**文件刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="7282c-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7282c-143">只有在原則指派至網站集合後，才會出現 **[文件刪除原則]** 連結。</span><span class="sxs-lookup"><span data-stu-id="7282c-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="7282c-144">此外，連結不會出現原則已指派至網站之後，立即 — 可能需要 24 小時的時間從時原則指派給時顯示**文件刪除原則**的連結。</span><span class="sxs-lookup"><span data-stu-id="7282c-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="7282c-145">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="7282c-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="7282c-146">**若要套用原則**選取原則\>選取該原則中的規則\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="7282c-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="7282c-147">只能將一個原則和一個規則可以為作用中的網站一次。</span><span class="sxs-lookup"><span data-stu-id="7282c-147">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="7282c-148">您的組織可能會提供數個原則和規則，以從中選擇或只能將一個原則或規則。</span><span class="sxs-lookup"><span data-stu-id="7282c-148">Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![選取原則選項](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="7282c-150">**若要選擇退出原則**選擇 [**退出： 不要注意刪除** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="7282c-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="7282c-151">網站擁有人，您可以選擇退出文件刪除原則如果您判斷該原則未適用於您的網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="7282c-151">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="7282c-152">不過，您無法選擇退出已標示為 [**強制**原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-152">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![選擇加入出選項](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="7282c-154">文件刪除原則會覆寫其他原則</span><span class="sxs-lookup"><span data-stu-id="7282c-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="7282c-155">網站可能使用其他原則來保留及刪除內容：</span><span class="sxs-lookup"><span data-stu-id="7282c-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="7282c-156">網站集合的內容類型原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="7282c-157">清單或文件庫的資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="7282c-158">如果您將文件刪除原則套用至已對清單或文件庫使用內容類型原則或資訊管理原則的站台，這些原則將會被忽略，而文件刪除原則會有效用。</span><span class="sxs-lookup"><span data-stu-id="7282c-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="7282c-159">如果會略過的其他原則，您會看到訊息 「 此網站上的內容使用文件刪除原則 」。</span><span class="sxs-lookup"><span data-stu-id="7282c-159">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="7282c-160">這表示您應該規劃站台能夠使用僅供結構化的內容 （的資訊管理原則與內容類型原則） 或非結構化的內容 （文件刪除原則） 的原則不能兩者同時。</span><span class="sxs-lookup"><span data-stu-id="7282c-160">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="7282c-161">如果您選擇退出文件刪除原則，將不會顯示警告，而其他類型的原則會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="7282c-161">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="7282c-162">網站原則不會受到文件刪除原則。</span><span class="sxs-lookup"><span data-stu-id="7282c-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="7282c-163">決定是否要忽略內容類型原則</span><span class="sxs-lookup"><span data-stu-id="7282c-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="7282c-164">如果正在使用您的網站內容類型原則，您現在會看到這個訊息，這些原則不再有效。</span><span class="sxs-lookup"><span data-stu-id="7282c-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="7282c-165">若要還原的內容類型原則，您可以從您的網站，移除文件刪除原則，如前所述，如果沒有可用的退出選項。</span><span class="sxs-lookup"><span data-stu-id="7282c-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="7282c-166">若要選擇退出任何選項時，文件刪除原則強制性，且您需要連絡法務人員在組織中。</span><span class="sxs-lookup"><span data-stu-id="7282c-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="7282c-167">在右上角，選擇 [**設定**[齒輪圖示] \> **網站設定]**。</span><span class="sxs-lookup"><span data-stu-id="7282c-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="7282c-168">在 [**網站管理**] 下\>**內容類型原則範本**。</span><span class="sxs-lookup"><span data-stu-id="7282c-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![文件刪除原則，正在使用的網站上的警告](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="7282c-170">決定是否要忽略資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="7282c-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="7282c-171">如果您的網站所使用的資訊管理原則，您現在會看到這個訊息，這些原則不再有效。</span><span class="sxs-lookup"><span data-stu-id="7282c-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="7282c-172">若要還原的資訊管理原則，您可以從您的網站，移除文件刪除原則，如前所述，如果沒有可用的退出選項。</span><span class="sxs-lookup"><span data-stu-id="7282c-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="7282c-173">若要選擇退出任何選項時，文件刪除原則強制性，且您需要連絡法務人員在組織中。</span><span class="sxs-lookup"><span data-stu-id="7282c-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="7282c-174">清單或文件庫，在功能區上的\>**文件庫**] 索引標籤\>**文件庫設定** \> **權限與管理**] 下\>**資訊管理原則設定**。</span><span class="sxs-lookup"><span data-stu-id="7282c-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![文件刪除原則，正在使用的網站上的警告](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="7282c-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7282c-176">See also</span></span>

[<span data-ttu-id="7282c-177">文件刪除原則概觀</span><span class="sxs-lookup"><span data-stu-id="7282c-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="7282c-178">建立文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="7282c-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

