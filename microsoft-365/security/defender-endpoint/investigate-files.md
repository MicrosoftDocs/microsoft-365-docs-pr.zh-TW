---
title: 調查 Microsoft Defender 的端點檔案
description: 使用調查選項可取得與警示、行為或事件相關聯之檔案的詳細資料。
keywords: 調查、調查、檔、惡意活動、攻擊動機、深入分析、深入分析報告
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058547"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="fb324-104">調查與 Microsoft Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="fb324-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fb324-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fb324-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb324-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fb324-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="fb324-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb324-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fb324-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fb324-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fb324-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fb324-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="fb324-110">調查與特定警示、行為或事件相關聯之檔案的詳細資料，以協助判斷該檔案是否展示惡意活動、識別攻擊動機，以及瞭解遭到破壞的潛在範圍。</span><span class="sxs-lookup"><span data-stu-id="fb324-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="fb324-111">有許多方式可以存取特定檔案的詳細設定檔頁面面。</span><span class="sxs-lookup"><span data-stu-id="fb324-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="fb324-112">例如，您可以使用「搜尋」功能，按一下 **警示處理樹狀目錄**、 **事件曲線圖**、 **專案時程表** 中的連結，或選取 **裝置時程表** 中所列的事件。</span><span class="sxs-lookup"><span data-stu-id="fb324-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="fb324-113">在 [詳細設定檔] 頁面上，您可以透過 [切換新的檔案] **頁面**，在新的和舊的頁面配置之間切換。</span><span class="sxs-lookup"><span data-stu-id="fb324-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="fb324-114">本文的其餘部分將說明較新的頁面配置。</span><span class="sxs-lookup"><span data-stu-id="fb324-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="fb324-115">您可以從下列 [檔案] 視圖中的區段取得資訊：</span><span class="sxs-lookup"><span data-stu-id="fb324-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="fb324-116">檔案詳細資料、惡意程式碼偵測、檔傳播</span><span class="sxs-lookup"><span data-stu-id="fb324-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="fb324-117">深入分析</span><span class="sxs-lookup"><span data-stu-id="fb324-117">Deep analysis</span></span>
- <span data-ttu-id="fb324-118">警示</span><span class="sxs-lookup"><span data-stu-id="fb324-118">Alerts</span></span>
- <span data-ttu-id="fb324-119">組織中的觀測</span><span class="sxs-lookup"><span data-stu-id="fb324-119">Observed in organization</span></span>
- <span data-ttu-id="fb324-120">深入分析</span><span class="sxs-lookup"><span data-stu-id="fb324-120">Deep analysis</span></span>
- <span data-ttu-id="fb324-121">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="fb324-121">File names</span></span>

<span data-ttu-id="fb324-122">您也可以從這個頁面對檔案採取動作。</span><span class="sxs-lookup"><span data-stu-id="fb324-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="fb324-123">檔動作</span><span class="sxs-lookup"><span data-stu-id="fb324-123">File actions</span></span>

<span data-ttu-id="fb324-124">在 [設定檔] 頁面上，沿著檔資訊卡片上方。</span><span class="sxs-lookup"><span data-stu-id="fb324-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="fb324-125">您可以在這裡執行的動作包括：</span><span class="sxs-lookup"><span data-stu-id="fb324-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="fb324-126">停止和隔離</span><span class="sxs-lookup"><span data-stu-id="fb324-126">Stop and quarantine</span></span>
- <span data-ttu-id="fb324-127">新增/編輯指示器</span><span class="sxs-lookup"><span data-stu-id="fb324-127">Add/edit indicator</span></span>
- <span data-ttu-id="fb324-128">下載檔案</span><span class="sxs-lookup"><span data-stu-id="fb324-128">Download file</span></span>
- <span data-ttu-id="fb324-129">諮詢威脅專家</span><span class="sxs-lookup"><span data-stu-id="fb324-129">Consult a threat expert</span></span>
- <span data-ttu-id="fb324-130">控制中心</span><span class="sxs-lookup"><span data-stu-id="fb324-130">Action center</span></span>

