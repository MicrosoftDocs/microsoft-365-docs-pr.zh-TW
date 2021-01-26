---
title: SharePoint Syntex 中的影像標記
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 SharePoint Syntex 中的影像標記
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975862"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="2ff8c-103">SharePoint Syntex 中的影像標記</span><span class="sxs-lookup"><span data-stu-id="2ff8c-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="2ff8c-104">(即將推出)</span><span class="sxs-lookup"><span data-stu-id="2ff8c-104">(Coming soon)</span></span>

<span data-ttu-id="2ff8c-105">透過 SharePoint Syntex 的影像標籤，使用者可以搜尋影像標籤找出影像，並根據影像標籤建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="2ff8c-106">預設會對 SharePoint 和 OneDrive 開啟基本的影像標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="2ff8c-107">上傳到兩個位置之一的影像會經過自動掃描，並從 37 個基本標記的清單套用適用的標記 (如果可用的話)。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="2ff8c-108">使用者可以搜尋影像上的標記，透過搜尋來尋找影像。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="2ff8c-109">當使用者上傳影像時，標記程序會自動執行。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="2ff8c-110">如果影像已經過編輯，標記程序會再次執行以更新標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="2ff8c-111">擁有影像權限的使用者可以在檔案資訊面板或搜尋結果頁面中查看及編輯標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="2ff8c-112">一旦使用者編輯影像的標記，系統就不再會於該影像上執行自動標記，即使該影像已經編輯過。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="2ff8c-113">如果您關閉標記，將不會再自動為影像加標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="2ff8c-114">將不會移除現有的標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff8c-115">系統產生的標記可能會隨著影像或標記技術的更新而變更。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="2ff8c-116">設定影像標記</span><span class="sxs-lookup"><span data-stu-id="2ff8c-116">Configure image tagging</span></span>

<span data-ttu-id="2ff8c-117">在您[設定 SharePoint Syntex ](set-up-content-understanding.md)之後，您可以在 Microsoft 365 系統管理中心設定影像標記。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="2ff8c-118">開啟或關閉影像標記</span><span class="sxs-lookup"><span data-stu-id="2ff8c-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="2ff8c-119">在 Microsoft 365 系統管理中心，按一下 [設定 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="2ff8c-120">在 [組織知識 **]** 底下，按一下 [自動內容瞭解 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="2ff8c-121">按一下 [管理 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-121">Click **Manage**.</span></span>

4. <span data-ttu-id="2ff8c-122">在 [影像標記 **]** 索引標籤上，按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="2ff8c-123">選擇允許 [基本標記 **]** 或將標記 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="2ff8c-124">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="2ff8c-124">Click **Save**.</span></span>

    ![影像標記控制項的螢幕擷取畫面](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
