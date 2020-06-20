---
title: 在安全性 & 規範中心內，使用 DSR 案例工具管理 GDPR 資料主體要求
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: 瞭解如何使用 DSR 案例工具來管理歐盟一般資料保護規定（GDPR）資料主體要求。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79d4ff2fb7a83f5c094b4d4f74e68918c2bd5fff
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815450"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-security--compliance-center"></a><span data-ttu-id="90a30-103">使用 Security & 合規性中心的 DSR 案例工具管理 GDPR 資料主體要求</span><span class="sxs-lookup"><span data-stu-id="90a30-103">Manage GDPR data subject requests with the DSR case tool in the Security & Compliance Center</span></span>

<span data-ttu-id="90a30-104">歐盟一般資料保護規定（GDPR）是在歐盟（EU）內部保護和啟用個人的隱私權權利。</span><span class="sxs-lookup"><span data-stu-id="90a30-104">The EU General Data Protection Regulation (GDPR) is about protecting and enabling individuals' privacy rights inside the European Union (EU).</span></span> <span data-ttu-id="90a30-105">GDPR 可讓歐盟（稱為資料主題）中的個別人員存取、檢索、更正、清除和限制處理其個人資料的許可權。</span><span class="sxs-lookup"><span data-stu-id="90a30-105">The GDPR gives individuals in the European Union (known as data subjects) the right to access, retrieve, correct, erase, and restrict processing of their personal data.</span></span> <span data-ttu-id="90a30-106">在 [GDPR] 下，「個人資料」是指與辨識或辨識的自然人員相關的任何資訊。</span><span class="sxs-lookup"><span data-stu-id="90a30-106">Under the GDPR, personal data means any information relating to an identified or identifiable natural person.</span></span> <span data-ttu-id="90a30-107">由某人對其組織執行其個人資料之動作的正式要求稱為「資料主體要求」或「DSR」。</span><span class="sxs-lookup"><span data-stu-id="90a30-107">A formal request by a person to their organization to take an action on their personal data is called a Data Subject Request or DSR.</span></span> <span data-ttu-id="90a30-108">如需針對 Office 365 中的資料回應 Dsr 的詳細資訊，請參閱[office 365 資料主體要求指南](https://go.microsoft.com/fwlink/?linkid=871169 )。</span><span class="sxs-lookup"><span data-stu-id="90a30-108">For detailed information about responding to DSRs for data in Office 365, see [Office 365 Data Subject Request Guide](https://go.microsoft.com/fwlink/?linkid=871169 ).</span></span>
  
<span data-ttu-id="90a30-109">若要管理調查以回應組織中的人員送出的 DSR，您可以使用《安全性 & 合規性中心的 DSR 案例工具，尋找儲存在中的內容：</span><span class="sxs-lookup"><span data-stu-id="90a30-109">To manage investigations in response to a DSR submitted by a person in your organization, you can use the DSR case tool in the Security & Compliance Center to find content stored in:</span></span>
  
- <span data-ttu-id="90a30-110">組織中的任何使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="90a30-110">Any user mailbox in your organization.</span></span> <span data-ttu-id="90a30-111">這包括商務用 Skype 交談和 Microsoft 小組中的一對一聊天</span><span class="sxs-lookup"><span data-stu-id="90a30-111">This includes Skype for Business conversations and one-to-one chats in Microsoft Teams</span></span>
    
- <span data-ttu-id="90a30-112">Microsoft 小組中所有與 Microsoft 365 群組和所有小組信箱相關聯的信箱</span><span class="sxs-lookup"><span data-stu-id="90a30-112">All mailboxes associated with an Microsoft 365 Group and all team mailboxes in Microsoft Teams</span></span>
    
- <span data-ttu-id="90a30-113">貴組織中所有的 Sharepoint 網站和商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="90a30-113">All SharePoint Online sites and OneDrive for Business accounts in your organization</span></span>
    
- <span data-ttu-id="90a30-114">您組織中的所有小組網站和 Microsoft 365 群組網站</span><span class="sxs-lookup"><span data-stu-id="90a30-114">All Teams sites and Microsoft 365 Group sites in your organization</span></span>
    
- <span data-ttu-id="90a30-115">Exchange Online 中的所有公用資料夾</span><span class="sxs-lookup"><span data-stu-id="90a30-115">All public folders in Exchange Online</span></span>
    
<span data-ttu-id="90a30-116">使用 DSR 案例工具，您可以：</span><span class="sxs-lookup"><span data-stu-id="90a30-116">Using the DSR case tool you can:</span></span>
  
- <span data-ttu-id="90a30-117">針對每一個 DSR 調查建立個別案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-117">Create a separate case for each DSR investigation.</span></span>
    
- <span data-ttu-id="90a30-118">將人員新增為案例成員，以控制誰可以存取 DSR 案例;只有成員可以存取案例，而且只能在 [安全性 & 規範中心] 的 [ **DSR 案例**] 頁面的案例清單中查看其案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-118">Control who has access to the DSR case by adding people as members of the case; only members can access the case and can only see their cases in the list of cases on the **DSR cases** page in the Security & Compliance Center.</span></span> <span data-ttu-id="90a30-119">此外，您也可以為相同案例的不同成員指派不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="90a30-119">Also, you can assign different permissions to different members of the same case.</span></span> <span data-ttu-id="90a30-120">例如，您可以允許某些成員只查看案例和搜尋結果，並允許其他成員建立搜尋並匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-120">For example, you can allow some members to only view the case and search results and allow other members to create searches and export search results.</span></span> 
    
- <span data-ttu-id="90a30-121">使用內建搜尋來搜尋特定資料主體所建立或上傳的所有內容。</span><span class="sxs-lookup"><span data-stu-id="90a30-121">Use the built-in search to search for all content created or uploaded by a specific data subject.</span></span>
    
- <span data-ttu-id="90a30-122">（選用）修訂內建的搜尋查詢，然後重新執行搜尋以縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-122">Optionally revise the built-in search query and rerun the search to narrow the search results.</span></span>
    
- <span data-ttu-id="90a30-123">新增與 DSR 案例相關聯的其他內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-123">Add other content searches associated with the DSR case.</span></span> <span data-ttu-id="90a30-124">這包括建立從 Office 漫遊服務傳回部分索引項目目和系統所產生記錄的搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-124">This includes creating searches that return partially indexed items and system-generated logs from the Office Roaming Service.</span></span>
    
- <span data-ttu-id="90a30-125">匯出資料以回應 DSR 存取或匯出要求。</span><span class="sxs-lookup"><span data-stu-id="90a30-125">Export data in response to a DSR access or export request.</span></span>
    
- <span data-ttu-id="90a30-126">DSR 調查程序完成時，請刪除案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-126">Delete cases when the DSR investigation process is complete.</span></span> <span data-ttu-id="90a30-127">這會移除與案例相關聯的所有搜尋和匯出工作。</span><span class="sxs-lookup"><span data-stu-id="90a30-127">This removes all searches and export jobs associated with the case.</span></span>
    
<span data-ttu-id="90a30-128">以下是使用 DSR 案例工具來管理 DSR 調查的高層級流程：</span><span class="sxs-lookup"><span data-stu-id="90a30-128">Here's the high-level process for using the DSR case tool to manage DSR investigations:</span></span>
  
