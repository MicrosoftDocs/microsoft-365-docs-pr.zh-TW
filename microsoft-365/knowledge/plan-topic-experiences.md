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
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150475"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="4ec3a-103">Microsoft Viva 主題的計畫</span><span class="sxs-lookup"><span data-stu-id="4ec3a-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="4ec3a-104">您可以掌控組織中主題的經驗。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="4ec3a-105">針對主題的規劃決策可確保向您的使用者顯示高品質的主題，且具有適當的許可權來使用及參與知識。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="4ec3a-106">在本文中，我們將會檢查這些規劃決策：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="4ec3a-107">您想要為主題編目的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="4ec3a-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="4ec3a-108">您想要從主題經驗中排除哪些主題（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="4ec3a-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="4ec3a-109">您要將主題顯示在哪個使用者上</span><span class="sxs-lookup"><span data-stu-id="4ec3a-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="4ec3a-110">您要在主題中心提供許可權以管理主題的使用者</span><span class="sxs-lookup"><span data-stu-id="4ec3a-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="4ec3a-111">您要在主題中心提供許可權以建立或編輯主題的使用者</span><span class="sxs-lookup"><span data-stu-id="4ec3a-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="4ec3a-112">您想要在主題中心提供什麼名稱</span><span class="sxs-lookup"><span data-stu-id="4ec3a-112">What name you want to give your topic center</span></span>

<span data-ttu-id="4ec3a-113">考慮到資料的安全性和隱私權，主題經驗不會授與使用者對他們沒有許可權之檔案的其他存取權。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="4ec3a-114">建議您在規劃過程中，閱讀 [Microsoft Viva 主題的安全性和隱私權](topic-experiences-security-privacy.md) 。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ec3a-115">需求</span><span class="sxs-lookup"><span data-stu-id="4ec3a-115">Requirements</span></span>

