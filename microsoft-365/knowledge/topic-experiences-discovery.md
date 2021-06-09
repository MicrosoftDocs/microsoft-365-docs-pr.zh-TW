---
title: 在 Microsoft Viva 主題中管理主題探索
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 瞭解如何在 Microsoft Viva 主題中管理主題探索。
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768971"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="7b042-103">在 Microsoft Viva 主題中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="7b042-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="7b042-104">您可以在[Microsoft 365 系統管理中心](https://admin.microsoft.com)管理主題探索設定。</span><span class="sxs-lookup"><span data-stu-id="7b042-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="7b042-105">您必須是全域系統管理員或 SharePoint 管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="7b042-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="7b042-106">若要存取主題管理設定：</span><span class="sxs-lookup"><span data-stu-id="7b042-106">To access topics management settings:</span></span>

1. <span data-ttu-id="7b042-107">在 Microsoft 365 系統管理中心，按一下 [**設定**，然後按一下 [**組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="7b042-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="7b042-108">在 [ **服務** ] 索引標籤上，按一下 [ **主題經驗**]。</span><span class="sxs-lookup"><span data-stu-id="7b042-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![連線人員的知識](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="7b042-110">選取 [ **主題探索** ] 索引標籤。請參閱下列各節以取得每個設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7b042-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![知識網路-設定](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="7b042-112">選取 SharePoint 主題來源</span><span class="sxs-lookup"><span data-stu-id="7b042-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="7b042-113">您可以變更組織中將會編目主題的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7b042-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="7b042-114">如果您想要包含或排除特定的網站清單，您可以使用下列 .csv 範本：</span><span class="sxs-lookup"><span data-stu-id="7b042-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="7b042-115">如果您使用網站選擇器新增網站，這些網站會新增到要包含或排除的現有網站清單中。</span><span class="sxs-lookup"><span data-stu-id="7b042-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="7b042-116">如果您上傳 .csv 檔案，它會覆寫任何現有的清單。</span><span class="sxs-lookup"><span data-stu-id="7b042-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="7b042-117">如果您先前已包含或排除特定網站，您可以將清單下載成 .csv 檔，進行變更，並上傳新的清單。</span><span class="sxs-lookup"><span data-stu-id="7b042-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="7b042-118">選擇網站以供主題探索</span><span class="sxs-lookup"><span data-stu-id="7b042-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="7b042-119">在 **[主題探索]** 索引標籤的 **[選取 SharePoint 主題來源]** 底下，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="7b042-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="7b042-120">在 [**選取 SharePoint 主題來源**] 頁面上，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7b042-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="7b042-121">這包括：</span><span class="sxs-lookup"><span data-stu-id="7b042-121">This includes:</span></span>
    - <span data-ttu-id="7b042-122">**所有網站**：您租使用者中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7b042-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="7b042-123">這會捕獲目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="7b042-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="7b042-124">**全部，除了選取的網站以外**：請輸入您要排除的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="7b042-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="7b042-125">您也可以從探索中上傳想要選擇從探索中移除的網站清單。</span><span class="sxs-lookup"><span data-stu-id="7b042-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="7b042-126">未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="7b042-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="7b042-127">**僅限選取的網站**：輸入您要包含的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="7b042-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="7b042-128">您也可以上傳網站清單。</span><span class="sxs-lookup"><span data-stu-id="7b042-128">You can also upload a list of sites.</span></span> <span data-ttu-id="7b042-129">未來建立的網站將不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="7b042-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="7b042-130">**無網站**：主題不會自動產生或更新 SharePoint 內容。</span><span class="sxs-lookup"><span data-stu-id="7b042-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="7b042-131">現有的主題會保留在主題中心。</span><span class="sxs-lookup"><span data-stu-id="7b042-131">Existing topics remain in the topic center.</span></span>

    ![SharePoint 主題來源使用者介面的螢幕擷取畫面](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="7b042-133">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7b042-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="7b042-134">根據名稱排除主題</span><span class="sxs-lookup"><span data-stu-id="7b042-134">Exclude topics by name</span></span>

<span data-ttu-id="7b042-135">您可以使用 .csv 檔案上傳清單，從探索中排除主題。</span><span class="sxs-lookup"><span data-stu-id="7b042-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="7b042-136">如果您先前已排除主題，您可以下載 .csv、進行變更，然後再次上傳。</span><span class="sxs-lookup"><span data-stu-id="7b042-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="7b042-137">在 **[主題探索]** 索引標籤的 **[排除主題]** 底下，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="7b042-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="7b042-138">按一下 [ **依名稱排除主題**]。</span><span class="sxs-lookup"><span data-stu-id="7b042-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="7b042-139">如果您需要建立清單，請下載 .csv 範本並新增您要排除的主題 (請參閱使用 *.csv 範本* 下方) 。</span><span class="sxs-lookup"><span data-stu-id="7b042-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="7b042-140">當檔案準備好時，請按一下 **[流覽]** 並上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="7b042-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="7b042-141">如果有現有的清單，您可以下載包含清單的 .csv。</span><span class="sxs-lookup"><span data-stu-id="7b042-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="7b042-142">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7b042-142">Click **Save**.</span></span>

    ![排除主題使用者介面的螢幕擷取畫面](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="7b042-144">使用 .csv 範本</span><span class="sxs-lookup"><span data-stu-id="7b042-144">Working with the .csv template</span></span>

<span data-ttu-id="7b042-145">您可以複製下列 csv 範本：</span><span class="sxs-lookup"><span data-stu-id="7b042-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="7b042-146">在 CSV 範本中，輸入下列您想要排除之主題的資訊：</span><span class="sxs-lookup"><span data-stu-id="7b042-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="7b042-147">**名稱**：輸入要排除之主題的名稱。</span><span class="sxs-lookup"><span data-stu-id="7b042-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="7b042-148">執行這項作業的方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="7b042-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="7b042-149">完全相符：您可以排除確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="7b042-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="7b042-150">部分相符：您可以排除包含特定單字的所有主題。</span><span class="sxs-lookup"><span data-stu-id="7b042-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="7b042-151">例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。</span><span class="sxs-lookup"><span data-stu-id="7b042-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="7b042-152">**代表 (選用)**：若要排除縮寫，請輸入縮寫所代表的字。</span><span class="sxs-lookup"><span data-stu-id="7b042-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="7b042-153">**MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</span><span class="sxs-lookup"><span data-stu-id="7b042-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="7b042-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b042-155">See also</span></span>

[<span data-ttu-id="7b042-156">在 Microsoft 365 中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="7b042-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="7b042-157">管理 Microsoft 365 中的主題許可權</span><span class="sxs-lookup"><span data-stu-id="7b042-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="7b042-158">在 Microsoft 365 中變更主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="7b042-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
