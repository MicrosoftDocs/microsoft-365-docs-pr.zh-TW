---
title: Microsoft Viva 主題的計畫
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 瞭解如何規劃 Microsoft Viva 主題的計畫
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583109"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="5aa7d-103">Microsoft Viva 主題的計畫</span><span class="sxs-lookup"><span data-stu-id="5aa7d-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="5aa7d-104">您可以掌控組織中主題的經驗。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="5aa7d-105">針對主題的規劃決策可確保向您的使用者顯示高品質的主題，且具有適當的許可權來使用及參與知識。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="5aa7d-106">在本文中，我們將會檢查這些規劃決策：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="5aa7d-107">您想要為主題編目的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="5aa7d-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="5aa7d-108">您想要從主題經驗中排除哪些主題（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="5aa7d-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="5aa7d-109">您要將主題顯示在哪個使用者上</span><span class="sxs-lookup"><span data-stu-id="5aa7d-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="5aa7d-110">您要在主題中心提供許可權以管理主題的使用者</span><span class="sxs-lookup"><span data-stu-id="5aa7d-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="5aa7d-111">您要在主題中心提供許可權以建立或編輯主題的使用者</span><span class="sxs-lookup"><span data-stu-id="5aa7d-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="5aa7d-112">您想要在主題中心提供什麼名稱</span><span class="sxs-lookup"><span data-stu-id="5aa7d-112">What name you want to give your topic center</span></span>

