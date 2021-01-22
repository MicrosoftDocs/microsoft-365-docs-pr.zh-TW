---
title: 在 Microsoft 365 Defender 中對進一步搜尋查詢結果採取行動
description: 在進位搜尋查詢結果中快速處理威脅和受影響的資產
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、採取行動
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932175"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="4bfad-104">進一步搜尋查詢結果採取行動</span><span class="sxs-lookup"><span data-stu-id="4bfad-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4bfad-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="4bfad-105">**Applies to:**</span></span>
- <span data-ttu-id="4bfad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bfad-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4bfad-107">您可以使用強大且完整的動作選項，快速包含威脅或位址在進[](advanced-hunting-overview.md)一步搜尋時發現被入侵的資產。</span><span class="sxs-lookup"><span data-stu-id="4bfad-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="4bfad-108">使用這些選項，您可以：</span><span class="sxs-lookup"><span data-stu-id="4bfad-108">With these options, you can:</span></span>

- <span data-ttu-id="4bfad-109">在裝置上採取各種動作</span><span class="sxs-lookup"><span data-stu-id="4bfad-109">Take various actions on devices</span></span>
- <span data-ttu-id="4bfad-110">隔離檔案</span><span class="sxs-lookup"><span data-stu-id="4bfad-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="4bfad-111">必要的權限</span><span class="sxs-lookup"><span data-stu-id="4bfad-111">Required permissions</span></span>
<span data-ttu-id="4bfad-112">為了能夠透過進一步搜尋採取行動，您需要 Microsoft Defender for Endpoint 中具有許可權的角色，以在裝置上提交 [補救動作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="4bfad-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="4bfad-113">如果您無法採取行動，請聯絡全域系統管理員以取得下列許可權：</span><span class="sxs-lookup"><span data-stu-id="4bfad-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="4bfad-114">*威脅和>管理的行動補救動作 - 補救處理*</span><span class="sxs-lookup"><span data-stu-id="4bfad-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="4bfad-115">在裝置上採取各種動作</span><span class="sxs-lookup"><span data-stu-id="4bfad-115">Take various actions on devices</span></span>
<span data-ttu-id="4bfad-116">您可以在查詢結果中欄所識別的裝置 `DeviceId` 上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4bfad-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="4bfad-117">隔離受影響的裝置以包含感染，或防止攻擊之後移動</span><span class="sxs-lookup"><span data-stu-id="4bfad-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="4bfad-118">收集調查套件以取得更多的資訊</span><span class="sxs-lookup"><span data-stu-id="4bfad-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="4bfad-119">使用最新的安全性智慧更新執行防毒軟體掃描來尋找和移除威脅</span><span class="sxs-lookup"><span data-stu-id="4bfad-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="4bfad-120">啟動自動化調查以檢查並修復裝置上的威脅，以及可能的其他受影響的裝置</span><span class="sxs-lookup"><span data-stu-id="4bfad-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="4bfad-121">將應用程式執行限制為只有 Microsoft 簽署的可執行檔，透過惡意程式碼或其他不受信任的可執行檔防止後續的威脅活動</span><span class="sxs-lookup"><span data-stu-id="4bfad-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="4bfad-122">若要進一步瞭解如何透過 Microsoft Defender for Endpoint 執行這些回應動作，請閱讀 [有關裝置上回應動作的資訊](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="4bfad-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="4bfad-123">隔離檔案</span><span class="sxs-lookup"><span data-stu-id="4bfad-123">Quarantine files</span></span>
<span data-ttu-id="4bfad-124">您可以對檔案 *部署* 隔離動作，讓檔案在遇到時自動隔離。</span><span class="sxs-lookup"><span data-stu-id="4bfad-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="4bfad-125">選取此動作時，您可以選擇下列兩欄以識別要隔離查詢結果中的哪些檔案：</span><span class="sxs-lookup"><span data-stu-id="4bfad-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="4bfad-126">`SHA1` — 在大部分進一步搜尋資料表中，這是受到錄製動作影響之檔案的 SHA-1。</span><span class="sxs-lookup"><span data-stu-id="4bfad-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="4bfad-127">例如，如果複製了檔案，這會是複製的檔案。</span><span class="sxs-lookup"><span data-stu-id="4bfad-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="4bfad-128">`InitiatingProcessSHA1` — 在大部分進步搜尋資料表中，這個檔案負責啟動錄製的動作。</span><span class="sxs-lookup"><span data-stu-id="4bfad-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="4bfad-129">例如，如果啟動副程式，則此為父程式。</span><span class="sxs-lookup"><span data-stu-id="4bfad-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="4bfad-130">`SHA256` — 這是資料行所識別之檔案的 SHA-256 相等 `SHA1` 值。</span><span class="sxs-lookup"><span data-stu-id="4bfad-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="4bfad-131">`InitiatingProcessSHA256` — 這是資料行所識別之檔案的 SHA-256 相等 `InitiatingProcessSHA1` 值。</span><span class="sxs-lookup"><span data-stu-id="4bfad-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="4bfad-132">若要深入瞭解如何執行隔離動作及如何還原檔案，請閱讀[有關檔案的回應動作。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="4bfad-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="4bfad-133">若要找出檔案並隔離這些檔案，查詢結果也應包含值 `DeviceId` 做為裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="4bfad-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="4bfad-134">採取行動</span><span class="sxs-lookup"><span data-stu-id="4bfad-134">Take action</span></span>
<span data-ttu-id="4bfad-135">若要執行任何描述的動作，請在查詢結果中選取一或多則記錄，然後選取執行 **動作**。</span><span class="sxs-lookup"><span data-stu-id="4bfad-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="4bfad-136">精靈會引導您完成選取並提交您偏好的動作。</span><span class="sxs-lookup"><span data-stu-id="4bfad-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![選取的記錄影像，以及用於檢查記錄的面板](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="4bfad-138">已執行審查動作</span><span class="sxs-lookup"><span data-stu-id="4bfad-138">Review actions taken</span></span>
<span data-ttu-id="4bfad-139">每個動作會個別記錄在控制中心的控制中心 [](mtp-action-center.md)的歷程記錄  >  \*\*\*\* [ (security.microsoft.com/action-center/history) 。](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="4bfad-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="4bfad-140">請前往控制中心，檢查每個動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="4bfad-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="4bfad-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="4bfad-141">Related topics</span></span>
- [<span data-ttu-id="4bfad-142">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="4bfad-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4bfad-143">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="4bfad-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4bfad-144">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="4bfad-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4bfad-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="4bfad-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4bfad-146">控制中心概觀</span><span class="sxs-lookup"><span data-stu-id="4bfad-146">Action center overview</span></span>](mtp-action-center.md)
