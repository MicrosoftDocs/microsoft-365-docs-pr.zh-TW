---
title: 在 Microsoft 365 Defender 中對高級搜尋查詢結果採取動作
description: 在您的高級搜尋查詢結果中快速處理威脅與受影響的資產
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 Defender、Microsoft 365、m365、搜尋、查詢、遙測、採取動作
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952605"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="b0f51-104">對高級搜尋查詢結果採取動作</span><span class="sxs-lookup"><span data-stu-id="b0f51-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0f51-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b0f51-105">**Applies to:**</span></span>
- <span data-ttu-id="b0f51-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f51-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b0f51-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0f51-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b0f51-108">您可以使用強大且全面的動作選項，快速包含威脅或使用您在 [高級搜尋](advanced-hunting-overview.md) 中所發現的受損資產。</span><span class="sxs-lookup"><span data-stu-id="b0f51-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="b0f51-109">使用這些選項，您可以：</span><span class="sxs-lookup"><span data-stu-id="b0f51-109">With these options, you can:</span></span>

- <span data-ttu-id="b0f51-110">在裝置上執行各種動作</span><span class="sxs-lookup"><span data-stu-id="b0f51-110">Take various actions on devices</span></span>
- <span data-ttu-id="b0f51-111">隔離檔</span><span class="sxs-lookup"><span data-stu-id="b0f51-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b0f51-112">必要權限</span><span class="sxs-lookup"><span data-stu-id="b0f51-112">Required permissions</span></span>
<span data-ttu-id="b0f51-113">若要能夠透過「高級搜尋」採取行動，您必須在 Microsoft Defender for Endpoint 中有一個角色，具有 [在裝置上提交修正動作的許可權](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="b0f51-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="b0f51-114">如果您無法採取行動，請洽詢全域管理員以取得下列許可權：</span><span class="sxs-lookup"><span data-stu-id="b0f51-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="b0f51-115">*> 威脅及弱點管理修正處理的使用中修復動作*</span><span class="sxs-lookup"><span data-stu-id="b0f51-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="b0f51-116">在裝置上執行各種動作</span><span class="sxs-lookup"><span data-stu-id="b0f51-116">Take various actions on devices</span></span>
<span data-ttu-id="b0f51-117">您可以在查詢結果中對欄所識別的裝置採取下列動作 `DeviceId` ：</span><span class="sxs-lookup"><span data-stu-id="b0f51-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="b0f51-118">隔離受影響的裝置以包含感染或防止攻擊移動橫向</span><span class="sxs-lookup"><span data-stu-id="b0f51-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="b0f51-119">收集調查套件以取得更多鑒證資訊</span><span class="sxs-lookup"><span data-stu-id="b0f51-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="b0f51-120">執行防病毒掃描，以利用最新的安全性情報更新來尋找並移除威脅</span><span class="sxs-lookup"><span data-stu-id="b0f51-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="b0f51-121">啟動自動調查以檢查和修正裝置上的威脅，以及可能受影響的裝置</span><span class="sxs-lookup"><span data-stu-id="b0f51-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="b0f51-122">將應用程式執行限制為僅限 Microsoft 簽署的可執行檔，以透過惡意程式碼或其他不可信的可執行檔進行後續的威脅</span><span class="sxs-lookup"><span data-stu-id="b0f51-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="b0f51-123">若要深入瞭解如何透過 Microsoft Defender for Endpoint 執行這些回應動作，請 [閱讀裝置上的回應動作](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="b0f51-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="b0f51-124">隔離檔</span><span class="sxs-lookup"><span data-stu-id="b0f51-124">Quarantine files</span></span>
<span data-ttu-id="b0f51-125">您可以在檔案上部署 *隔離* 動作，使其在遇到時自動隔離。</span><span class="sxs-lookup"><span data-stu-id="b0f51-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="b0f51-126">選取此動作時，您可以選擇下列各欄，以識別要隔離的查詢結果中的檔案：</span><span class="sxs-lookup"><span data-stu-id="b0f51-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="b0f51-127">`SHA1` —在大多數高級搜尋表格中，這是受錄製動作所影響的檔案 SHA-1。</span><span class="sxs-lookup"><span data-stu-id="b0f51-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="b0f51-128">例如，如果複製檔案，這會是複製的檔案。</span><span class="sxs-lookup"><span data-stu-id="b0f51-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="b0f51-129">`InitiatingProcessSHA1` —在大多數高級搜尋表格中，這是負責初始化錄製的動作的檔案。</span><span class="sxs-lookup"><span data-stu-id="b0f51-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="b0f51-130">例如，如果子流程已啟動，這會是父進程。</span><span class="sxs-lookup"><span data-stu-id="b0f51-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="b0f51-131">`SHA256` -這是欄所識別之檔案的 SHA-256 對等專案 `SHA1` 。</span><span class="sxs-lookup"><span data-stu-id="b0f51-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="b0f51-132">`InitiatingProcessSHA256` -這是欄所識別之檔案的 SHA-256 對等專案 `InitiatingProcessSHA1` 。</span><span class="sxs-lookup"><span data-stu-id="b0f51-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="b0f51-133">若要深入瞭解如何採取隔離動作和還原檔案，請 [參閱檔案的回應動作](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。</span><span class="sxs-lookup"><span data-stu-id="b0f51-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="b0f51-134">若要尋找並隔離檔案，查詢結果也應包含 `DeviceId` 設備識別碼的值。</span><span class="sxs-lookup"><span data-stu-id="b0f51-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="b0f51-135">採取行動</span><span class="sxs-lookup"><span data-stu-id="b0f51-135">Take action</span></span>
<span data-ttu-id="b0f51-136">若要採取任何說明的動作，請在查詢結果中選取一或多筆記錄，然後選取 [ **採取動作**]。</span><span class="sxs-lookup"><span data-stu-id="b0f51-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="b0f51-137">嚮導會引導您完成選取及提交您偏好動作的程式。</span><span class="sxs-lookup"><span data-stu-id="b0f51-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![具有檢查記錄之面板之選取記錄的影像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="b0f51-139">審閱採取的動作</span><span class="sxs-lookup"><span data-stu-id="b0f51-139">Review actions taken</span></span>
<span data-ttu-id="b0f51-140">每個動作會個別記錄在「**動作中心**」的「動作中心」下的「動作 [中心](m365d-action-center.md)」  >   ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)) 。</span><span class="sxs-lookup"><span data-stu-id="b0f51-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="b0f51-141">移至 [行動中心]，檢查每個動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="b0f51-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="b0f51-142">本文中的部分表格可能無法在 Microsoft Defender for Endpoint 中使用。</span><span class="sxs-lookup"><span data-stu-id="b0f51-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b0f51-143">使用更多資料來源[開啟 Microsoft 365 Defender](m365d-enable.md)以搜尋威脅。</span><span class="sxs-lookup"><span data-stu-id="b0f51-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="b0f51-144">您可以遵循[從 microsoft defender for endpoint 遷移高級搜尋查詢](advanced-hunting-migrate-from-mde.md)中的步驟，將您的高級搜尋工作流程從 microsoft defender for endpoint 移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="b0f51-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0f51-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="b0f51-145">Related topics</span></span>
- [<span data-ttu-id="b0f51-146">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b0f51-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0f51-147">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="b0f51-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0f51-148">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="b0f51-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b0f51-149">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b0f51-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b0f51-150">行動中心概述</span><span class="sxs-lookup"><span data-stu-id="b0f51-150">Action center overview</span></span>](m365d-action-center.md)