<span data-ttu-id="fb324-131">如需這些動作的詳細資訊，請參閱 [在檔案上採取回應動作](respond-file-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="fb324-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="fb324-132">檔案詳細資料、惡意程式碼偵測和檔傳播</span><span class="sxs-lookup"><span data-stu-id="fb324-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="fb324-133">檔案詳細資料、事件、惡意程式碼偵測和檔案流行卡會顯示檔案的各種屬性。</span><span class="sxs-lookup"><span data-stu-id="fb324-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="fb324-134">您會看到詳細資料，例如檔案的 MD5、病毒的偵測比率，以及 Microsoft Defender AV 偵測（若有的話），以及檔案的流行情況。</span><span class="sxs-lookup"><span data-stu-id="fb324-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="fb324-135">檔傳播卡片顯示在組織中的裝置及全球範圍內，看到該檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="fb324-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="fb324-136">不同的使用者可能會在檔傳播卡片的 [ *組織中的裝置* ] 區段中看到不同的值。</span><span class="sxs-lookup"><span data-stu-id="fb324-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="fb324-137">這是因為名片會根據使用者所擁有的 RBAC 範圍來顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="fb324-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="fb324-138">也就是說，如果使用者已被授與特定裝置集，只會看到這些裝置上的檔組織傳播。</span><span class="sxs-lookup"><span data-stu-id="fb324-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![檔資訊影像](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="fb324-140">警示</span><span class="sxs-lookup"><span data-stu-id="fb324-140">Alerts</span></span>

<span data-ttu-id="fb324-141">[ **警示** ] 索引標籤提供與檔案相關聯的警示清單。</span><span class="sxs-lookup"><span data-stu-id="fb324-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="fb324-142">此清單涵蓋許多與警示佇列相同的資訊，但裝置群組（如果有的話）屬於，則受影響裝置除外。</span><span class="sxs-lookup"><span data-stu-id="fb324-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="fb324-143">您可以從欄標題上方的工具列中，選取 [ **自訂資料行** ]，以選擇要顯示的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="fb324-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![與檔案區段相關的警示圖像](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="fb324-145">組織中的觀測</span><span class="sxs-lookup"><span data-stu-id="fb324-145">Observed in organization</span></span>

<span data-ttu-id="fb324-146">[ **在組織中看到** 的] 索引標籤可讓您指定日期範圍，以查看哪些裝置已對檔案進行觀測。</span><span class="sxs-lookup"><span data-stu-id="fb324-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="fb324-147">此索引標籤會顯示100裝置的數目上限。</span><span class="sxs-lookup"><span data-stu-id="fb324-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="fb324-148">若要查看檔案中的 _所有_ 裝置，請從索引標籤欄上方的 [動作] 功能表中，選取 [ **匯出** ]，將索引標籤匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="fb324-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![具有檔案的最近觀測裝置的影像](images/atp-observed-machines.png)

<span data-ttu-id="fb324-150">使用滑塊或範圍選取器，快速指定您要檢查與檔案相關之事件的時段。</span><span class="sxs-lookup"><span data-stu-id="fb324-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="fb324-151">您可以指定小至一天的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="fb324-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="fb324-152">這可讓您在該時間只看到與該 IP 位址通訊的檔案，以大幅減少不必要的滾動和搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb324-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="fb324-153">深入分析</span><span class="sxs-lookup"><span data-stu-id="fb324-153">Deep analysis</span></span>

<span data-ttu-id="fb324-154">[ **深入分析** ] 索引標籤可讓您 [提交檔案進行深入分析](respond-file-alerts.md#deep-analysis)，以找出檔案行為的詳細資訊，以及組織內所用的影響。</span><span class="sxs-lookup"><span data-stu-id="fb324-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="fb324-155">在您提交檔案之後，[詳細分析] 報告會在此索引標籤中出現一次可用結果。</span><span class="sxs-lookup"><span data-stu-id="fb324-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="fb324-156">如果深入分析沒有找到任何專案，則報告將會是空的，而且結果空間也會保留空白。</span><span class="sxs-lookup"><span data-stu-id="fb324-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![深入分析索引標籤的影像](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="fb324-158">檔案名稱</span><span class="sxs-lookup"><span data-stu-id="fb324-158">File names</span></span>

<span data-ttu-id="fb324-159">[檔案 **名稱** ] 索引標籤會列出已在組織中觀測出的所有檔案名。</span><span class="sxs-lookup"><span data-stu-id="fb324-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![[檔案名] 索引標籤的影像](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="fb324-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="fb324-161">Related topics</span></span>

- [<span data-ttu-id="fb324-162">查看和組織 Microsoft Defender for Endpoint 佇列</span><span class="sxs-lookup"><span data-stu-id="fb324-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="fb324-163">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="fb324-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="fb324-164">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="fb324-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="fb324-165">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="fb324-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="fb324-166">調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fb324-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="fb324-167">調查與 Microsoft Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="fb324-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="fb324-168">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fb324-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="fb324-169">對檔案採取回應動作</span><span class="sxs-lookup"><span data-stu-id="fb324-169">Take response actions on a file</span></span>](respond-file-alerts.md)
