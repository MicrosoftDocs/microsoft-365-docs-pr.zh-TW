---
title: 開始使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 設定 Microsoft 365 資料外洩防護內部部署掃描器
ms.openlocfilehash: b21474f3a9e045bf353d62ef6c7c8d4174801a1b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623830"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="dcce3-103">開始使用資料外洩防護內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dcce3-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="dcce3-104">本文會逐步引導您完成 Microsoft 365 資料外洩防護內部部署掃描器的必要條件和設定。</span><span class="sxs-lookup"><span data-stu-id="dcce3-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dcce3-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="dcce3-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="dcce3-106">SKU/訂閱授權</span><span class="sxs-lookup"><span data-stu-id="dcce3-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="dcce3-107">開始使用 DLP 內部部署掃描器之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="dcce3-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="dcce3-108">若要參與預覽，設定 DLP 規則的系統管理員帳戶必須指派下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="dcce3-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="dcce3-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dcce3-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="dcce3-110">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="dcce3-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="dcce3-111">Microsoft 365 E5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="dcce3-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="dcce3-112">如需完整授權的詳情，請參閱：[Microsoft 365 安全性與合規性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="dcce3-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="dcce3-113">權限</span><span class="sxs-lookup"><span data-stu-id="dcce3-113">Permissions</span></span>


