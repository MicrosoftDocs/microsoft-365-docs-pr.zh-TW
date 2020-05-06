---
title: 套用或移除網站的文件刪除原則
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何在 Office 365 網站集合中建立、刪除及管理檔刪除原則。
ms.openlocfilehash: 7a9cbec25349de02da35f0aaf0cc206774a9b59a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034337"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="28103-103">套用或移除網站的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="28103-103">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="28103-104">組織通常會受到法規遵從性、法律或其他法規的制約，這些法規要求他們在特定的一段時間內保留檔。</span><span class="sxs-lookup"><span data-stu-id="28103-104">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="28103-105">但是，將文件保留超過要求時間，可能會讓組織暴露在法律風險下。</span><span class="sxs-lookup"><span data-stu-id="28103-105">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="28103-106">因此，您的組織可能已為網站&mdash;建立檔刪除原則例如，在建立一般商務檔後，可能需要將其刪除五年。</span><span class="sxs-lookup"><span data-stu-id="28103-106">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="28103-107">視您的組織而定，檔刪除原則可能是：</span><span class="sxs-lookup"><span data-stu-id="28103-107">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="28103-108">**強制**網站擁有者無法選擇不需要的強制原則，這會自動套用至網站。</span><span class="sxs-lookup"><span data-stu-id="28103-108">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="28103-109">**預設值**預設原則會自動套用至網站，但網站擁有者可以：</span><span class="sxs-lookup"><span data-stu-id="28103-109">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="28103-110">選擇另一個原則（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="28103-110">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="28103-111">若未與網站內容相關，請將原則完全取消選擇。</span><span class="sxs-lookup"><span data-stu-id="28103-111">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="28103-112">**不是強制或預設**在此情況下，不會將任何原則套用至網站，網站擁有人必須採取行動才能套用。</span><span class="sxs-lookup"><span data-stu-id="28103-112">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="28103-113">檔刪除原則可以包含一個以上的規則&mdash;。例如，一個規則可能會在建立檔一年後將其刪除一年，但另一個規則可能會指出刪除檔的最後一年修改。</span><span class="sxs-lookup"><span data-stu-id="28103-113">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="28103-114">若原則包含一個以上的規則，您可以選取最適合您網站的規則。</span><span class="sxs-lookup"><span data-stu-id="28103-114">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="28103-115">刪除規則會套用至網站中的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="28103-115">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="28103-116">在網站中，一次只能有一個原則和一個規則可供使用。</span><span class="sxs-lookup"><span data-stu-id="28103-116">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="28103-117">與原則類似的是，規則可以設定為預設值，以便在套用原則時自動套用。</span><span class="sxs-lookup"><span data-stu-id="28103-117">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="28103-118">最後，會繼承檔刪除原則。</span><span class="sxs-lookup"><span data-stu-id="28103-118">Finally, document deletion policies are inherited.</span></span> <span data-ttu-id="28103-119">當您為網站選取原則或規則時，所有子網站會繼承該選取範圍，雖然子網站的擁有者可以透過選取其他原則或規則來中斷繼承。</span><span class="sxs-lookup"><span data-stu-id="28103-119">When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule.</span></span> <span data-ttu-id="28103-120">當您選取原則或規則時，請考慮網站底下任何子網站的內容。</span><span class="sxs-lookup"><span data-stu-id="28103-120">When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="28103-121">查看網站集合中可用的檔刪除原則</span><span class="sxs-lookup"><span data-stu-id="28103-121">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="28103-122">您的組織可以指派不同的原則給不同的網站集合。</span><span class="sxs-lookup"><span data-stu-id="28103-122">Your organization may assign different policies to different site collections.</span></span> <span data-ttu-id="28103-123">在網站集合層級，網站集合的擁有者可以查看該網站集合可使用的所有檔刪除原則。</span><span class="sxs-lookup"><span data-stu-id="28103-123">At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection.</span></span> <span data-ttu-id="28103-124">這些原則可能已提供給網站集合範本（因而由此範本所建立的所有網站集合）或此特定的網站集合。</span><span class="sxs-lookup"><span data-stu-id="28103-124">The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="28103-125">在網站集合的最上層網站中，選擇右上角的 [**設定**] [齒輪圖示] [ \> **網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="28103-125">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28103-126">在 [**網站集合管理** \> **檔刪除原則**] 底下。</span><span class="sxs-lookup"><span data-stu-id="28103-126">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="28103-127">只有在原則指派至網站集合後，才會出現 **[文件刪除原則]** 連結。</span><span class="sxs-lookup"><span data-stu-id="28103-127">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="28103-128">此外，在將原則指派給網站後，連結不會立即顯示出來，當 [**檔刪除原則**] 連結出現時，它最多可能需要24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="28103-128">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="28103-129">您可以在此頁面上查看：</span><span class="sxs-lookup"><span data-stu-id="28103-129">On this page you can view:</span></span>
    
  - <span data-ttu-id="28103-130">目前指派的原則及相關聯的規則。</span><span class="sxs-lookup"><span data-stu-id="28103-130">The currently assigned policies and the associated rules.</span></span> <span data-ttu-id="28103-131">選取原則，以在右窗格中查看規則。</span><span class="sxs-lookup"><span data-stu-id="28103-131">Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="28103-132">預設原則（如果有的話）會在 [**預設**] 欄中顯示 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="28103-132">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="28103-133">若原則指派為**強制**，郵件會顯示在清單下方。</span><span class="sxs-lookup"><span data-stu-id="28103-133">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="28103-134">此清單僅供查看，供網站集合擁有人查看所有可用的原則和規則。</span><span class="sxs-lookup"><span data-stu-id="28103-134">This list is view only, for the site collection owner to see all of the available policies and rules.</span></span> <span data-ttu-id="28103-135">若要套用原則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="28103-135">To apply a policy, see the next section.</span></span>
  