<span data-ttu-id="4ec3a-116">您必須 [訂閱 Viva 主題](https://www.microsoft.com/microsoft-viva/topics) ，以及全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定相關主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="4ec3a-117">所有要使用主題的使用者都需要經驗豐富的授權 **主題** 。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="4ec3a-118">在 [設定 Microsoft Viva 主題](set-up-topic-experiences.md)中涵蓋指派授權。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="4ec3a-119">主題探索</span><span class="sxs-lookup"><span data-stu-id="4ec3a-119">Topic discovery</span></span>

<span data-ttu-id="4ec3a-120">「主題探索」設定會指定哪些 SharePoint 網站用作主題的來源。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="4ec3a-121">您可以選擇包含所有的 SharePoint 網站、特定的網站清單，或沒有網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="4ec3a-122">建議您選擇 [所有網站]，讓主題體驗能夠為您的使用者探索大量的良好主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="4ec3a-123">當您設定主題時，可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="4ec3a-124">**所有網站**：您組織中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="4ec3a-125">這包括目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-125">This includes current and future sites.</span></span>
- <span data-ttu-id="4ec3a-126">**全部，除了選取的網站** 之外：所有網站，您指定的網站除外。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="4ec3a-127">在未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="4ec3a-128">**僅限選取的網站**：僅限您指定的網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="4ec3a-129">未來建立的網站不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="4ec3a-130">**無網站**：不包含任何 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="4ec3a-131">如果您選擇 [ **全部] （選取的網站除外** 或 **僅限選取的網站**），您可以上傳具有網站清單的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="4ec3a-132">如果您正在執行試驗，而且想要包含有限數目的網站來啟動，這些選項會非常有用。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="4ec3a-133">您可以複製下列 .csv 範本：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="4ec3a-134">建議您不要選擇「 **沒有網站** 」，因為這會使主題不會自動建立或更新。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="4ec3a-135">不過，如果您想要設定後續主題，然後再新增網站，您可以選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="4ec3a-136">建議您為使用者或知識管理員建立一個程式，以便在組織中需要從主題探索中移除個別網站。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="4ec3a-137">使用者權限</span><span class="sxs-lookup"><span data-stu-id="4ec3a-137">User permissions</span></span>

<span data-ttu-id="4ec3a-138">您指定的使用者權限會決定您的組織中的哪些人員與主題及可執行檔動作進行互動。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="4ec3a-139">*管理主題*</span><span class="sxs-lookup"><span data-stu-id="4ec3a-139">*Manage topics*</span></span>

<span data-ttu-id="4ec3a-140">知識管理員會監督資訊的品質，以及組織中其結構化及其他最佳作法的方式。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="4ec3a-141">他們可以確認和拒絕主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="4ec3a-142">雖然您可以指定個別的主題管理員，但建議您建立安全性群組 (或使用現有的一個) ，其中包含您想要成為知識管理員的人員。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="4ec3a-143">您可以在安裝過程中指定此安全性群組。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="4ec3a-144">*建立及編輯主題*</span><span class="sxs-lookup"><span data-stu-id="4ec3a-144">*Create and edit topics*</span></span>

<span data-ttu-id="4ec3a-145">主題參與者是組織中的擁護者和主題專家。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="4ec3a-146">他們可以建立及編輯主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-146">They can create and edit topics.</span></span> 

<span data-ttu-id="4ec3a-147">建議您讓組織中的每個人都可以建立及編輯主題，因為在所有使用者都能共用資訊時，主題所能發揮最佳作用。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="4ec3a-148">如果您想要限制建立及編輯特定人員或群組的主題，請為他們建立安全性群組並在安裝過程中加以指定。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="4ec3a-149">您可以選擇不允許任何人參與主題，但是不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="4ec3a-150">如果您選擇此選項，則知識管理員仍可編輯及建立主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="4ec3a-151">*主題檢視器*</span><span class="sxs-lookup"><span data-stu-id="4ec3a-151">*Topic viewers*</span></span>

<span data-ttu-id="4ec3a-152">主題檢視器可以查看主題頁面上的資訊、搜尋結果和主題在 SharePoint 頁面等內容中的反白顯示。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="4ec3a-153">當使用者可以存取已發現主題的檔案和頁面時，使用者才會看到已發現的主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="4ec3a-154">當您設定主題檢視器時，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="4ec3a-155">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="4ec3a-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="4ec3a-156">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="4ec3a-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="4ec3a-157">**沒人**</span><span class="sxs-lookup"><span data-stu-id="4ec3a-157">**No one**</span></span>

<span data-ttu-id="4ec3a-158">我們建議您 **在組織中的每個人**，但如果您要進行試生產，您可能只想選擇選取的人員或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="4ec3a-159">如果您想要設定主題，但不允許人員查看主題，也可以選擇 [ **否** ]。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="4ec3a-160"> (知識管理員仍具有存取權，讓他們可以查看主題，並協助您決定是否要讓主題獲得廣泛的使用。 ) </span><span class="sxs-lookup"><span data-stu-id="4ec3a-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="4ec3a-161">知識規則</span><span class="sxs-lookup"><span data-stu-id="4ec3a-161">Knowledge rules</span></span>

<span data-ttu-id="4ec3a-162">以管理員的身分，您可以從主題經驗中排除特定主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="4ec3a-163">如果您想要讓機密資料不會出現在主題中，這是很有用的。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="4ec3a-164">雖然知識管理員可以排除主題中心的主題，但不是管理員所排除的主題，也不會對知識管理員顯示。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="4ec3a-165"> (知識管理員也可以移除探索之後主題中心的主題。 ) </span><span class="sxs-lookup"><span data-stu-id="4ec3a-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="4ec3a-166">如果您想要排除系統管理員層級的主題，您必須將它們新增至 .csv 檔案並上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="4ec3a-167">您可以在安裝程式或更新版本期間執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-167">You can do this during setup or later.</span></span>

<span data-ttu-id="4ec3a-168">.Csv 檔案必須包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="4ec3a-169">**名稱**：輸入您要排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4ec3a-170">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-170">There are two ways to do this:</span></span>
- <span data-ttu-id="4ec3a-171">**MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="4ec3a-172">完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="4ec3a-173">部分相符：您可以排除包含特定單字的所有主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4ec3a-174">例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="4ec3a-175">**代表 (選用)**： (也稱為 *擴充*) 若要排除縮寫，請輸入縮寫詞代表的字。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

<span data-ttu-id="4ec3a-177">您可以複製下列 csv 範本：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="4ec3a-178">系統管理</span><span class="sxs-lookup"><span data-stu-id="4ec3a-178">Administration</span></span>

<span data-ttu-id="4ec3a-179">當您設定主題時，會自動建立主題中心。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="4ec3a-180">請考慮您想要為主題中心命名的專案，以及您想要的 URL 的名稱。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="4ec3a-181">您可以設定名稱和 URL 做為安裝程式的一部分，您可以在 Microsoft 365 系統管理中心中變更名稱 (但不包括 URL) 。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ec3a-182">您可以只有一個主題中心。</span><span class="sxs-lookup"><span data-stu-id="4ec3a-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="4ec3a-183">安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="4ec3a-183">Setup checklist</span></span>

<span data-ttu-id="4ec3a-184">當您設定主題經驗時，當您執行安裝精靈時，需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="4ec3a-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="4ec3a-185">若未包含主題探索的所有網站，要包含或排除的網站清單</span><span class="sxs-lookup"><span data-stu-id="4ec3a-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="4ec3a-186">如果不允許所有使用者查看主題，則為主題檢視器的安全性群組</span><span class="sxs-lookup"><span data-stu-id="4ec3a-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="4ec3a-187">主題參與者的安全性群組（如果不允許所有使用者建立及編輯主題）</span><span class="sxs-lookup"><span data-stu-id="4ec3a-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="4ec3a-188">如果不允許所有使用者管理主題，則為主題知識管理員的安全性群組</span><span class="sxs-lookup"><span data-stu-id="4ec3a-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="4ec3a-189">要從主題探索中排除的機密主題清單</span><span class="sxs-lookup"><span data-stu-id="4ec3a-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="4ec3a-190">主題中心網站的名稱</span><span class="sxs-lookup"><span data-stu-id="4ec3a-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="4ec3a-191">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ec3a-191">See also</span></span>

[<span data-ttu-id="4ec3a-192">設定主題體驗</span><span class="sxs-lookup"><span data-stu-id="4ec3a-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="4ec3a-193">在 Microsoft 365 中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="4ec3a-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="4ec3a-194">在 Microsoft 365 中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="4ec3a-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="4ec3a-195">在 Microsoft 365 中管理主題許可權</span><span class="sxs-lookup"><span data-stu-id="4ec3a-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="4ec3a-196">變更 Microsoft 365 主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="4ec3a-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