[<span data-ttu-id="90a30-129">步驟1：將 eDiscovery 許可權指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="90a30-129">Step 1: Assign eDiscovery permissions to potential case members</span></span>](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[<span data-ttu-id="90a30-130">步驟2：建立 DSR 案例並新增成員</span><span class="sxs-lookup"><span data-stu-id="90a30-130">Step 2: Create a DSR case and add members</span></span>](#step-2-create-a-dsr-case-and-add-members)

[<span data-ttu-id="90a30-131">步驟3：執行搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="90a30-131">Step 3: Run the search query</span></span>](#step-3-run-the-search-query)

[<span data-ttu-id="90a30-132">步驟4：匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-132">Step 4: Export the data</span></span>](#step-4-export-the-data)

[<span data-ttu-id="90a30-133">選步驟5：修改內建的搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="90a30-133">(Optional) Step 5: Revise the built-in search query</span></span>](#optional-step-5-revise-the-built-in-search-query)

[<span data-ttu-id="90a30-134">使用 DSR case 工具的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="90a30-134">More information about using the DSR case tool</span></span>](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> <span data-ttu-id="90a30-135">我們的工具可協助管理員執行 DSR 存取或匯出要求，其方式是讓使用者使用 DSR 案例工具中的內建搜尋和匯出功能。</span><span class="sxs-lookup"><span data-stu-id="90a30-135">Our tools can help admins perform DSR access or export requests by enabling them to utilize the built-in search and export functionality found in the DSR case tool.</span></span> <span data-ttu-id="90a30-136">此工具可協助您協助最佳的方式，匯出與資料主體所送出的 DSR 要求相關的資料。</span><span class="sxs-lookup"><span data-stu-id="90a30-136">The tool helps to facilitate a best-effort method to export data that's relevant to a DSR request submitted by a data subject.</span></span> <span data-ttu-id="90a30-137">不過，請務必注意，搜尋結果會因所採取的資料主體或系統管理動作而異，這可能會影響專案是否視為「個人資料」，以用於匯出目的。</span><span class="sxs-lookup"><span data-stu-id="90a30-137">However, it's important to note that search results can vary based on the data subject or the admin actions taken that may impact whether or not an item would be deemed as "personal data" for export purposes.</span></span> <span data-ttu-id="90a30-138">例如，如果資料主體是最後一個修改其未建立之檔案的使用者，則該檔案可能不會在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="90a30-138">For example, if the data subject was the last person to modify a file they didn't create, the file might not be returned in the search results.</span></span> <span data-ttu-id="90a30-139">同樣地，系統管理員可以匯出資料，但不包括部分索引的專案或 SharePoint 檔的所有版本。</span><span class="sxs-lookup"><span data-stu-id="90a30-139">Similarly, an admin could export data without including partially indexed items or all versions of SharePoint documents.</span></span> <span data-ttu-id="90a30-140">因此，提供的工具可協助協助存取及匯出資料要求;不過，結果會受制于特定的系統管理員和資料主體使用案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-140">Therefore, the tools provided can help facilitate accessing and exporting data requests; however, the results are subject to specific admin and data subject usage scenarios.</span></span> 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="90a30-141">步驟1：將 eDiscovery 許可權指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="90a30-141">Step 1: Assign eDiscovery permissions to potential case members</span></span>

<span data-ttu-id="90a30-142">根據預設，全域管理員可以存取 Security & 合規性中心的 DSR 案例工具。</span><span class="sxs-lookup"><span data-stu-id="90a30-142">By default, a global administrator can access the DSR case tool in the Security & Compliance Center.</span></span> <span data-ttu-id="90a30-143">根據設計，其他使用者（例如資料隱私權監察官、人力資源管理員或其他與 DSR 調查相關的人員）無法存取 DSR 案例工具，因此必須獲指派適當的許可權，才能存取工具。</span><span class="sxs-lookup"><span data-stu-id="90a30-143">By design, other users such as a data privacy officer, a human resources manager, or other people involved in DSR investigations don't have access to the DSR case tool and will have to be assigned the appropriate permissions to access the tool.</span></span> <span data-ttu-id="90a30-144">若要這麼做，最簡單的方法是移至 [安全性 & 規範中心] 中的 [**許可權**] 頁面，並將使用者新增至「eDiscovery 管理員」角色群組。</span><span class="sxs-lookup"><span data-stu-id="90a30-144">The easiest way to do this is to go to the **Permissions** page in the Security & Compliance Center and add users to the eDiscovery Manager role group.</span></span> <span data-ttu-id="90a30-145">您也必須指派這些許可權，以便將其新增為您在步驟2中建立的 DSR 案例成員。</span><span class="sxs-lookup"><span data-stu-id="90a30-145">You also have to assign these permissions so you can add them as members of the DSR case that you create in Step 2.</span></span> 
  
<span data-ttu-id="90a30-146">如需逐步指示，請參閱[在 Office 365 安全性 & 規範中心指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="90a30-146">For step-by-step instructions, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="90a30-147">根據預設，全域管理員（或安全性 & 合規性中心內的組織管理角色群組的其他成員不具備匯出內容搜尋結果所需的許可權（請參閱本文中的步驟4）。</span><span class="sxs-lookup"><span data-stu-id="90a30-147">By default, a global administrator (or other members of the Organization Management role group in the Security & Compliance Center don't have the necessary permissions to export Content Search results (see Step 4 in this article).</span></span> <span data-ttu-id="90a30-148">若要解決此情況，系統管理員可以將自己新增為 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90a30-148">To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a><span data-ttu-id="90a30-149">步驟2：建立 DSR 案例並新增成員</span><span class="sxs-lookup"><span data-stu-id="90a30-149">Step 2: Create a DSR case and add members</span></span>

<span data-ttu-id="90a30-150">下一步是建立 DSR 案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-150">The next step is to create a DSR case.</span></span> <span data-ttu-id="90a30-151">當您建立案例時，您可以選擇啟動內建搜尋，也可以建立大小寫，而不啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-151">When you create a case, you can choose to start the built-in search or you can create the case without starting the search.</span></span> <span data-ttu-id="90a30-152">下列程式會指示您建立 case，但不啟動搜尋，然後示範如何將成員新增至案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-152">The following procedure instructs you to create the case without starting the search and then show you how to add members to the case.</span></span>
  
1. <span data-ttu-id="90a30-153">移至 [https://protection.office.com](https://protection.office.com) 並使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="90a30-153">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="90a30-154">在 [安全性 & 規範中心] 中，按一下 [**資料隱私權** \> **資料主體要求**]，然後按一下 [ ![ 新增圖示] [ ](../media/ITPro-EAC-AddIcon.gif) **新增 DSR 案例**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-154">In the Security & Compliance Center, click **Data privacy** \> **Data subject requests**, and then click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) **New DSR case**.</span></span>
    
3. <span data-ttu-id="90a30-155">在 [**新的 DSR 案例**飛入] 頁面上，為案例輸入名稱，輸入選用的描述，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90a30-155">On the **New DSR case** flyout page, give the case a name, type an optional description, and then click **Next**.</span></span> <span data-ttu-id="90a30-156">案例名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="90a30-156">The name of the case must be unique in your organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="90a30-157">考慮在新案例的名稱和/或描述中，新增您要調查之 DSR 要求的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="90a30-157">Consider adding the name of the person who submitted the DSR request that you're investigating in the name and/or description of the new case.</span></span> <span data-ttu-id="90a30-158">請注意，只有此案例（和 eDiscovery 系統管理員）的成員可以在 [**資料主體要求**] 頁面的案例清單中查看案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-158">Note that only members of this case (and eDiscovery Administrators) will be able to see the case in the list of cases on the **Data subject requests** page.</span></span> 
  
4. <span data-ttu-id="90a30-159">在 [**要求詳細**資料] 頁面的 [**資料主體] （「提交此要求的人員）**] 下，選取您要尋找及匯出資料的人員，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90a30-159">On the **Request details** page, under **Data subject (the person who filed this request)**, select the person that you want to find and export data for and then click **Next**.</span></span>
    
5. <span data-ttu-id="90a30-160">在 [**確認您的案例設定**] 頁面上，您可以變更案例名稱和描述，然後選取不同的資料主體。</span><span class="sxs-lookup"><span data-stu-id="90a30-160">On the **Confirm your case settings** page, you can change the case name and description, and select a different data subject.</span></span> <span data-ttu-id="90a30-161">否則，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-161">Otherwise, click **Save**.</span></span>
    
    <span data-ttu-id="90a30-162">隨即會顯示一個頁面，確認已建立新的 DSR 案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-162">A page is displayed that confirms the new DSR case has been created.</span></span>
    
    ![啟動搜尋或關閉新的 DSR 案例頁面](../media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    <span data-ttu-id="90a30-164">此時，您可以執行下列兩項動作之一：</span><span class="sxs-lookup"><span data-stu-id="90a30-164">At this point, you can do one of two things:</span></span>
    
    <span data-ttu-id="90a30-165">a.</span><span class="sxs-lookup"><span data-stu-id="90a30-165">a.</span></span> <span data-ttu-id="90a30-166">按一下 [**顯示我的搜尋結果**] 即會啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-166">Clicking **Show me search results** starts the search.</span></span> <span data-ttu-id="90a30-167">這是預設的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="90a30-167">This is the default selection.</span></span> <span data-ttu-id="90a30-168">當您選取此選項時，會執行的內建搜尋，而且會在步驟3中討論傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-168">The built-in search that's run when you select this option and the results that are returned are discussed in Step 3.</span></span>
    
    <span data-ttu-id="90a30-169">b.</span><span class="sxs-lookup"><span data-stu-id="90a30-169">b.</span></span> <span data-ttu-id="90a30-170">按一下 **[完成]** 關閉新的 DSR 主機殼，但不啟動內建搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-170">Clicking **Finish** closes the new DSR case without starting the built-in search.</span></span> <span data-ttu-id="90a30-171">當您選取此選項時，新的 DSR 案例會顯示在 [**資料主體要求**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="90a30-171">When you select this option, the new DSR case is displayed on the **Data subject requests** page.</span></span>
    
6. <span data-ttu-id="90a30-172">按一下 **[完成]** ，讓您可以移至新的 DSR 案例，並新增成員至此案例。</span><span class="sxs-lookup"><span data-stu-id="90a30-172">Click **Finish** so that you can go in to the new DSR case and add members to it.</span></span> 
    
7. <span data-ttu-id="90a30-173">在 [**資料主體要求**] 頁面上，按一下您建立的 DSR 案例名稱。</span><span class="sxs-lookup"><span data-stu-id="90a30-173">On the **Data subject requests** page, click the name of the DSR case that you created.</span></span> 
    
8. <span data-ttu-id="90a30-174">在 [**管理此案例**飛入] 頁面的 [**管理成員**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-174">On the **Manage this case** flyout page, under **Manage members**, click **Add**.</span></span> 
    
    <span data-ttu-id="90a30-175">在 [**使用者**] 底下，會顯示指派適當 eDiscovery 許可權的人員清單。</span><span class="sxs-lookup"><span data-stu-id="90a30-175">Under **Users**, a list of people that are assigned the appropriate eDiscovery permissions is displayed.</span></span> <span data-ttu-id="90a30-176">您在步驟1中為您指派 eDiscovery 許可權的人員會顯示在此清單中。</span><span class="sxs-lookup"><span data-stu-id="90a30-176">The people you assigned eDiscovery permissions to in Step 1 will be displayed in this list.</span></span> 
    
9. <span data-ttu-id="90a30-177">選取要新增為 DSR 案例成員的人員，按一下 [**新增**]，然後儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="90a30-177">Select the people to add as members of the DSR case, click **Add**, and then save your changes.</span></span>
    
    <span data-ttu-id="90a30-178">您也可以按一下 [**管理角色群組**] 下的 [**新增**]，將角色群組新增為 DSR 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="90a30-178">You can also add role groups as members of DSR case by clicking **Add** under **Manage role groups**.</span></span> 
    
## <a name="step-3-run-the-search-query"></a><span data-ttu-id="90a30-179">步驟3：執行搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="90a30-179">Step 3: Run the search query</span></span>

<span data-ttu-id="90a30-180">在您建立 DSR 案例並新增成員之後，下一步是執行與案例相關聯的內建搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-180">After you create a DSR case and add members, the next step is to run the built-in search that's associated with the case.</span></span> <span data-ttu-id="90a30-181">此預設搜尋查詢會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="90a30-181">This default search query does the following things:</span></span>
  
- <span data-ttu-id="90a30-182">搜尋組織中的所有信箱，以找出資料主體所傳送或接收的所有電子郵件專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-182">Searches all mailboxes in your organization for all email items that were sent or received by the data subject.</span></span> <span data-ttu-id="90a30-183">若要完成此工作，您可以使用*參與者*的 email 屬性，在電子郵件中搜尋所有人員欄位中的資料主體。</span><span class="sxs-lookup"><span data-stu-id="90a30-183">This is accomplished by using the  *Participants*  email property, which searches for the data subject in all the people fields in an email message.</span></span> <span data-ttu-id="90a30-184">此屬性會傳回在 [**寄件者**]、[**收件者** **]、[** 副本] 及 [**密件副本**] 欄位中的資料主體。</span><span class="sxs-lookup"><span data-stu-id="90a30-184">This property returns items in which the data subject is in the **From**, **To**, **CC**, and **BCC** fields.</span></span> <span data-ttu-id="90a30-185">Exchange Online 中的公用資料夾也會搜尋資料主體所傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="90a30-185">Public folders in Exchange Online are also searched for messages sent or received by the data subject.</span></span> 
    
- <span data-ttu-id="90a30-186">搜尋組織中的所有網站，以查看資料主體建立或上傳的檔及專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-186">Searches all sites in your organization for documents and items created or uploaded by the data subject.</span></span> <span data-ttu-id="90a30-187">這是透過使用下列網站屬性來完成：</span><span class="sxs-lookup"><span data-stu-id="90a30-187">This is accomplished by using the following site properties:</span></span>
    
  - <span data-ttu-id="90a30-188">*Author*屬性會傳回資料主題列于 Office 檔的 Author 欄位中的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-188">The  *Author*  property returns items where the data subject is listed in the author field in Office documents.</span></span> <span data-ttu-id="90a30-189">此值會持續存在，即使其他人複製並上傳檔也是一樣。</span><span class="sxs-lookup"><span data-stu-id="90a30-189">This value persists, even if the document is copied and uploaded by someone else.</span></span> 
    
  - <span data-ttu-id="90a30-190">*CreatedBy*屬性會傳回資料主體建立或上傳的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-190">The  *CreatedBy*  property returns items that were created or uploaded by the data subject.</span></span> 
    
<span data-ttu-id="90a30-191">以下是在您建立 DSR 案例時，自動建立的內建搜尋關鍵字查詢的功能。</span><span class="sxs-lookup"><span data-stu-id="90a30-191">Here's what the keyword query looks like for the built-in search that gets automatically created when you create a DSR case.</span></span>
  
```powershell
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

<span data-ttu-id="90a30-192">例如，如果資料主體的名稱是為 Leonte，關鍵字查詢會如下所示：</span><span class="sxs-lookup"><span data-stu-id="90a30-192">For example, if the name of the data subject is Ina Leonte, the keyword query would look like this:</span></span>
  
```powershell
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 <span data-ttu-id="90a30-193">**若要執行 DSR 主機殼內建的搜尋：**</span><span class="sxs-lookup"><span data-stu-id="90a30-193">**To run the built-in search for a DSR case:**</span></span>
  
1. <span data-ttu-id="90a30-194">在 [安全性 & 規範中心] 中，按一下 [**資料隱私權** \> **資料主體要求**]，然後按一下您在步驟2中建立的 DSR 案例旁邊的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-194">In the Security & Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you created in Step 2.</span></span> 
    
    <span data-ttu-id="90a30-195">按一下頁面頂端的 [**搜尋] 索引**標籤，然後按一下您建立 DSR 案例時所建立的內建搜尋旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90a30-195">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the DSR case.</span></span> <span data-ttu-id="90a30-196">搜尋與 DSR 案例同名。</span><span class="sxs-lookup"><span data-stu-id="90a30-196">The search has the same name as the DSR case.</span></span> 
    
2. <span data-ttu-id="90a30-197">在 [搜尋飛出] 頁面上，按一下 [**開啟查詢**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-197">In the search flyout page, click **Open query**.</span></span>
    
    <span data-ttu-id="90a30-198">當您開啟查詢時，搜尋會開始，並會在幾分鐘後完成。</span><span class="sxs-lookup"><span data-stu-id="90a30-198">When you open the query, the search is started and will complete in a few moments.</span></span> 
    
3. <span data-ttu-id="90a30-199">當搜尋完成時，按一下 [**預覽結果**] 以預覽搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-199">When the search is complete, click **Preview results** to preview the search results.</span></span> <span data-ttu-id="90a30-200">如需詳細資訊，請參閱[預覽搜尋結果](content-search.md#preview-search-results)。</span><span class="sxs-lookup"><span data-stu-id="90a30-200">For more information, see [Preview search results](content-search.md#preview-search-results).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="90a30-201">您也可以查看搜尋查詢統計資料，以查看搜尋所傳回的信箱和網站專案數目，以及包含符合搜尋查詢之專案的頂端內容位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-201">You can also view the search query statistics to see the number of mailbox and site items that are returned by the search, and the top content locations that contain items that match the search query.</span></span> <span data-ttu-id="90a30-202">如需詳細資訊，請參閱[查看有關搜尋的資訊和統計資料](content-search.md#view-information-and-statistics-about-a-search)。</span><span class="sxs-lookup"><span data-stu-id="90a30-202">For more information, see [View information and statistics about a search](content-search.md#view-information-and-statistics-about-a-search).</span></span> 
  
<span data-ttu-id="90a30-203">您可以編輯內建的搜尋查詢、變更所搜尋的內容位置，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-203">You can edit the built-in search query, change the content locations that are searched, and then rerun the search.</span></span> <span data-ttu-id="90a30-204">如需詳細資訊，請參閱[步驟 5](#optional-step-5-revise-the-built-in-search-query) 。</span><span class="sxs-lookup"><span data-stu-id="90a30-204">See [Step 5](#optional-step-5-revise-the-built-in-search-query) for more information.</span></span> 
  
## <a name="step-4-export-the-data"></a><span data-ttu-id="90a30-205">步驟4：匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-205">Step 4: Export the data</span></span>

<span data-ttu-id="90a30-206">在您執行內建搜尋之後，您可以匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-206">After you run the built-in search, you can export the search results.</span></span> <span data-ttu-id="90a30-207">或者，在您匯出資料之前，您可能會想要修改查詢以減少搜尋結果的數目。</span><span class="sxs-lookup"><span data-stu-id="90a30-207">Alternatively, before you export the data, you may want to revise the query to reduce the number of search results.</span></span> <span data-ttu-id="90a30-208">如需縮小搜尋結果的詳細資訊，請參閱步驟5。</span><span class="sxs-lookup"><span data-stu-id="90a30-208">See Step 5 for more information about narrowing the search results.</span></span>
  
<span data-ttu-id="90a30-209">當您匯出搜尋結果時，信箱專案可以下載 PST 檔案或個別郵件。</span><span class="sxs-lookup"><span data-stu-id="90a30-209">When you export search results, mailbox items can be downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="90a30-210">當您從 SharePoint 和 OneDrive 帳戶匯出內容時，會匯出原生 Office 檔和其他檔的副本。</span><span class="sxs-lookup"><span data-stu-id="90a30-210">When you export content from SharePoint and OneDrive accounts, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="90a30-211">包含每個匯出專案相關資訊的結果檔會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="90a30-211">A results file that contains information about every exported item is included with the search results.</span></span> <span data-ttu-id="90a30-212">如需匯出的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="90a30-212">For more detailed information about exporting, see [Export Content Search results](export-search-results.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="90a30-213">根據預設，全域管理員（或安全性 & 合規性中心內的組織管理角色群組的其他成員）不具備匯出內容搜尋結果的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="90a30-213">By default, a global administrator (or other members of the Organization Management role group in the Security & Compliance Center) don't have the necessary permissions to export Content Search results.</span></span> <span data-ttu-id="90a30-214">若要解決此情況，系統管理員可以將自己新增為 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90a30-214">To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
<span data-ttu-id="90a30-215">您用來匯出資料的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="90a30-215">The computer you use to export data has to meet the following system requirements:</span></span>
  
- <span data-ttu-id="90a30-216">32位或64位版本的 Windows 7 和更新版本</span><span class="sxs-lookup"><span data-stu-id="90a30-216">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
- <span data-ttu-id="90a30-217">Microsoft .NET Framework 4。7</span><span class="sxs-lookup"><span data-stu-id="90a30-217">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="90a30-218">支援的瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="90a30-218">A supported browser:</span></span>
    
  - <span data-ttu-id="90a30-219">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="90a30-219">Microsoft Edge</span></span>
    
    <span data-ttu-id="90a30-220">或者</span><span class="sxs-lookup"><span data-stu-id="90a30-220">Or</span></span>
    
  - <span data-ttu-id="90a30-221">Microsoft Internet Explorer 10 和更新版本</span><span class="sxs-lookup"><span data-stu-id="90a30-221">Microsoft Internet Explorer 10 and later versions</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90a30-222">Microsoft 不會製造協力廠商擴充模組或 ClickOnce 應用程式的附加元件。</span><span class="sxs-lookup"><span data-stu-id="90a30-222">Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="90a30-223">不支援使用不受支援的瀏覽器匯出資料和協力廠商分機或附加元件。</span><span class="sxs-lookup"><span data-stu-id="90a30-223">Exporting data using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
  
 <span data-ttu-id="90a30-224">**若要在 DSR 案例中從內建搜尋匯出資料：**</span><span class="sxs-lookup"><span data-stu-id="90a30-224">**To export data from the built-in search in a DSR case:**</span></span>
  
1. <span data-ttu-id="90a30-225">在 [安全性 & 規範中心] 中，按一下 [**資料隱私權** \> **資料主體要求**]，然後按一下您想要從中匯出資料的 DSR 案例旁邊的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-225">In the Security & Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you want to export data from.</span></span> 
    
2. <span data-ttu-id="90a30-226">按一下頁面頂端的 [**搜尋] 索引**標籤，然後按一下您建立 DSR 案例時所建立的內建搜尋旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90a30-226">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the DSR case.</span></span> <span data-ttu-id="90a30-227">或是按一下其他搜尋，從該搜尋中匯出資料。</span><span class="sxs-lookup"><span data-stu-id="90a30-227">Or click another search to export data from that search.</span></span> 
    
3. <span data-ttu-id="90a30-228">在 [搜尋飛出] 頁面上，按一下 [ ![ 更多匯出搜尋結果圖示] ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\* **，然後從下拉式清單中選取 [**匯出結果\*\*]。</span><span class="sxs-lookup"><span data-stu-id="90a30-228">On the search flyout page, click ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="90a30-229">在 [**匯出結果**] 頁面上，選取下列 DSR 匯出要求的建議選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-229">On the **Export results** page, select the following recommended options for DSR export requests.</span></span> 
    
    ![設定匯出設定](../media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    <span data-ttu-id="90a30-231">a.</span><span class="sxs-lookup"><span data-stu-id="90a30-231">a.</span></span> <span data-ttu-id="90a30-232">在 [輸出選項] 的 [**輸出選項**] 底下，選取第一個選項（**包括具有無法辨識格式之專案的所有專案，也就是已加密的專案，或是尚未為其他原因編制索引**），只匯出索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-232">Under **Output options**, select the first option (**All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only.</span></span> <span data-ttu-id="90a30-233">您不想從內建搜尋中匯出部分索引項目目的原因，是因為也會匯出其他使用者的部分已編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-233">The reason you don't want to export partially indexed items from the built-in search is because partially indexed items from other users will also be exported.</span></span> <span data-ttu-id="90a30-234">若只要匯出資料主體的部分索引項目目，我們建議您建立個別的搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-234">To export only the partially indexed items for the data subject, we recommend that you create a separate search.</span></span> <span data-ttu-id="90a30-235">如需詳細資訊，請參閱《使用 DSR 案例工具的詳細資訊》一節中的[匯出部分索引的專案](#exporting-partially-indexed-items)。</span><span class="sxs-lookup"><span data-stu-id="90a30-235">For more information, see [Exporting partially indexed items](#exporting-partially-indexed-items) in the "More information about using the DSR case tool" section.</span></span>
    
    <span data-ttu-id="90a30-236">b.</span><span class="sxs-lookup"><span data-stu-id="90a30-236">b.</span></span> <span data-ttu-id="90a30-237">在 [將**Exchange 內容匯出為**] 底下，選取第三個選項（**一個 PST 檔案包含單一資料夾中的所有郵件**）。</span><span class="sxs-lookup"><span data-stu-id="90a30-237">Under **Export Exchange content as**, select the third option, **One PST file containing all messages in a single folder**.</span></span> <span data-ttu-id="90a30-238">因為部分結果可能是針對來自其他使用者信箱的專案，所以此選項只會列出單一資料夾中的專案，而不會指出實際的信箱，而且在您將結果重新複製為下一個專案時，是使用的最佳選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-238">Because some of the results may be for items that originated in another user's mailbox, this option just lists the item in a single folder without indicating the actual mailbox and is the best option to use when you de-duplicate the results as recommended in the next item.</span></span> <span data-ttu-id="90a30-239">此選項也可讓資料主體逐項審閱專案（專案是依照傳送日期排序），而不需流覽每個專案的原始信箱資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="90a30-239">This option also lets the data subject review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span>
    
    <span data-ttu-id="90a30-240">c.</span><span class="sxs-lookup"><span data-stu-id="90a30-240">c.</span></span> <span data-ttu-id="90a30-241">選取 [**啟用重復資料**刪除] 選項，以排除重複的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="90a30-241">Select **Enable de-duplication** option to excludes duplicate email messages.</span></span> <span data-ttu-id="90a30-242">由於內建搜尋會搜尋組織中的所有信箱，因此建議您選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-242">We recommend this option because the built-in search searches all mailboxes in your organization.</span></span> <span data-ttu-id="90a30-243">因此，如果在搜尋的信箱中找到相同郵件的多個副本，此選項表示只會匯出郵件的一個副本。</span><span class="sxs-lookup"><span data-stu-id="90a30-243">So if multiple copies of the same message are found in the mailboxes that were searched, this option means that only one copy of a message will be exported.</span></span> <span data-ttu-id="90a30-244">此選項一起將郵件以單一資料夾的一個 PST 檔案匯出，以取得 DSR 匯出要求的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="90a30-244">This option, together will exporting messages in one PST file in a single folder, results in the best user experience for DSR export requests.</span></span> <span data-ttu-id="90a30-245">Results.csv 匯出報告會列出找到重複郵件的所有位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-245">The Results.csv export report lists all locations where duplicate messages were found.</span></span>
    
    <span data-ttu-id="90a30-246">您也可以選取 [**包括 SharePoint 檔的版本**] 選項，以匯出 SharePoint 和 OneDrive 檔的所有版本。</span><span class="sxs-lookup"><span data-stu-id="90a30-246">Optionally, you can select **Include versions for SharePoint documents** option to export all versions of SharePoint and OneDrive documents.</span></span> <span data-ttu-id="90a30-247">這需要啟用文件庫的版本設定。</span><span class="sxs-lookup"><span data-stu-id="90a30-247">This requires that versioning is turned on for document libraries.</span></span> <span data-ttu-id="90a30-248">這個選項可協助確定所有相關資料都已匯出。</span><span class="sxs-lookup"><span data-stu-id="90a30-248">This option helps to ensure that all relevant data is exported.</span></span>
    
5. <span data-ttu-id="90a30-249">選擇匯出設定後，按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-249">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="90a30-250">搜尋結果已準備好下載，也就是將其上傳至 Microsoft 雲端中組織的 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="90a30-250">The search results are prepared for downloading, which means they're uploaded to the Azure Storage area for your organization in the Microsoft cloud.</span></span> <span data-ttu-id="90a30-251">接下來的步驟將示範如何將此資料下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="90a30-251">The next steps show you how to download this data to your local computer.</span></span>
    
6. <span data-ttu-id="90a30-252">按一下 [**匯出**] 索引標籤，顯示您建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="90a30-252">Click the **Export** tab to display the export job you created.</span></span> <span data-ttu-id="90a30-253">匯出工作與對應的搜尋同名，但 **_Export**附加于搜尋名稱的結尾。</span><span class="sxs-lookup"><span data-stu-id="90a30-253">Export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
7. <span data-ttu-id="90a30-254">按一下您剛才建立的匯出工作以顯示 [匯出飛出] 頁面。</span><span class="sxs-lookup"><span data-stu-id="90a30-254">Click the export job that you just created to display the export flyout page.</span></span> <span data-ttu-id="90a30-255">此頁面會顯示搜尋的相關資訊，例如要匯出的專案大小和總數，以及已轉接至 Azure 儲存體區域的專案百分比。</span><span class="sxs-lookup"><span data-stu-id="90a30-255">This page shows information about the search, such as the size and total number of items to be exported, and the percentage of the items that have been transferred to an Azure storage area.</span></span> <span data-ttu-id="90a30-256">按一下 **[** 重新整理] 以更新上傳狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="90a30-256">Click **Refresh** to update the upload status information.</span></span> 
    
8. <span data-ttu-id="90a30-257">在 [**匯出金鑰**] 底下，按一下 [**複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="90a30-257">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="90a30-258">您可以在步驟11中使用此機碼下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-258">You use this key in step 11 to download the search results.</span></span>
    
9. <span data-ttu-id="90a30-259">按一下 ![ [匯出飛出] 頁面頂端的 [匯出搜尋結果圖示 ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **下載結果**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-259">Click ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
10. <span data-ttu-id="90a30-260">在頁面底部的快顯視窗中，按一下 [**開啟**] 以開啟 [ **eDiscovery 匯出工具**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-260">In the pop-up window at the bottom of the page, click **Open** to open the **eDiscovery Export Tool**.</span></span> <span data-ttu-id="90a30-261">第一次下載搜尋結果時會安裝**EDiscovery 匯出工具**。</span><span class="sxs-lookup"><span data-stu-id="90a30-261">The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
11. <span data-ttu-id="90a30-262">在 [ **EDiscovery 匯出工具**] 中，在適當的方塊中貼上您在步驟8中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="90a30-262">In the **eDiscovery Export Tool**, paste the export key that you copied in step 8 in the appropriate box.</span></span>
    
12. <span data-ttu-id="90a30-263">按一下 [瀏覽]\*\*\*\* 以指定搜尋結果檔案要下載到的位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-263">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="90a30-264">由於大量的磁片活動（讀取和寫入），您應該將搜尋結果下載到本機磁片磁碟機;不要將其下載到對應的網路磁碟機或其他網路位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-264">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
13. <span data-ttu-id="90a30-265">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="90a30-265">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="90a30-266">**EDiscovery 匯出工具**會顯示匯出程式的狀態資訊，包括要下載之其餘專案的數位（和大小）的預估。</span><span class="sxs-lookup"><span data-stu-id="90a30-266">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="90a30-267">匯出程式完成後，您可以在下載檔案的位置存取檔案。</span><span class="sxs-lookup"><span data-stu-id="90a30-267">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> <span data-ttu-id="90a30-268">如需下載內容搜尋結果時所包含報告的詳細資訊，請參閱「匯出內容搜尋結果」中的[詳細資訊](export-search-results.md#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="90a30-268">For more information about the reports that included when you download Content Search results, see the [More information](export-search-results.md#more-information) section in "Export Content Search results".</span></span> 
    
<span data-ttu-id="90a30-269">匯出資料後，搜尋結果和匯出報告都位於與 DSR 案例同名的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="90a30-269">After the data is exported, the search results and export reports are located in a folder that has the same name as the DSR case.</span></span> <span data-ttu-id="90a30-270">包含信箱專案的 PST 檔案位於名為**Exchange**的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="90a30-270">The PST files that contain mailbox items are located in a subfolder named **Exchange**.</span></span> <span data-ttu-id="90a30-271">網站中的檔和其他專案位於名為**SharePoint**的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="90a30-271">Documents and other items from sites are located in a subfolder named **SharePoint**.</span></span> 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a><span data-ttu-id="90a30-272">選步驟5：修改內建的搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="90a30-272">(Optional) Step 5: Revise the built-in search query</span></span>

<span data-ttu-id="90a30-273">在您執行內建搜尋之後，您可以修改它，以縮小範圍以傳回較少的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-273">After you run the built-in search, you can revise it to narrow the scope to return fewer search results.</span></span> <span data-ttu-id="90a30-274">若要這麼做，您可以將條件新增至查詢。</span><span class="sxs-lookup"><span data-stu-id="90a30-274">You can do this by adding conditions to the query.</span></span> <span data-ttu-id="90a30-275">**And**運算子會以邏輯方式連線至關鍵字查詢的條件。</span><span class="sxs-lookup"><span data-stu-id="90a30-275">A condition is logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="90a30-276">這表示要在搜尋結果中傳回，專案必須同時滿足關鍵字查詢和您新增的任何條件。</span><span class="sxs-lookup"><span data-stu-id="90a30-276">That means to be returned in the search results, items must satisfy both the keyword query and any conditions you add.</span></span> <span data-ttu-id="90a30-277">這就是條件如何協助縮小結果的方式。</span><span class="sxs-lookup"><span data-stu-id="90a30-277">This is how conditions help to narrow the results.</span></span> <span data-ttu-id="90a30-278">如果您將兩個或多個唯一條件新增至搜尋查詢（指定不同屬性的條件），這些條件會以**AND**運算子在邏輯上連接。</span><span class="sxs-lookup"><span data-stu-id="90a30-278">If you add two or more unique conditions to a search query (conditions that specify different properties), those conditions are logically connected by the **AND** operator.</span></span> <span data-ttu-id="90a30-279">這表示只會傳回符合所有條件的專案（除關鍵字查詢之外）。</span><span class="sxs-lookup"><span data-stu-id="90a30-279">That means only items that satisfy all the conditions (in addition to the keyword query) are returned.</span></span> <span data-ttu-id="90a30-280">如果您將多個值（以逗號或分號分隔）新增至單一條件，則這些值是由**or**運算子所連接。</span><span class="sxs-lookup"><span data-stu-id="90a30-280">If you add multiple values (separated by commas or semi-colons) to a single condition, those values are connected by the **OR** operator.</span></span> <span data-ttu-id="90a30-281">這表示如果專案包含條件中屬性的任何指定值，則會傳回專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-281">That means items are returned if they contain any of the specified values for the property in the condition.</span></span> 
  
<span data-ttu-id="90a30-282">以下是一些您可以新增至 DSR 案例內建搜尋查詢的條件範例。</span><span class="sxs-lookup"><span data-stu-id="90a30-282">Here are some examples of the conditions that you can add to the built-in search query of a DSR case.</span></span> <span data-ttu-id="90a30-283">搜尋查詢中所用的實際屬性名稱會顯示在括弧中。</span><span class="sxs-lookup"><span data-stu-id="90a30-283">The name of the actual property used in a search query is shown parentheses.</span></span>
  
- <span data-ttu-id="90a30-284">**檔案類型（ `filetype` ）** –指定檔或檔案的副檔名。</span><span class="sxs-lookup"><span data-stu-id="90a30-284">**File type ( `filetype`)** – Specifies the extension of a document or file.</span></span> <span data-ttu-id="90a30-285">使用此條件可搜尋特定 Office 應用程式（例如 Word、Excel 及 OneNote）所建立的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="90a30-285">Use this condition to search for documents and files created by specific Office applications, such as Word, Excel, and OneNote.</span></span> 
    
- <span data-ttu-id="90a30-286">**郵件類型（ `kind` ）** –指定要搜尋的電子郵件專案類型。</span><span class="sxs-lookup"><span data-stu-id="90a30-286">**Message type ( `kind`)** – Specifies the type of email item to search for.</span></span> <span data-ttu-id="90a30-287">例如，您可以使用此語法， `kind:email OR kind:im` 只傳回電子郵件、商務用 Skype 交談或 Microsoft 小組中的一對一聊天。</span><span class="sxs-lookup"><span data-stu-id="90a30-287">For example, you can use the syntax  `kind:email OR kind:im` to return only email messages and Skype for Business conversations or one-to-one chats in Microsoft Teams.</span></span> 
    
- <span data-ttu-id="90a30-288">**合規性標記（ `compliancetag` ）** –指定指派給電子郵件或檔的標籤。</span><span class="sxs-lookup"><span data-stu-id="90a30-288">**Compliance tag (`compliancetag`)** – Specifies a label assigned to an email message or a document.</span></span> <span data-ttu-id="90a30-289">此條件會傳回以特定標籤分類的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-289">This condition returns items that are classified with a specific label.</span></span> <span data-ttu-id="90a30-290">標籤可用來分類電子郵件和檔，以進行資料控管，並根據標籤定義的分類強制執行保留規則。</span><span class="sxs-lookup"><span data-stu-id="90a30-290">Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label.</span></span> <span data-ttu-id="90a30-291">這是 DSR 調查的有用條件，因為您的組織可能會使用標籤來分類與資料隱私權相關的內容，或包含個人資料或機密資訊的內容。</span><span class="sxs-lookup"><span data-stu-id="90a30-291">This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information.</span></span> <span data-ttu-id="90a30-292">針對此狀況的值，請使用完整的標籤名稱或標籤名稱的第一個部分搭配萬用字元。</span><span class="sxs-lookup"><span data-stu-id="90a30-292">For the value of this condition, use the complete label name or the first part of the label name with a wildcard.</span></span> <span data-ttu-id="90a30-293">如需詳細資訊，請參閱[Office 365 中的標籤綜述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="90a30-293">For more information, see [Overview of labels in Office 365](labels.md).</span></span>
    
<span data-ttu-id="90a30-294">如需 DSR 案例工具中所有可用條件的清單和描述，請參閱「內容搜尋的關鍵字查詢和搜尋條件」文章中的[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="90a30-294">For a list and description of all the conditions available in the DSR case tool, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions) in the "Keyword queries and search conditions for Content Search" article.</span></span> 
  
### <a name="changing-the-content-locations-that-are-searched"></a><span data-ttu-id="90a30-295">變更搜尋的內容位置</span><span class="sxs-lookup"><span data-stu-id="90a30-295">Changing the content locations that are searched</span></span>

<span data-ttu-id="90a30-296">除了修改 DSR 案例內建的搜尋之外，您也可以變更所搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-296">In addition to revising the built-in search for a DSR case, you can also change the content locations that are searched.</span></span> <span data-ttu-id="90a30-297">如先前所述，內建搜尋會搜尋組織中的每個信箱和網站，以及任何 Exchange Online 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="90a30-297">As previously explained, the built-in search searches every mailbox and site in the organization, and any Exchange Online public folders.</span></span> <span data-ttu-id="90a30-298">例如，您可以縮小搜尋範圍，只搜尋資料主體的信箱和 OneDrive 帳戶，並選取 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="90a30-298">For example, you could narrow the search to only search the data subject's mailbox and OneDrive account and selected SharePoint sites.</span></span> <span data-ttu-id="90a30-299">如果您選擇搜尋特定網站，您必須新增每個要搜尋的網站。</span><span class="sxs-lookup"><span data-stu-id="90a30-299">If you choose to search specific sites, you have to add each site that you want to search.</span></span>
  
<span data-ttu-id="90a30-300">若要修改要搜尋的內容位置：</span><span class="sxs-lookup"><span data-stu-id="90a30-300">To modify the content locations to search:</span></span>
  
1. <span data-ttu-id="90a30-301">開啟您要變更其內容位置的內建搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-301">Open the built-in search that you want to change the content locations for.</span></span>
    
2. <span data-ttu-id="90a30-302">在搜尋查詢的 [**位置**] 底下，按一下 [**特定位置**] 選項旁的 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-302">In the search query, under **Locations**, click **Modify** next to the **Specific locations** option.</span></span> 
    
    ![按一下 [修改] 以變更內建搜尋查詢的內容位置。](../media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    <span data-ttu-id="90a30-304">隨即會顯示 [**修改位置**] 飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="90a30-304">The **Modify locations** flyout page is displayed.</span></span> <span data-ttu-id="90a30-305">以下是內建搜尋中內容位置的描述，以及有關修改所搜尋位置的一些資訊。</span><span class="sxs-lookup"><span data-stu-id="90a30-305">Here's a description of the content locations in the built-in search and some information about modifying the locations that are searched.</span></span> 
    
    ![修改位置飛出頁面](../media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    <span data-ttu-id="90a30-307">a.</span><span class="sxs-lookup"><span data-stu-id="90a30-307">a.</span></span> <span data-ttu-id="90a30-308">會選取飛入頁面頂端的 [**選取所有**信箱] 區段下的切換，這表示會搜尋所有信箱。</span><span class="sxs-lookup"><span data-stu-id="90a30-308">The toggle under **Select all** in mailbox section at the top of the flyout page is selected, which indicates that all mailboxes are searched.</span></span> <span data-ttu-id="90a30-309">若要縮小搜尋範圍，請按一下 [切換] 以取消選取它，然後按一下 **[選擇使用者、群組或小組**]，然後選擇要搜尋的特定信箱。</span><span class="sxs-lookup"><span data-stu-id="90a30-309">To narrow the scope of the search, click the toggle to unselect it, and then click **Choose users, groups, or teams** and choose specific mailboxes to search.</span></span>
    
    <span data-ttu-id="90a30-310">b.</span><span class="sxs-lookup"><span data-stu-id="90a30-310">b.</span></span> <span data-ttu-id="90a30-311">會選取飛入頁面中間的 [**選取**網站] 區段中的切換，這表示會搜尋所有網站。</span><span class="sxs-lookup"><span data-stu-id="90a30-311">The toggle under **Select all** in the sites section in the middle of the flyout page is selected, which indicates that all sites are searched.</span></span> <span data-ttu-id="90a30-312">若要將搜尋縮小至選取的網站，您可以取消選取 [切換]，然後按一下 **[選擇網站**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-312">To narrow the search to selected sites, you would unselect the toggle and then click **Choose sites**.</span></span> <span data-ttu-id="90a30-313">您必須新增每個要搜尋的特定網站，包含資料主體的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="90a30-313">You have to add each specific site that you want to search, including the data subject's OneDrive account.</span></span>
    
    <span data-ttu-id="90a30-314">c.</span><span class="sxs-lookup"><span data-stu-id="90a30-314">c.</span></span> <span data-ttu-id="90a30-315">已選取 [Exchange 公用資料夾] 區段中的 [切換]，這表示會搜尋所有 Exchange 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="90a30-315">The toggle in the Exchange public folders section is selected, which means all Exchange public folders are searched.</span></span> <span data-ttu-id="90a30-316">您只能搜尋所有 Exchange 公用資料夾或不進行任何搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-316">You can only search all Exchange public folders or none of them.</span></span> <span data-ttu-id="90a30-317">您無法選擇要搜尋的特定專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-317">You can't choose specific ones to search.</span></span>
    
3. <span data-ttu-id="90a30-318">如果您修改內建搜尋中的內容位置，請按一下 [**儲存 &amp; 執行**] 以重新開機搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-318">If you modify the content locations in the built-in search, click **Save &amp; run** to restart the search.</span></span> 

> [!NOTE]
> <span data-ttu-id="90a30-319">當您搜尋所有信箱位置或僅限特定信箱時，當您匯出搜尋結果時，會包含儲存至使用者信箱之其他 Office 365 應用程式中的資料。</span><span class="sxs-lookup"><span data-stu-id="90a30-319">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of the search.</span></span> <span data-ttu-id="90a30-320">此資料不會包含在估計的搜尋結果中，並且無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="90a30-320">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="90a30-321">但會包含在您匯出及下載搜尋結果時。</span><span class="sxs-lookup"><span data-stu-id="90a30-321">But it's included when you export and download the search results.</span></span> <span data-ttu-id="90a30-322">如需將資料儲存在使用者信箱中的應用程式的詳細資訊，請參閱[儲存在 Exchange Online 信箱中的內容](what-is-stored-in-exo-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="90a30-322">For more information the applications that store data in a user's mailbox, see [Content stored in Exchange Online mailboxes](what-is-stored-in-exo-mailbox.md).</span></span>
  
## <a name="more-information-about-using-the-dsr-case-tool"></a><span data-ttu-id="90a30-323">使用 DSR case 工具的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="90a30-323">More information about using the DSR case tool</span></span>

<span data-ttu-id="90a30-324">下列各節包含使用 DSR 案例工具回應 DSR 出口要求的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="90a30-324">The following sections contain more information about using the DSR case tool to respond to DSR export requests.</span></span>
  
[<span data-ttu-id="90a30-325">從 Office 漫遊服務匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-325">Exporting data from the Office Roaming Service</span></span>](#exporting-data-from-the-office-roaming-service)

[<span data-ttu-id="90a30-326">匯出部分索引項目目</span><span class="sxs-lookup"><span data-stu-id="90a30-326">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="90a30-327">從 Microsoft 團隊和 Microsoft 365 群組搜尋及匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-327">Searching and exporting data from Microsoft Teams and Microsoft 365 Groups</span></span>](#searching-and-exporting-data-from-microsoft-teams-and-microsoft-365-groups)

[<span data-ttu-id="90a30-328">搜尋 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="90a30-328">Searching Exchange public folders</span></span>](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-the-office-roaming-service"></a><span data-ttu-id="90a30-329">從 Office 漫遊服務匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-329">Exporting data from the Office Roaming Service</span></span>

<span data-ttu-id="90a30-330">您可以使用 DSR 案例工具來搜尋和匯出 Office 漫遊服務所產生的使用狀況資料。</span><span class="sxs-lookup"><span data-stu-id="90a30-330">You can use the DSR case tool to search for and export usage data that's generated by the Office Roaming Service.</span></span> <span data-ttu-id="90a30-331">「漫遊」是一種服務，可儲存與 Office 相關的設定，例如 Office 主題、自訂字典、語言設定、開發人員模式和自動校正。</span><span class="sxs-lookup"><span data-stu-id="90a30-331">Roaming is a service that stores Office-related settings, such as Office theme, custom dictionary, language settings, developer mode, and auto correct.</span></span> 
    
<span data-ttu-id="90a30-332">來自 Office 漫遊服務的資料會儲存在 Exchange Online 信箱的非人際郵件（非 IPM）子樹系中的隱藏資料夾中的資料主體信箱中。</span><span class="sxs-lookup"><span data-stu-id="90a30-332">The data from the Office Roaming service is stored in a data subject's mailbox in a hidden folder located in a non-interpersonal message (non-IPM) subtree of Exchange Online mailboxes.</span></span> <span data-ttu-id="90a30-333">這表示當使用者使用 Outlook 或其他郵件用戶端存取其信箱時，會將資料從使用者的視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="90a30-333">This means that the data is hidden from the user's view when they use Outlook or other mail clients to access their mailbox.</span></span> <span data-ttu-id="90a30-334">如需有關隱藏資料夾的詳細資訊，請參閱[MAPI 隱藏資料夾](https://go.microsoft.com/fwlink/?linkid=872758)。</span><span class="sxs-lookup"><span data-stu-id="90a30-334">For more information about hidden folders, see [MAPI Hidden Folders](https://go.microsoft.com/fwlink/?linkid=872758).</span></span>
  
<span data-ttu-id="90a30-335">您可以建立不同的內容搜尋（並將其與 DSR 案例關聯），以傳回資料主體信箱中的 Office 漫遊服務使用狀況資料。</span><span class="sxs-lookup"><span data-stu-id="90a30-335">You can create a separate content search (and associate it with a DSR case) that returns the Office Roaming Service usage data in the data subject's mailbox.</span></span> <span data-ttu-id="90a30-336">此資料不會包含在搜尋統計資料中，也不會供預覽使用。</span><span class="sxs-lookup"><span data-stu-id="90a30-336">This data isn't included in the search statistics and it won't be available for preview.</span></span> <span data-ttu-id="90a30-337">不過，您可以將其匯出，然後將其提供給回應 DSR 匯出要求的資料主體。</span><span class="sxs-lookup"><span data-stu-id="90a30-337">But you can export it and then give it to the data subject in response to a DSR export request.</span></span>
  
<span data-ttu-id="90a30-338">當您從 Office 漫遊服務匯出資料時，會將資料儲存至位於**ApplicationDataRoot**資料夾中的個別資料夾（位於名稱與資料主體的電子郵件地址的資料夾底下）。</span><span class="sxs-lookup"><span data-stu-id="90a30-338">When you export data from the Office Roaming Service, the data is saved to a separate folder that's located in the **ApplicationDataRoot** folder, which is under a folder that is name with the data subject's email address.</span></span> <span data-ttu-id="90a30-339">此資料會匯出為 JSON 檔案，也就是附加至電子郵件的可讀取的文字檔（類似 XML 或 TXT 檔案）。</span><span class="sxs-lookup"><span data-stu-id="90a30-339">This data is exported as JSON files, which are human-readable text files similar to XML or TXT files, that are attached to email messages.</span></span> <span data-ttu-id="90a30-340">目前這個資料夾是以全域唯一識別碼（GUID）命名： **1caee58f-eb14-4a6b-9339-1fe2ddf6692b**。</span><span class="sxs-lookup"><span data-stu-id="90a30-340">Currently, this folder is named with the globally unique identifier (GUID): **1caee58f-eb14-4a6b-9339-1fe2ddf6692b**.</span></span> <span data-ttu-id="90a30-341">在未來版本的 DSR 案例工具中，GUID 將會以實際的應用程式名稱取代。</span><span class="sxs-lookup"><span data-stu-id="90a30-341">In future versions of the DSR case tool, the GUID will be replaced with the name of the actual application.</span></span> 

   
 <span data-ttu-id="90a30-342">**若要搜尋並匯出 Office 漫遊服務資料：**</span><span class="sxs-lookup"><span data-stu-id="90a30-342">**To search for and export Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="90a30-343">在 [安全性 & 規範中心] 中，按一下 [**資料隱私權** \> **資料主體要求**]，然後針對您想要匯出使用方式資料的資料主體，按一下 DSR 案例旁邊的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-343">In the Security & Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case for the data subject that you want to export usage data for.</span></span> 
    
2. <span data-ttu-id="90a30-344">按一下頁面頂端的 [**搜尋] 索引**標籤，然後按一下 [ ![ 加入圖示 ](../media/ITPro-EAC-AddIcon.gif) **導向搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-344">Click the **Search** tab at the top of the page, and then click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) **Guided search**.</span></span>
    
3. <span data-ttu-id="90a30-345">在 [**命名您的搜尋**] 頁面上，按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-345">Click **Cancel** on the **Name your search** page.</span></span> 
    
4. <span data-ttu-id="90a30-346">在 [**搜尋查詢**] 底下的 [**類型**] 條件中，選取 [ **Office 漫遊服務**] 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90a30-346">Under **Search query**, in the **Type** condition, select the check box next to **Office Roaming Service**.</span></span> 
    
    ![選取 [Office 漫遊服務] 核取方塊，以匯出使用狀況資料](../media/O365_DSRCase_SDSDataExport1.png)
  
    <span data-ttu-id="90a30-348">**類型**條件（即電子郵件類別）應為搜尋查詢中的唯一專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-348">The **Type** condition (which are email message classes) should be the only item in the search query.</span></span> <span data-ttu-id="90a30-349">您可以刪除 [**關鍵字**] 方塊或保留空白。</span><span class="sxs-lookup"><span data-stu-id="90a30-349">You can delete the **Keywords** box or leave it blank.</span></span> 
    
5. <span data-ttu-id="90a30-350">在 [**位置**] 下，確定已選取**特定位置**，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-350">Under **Locations**, make sure that **Specific locations** is selected, and then click **Modify**.</span></span>
    
6. <span data-ttu-id="90a30-351">在 [**修改位置**] 飛入頁面（信箱區段）的上方，按一下 **[選擇使用者、群組或小組**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-351">On top part of the **Modify locations** flyout page (the mailbox section), click **Choose users, groups, or teams**.</span></span>
    
7. <span data-ttu-id="90a30-352">在 [**編輯位置**] 頁面上，按一下 **[選擇使用者、群組或小組**]，選擇資料主體的信箱，然後儲存您的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="90a30-352">On the **Edit locations** page, click **Choose users, groups, or teams**, choose the data subject's mailbox, and then save your selection.</span></span> 
    
8. <span data-ttu-id="90a30-353">按一下 [**儲存 & 執行**]，然後命名搜尋並儲存。</span><span class="sxs-lookup"><span data-stu-id="90a30-353">Click **Save & run**, and then name the search and save it.</span></span>
    
    <span data-ttu-id="90a30-354">已啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-354">The search is started.</span></span>
    
 <span data-ttu-id="90a30-355">**若要匯出 Office 漫遊服務資料：**</span><span class="sxs-lookup"><span data-stu-id="90a30-355">**To export Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="90a30-356">當您在上一個步驟中建立的搜尋完成時，請按一下頁面頂端的 [**搜尋**] 索引標籤，然後按一下搜尋旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90a30-356">When the search that you created in the previous step is complete, click the **Search** tab at the top of the page, and then click the checkbox next to the search.</span></span> <span data-ttu-id="90a30-357">您可能需要按一下 [重新整理] 重新整理 ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Refresh** ，以顯示搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-357">You may have to click ![Refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Refresh** to display the search.</span></span> 
    
2. <span data-ttu-id="90a30-358">在 [搜尋飛出] 頁面上，按一下 [ ![ 更多匯出搜尋結果圖示] ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\* **，然後從下拉式清單中選取 [**匯出結果\*\*]。</span><span class="sxs-lookup"><span data-stu-id="90a30-358">On the search flyout page, click ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="90a30-359">在 [**匯出結果**] 頁面上，選取匯出使用狀況資料的建議選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-359">On the **Export results** page, select the recommended options to export usage data.</span></span> 
    
    ![匯出 Office 漫遊服務使用狀況資料時的匯出選項](../media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    <span data-ttu-id="90a30-361">a.</span><span class="sxs-lookup"><span data-stu-id="90a30-361">a.</span></span> <span data-ttu-id="90a30-362">在 [輸出選項] 的 [**輸出選項**] 底下，選取第一個選項（**包括具有無法辨識格式之專案的所有專案，也就是已加密的專案，或是尚未為其他原因編制索引**），只匯出索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-362">Under **Output options**, select the first option (**All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only.</span></span>
    
    <span data-ttu-id="90a30-363">b.</span><span class="sxs-lookup"><span data-stu-id="90a30-363">b.</span></span> <span data-ttu-id="90a30-364">在 [將**Exchange 內容匯出為**] 底下，選取第二個選項，**其中包含所有郵件的一個 PST**檔案。</span><span class="sxs-lookup"><span data-stu-id="90a30-364">Under **Export Exchange content as**, select the second option, **One PST file containing all messages**.</span></span>
    
    <span data-ttu-id="90a30-365">c.</span><span class="sxs-lookup"><span data-stu-id="90a30-365">c.</span></span> <span data-ttu-id="90a30-366">保留未選取的其餘匯出選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-366">Leave the remaining export options unselected.</span></span>
    
4. <span data-ttu-id="90a30-367">選擇匯出設定後，按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-367">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="90a30-368">搜尋結果已準備好下載，也就是將其上傳至 Microsoft 雲端中組織的 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="90a30-368">The search results are prepared for downloading, which means they're uploaded to the Azure storage area for your organization in the Microsoft cloud.</span></span> <span data-ttu-id="90a30-369">接下來的步驟將示範如何將此資料下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="90a30-369">The next steps show you how to download this data to your local computer.</span></span>
    
5. <span data-ttu-id="90a30-370">按一下 [**匯出**] 索引標籤，顯示您建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="90a30-370">Click the **Export** tab to display the export job you created.</span></span> <span data-ttu-id="90a30-371">匯出工作與對應的搜尋同名，但 **_Export**附加于搜尋名稱的結尾。</span><span class="sxs-lookup"><span data-stu-id="90a30-371">The export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="90a30-372">按一下您剛才建立的匯出工作以顯示 [匯出飛出] 頁面。</span><span class="sxs-lookup"><span data-stu-id="90a30-372">Click the export job that you just created to display the export flyout page.</span></span> 
    
7. <span data-ttu-id="90a30-373">在 [**匯出金鑰**] 底下，按一下 [**複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="90a30-373">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="90a30-374">您可以在步驟10中使用此機碼下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90a30-374">You use this key in step 10 to download the search results.</span></span>
    
8. <span data-ttu-id="90a30-375">按一下 ![ [匯出飛出] 頁面頂端的 [匯出搜尋結果圖示 ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **下載結果**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-375">Click ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
9. <span data-ttu-id="90a30-376">在頁面底部的快顯視窗中，按一下 [**開啟**] 以開啟 [ **eDiscovery 匯出工具**]。</span><span class="sxs-lookup"><span data-stu-id="90a30-376">In the pop-up window at the bottom of the page, click **Open** to open the **eDiscovery Export Tool**.</span></span> <span data-ttu-id="90a30-377">第一次下載搜尋結果時會安裝**EDiscovery 匯出工具**。</span><span class="sxs-lookup"><span data-stu-id="90a30-377">The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
10. <span data-ttu-id="90a30-378">在 [電子文件探索匯出工具]\*\*\*\* 中，於適當的方塊中貼上您在步驟 7 中所複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="90a30-378">In the **eDiscovery Export Tool**, paste the export key that you copied in step 7 in the appropriate box.</span></span>
    
11. <span data-ttu-id="90a30-379">按一下 [瀏覽]\*\*\*\* 以指定搜尋結果檔案要下載到的位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-379">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="90a30-380">由於大量的磁片活動（讀取和寫入），您應該將搜尋結果下載到本機磁片磁碟機;不要將其下載到對應的網路磁碟機或其他網路位置。</span><span class="sxs-lookup"><span data-stu-id="90a30-380">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
12. <span data-ttu-id="90a30-381">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="90a30-381">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="90a30-382">**EDiscovery 匯出工具**會顯示匯出程式的狀態資訊，包括要下載之其餘專案的數位（和大小）的預估。</span><span class="sxs-lookup"><span data-stu-id="90a30-382">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="90a30-383">當匯出程式完成時，您可以在 Outlook 中開啟 Exchange PST 檔案，然後移至**ApplicationDataRoot**資料夾，以存取漫遊服務的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="90a30-383">When the export process is complete, you can open the Exchange PST file in Outlook and then go to the **ApplicationDataRoot** folder to access the subfolder for the Roaming service.</span></span> 
    
    <span data-ttu-id="90a30-384">如先前所述，包含使用狀況資料的 JSON 檔案會附加到郵件。</span><span class="sxs-lookup"><span data-stu-id="90a30-384">As previously explained, the JSON files that contain usage data are attached to messages.</span></span> <span data-ttu-id="90a30-385">若要查看 JSON 檔，請按一下郵件，然後開啟附加的 JSON 檔案。</span><span class="sxs-lookup"><span data-stu-id="90a30-385">To view a JSON file, click a message and then open the attached JSON file.</span></span> 
  
### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="90a30-386">匯出部分索引項目目</span><span class="sxs-lookup"><span data-stu-id="90a30-386">Exporting partially indexed items</span></span>

<span data-ttu-id="90a30-387">建議您不要從建立 DSR 案例時所建立的內建搜尋中，匯出部分編制索引的專案（也稱為未編制索引的專案）。</span><span class="sxs-lookup"><span data-stu-id="90a30-387">We recommend that you don't export partially indexed items (also called unindexed items) from the built-in search that's created when you create a DSR case.</span></span> <span data-ttu-id="90a30-388">這是因為搜尋結果可能會包含組織中其他使用者的部分索引項目目，而不只是資料主體的部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="90a30-388">That's because the search results will more than likely include partially indexed items for other users in your organization, and not just partially indexed items for the data subject).</span></span> <span data-ttu-id="90a30-389">相反地，我們建議您建立與 DSR 案例相關聯的個別內容搜尋，其設計目的是只匯出與資料主體相關的部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="90a30-389">Instead, we recommend that you create a separate Content Search that's associated with the DSR case that's designed to export only the partially indexed items related to the data subject.</span></span> 
  
<span data-ttu-id="90a30-390">以下是匯出部分索引項目目的高層級程式。</span><span class="sxs-lookup"><span data-stu-id="90a30-390">Here's a high-level process to export partially indexed items.</span></span> <span data-ttu-id="90a30-391">匯出完畢後，您可以進行檢查，以判斷專案是否回應 DSR 存取或匯出要求。</span><span class="sxs-lookup"><span data-stu-id="90a30-391">After they're export, you can review them to determine if an item is responsive to a DSR access or export request.</span></span>
  
1. <span data-ttu-id="90a30-392">開啟 DSR 案例，並在 [**搜尋**] 頁面上建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-392">Open the DSR case and create a search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="90a30-393">使用下列準則來設定搜尋查詢及要搜尋的內容位置：</span><span class="sxs-lookup"><span data-stu-id="90a30-393">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
    - <span data-ttu-id="90a30-394">使用空白/空白關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="90a30-394">Use an empty/blank keyword query.</span></span> <span data-ttu-id="90a30-395">這會傳回搜尋內容位置中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-395">This returns all items in the content locations that are searched.</span></span>
    
    - <span data-ttu-id="90a30-396">僅搜尋資料主體的 Exchange Online 信箱及其 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="90a30-396">Search only the data subject's Exchange Online mailbox and their OneDrive account.</span></span>
    
3. <span data-ttu-id="90a30-397">在您執行搜尋並完成後，您可以匯出及下載搜尋結果（如[步驟 4](#step-4-export-the-data)所述）。</span><span class="sxs-lookup"><span data-stu-id="90a30-397">After you run the search and it completes, you can export and download the search results (as described in [Step 4](#step-4-export-the-data)).</span></span> <span data-ttu-id="90a30-398">使用下列設定來匯出部分編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-398">Use the following settings to export partially indexed items.</span></span> 
    
    - <span data-ttu-id="90a30-399">在 [**輸出選項**] 底下，選取第三個選項（**僅限無法辨識之格式的專案、已加密或尚未為其他原因編制索引**），以只匯出部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="90a30-399">Under **Output options**, select the third option (**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export partially indexed items only.</span></span>
    
    - <span data-ttu-id="90a30-400">在 [將**Exchange 內容匯出為**] 底下，您可以根據喜好設定來選取任何選項。</span><span class="sxs-lookup"><span data-stu-id="90a30-400">Under **Export Exchange content as**, you can select any option based on your preferences.</span></span> 
    
    - <span data-ttu-id="90a30-401">選取 [**包含版本的 SharePoint 檔**] 選項會匯出檔版本（如果版本已部分編制索引）。</span><span class="sxs-lookup"><span data-stu-id="90a30-401">Selecting the **Include versions for SharePoint documents** option exports versions of documents if a version is partially indexed.</span></span> 
    
<span data-ttu-id="90a30-402">如需部分索引項目目的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="90a30-402">For more information about partially indexed items, see:</span></span> 
  
- [<span data-ttu-id="90a30-403">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="90a30-403">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="90a30-404">匯出部分索引項目目</span><span class="sxs-lookup"><span data-stu-id="90a30-404">Exporting partially indexed items</span></span>](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-microsoft-365-groups"></a><span data-ttu-id="90a30-405">從 Microsoft 團隊和 Microsoft 365 群組搜尋及匯出資料</span><span class="sxs-lookup"><span data-stu-id="90a30-405">Searching and exporting data from Microsoft Teams and Microsoft 365 Groups</span></span>

<span data-ttu-id="90a30-406">[！注意] 屬於 Microsoft 球隊（稱為「小組聊天] 或「一對一聊天」）中之聊天清單一部分的對話會儲存在參與交談之使用者的 Exchange Online 信箱中。</span><span class="sxs-lookup"><span data-stu-id="90a30-406">Conversations that are part of the Chat list in Microsoft Teams (called Team chats or one-to-one chats) are stored in the Exchange Online mailbox of the users who participate in the chats.</span></span> <span data-ttu-id="90a30-407">此外，在一對一聊天中共用的檔案，會儲存在共用該檔案之人員的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="90a30-407">Also, the files a person shares in a one-to-one chat are stored in the OneDrive account of the person who shares the file.</span></span> <span data-ttu-id="90a30-408">由於內建搜尋會搜尋組織中的所有信箱和 OneDrive 帳戶，所以在聊天會話中共用的小組研討和檔（已建立或上傳的資料主體）會由內建搜尋在 DSR 案例中傳回。</span><span class="sxs-lookup"><span data-stu-id="90a30-408">Because the built-in search searches all mailboxes and OneDrive accounts in the organization, team chats and documents shared in a chat session (that the data subject created or uploaded) are returned by built-in search in a DSR case.</span></span>
  
<span data-ttu-id="90a30-409">或者，「小組」通道（也稱為「通道」）一部分的交談會儲存在與小組相關聯的信箱中。</span><span class="sxs-lookup"><span data-stu-id="90a30-409">Alternatively, conversations that are part of a Teams channel (also called channel messages) are stored in the mailbox that's associated with a team.</span></span> <span data-ttu-id="90a30-410">因為搜尋與小組相關聯的所有信箱，所以內建的搜尋也會傳回這些資料主題所參與的交談類型。</span><span class="sxs-lookup"><span data-stu-id="90a30-410">These types of conversations that the data subject participated in are also returned by the built-in search because all mailboxes associated with Teams are searched.</span></span> <span data-ttu-id="90a30-411">此外，小組管道中的資料主體共用的檔案會儲存在小組的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="90a30-411">Additionally, files that a data subject shares in a Teams channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="90a30-412">由資料主體所建立或上傳的檔案會由 DSR 案例內建的搜尋傳回，因為與小組相關聯的網站會包含在搜尋中。</span><span class="sxs-lookup"><span data-stu-id="90a30-412">Files created or uploaded by the data subject are returned by the built-in search in a DSR case because the sites associated with Teams are included in the search.</span></span>
  
<span data-ttu-id="90a30-413">同樣地，在內建搜尋中也會包含對應至 Microsoft 365 群組的信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="90a30-413">Similarly, mailboxes and SharePoint sites that correspond to an Microsoft 365 Group are also included in the built-in search.</span></span> <span data-ttu-id="90a30-414">這表示會傳回由資料主體所傳送或接收的電子郵件，以及資料主體所建立或上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="90a30-414">This means that email messages sent or received by the data subject and files created or uploaded by the data subject are returned.</span></span> 
  
<span data-ttu-id="90a30-415">如需使用內容搜尋來搜尋 Microsoft 團隊和 Microsoft 365 群組中的專案，或若要瞭解如何取得成員清單的詳細資訊，請參閱[microsoft 365 中內容搜尋](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)中的「搜尋 Microsoft 團隊和 Microsoft 365 群組」一節。</span><span class="sxs-lookup"><span data-stu-id="90a30-415">For more information about using Content Search to search for items in Microsoft Teams and Microsoft 365 Groups or to see how to get a list of members, see the "Searching Microsoft Teams and Microsoft 365 Groups" section in [Content Search in Microsoft 365](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span> 
  
### <a name="searching-exchange-public-folders"></a><span data-ttu-id="90a30-416">搜尋 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="90a30-416">Searching Exchange public folders</span></span>

<span data-ttu-id="90a30-417">DSR 案例內內建的搜尋只會傳回傳送給擁有郵件功能之公用資料夾的電子郵件訊息，或其他人傳送至公用資料夾的郵件，也會複製資料主體。</span><span class="sxs-lookup"><span data-stu-id="90a30-417">The built-in search in a DSR case will only return email messages that the data subject sent to a mail-enabled public folder or messages that someone else sent to a public folder and also copied the data subject.</span></span> <span data-ttu-id="90a30-418">它不會傳回傳送至公用資料夾之資料主體的郵件。</span><span class="sxs-lookup"><span data-stu-id="90a30-418">It doesn't return messages that the data subject posted to a public folder.</span></span> <span data-ttu-id="90a30-419">若要搜尋已傳送至公用資料夾之資料主體的專案，您可以建立個別的內容搜尋，以搜尋資料主體傳送至公用資料夾的任何專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-419">To search for items that the data subject posted to a public folder, you can create a separate create a separate Content Search that searches for any item posted to a public folder by the data subject.</span></span>
  
<span data-ttu-id="90a30-420">以下是一個高層級的處理常式，可搜尋傳送至公用資料夾之資料主體的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-420">Here's a high-level process to search for items that the data subject posted to a public folder.</span></span> 
  
1. <span data-ttu-id="90a30-421">開啟 DSR 案例，並在 [**搜尋**] 頁面上建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="90a30-421">Open the DSR case and create a search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="90a30-422">使用下列準則來設定搜尋查詢及要搜尋的內容位置：</span><span class="sxs-lookup"><span data-stu-id="90a30-422">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
  - <span data-ttu-id="90a30-423">在 [**關鍵字**] 方塊中，使用下列搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="90a30-423">In the **Keywords** box, use the following search query:</span></span> 
    
    ```powershell
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - <span data-ttu-id="90a30-424">搜尋所有 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="90a30-424">Search all Exchange public folders</span></span>
    
  - <span data-ttu-id="90a30-425">在您執行搜尋並完成後，您可以匯出及下載搜尋結果（如[步驟 4](#step-4-export-the-data)所述）。</span><span class="sxs-lookup"><span data-stu-id="90a30-425">After you run the search and it completes, you can export and download the search results (as described in [Step 4](#step-4-export-the-data)).</span></span> <span data-ttu-id="90a30-426">使用下列設定來匯出部分編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="90a30-426">Use the following settings to export partially indexed items.</span></span> 