![指派給網站集合的文件刪除原則檢視](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="28103-137">套用或移除網站的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="28103-137">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="28103-138">網站擁有人或網站集合擁有者，您的組織可能已建立原則，您可以將其套用至您的網站，也可以選擇不完全使用。</span><span class="sxs-lookup"><span data-stu-id="28103-138">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="28103-139">在右上角，選擇 [**設定**] [齒輪圖示] [ \> **網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="28103-139">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28103-140">在 [**網站管理** \> **檔刪除原則**] 底下。</span><span class="sxs-lookup"><span data-stu-id="28103-140">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="28103-141">只有在原則指派至網站集合後，才會出現 **[文件刪除原則]** 連結。</span><span class="sxs-lookup"><span data-stu-id="28103-141">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="28103-142">此外，在將原則指派給網站後，連結不會立即顯示出來，當 [**檔刪除原則**] 連結出現時，它最多可能需要24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="28103-142">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="28103-143">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="28103-143">Do one of the following:</span></span>
    
  - <span data-ttu-id="28103-144">套用**原則**選取原則\> ：在 [ \> **儲存**原則] 中選取規則。</span><span class="sxs-lookup"><span data-stu-id="28103-144">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="28103-145">在網站中，一次只能有一個原則和一個規則可供使用。</span><span class="sxs-lookup"><span data-stu-id="28103-145">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="28103-146">您的組織可能會提供數個原則和規則，以供選擇，或僅有一個原則或規則。</span><span class="sxs-lookup"><span data-stu-id="28103-146">Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![選取原則選項](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="28103-148">**若要選擇不使用原則**選擇 [**自願注意：待辦事項請刪除** \> **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28103-148">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="28103-149">網站擁有者若您決定原則不適用於網站內容，您可以退出宣告檔刪除原則。</span><span class="sxs-lookup"><span data-stu-id="28103-149">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="28103-150">不過，您無法選擇已標記為**強制**的原則。</span><span class="sxs-lookup"><span data-stu-id="28103-150">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![自願退出選項](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="28103-152">檔刪除原則會覆寫其他原則</span><span class="sxs-lookup"><span data-stu-id="28103-152">Document deletion policies override other policies</span></span>

<span data-ttu-id="28103-153">網站可以使用其他原則來保留和刪除內容：</span><span class="sxs-lookup"><span data-stu-id="28103-153">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="28103-154">網站集合的內容類型原則。</span><span class="sxs-lookup"><span data-stu-id="28103-154">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="28103-155">清單或文件庫的資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="28103-155">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="28103-156">如果您將文件刪除原則套用至已對清單或文件庫使用內容類型原則或資訊管理原則的站台，這些原則將會被忽略，而文件刪除原則會有效用。</span><span class="sxs-lookup"><span data-stu-id="28103-156">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="28103-157">如果忽略其他原則，您會看到 [此網站上的內容使用檔刪除原則] 的訊息。</span><span class="sxs-lookup"><span data-stu-id="28103-157">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="28103-158">這表示您應該規劃網站只使用結構化內容（資訊管理原則和內容類型原則）或非結構化內容（檔刪除原則）的原則，而不是兩者同時使用。</span><span class="sxs-lookup"><span data-stu-id="28103-158">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="28103-159">如果您退出宣告檔刪除原則，將不會顯示警告，其他類型的原則也會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="28103-159">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="28103-160">網站原則不會受到檔刪除原則的影響。</span><span class="sxs-lookup"><span data-stu-id="28103-160">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="28103-161">決定是否要忽略內容類型原則</span><span class="sxs-lookup"><span data-stu-id="28103-161">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="28103-162">如果您的網站使用內容類型原則，而您現在看到此訊息，這些原則將不再有效。</span><span class="sxs-lookup"><span data-stu-id="28103-162">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="28103-163">若要還原內容類型原則，您可以從網站移除檔刪除原則（如前文所述），如果有可用的自願退出選項。</span><span class="sxs-lookup"><span data-stu-id="28103-163">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="28103-164">如果沒有任何選項可供選擇，則檔刪除原則是必要的，而且您必須與組織中的合規性監察官聯繫。</span><span class="sxs-lookup"><span data-stu-id="28103-164">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="28103-165">在右上角，選擇 [**設定**] [齒輪圖示] [ \> **網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="28103-165">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28103-166">在 [**網站管理** \> **內容類型原則範本**] 底下。</span><span class="sxs-lookup"><span data-stu-id="28103-166">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![使用檔刪除原則的網站上的警告](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="28103-168">決定是否要忽略資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="28103-168">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="28103-169">如果您的網站使用資訊管理原則，而且現在看到此訊息，則這些原則將不再有效。</span><span class="sxs-lookup"><span data-stu-id="28103-169">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="28103-170">若要還原資訊管理原則，您可以從網站移除檔刪除原則（如前文所述），如果有可用的自願退出選項。</span><span class="sxs-lookup"><span data-stu-id="28103-170">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="28103-171">如果沒有任何選項可供選擇，則檔刪除原則是必要的，而且您必須與組織中的合規性監察官聯繫。</span><span class="sxs-lookup"><span data-stu-id="28103-171">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="28103-172">若為清單或文件庫，請在\> [**許可權與管理** \> **資訊管理原則設定**] 底下的 [功能區**庫**] \>索引標籤**庫設定** \> 。</span><span class="sxs-lookup"><span data-stu-id="28103-172">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![使用檔刪除原則的網站上的警告](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="28103-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28103-174">See also</span></span>

[<span data-ttu-id="28103-175">文件刪除原則概觀</span><span class="sxs-lookup"><span data-stu-id="28103-175">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="28103-176">建立文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="28103-176">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

