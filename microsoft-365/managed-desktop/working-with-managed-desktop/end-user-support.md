---
title: 取得 Microsoft 受管理的電腦的使用者支援
description: 使用者如何取得服務和裝置的協助
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362603"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="7a7a8-104">為使用者取得協助</span><span class="sxs-lookup"><span data-stu-id="7a7a8-104">Getting help for users</span></span>

<span data-ttu-id="7a7a8-105">如果您已到達 [工作流程](../service-description/user-support.md) 中需要要求提升裝置存取或升級至 Microsoft 的點，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="7a7a8-106">這些支援選項不適用於測試群組中的裝置。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="7a7a8-107">提升要求</span><span class="sxs-lookup"><span data-stu-id="7a7a8-107">Elevation requests</span></span>

<span data-ttu-id="7a7a8-108">在您要求更高的裝置存取權之前，最好先檢查哪些動作最適合。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="7a7a8-109">**一般動作** 為此程式的目的，在疑難排解 Microsoft 受管理的電腦裝置的問題時，會進行定期執行。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7a7a8-110">範例包含：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-110">Examples include:</span></span>
    - <span data-ttu-id="7a7a8-111">提升內建的系統疑難排解程式、命令提示字元，或 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a7a8-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="7a7a8-112">疑難排解商務營運應用程式</span><span class="sxs-lookup"><span data-stu-id="7a7a8-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="7a7a8-113">使用變通辦法修正應該在設計 (運作的專案，例如 BitLocker 啟用或系統時間未更新) </span><span class="sxs-lookup"><span data-stu-id="7a7a8-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="7a7a8-114">提升裝置管理員執行的工作如更新驅動程式、卸載裝置或掃描新的變更</span><span class="sxs-lookup"><span data-stu-id="7a7a8-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="7a7a8-115">**不建議採取的動作** 包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="7a7a8-116">安裝軟體或瀏覽器</span><span class="sxs-lookup"><span data-stu-id="7a7a8-116">Installing software or browsers</span></span>
    - <span data-ttu-id="7a7a8-117">在 Windows 設定外安裝驅動程式（包括週邊設備的驅動程式）</span><span class="sxs-lookup"><span data-stu-id="7a7a8-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="7a7a8-118">安裝 .msi 或 .exe 檔</span><span class="sxs-lookup"><span data-stu-id="7a7a8-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="7a7a8-119">安裝 Windows 功能</span><span class="sxs-lookup"><span data-stu-id="7a7a8-119">Installing Windows features</span></span>

- <span data-ttu-id="7a7a8-120">**不支援的動作** 包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="7a7a8-121">安裝與 Microsoft 受管理的電腦安全性或管理功能或作業相衝突的軟體或功能</span><span class="sxs-lookup"><span data-stu-id="7a7a8-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="7a7a8-122">停用 Microsoft 受管理的電腦所需的 Windows 功能，例如 BitLocker</span><span class="sxs-lookup"><span data-stu-id="7a7a8-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="7a7a8-123">修改組織所管理的設定</span><span class="sxs-lookup"><span data-stu-id="7a7a8-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="7a7a8-124">要求提升</span><span class="sxs-lookup"><span data-stu-id="7a7a8-124">To request elevation</span></span>

1. <span data-ttu-id="7a7a8-125">移至入口網站 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，並以您的 Azure Active Directory 認證登入。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="7a7a8-126">選取 [ **新增提升要求**]。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="7a7a8-127">提供這些詳細資料：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-127">Provide these details:</span></span>
    - <span data-ttu-id="7a7a8-128">支援來自您自己支援票證系統的 **票證識別碼**。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="7a7a8-129">**裝置名稱**：輸入裝置序號，然後從功能表中選取裝置。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="7a7a8-130">**類別**：選取最符合您問題的類別。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="7a7a8-131">如果 [沒有] 選項似乎是關閉的，請選取 [ **其他** ]，並在 [動作] 欄位的 **標題** 和 **方案** 中提供其他資訊。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="7a7a8-132">您最好盡可能選取類別。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="7a7a8-133">**子類別**：選取最符合問題的一種。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="7a7a8-134">如果沒有任何選項似乎是關閉的，請選取 [ **其他** ]，並在 **標題** 中提供簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="7a7a8-135">在 [ **行動計畫**] 中，提供您計畫在授與後採取的疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="7a7a8-136">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="7a7a8-137">上報要求</span><span class="sxs-lookup"><span data-stu-id="7a7a8-137">Escalation requests</span></span>


<span data-ttu-id="7a7a8-138">如果您需要將問題 [提升](../service-description/user-support.md#escalation-portal) 至 Microsoft，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="7a7a8-139">移至入口網站 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，並以您的 Azure Active Directory 認證登入。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="7a7a8-140">選取 [ **呈報要求**]，然後選取 [ **新增呈報要求**]。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="7a7a8-141">提供這些詳細資料：</span><span class="sxs-lookup"><span data-stu-id="7a7a8-141">Provide these details:</span></span>
    - <span data-ttu-id="7a7a8-142">**類別**：選取最符合您問題的類別。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="7a7a8-143">**Title**：提供非常簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="7a7a8-144">**描述**：新增可協助我們小組瞭解問題的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="7a7a8-145">如果您需要附加檔案，您可以在提交要求後回到要求。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="7a7a8-146">**主要連絡人資訊**：提供如何聯繫主要人員，以與我們的小組合作的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="7a7a8-147">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-147">Select **Submit**.</span></span>
5. <span data-ttu-id="7a7a8-148">重新訪問相同入口網站中的票證，以與我們的小組互動。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="7a7a8-149">只有嚴重的 C 問題可透過此路徑上報。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="7a7a8-150">如需其他問題，請與您的 IT 系統管理員聯繫以透過管理入口網站來歸檔要求。</span><span class="sxs-lookup"><span data-stu-id="7a7a8-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>