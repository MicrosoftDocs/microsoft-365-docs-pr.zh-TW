---
title: SharePoint Syntex 中的影像標記
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解 SharePoint Syntex 中的影像標記
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295801"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="99129-103">SharePoint Syntex 中的影像標記</span><span class="sxs-lookup"><span data-stu-id="99129-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="99129-104">預設會對 SharePoint 和 OneDrive 開啟基本的影像標記。</span><span class="sxs-lookup"><span data-stu-id="99129-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="99129-105">上傳到兩個位置之一的影像會經過自動掃描，並從 37 個基本標記的清單套用適用的標記 (如果可用的話)。</span><span class="sxs-lookup"><span data-stu-id="99129-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="99129-106">使用者可以搜尋影像上的標記，透過搜尋來尋找影像。</span><span class="sxs-lookup"><span data-stu-id="99129-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="99129-107">當使用者上傳影像時，標記程序會自動執行。</span><span class="sxs-lookup"><span data-stu-id="99129-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="99129-108">如果影像已經過編輯，標記程序會再次執行以更新標記。</span><span class="sxs-lookup"><span data-stu-id="99129-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="99129-109">擁有影像權限的使用者可以在檔案資訊面板或搜尋結果頁面中查看及編輯標記。</span><span class="sxs-lookup"><span data-stu-id="99129-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="99129-110">一旦使用者編輯影像的標記，系統就不再會於該影像上執行自動標記，即使該影像已經過編輯。</span><span class="sxs-lookup"><span data-stu-id="99129-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="99129-111">如果您關閉標記，將不會再自動為影像加標記。</span><span class="sxs-lookup"><span data-stu-id="99129-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="99129-112">將不會移除現有的標記。</span><span class="sxs-lookup"><span data-stu-id="99129-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="99129-113">設定影像標記</span><span class="sxs-lookup"><span data-stu-id="99129-113">Configure image tagging</span></span>

<span data-ttu-id="99129-114">您可以在 Microsoft 365 系統管理中心設定影像標記。</span><span class="sxs-lookup"><span data-stu-id="99129-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="99129-115">開啟或關閉影像標記</span><span class="sxs-lookup"><span data-stu-id="99129-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="99129-116">在 Microsoft 365 系統管理中心，按一下 [設定 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="99129-117">在 [組織知識 **]** 底下，按一下 [自動內容瞭解 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="99129-118">按一下 [管理 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-118">Click **Manage**.</span></span>

4. <span data-ttu-id="99129-119">在 [影像標記 **]** 索引標籤上，按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="99129-120">選擇允許 [基本標記 **]** 或將標記 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="99129-121">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="99129-121">Click **Save**.</span></span>

    ![影像標記控制項的螢幕擷取畫面](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="99129-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="99129-123">See also</span></span>

[<span data-ttu-id="99129-124">設定內容瞭解</span><span class="sxs-lookup"><span data-stu-id="99129-124">Set up content understanding</span></span>](set-up-content-understanding.md)