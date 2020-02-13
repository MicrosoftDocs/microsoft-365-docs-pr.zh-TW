---
title: 資料分類預覽版本資訊 (預覽)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 資料分類公開預覽版的版本資訊。
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887333"
---
# <a name="data-classification-public-preview-release-notes-preview"></a><span data-ttu-id="78498-103">資料分類公開預覽版本資訊 (預覽)</span><span class="sxs-lookup"><span data-stu-id="78498-103">Data classification public preview release notes (preview)</span></span>

<span data-ttu-id="78498-104">此公開預覽版引進新功能，可在您建立任何原則*之前*，開始掃描敏感內容和標籤內容。</span><span class="sxs-lookup"><span data-stu-id="78498-104">This public preview introduces new functionality where scanning of your sensitive content and labeled content starts *before* you create any policies.</span></span> <span data-ttu-id="78498-105">這稱為**零變更管理**。</span><span class="sxs-lookup"><span data-stu-id="78498-105">This is called **zero change management**.</span></span> <span data-ttu-id="78498-106">這可讓您查看所有保留和敏感度標籤對環境的影響，並協助您開始評估自己的保護和控管原則需求。</span><span class="sxs-lookup"><span data-stu-id="78498-106">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

<span data-ttu-id="78498-107">請檢閱這些版本資訊，讓您可以享有公開預覽版的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="78498-107">Please review these release notes so that you have the best experience with this public preview.</span></span> <span data-ttu-id="78498-108">我們將在目前版本與正式版本 (GA) 之間致力於處理這些要點。</span><span class="sxs-lookup"><span data-stu-id="78498-108">We will be working on addressing these points between now and general availability (GA).</span></span>

## <a name="permissions-for-accessing-content-explorer"></a><span data-ttu-id="78498-109">存取內容總管的權限</span><span class="sxs-lookup"><span data-stu-id="78498-109">Permissions for accessing content explorer</span></span>

<span data-ttu-id="78498-110">內容總管的存取權限受到高度限制，因為該權限可讓您讀取掃描檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="78498-110">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span> <span data-ttu-id="78498-111">若要存取內容總管，需要**內容總管清單檢視器**和**內容總管內容檢視器**角色群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="78498-111">Access to content explorer requires membership in the **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups.</span></span> <span data-ttu-id="78498-112">根據預設，沒有帳戶可以存取內容總管。</span><span class="sxs-lookup"><span data-stu-id="78498-112">No account has access to content explorer by default.</span></span> <span data-ttu-id="78498-113">請參閱[使用資料分類內容總管 (預覽)](data-classification-content-explorer.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="78498-113">See, [Using data classification content explorer (preview)](data-classification-content-explorer.md#permissions).</span></span> <span data-ttu-id="78498-114">全域系統管理員、合規性系統管理員或資料系統管理員可以指派必要的**內容總管清單檢視器**和**內容總管內容檢視器**角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="78498-114">A Global admin, Compliance admin, or Data admin can assign the necessary **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role group membership.</span></span>

> [!TIP]
> <span data-ttu-id="78498-115">在全球部署角色型存取控制 (RBAC) 時，**內容總管清單檢視器**和**內容總管內容檢視器**角色群組可能不會出現在權限頁面上。</span><span class="sxs-lookup"><span data-stu-id="78498-115">The **Content Explorer List Viewer**, and the **Content Explorer Content Viewer** role groups may not appear on the permissions page while the Role Based Access Controls (RBAC) are being deployed worldwide.</span></span> <span data-ttu-id="78498-116">如果權限頁面上沒有顯示該角色群組，則必須建立自訂角色群組，並將 `data classification list viewer` 角色和 (或) `data classification content viewer` 角色指派給您自訂的角色群組。</span><span class="sxs-lookup"><span data-stu-id="78498-116">If they aren't appearing on the permissions page, you must create a custom role group and assign the `data classification list viewer` role and or the `data classification content viewer` roles to your custom role group.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="78498-117">Exchange 信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="78498-117">Exchange mailbox count</span></span>

<span data-ttu-id="78498-118">當您深入了解 Exchange 信箱時，會注意到出現小工具提示。</span><span class="sxs-lookup"><span data-stu-id="78498-118">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="78498-119">這是為了表明以下事實：對於敏感資訊類型、敏感度標籤和保留標籤顯示的彙總計數，可能與信箱中所找到的項目數不完全相符。</span><span class="sxs-lookup"><span data-stu-id="78498-119">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="78498-120">原因是深入查看資料夾時會提取分類內容的即時檢視，同時計算彙總的計數。</span><span class="sxs-lookup"><span data-stu-id="78498-120">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>

## <a name="seeing-guids-instead-of-label-names"></a><span data-ttu-id="78498-121">看到 GUID 而不是標籤名稱</span><span class="sxs-lookup"><span data-stu-id="78498-121">Seeing GUIDs instead of label names</span></span>

<span data-ttu-id="78498-122">私人預覽版客戶已看到下列情況：刪除貼有內容的標籤時，會導致標籤名稱解析為內容總管和活動總管中的 32位元 GUID，而不是標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="78498-122">Private preview customers have seen instances where the deletion of a label that content has already been stamped with results in label names resolving to a 32-bit GUID in content explorer and activity explorer instead of the label name.</span></span> 

## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="78498-123">呈現加密的文件</span><span class="sxs-lookup"><span data-stu-id="78498-123">Rendering of encrypted documents</span></span>

<span data-ttu-id="78498-124">加密的 SharePoint、Exchange 和 OneDrive 檔案不會呈現在內容總管中。</span><span class="sxs-lookup"><span data-stu-id="78498-124">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="78498-125">這是敏感問題，需要在內容總管中查看檔案內容與將內容保留加密狀態中，這兩種需求之間取得平衡。</span><span class="sxs-lookup"><span data-stu-id="78498-125">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="78498-126">透過**內容總管清單檢視器**和**內容總管內容檢視器**角色群組授與的權限，您會看到一個清單檢視，其中列出檔案、檔案中繼資料，以及可以用來透過 Web 用戶端存取內容的連結。</span><span class="sxs-lookup"><span data-stu-id="78498-126">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="78498-127">SharePoint 搜尋中保留標籤名稱中的支援字元</span><span class="sxs-lookup"><span data-stu-id="78498-127">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="78498-128">SharePoint search 不支援內含 `-``_` 的保留標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="78498-128">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="78498-129">例如，不支援 `Label-MIP` 和 `Label_MIP`。</span><span class="sxs-lookup"><span data-stu-id="78498-129">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="78498-130">SharePoint 搜尋不支援在敏感性標籤名稱和敏感資訊類型名稱中使用那些字元。</span><span class="sxs-lookup"><span data-stu-id="78498-130">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="see-also"></a><span data-ttu-id="78498-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78498-131">See also</span></span>

- [<span data-ttu-id="78498-132">開始使用資料分類 (預覽)</span><span class="sxs-lookup"><span data-stu-id="78498-132">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="78498-133">查看標籤活動 (預覽)</span><span class="sxs-lookup"><span data-stu-id="78498-133">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="78498-134">檢視已套用標籤的內容 (預覽)</span><span class="sxs-lookup"><span data-stu-id="78498-134">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="78498-135">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="78498-135">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="78498-136">保留標籤</span><span class="sxs-lookup"><span data-stu-id="78498-136">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="78498-137">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="78498-137">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

