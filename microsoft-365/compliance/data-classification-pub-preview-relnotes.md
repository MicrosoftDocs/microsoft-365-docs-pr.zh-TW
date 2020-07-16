---
title: 資料分類版本資訊
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
description: 資料分類的版本資訊。
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127138"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="4ed1d-103">資料分類版本資訊</span><span class="sxs-lookup"><span data-stu-id="4ed1d-103">Data classification release notes</span></span>

<span data-ttu-id="4ed1d-104">請檢閱這些版本資訊，讓您可以享有資料分類的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="4ed1d-105">Exchange 信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="4ed1d-105">Exchange mailbox count</span></span>

<span data-ttu-id="4ed1d-106">當您深入了解 Exchange 信箱時，會注意到出現小工具提示。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="4ed1d-107">這是為了表明以下事實：對於敏感資訊類型、敏感度標籤和保留標籤顯示的彙總計數，可能與信箱中所找到的項目數不完全相符。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="4ed1d-108">原因是深入查看資料夾時會提取分類內容的即時檢視，同時計算彙總的計數。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="4ed1d-109">呈現加密的文件</span><span class="sxs-lookup"><span data-stu-id="4ed1d-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="4ed1d-110">加密的 SharePoint、Exchange 和 OneDrive 檔案不會呈現在內容總管中。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="4ed1d-111">這是敏感問題，需要在內容總管中查看檔案內容與將內容保留加密狀態中，這兩種需求之間取得平衡。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="4ed1d-112">透過**內容總管清單檢視器**和**內容總管內容檢視器**角色群組授與的權限，您會看到一個清單檢視，其中列出檔案、檔案中繼資料，以及可以用來透過 Web 用戶端存取內容的連結。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="4ed1d-113">SharePoint 搜尋中保留標籤名稱中的支援字元</span><span class="sxs-lookup"><span data-stu-id="4ed1d-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="4ed1d-114">SharePoint search 不支援內含 `-``_` 的保留標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="4ed1d-115">例如，不支援 `Label-MIP` 和 `Label_MIP`。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="4ed1d-116">SharePoint 搜尋不支援在敏感性標籤名稱和敏感資訊類型名稱中使用那些字元。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="4ed1d-117">OneDrive 仍處於預覽階段</span><span class="sxs-lookup"><span data-stu-id="4ed1d-117">OneDrive remains in preview</span></span>

<span data-ttu-id="4ed1d-118">我們收到了您在預覽計劃期間對 OneDrive 整合的寶貴意見反應。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="4ed1d-119">當我們瀏覽特定資訊時，您可能會遇到不一致的資料/流程。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="4ed1d-120">我們會繼續在預覽中展示 OneDrive，直到所有修正都已推出為止。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="4ed1d-121">非常感謝您的持續支持。</span><span class="sxs-lookup"><span data-stu-id="4ed1d-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="4ed1d-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ed1d-122">See also</span></span>

- [<span data-ttu-id="4ed1d-123">開始使用資料分類 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4ed1d-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="4ed1d-124">查看標籤活動 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4ed1d-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4ed1d-125">檢視已套用標籤的內容 (預覽)</span><span class="sxs-lookup"><span data-stu-id="4ed1d-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="4ed1d-126">瞭解敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4ed1d-126">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="4ed1d-127">瞭解保留原則和保留標記</span><span class="sxs-lookup"><span data-stu-id="4ed1d-127">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="4ed1d-128">敏感資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="4ed1d-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)