<span data-ttu-id="dcce3-114">可在 [活動總管](data-classification-activity-explorer.md) 中檢視來自 DLP 內部部署掃描器的資料。</span><span class="sxs-lookup"><span data-stu-id="dcce3-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="dcce3-115">有四個角色可以將權限授與活動總管，您用來存取資料的帳戶必須是其中任一的成員。</span><span class="sxs-lookup"><span data-stu-id="dcce3-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="dcce3-116">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="dcce3-116">Global administrator</span></span>
- <span data-ttu-id="dcce3-117">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="dcce3-117">Compliance administrator</span></span>
- <span data-ttu-id="dcce3-118">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="dcce3-118">Security administrator</span></span>
- <span data-ttu-id="dcce3-119">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="dcce3-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="dcce3-120">DLP 內部部署掃描器必要條件</span><span class="sxs-lookup"><span data-stu-id="dcce3-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="dcce3-p103">Azure 資訊保護 (AIP) 掃描器會執行 DLP 原則配對和原則強制執行。此掃描器會安裝為 AIP 用戶端的一部分，因此您的安裝必須符合 AIP、AIP 用戶端和 AIP 統一標籤掃描器的所有必要條件。</span><span class="sxs-lookup"><span data-stu-id="dcce3-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="dcce3-123">部署 AIP 用戶端和掃描器。</span><span class="sxs-lookup"><span data-stu-id="dcce3-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="dcce3-124">如需深入了解 [安裝 AIP 統一標籤用戶端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 和 []，請參閱 [設定和安裝 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner-configure-install)。</span><span class="sxs-lookup"><span data-stu-id="dcce3-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="dcce3-125">即使您的所有偵測規則都只以敏感資訊類型為基礎，租用戶中仍至少必須發佈一個標籤和原則。</span><span class="sxs-lookup"><span data-stu-id="dcce3-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="dcce3-126">部署 DLP 內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="dcce3-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="dcce3-127">請遵循 [ 安裝 AIP 統一標籤用戶端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="dcce3-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="dcce3-128">請遵循 [設定和安裝 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner-configure-install) 中的步驟以完成掃描器安裝。</span><span class="sxs-lookup"><span data-stu-id="dcce3-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="dcce3-129">網路探索工作設定是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="dcce3-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="dcce3-130">您可以略過它，並定義內容掃描工作要掃描的特定存放庫。</span><span class="sxs-lookup"><span data-stu-id="dcce3-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="dcce3-131">您必須建立內容掃描工作，並指定裝載著需由 DLP 引擎評估之檔案的存放庫。</span><span class="sxs-lookup"><span data-stu-id="dcce3-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="dcce3-132">在建立的內容掃描工作中啟用 DLP 規則，並將 **強制** 選項設定 為 **關閉**，但若您要直接進入 DLP 強制階段則例外。</span><span class="sxs-lookup"><span data-stu-id="dcce3-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="dcce3-p106">請驗證您的內容掃描工作已指派至正確的叢集。如果您仍未建立內容掃描工作，請建立新工作，並將它指派給包含執行公開預覽版本的掃描器節點的叢集。</span><span class="sxs-lookup"><span data-stu-id="dcce3-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="dcce3-135">連接至 [Azure 入口網站中的 Azure 資訊保護延伸模組](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) ，並將您的存放庫新增到將執行掃描的內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="dcce3-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="dcce3-136">執行下列其中一項操作以執行掃描：</span><span class="sxs-lookup"><span data-stu-id="dcce3-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="dcce3-137">設定掃描器排程</span><span class="sxs-lookup"><span data-stu-id="dcce3-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="dcce3-138">使用入口網站中的手動 **立即掃描** 選項</span><span class="sxs-lookup"><span data-stu-id="dcce3-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="dcce3-139">或執行 **Start-AIPScan** PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dcce3-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="dcce3-140">請記住，掃描器預設會執行存放庫的差異掃描，且除非檔案已變更或您初始化完整重新掃描，否則將會略過先前掃描週期中已掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="dcce3-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="dcce3-141">您可以使用 UI 中的 **重新掃描所有檔案** 選項，或執行 **Start-AIPScan-Reset** 來起始完整重新掃描。</span><span class="sxs-lookup"><span data-stu-id="dcce3-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="dcce3-142">在 Microsoft 365 合規性中心開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="dcce3-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="dcce3-143">選擇 **建立原則** ，然後建立測試 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="dcce3-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="dcce3-144">如果您需要協助建立原則。請參閱 [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)。</span><span class="sxs-lookup"><span data-stu-id="dcce3-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="dcce3-145">請務必在測試中執行，直到您熟悉這項功能。</span><span class="sxs-lookup"><span data-stu-id="dcce3-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="dcce3-146">針對您的原則使用這些參數：</span><span class="sxs-lookup"><span data-stu-id="dcce3-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="dcce3-147">如有必要，將 DLP 內部部署掃描器規則的範圍縮小到特定位置。</span><span class="sxs-lookup"><span data-stu-id="dcce3-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="dcce3-148">如果您將範圍 **位置** 設為 **所有**，掃描器所掃描的所有檔案都會受到 DLP 規則配對和強制執行。</span><span class="sxs-lookup"><span data-stu-id="dcce3-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="dcce3-149">指定位置時，您可以使用排除或包含清單。</span><span class="sxs-lookup"><span data-stu-id="dcce3-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="dcce3-150">在公開預覽期間，您無法同時設定這兩者。</span><span class="sxs-lookup"><span data-stu-id="dcce3-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="dcce3-151">您可以將規則定義為只與包含清單中所列的其中一個模式相符的路徑相關，或是所有檔案，但符合包含清單中所列模式的檔案除外。</span><span class="sxs-lookup"><span data-stu-id="dcce3-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="dcce3-152">不支援任何本機路徑。</span><span class="sxs-lookup"><span data-stu-id="dcce3-152">No local paths are supported.</span></span> <span data-ttu-id="dcce3-153">以下是一些有效路徑的範例：</span><span class="sxs-lookup"><span data-stu-id="dcce3-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="dcce3-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="dcce3-154">\\\server\share</span></span>
      - <span data-ttu-id="dcce3-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="dcce3-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="dcce3-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="dcce3-156">\*\\folder1</span></span>
      - <span data-ttu-id="dcce3-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="dcce3-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="dcce3-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="dcce3-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="dcce3-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="dcce3-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="dcce3-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="dcce3-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="dcce3-161">以下是一些不被接受的值範例：</span><span class="sxs-lookup"><span data-stu-id="dcce3-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="dcce3-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="dcce3-162">\*\\a</span></span>
      - <span data-ttu-id="dcce3-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="dcce3-163">Aaa</span></span>
      - <span data-ttu-id="dcce3-164">c:</span><span class="sxs-lookup"><span data-stu-id="dcce3-164">c:</span></span>\
      - <span data-ttu-id="dcce3-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="dcce3-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcce3-166">排除清單優先於包含清單。</span><span class="sxs-lookup"><span data-stu-id="dcce3-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="dcce3-167">在 DLP 警示管理儀表板中檢視DLP 內部部署掃描器警示</span><span class="sxs-lookup"><span data-stu-id="dcce3-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="dcce3-168">在 Microsoft 365 合規性中心開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies) 然後選取 **警示**。</span><span class="sxs-lookup"><span data-stu-id="dcce3-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="dcce3-169">請參閱[如何設定和檢視 DLP 原則的警示](dlp-configure-view-alerts-policies.md)中的程序，以檢視您端點 DLP 原則的警示。</span><span class="sxs-lookup"><span data-stu-id="dcce3-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="dcce3-170">在活動總管和稽核記錄中檢視 DLP 內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="dcce3-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="dcce3-171">內部部署掃描器要求啟用稽核。</span><span class="sxs-lookup"><span data-stu-id="dcce3-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="dcce3-172">在 Microsoft 365 中，稽核預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="dcce3-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="dcce3-173">在 Microsoft 365 合規性中心開啟您網域的 [資料分類頁面](https://compliance.microsoft.com/dataclassification?viewid=overview)，然後選取活動總管。</span><span class="sxs-lookup"><span data-stu-id="dcce3-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="dcce3-174">請參閱 [開始使用活動總管](data-classification-activity-explorer.md) 中的程序，以存取及篩選您內部部署掃描器位置的所有資料。</span><span class="sxs-lookup"><span data-stu-id="dcce3-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="dcce3-175">開啟 [合規性中心裡的稽核記錄](https://security.microsoft.com/auditlogsearch)。</span><span class="sxs-lookup"><span data-stu-id="dcce3-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="dcce3-176">在公開預覽期間，DLP 規則相符項目可在稽核記錄 UI 中取得，或可透過 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="dcce3-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="dcce3-177">後續步驟</span><span class="sxs-lookup"><span data-stu-id="dcce3-177">Next steps</span></span>
<span data-ttu-id="dcce3-178">現在您已為 DLP 內部部署位置部署了測試原則，且可以在活動總管中檢視活動資料，您已準備好開始建立可保護您敏感性項目之 DLP 原則的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="dcce3-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="dcce3-179">使用 DLP 內部部署 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dcce3-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="dcce3-180">請參閱</span><span class="sxs-lookup"><span data-stu-id="dcce3-180">See also</span></span>

- [<span data-ttu-id="dcce3-181">了解 DLP 內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dcce3-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="dcce3-182">使用 DLP 內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="dcce3-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="dcce3-183">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="dcce3-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="dcce3-184">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="dcce3-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dcce3-185">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="dcce3-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dcce3-186">Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="dcce3-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)