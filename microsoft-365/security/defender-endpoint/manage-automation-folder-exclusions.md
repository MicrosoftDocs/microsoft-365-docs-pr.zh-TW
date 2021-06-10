---
title: 管理自動化資料夾排除
description: 新增「自動化」資料夾排除，以控制從自動調查中排除的檔案。
keywords: 管理，自動化，排除，封鎖，乾淨，惡意
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185834"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="a9fda-104">管理自動化資料夾排除</span><span class="sxs-lookup"><span data-stu-id="a9fda-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a9fda-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a9fda-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9fda-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a9fda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9fda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9fda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a9fda-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a9fda-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9fda-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a9fda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="a9fda-110">自動化資料夾排除可讓您指定自動調查將略過的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a9fda-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="a9fda-111">您可以控制下列您想略過之資料夾的屬性：</span><span class="sxs-lookup"><span data-stu-id="a9fda-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="a9fda-112">資料夾</span><span class="sxs-lookup"><span data-stu-id="a9fda-112">Folders</span></span> 
- <span data-ttu-id="a9fda-113">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="a9fda-113">Extensions of the files</span></span>
- <span data-ttu-id="a9fda-114">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="a9fda-114">File names</span></span>


<span data-ttu-id="a9fda-115">**資料夾**</span><span class="sxs-lookup"><span data-stu-id="a9fda-115">**Folders**</span></span><br>
<span data-ttu-id="a9fda-116">您可以指定要略過的資料夾及其子資料夾。</span><span class="sxs-lookup"><span data-stu-id="a9fda-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="a9fda-117">此時，您可以使用萬用字元來排除尚未支援的目錄下的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9fda-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="a9fda-118">**延伸模組**</span><span class="sxs-lookup"><span data-stu-id="a9fda-118">**Extensions**</span></span><br>
<span data-ttu-id="a9fda-119">您可以指定要排除在特定目錄中的副檔名。</span><span class="sxs-lookup"><span data-stu-id="a9fda-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="a9fda-120">這種擴充功能可防止攻擊者使用排除的資料夾來隱藏利用漏洞。</span><span class="sxs-lookup"><span data-stu-id="a9fda-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="a9fda-121">副檔名明確定義要忽略的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9fda-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="a9fda-122">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="a9fda-122">**File names**</span></span><br>
<span data-ttu-id="a9fda-123">您可以指定要在特定目錄中排除的檔案名。</span><span class="sxs-lookup"><span data-stu-id="a9fda-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="a9fda-124">這些名稱是防止攻擊者使用排除的資料夾來隱藏利用漏洞的方式。</span><span class="sxs-lookup"><span data-stu-id="a9fda-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="a9fda-125">名稱明確定義要忽略的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9fda-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="a9fda-126">新增自動化資料夾排除</span><span class="sxs-lookup"><span data-stu-id="a9fda-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="a9fda-127">在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="a9fda-128">按一下 [ **新增資料夾排除**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="a9fda-129">輸入資料夾詳細資料：</span><span class="sxs-lookup"><span data-stu-id="a9fda-129">Enter the folder details:</span></span>

    - <span data-ttu-id="a9fda-130">資料夾</span><span class="sxs-lookup"><span data-stu-id="a9fda-130">Folder</span></span>
    - <span data-ttu-id="a9fda-131">延伸模組</span><span class="sxs-lookup"><span data-stu-id="a9fda-131">Extensions</span></span>
    - <span data-ttu-id="a9fda-132">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="a9fda-132">File names</span></span>
    - <span data-ttu-id="a9fda-133">描述</span><span class="sxs-lookup"><span data-stu-id="a9fda-133">Description</span></span>
    

4. <span data-ttu-id="a9fda-134">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a9fda-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="a9fda-135">收集或檢查排除的檔案的即時回應命令會失敗，錯誤如下：「File 已排除」。</span><span class="sxs-lookup"><span data-stu-id="a9fda-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="a9fda-136">此外，自動調查會忽略排除的專案。</span><span class="sxs-lookup"><span data-stu-id="a9fda-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="a9fda-137">編輯自動化資料夾排除</span><span class="sxs-lookup"><span data-stu-id="a9fda-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="a9fda-138">在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="a9fda-139">在資料夾排除上按一下 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="a9fda-140">更新規則的詳細資料，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="a9fda-141">移除自動化資料夾排除</span><span class="sxs-lookup"><span data-stu-id="a9fda-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="a9fda-142">在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="a9fda-143">按一下 [ **移除排除**]。</span><span class="sxs-lookup"><span data-stu-id="a9fda-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="a9fda-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="a9fda-144">Related topics</span></span>
- [<span data-ttu-id="a9fda-145">管理自動化的允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="a9fda-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="a9fda-146">管理自動化檔案上傳</span><span class="sxs-lookup"><span data-stu-id="a9fda-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