<span data-ttu-id="5aa7d-113">考慮到資料的安全性和隱私權，主題經驗不會授與使用者對他們沒有許可權之檔案的其他存取權。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="5aa7d-114">建議您在規劃過程中，閱讀 [Microsoft Viva 主題的安全性和隱私權](topic-experiences-security-privacy.md) 。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="5aa7d-115">若要深入瞭解 Viva 主題背後的 AI 技術，請參閱 [Microsoft Viva 主題中的 Alexandria：從大型資料到大型知識](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="5aa7d-116">需求</span><span class="sxs-lookup"><span data-stu-id="5aa7d-116">Requirements</span></span>

<span data-ttu-id="5aa7d-117">您必須[訂閱 Viva 主題](https://www.microsoft.com/microsoft-viva/topics)，以及全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定相關主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="5aa7d-118">所有要使用主題的使用者都需要經驗豐富的授權 **主題** 。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="5aa7d-119">在 [設定 Microsoft Viva 主題](set-up-topic-experiences.md)中涵蓋指派授權。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="5aa7d-120">主題探索</span><span class="sxs-lookup"><span data-stu-id="5aa7d-120">Topic discovery</span></span>

<span data-ttu-id="5aa7d-121">主題探索設定會指定使用哪些 SharePoint 網站作為主題的來源。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="5aa7d-122">您可以選擇包含所有 SharePoint 網站、特定網站清單或沒有網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-122">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="5aa7d-123">建議您選擇 [所有網站]，讓主題體驗能夠為您的使用者探索大量的良好主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-123">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="5aa7d-124">當您設定 Viva Topics 時，可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-124">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="5aa7d-125">**所有網站**：貴組織的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-125">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="5aa7d-126">這包括目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-126">This includes current and future sites.</span></span>
- <span data-ttu-id="5aa7d-127">**除了選取的網站以外的所有網站**：除了您所指定網站之外的所有網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-127">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="5aa7d-128">在未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-128">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="5aa7d-129">**僅限選取的網站**：僅限您指定的網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-129">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="5aa7d-130">未來建立的網站將不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-130">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="5aa7d-131">**沒有網站**：不包含任何 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-131">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="5aa7d-132">如果您選擇 [ **全部] （選取的網站除外** 或 **僅限選取的網站**），您可以上傳具有網站清單的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-132">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="5aa7d-133">如果您正在執行試驗，而且想要包含有限數目的網站來啟動，這些選項會非常有用。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-133">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="5aa7d-134">您可以複製下列的 .csv 範本：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-134">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="5aa7d-135">建議您不要選擇「 **沒有網站** 」，因為這會使主題不會自動建立或更新。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-135">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="5aa7d-136">不過，如果您想要設定後續主題，然後再新增網站，您可以選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-136">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="5aa7d-137">建議您為使用者或知識管理員建立一個程式，以便在組織中需要從主題探索中移除個別網站。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-137">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="5aa7d-138">多地理位置</span><span class="sxs-lookup"><span data-stu-id="5aa7d-138">Multi-geo</span></span>

<span data-ttu-id="5aa7d-139">如果您的組織已部署[Microsoft 365 多地理](/microsoft-365/enterprise/microsoft-365-multi-geo)位置，主題中心會布建于中央位置，而且位於中央位置的 SharePoint 網站可作為主題的來源使用。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-139">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="5aa7d-140"> (如果選取 [ **所有網站**]，Viva 主題將使用中央位置中的所有網站。 ) </span><span class="sxs-lookup"><span data-stu-id="5aa7d-140">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="5aa7d-141">內容的所有處理及儲存都是在中央位置進行的。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-141">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="5aa7d-142">使用者權限</span><span class="sxs-lookup"><span data-stu-id="5aa7d-142">User permissions</span></span>

<span data-ttu-id="5aa7d-143">您指定的使用者權限會決定您的組織中的哪些人員與主題及可執行檔動作進行互動。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-143">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="5aa7d-144">在這個階段中，Viva 主題不支援提供來賓 (外部) 使用者的授權或使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-144">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="5aa7d-145">*管理主題*</span><span class="sxs-lookup"><span data-stu-id="5aa7d-145">*Manage topics*</span></span>

<span data-ttu-id="5aa7d-146">知識管理員會監督資訊的品質，以及組織中其結構化及其他最佳作法的方式。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-146">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="5aa7d-147">他們可以確認和拒絕主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-147">They can confirm and reject topics.</span></span>

<span data-ttu-id="5aa7d-148">雖然您可以指定個別的主題管理員，但建議您建立安全性群組 (或使用現有的一個) ，其中包含您想要成為知識管理員的人員。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-148">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="5aa7d-149">您可以在安裝過程中指定此安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-149">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="5aa7d-150">*建立和編輯主題*</span><span class="sxs-lookup"><span data-stu-id="5aa7d-150">*Create and edit topics*</span></span>

<span data-ttu-id="5aa7d-151">主題參與者是組織中的擁護者和主題專家。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-151">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="5aa7d-152">他們可以建立及編輯主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-152">They can create and edit topics.</span></span> 

<span data-ttu-id="5aa7d-153">建議您讓組織中的每個人都可以建立及編輯主題，因為在所有使用者都能共用資訊時，主題所能發揮最佳作用。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-153">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="5aa7d-154">如果您想要限制建立及編輯特定人員或群組的主題，請為他們建立安全性群組並在安裝過程中加以指定。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-154">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="5aa7d-155">您可以選擇不允許任何人參與主題，但是不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-155">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="5aa7d-156">如果您選擇此選項，則知識管理員仍可編輯及建立主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-156">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="5aa7d-157">*主題檢視器*</span><span class="sxs-lookup"><span data-stu-id="5aa7d-157">*Topic viewers*</span></span>

<span data-ttu-id="5aa7d-158">主題檢視器可以查看主題頁面上的資訊、搜尋結果和主題在 SharePoint 頁面等內容中的反白顯示。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-158">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="5aa7d-159">當使用者可以存取已發現主題的檔案和頁面時，使用者才會看到已發現的主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-159">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="5aa7d-160">當您設定主題檢視器時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-160">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="5aa7d-161">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="5aa7d-161">**Everyone in my organization**</span></span>
- <span data-ttu-id="5aa7d-162">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="5aa7d-162">**Only selected people or security groups**</span></span>
- <span data-ttu-id="5aa7d-163">**沒人**</span><span class="sxs-lookup"><span data-stu-id="5aa7d-163">**No one**</span></span>

<span data-ttu-id="5aa7d-164">我們建議您 **在組織中的每個人**，但如果您要進行試生產，您可能只想選擇選取的人員或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-164">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="5aa7d-165">如果您想要設定主題，但不允許人員查看主題，也可以選擇 [ **否** ]。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-165">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="5aa7d-166"> (知識管理員仍具有存取權，讓他們可以查看主題，並協助您決定是否要讓主題獲得廣泛的使用。 ) </span><span class="sxs-lookup"><span data-stu-id="5aa7d-166">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="5aa7d-167">知識規則</span><span class="sxs-lookup"><span data-stu-id="5aa7d-167">Knowledge rules</span></span>

<span data-ttu-id="5aa7d-168">以管理員的身分，您可以從主題經驗中排除特定主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-168">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="5aa7d-169">如果您想要讓機密資料不會出現在主題中，這是很有用的。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-169">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="5aa7d-170">雖然知識管理員可以排除主題中心的主題，但不是管理員所排除的主題，也不會對知識管理員顯示。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-170">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="5aa7d-171"> (知識管理員也可以移除探索之後主題中心的主題。 ) </span><span class="sxs-lookup"><span data-stu-id="5aa7d-171">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="5aa7d-172">如果您想要在系統管理員層級排除主題，您必須將它們新增至 .csv 檔案，並上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-172">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="5aa7d-173">您可以在安裝程式或更新版本期間執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-173">You can do this during setup or later.</span></span>

<span data-ttu-id="5aa7d-174">.csv 檔必須包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-174">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="5aa7d-175">**名稱**：輸入要排除之主題的名稱。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-175">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="5aa7d-176">執行這項作業的方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-176">There are two ways to do this:</span></span>
- <span data-ttu-id="5aa7d-177">**MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-177">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="5aa7d-178">完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-178">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="5aa7d-179">部分相符：您可以排除包含特定單字的所有主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-179">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="5aa7d-180">例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-180">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="5aa7d-181">**代表 (選用)**： (也稱為 *擴充*) 若要排除縮寫，請輸入縮寫詞代表的字。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-181">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

<span data-ttu-id="5aa7d-183">您可以複製下列 csv 範本：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-183">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="5aa7d-184">系統管理</span><span class="sxs-lookup"><span data-stu-id="5aa7d-184">Administration</span></span>

<span data-ttu-id="5aa7d-185">當您設定主題時，會自動建立主題中心。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-185">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="5aa7d-186">請考慮您想要為主題中心命名的專案，以及您想要的 URL 的名稱。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-186">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="5aa7d-187">您可以設定名稱和 URL 做為安裝程式的一部分，您可以變更 Microsoft 365 系統管理中心的名稱 (，但不能變更 URL) 。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-187">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5aa7d-188">您可以只有一個主題中心。</span><span class="sxs-lookup"><span data-stu-id="5aa7d-188">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="5aa7d-189">安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="5aa7d-189">Setup checklist</span></span>

<span data-ttu-id="5aa7d-190">當您設定主題經驗時，當您執行安裝精靈時，需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="5aa7d-190">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5aa7d-191">要包含或排除的網站清單 (如果不包含所有網站以進行主題探索)</span><span class="sxs-lookup"><span data-stu-id="5aa7d-191">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="5aa7d-192">主題檢視者的安全性群組 (如果不允許所有使用者檢視主題)</span><span class="sxs-lookup"><span data-stu-id="5aa7d-192">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="5aa7d-193">主題參與者的安全性群組 (如果不允許所有使用者建立及編輯主題)</span><span class="sxs-lookup"><span data-stu-id="5aa7d-193">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="5aa7d-194">主題知識管理員的安全性群組 (如果不允許所有使用者管理主題)</span><span class="sxs-lookup"><span data-stu-id="5aa7d-194">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="5aa7d-195">要從主題探索中排除的機密主題清單</span><span class="sxs-lookup"><span data-stu-id="5aa7d-195">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="5aa7d-196">主題中心網站的名稱</span><span class="sxs-lookup"><span data-stu-id="5aa7d-196">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="5aa7d-197">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5aa7d-197">See also</span></span>

[<span data-ttu-id="5aa7d-198">設定主題體驗</span><span class="sxs-lookup"><span data-stu-id="5aa7d-198">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="5aa7d-199">在 Microsoft 365 中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="5aa7d-199">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="5aa7d-200">在 Microsoft 365 中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="5aa7d-200">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="5aa7d-201">管理 Microsoft 365 中的主題許可權</span><span class="sxs-lookup"><span data-stu-id="5aa7d-201">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="5aa7d-202">在 Microsoft 365 中變更主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="5aa7d-202">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
