---
title: Microsoft 合規性管理員和 GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595800"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="a9e0e-104">Microsoft 合規性管理員和 GDPR</span><span class="sxs-lookup"><span data-stu-id="a9e0e-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="a9e0e-105">歐盟所頒佈的一般資料保護法規 (GDPR) 會影響您的規範策略，並強制執行管理合規性管理員中所使用的使用者和客戶資訊的特定動作。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="a9e0e-106">使用者隱私權設定</span><span class="sxs-lookup"><span data-stu-id="a9e0e-106">User Privacy settings</span></span>

<span data-ttu-id="a9e0e-107">某些法規要求組織必須能夠刪除使用者的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="a9e0e-108">合規性管理員提供 **使用者隱私權設定** 功能，可讓系統管理員：</span><span class="sxs-lookup"><span data-stu-id="a9e0e-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="a9e0e-109">使用者搜尋</span><span class="sxs-lookup"><span data-stu-id="a9e0e-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="a9e0e-110">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="a9e0e-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="a9e0e-111">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="a9e0e-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="a9e0e-112">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="a9e0e-112">Search for a user</span></span>

<span data-ttu-id="a9e0e-113">若要搜尋使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="a9e0e-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="a9e0e-114">輸入使用者的電子郵件別名 (@ 符號左邊的資訊) ，然後從右邊的 [網域尾碼] 清單中選擇功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="a9e0e-115">如果組織有多個註冊的網域，請加倍檢查功能變數名稱尾碼，以確保正確無誤。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="a9e0e-116">當您輸入正確的使用者名稱時，請選取 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="a9e0e-117">未傳回的使用者帳戶會顯示 [ **找不到使用者**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="a9e0e-118">檢查使用者的電子郵件地址資訊，並視需要進行修正。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="a9e0e-119">若要重試，請選取 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="a9e0e-120">對於傳回的使用者帳戶，按鈕的文字會從 **搜尋** 變更為 **Clear**。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="a9e0e-121">這表示傳回的使用者帳戶為其他功能的作業內容，且這些功能適用于此使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="a9e0e-122">若要清除搜尋結果並搜尋不同的使用者，請選取 [ **清除**]。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="a9e0e-123">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="a9e0e-123">Export a report of account data history</span></span>

<span data-ttu-id="a9e0e-124">針對每個識別的使用者帳戶，您可以產生連結至該帳戶的相依性報告。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="a9e0e-125">這項資訊可讓您重新指派開啟的動作專案，或確定先前上傳的證據的存取權。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="a9e0e-126">若要產生並匯出報告：</span><span class="sxs-lookup"><span data-stu-id="a9e0e-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="a9e0e-127">選取 [ **匯出** ] 以產生及下載目前指派給傳回之使用者帳戶的合規性管理員控制項動作專案，以及該使用者上傳的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="a9e0e-128">如果沒有任何指派的動作或上傳的檔，錯誤訊息會指出「沒有此使用者的資料」。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="a9e0e-129">在使用中瀏覽器視窗的背景中下載報告（如果您沒有看到您想要檢查瀏覽器下載歷程記錄的下載快顯功能表）。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="a9e0e-130">開啟文件以檢視報告資料。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9e0e-131">報告資料不是一份歷史清單，可保留及顯示動作專案指派歷程記錄的狀態變更。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="a9e0e-132">產生的報表是在執行報表時所指派之控制項動作專案的快照 (會寫入報告) 中的日期和時間戳記。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="a9e0e-133">例如，任何後續重新分派動作專案時，如果為相同使用者再次產生報表，便會產生不同的快照報告資料。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="a9e0e-134">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="a9e0e-134">Delete user data history</span></span>

<span data-ttu-id="a9e0e-135">將指派給傳回之使用者的所有控制動作專案設定為「未指派」。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="a9e0e-136">將傳回使用者上傳的任何檔的 **上傳** 值，設定為「使用者已移除」。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="a9e0e-137">若要刪除使用者帳戶動作專案和檔上傳歷程記錄：</span><span class="sxs-lookup"><span data-stu-id="a9e0e-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="a9e0e-138">選取 [刪除 **]**。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-138">Select **Delete**.</span></span>

    <span data-ttu-id="a9e0e-139">隨即會顯示確認對話方塊：「*這會移除所有控制項動作專案指派，以及所選使用者的檔上傳記錄。此動作為永久性。您確定要繼續嗎？*</span><span class="sxs-lookup"><span data-stu-id="a9e0e-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="a9e0e-140">若要繼續，請選取 **[確定]**，否則請選取 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="a9e0e-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
