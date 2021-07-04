---
title: 使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
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
description: 了解如何使用 Microsoft 365 資料外洩防護內部部署掃描器安心掃描資料，並針對內部部署檔案共用和內部部署 SharePoint 資料夾和文件庫執行保護動作。
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289172"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="8bac1-103">使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="8bac1-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="8bac1-104">為協助您熟悉 DLP 內部部署功能及其在 DLP 原則中的呈現方式，我們為您整理了一些可遵循的案例。</span><span class="sxs-lookup"><span data-stu-id="8bac1-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bac1-105">這些 DLP 內部部署案例非建立和調整 DLP 原則的正式程式。</span><span class="sxs-lookup"><span data-stu-id="8bac1-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="8bac1-106">當您需要在一般情況下使用 DLP 原則時，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="8bac1-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>
> - [<span data-ttu-id="8bac1-107">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="8bac1-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
> - [<span data-ttu-id="8bac1-108">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="8bac1-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
> - [<span data-ttu-id="8bac1-109">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="8bac1-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
> - [<span data-ttu-id="8bac1-110">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="8bac1-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="8bac1-111">案例：探索符合 DLP 規則的檔案</span><span class="sxs-lookup"><span data-stu-id="8bac1-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="8bac1-112">來自 DLP 內部部署掃描器的資料於數個區域出現</span><span class="sxs-lookup"><span data-stu-id="8bac1-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="8bac1-113">活動總管</span><span class="sxs-lookup"><span data-stu-id="8bac1-113">Activity explorer</span></span>

 <span data-ttu-id="8bac1-114">適用於內部部署的 Microsoft DLP 會偵測 DLP 規則相符項目，並將其回報給 [活動總管](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)。</span><span class="sxs-lookup"><span data-stu-id="8bac1-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span>

#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="8bac1-115">Microsoft 365 稽核記錄</span><span class="sxs-lookup"><span data-stu-id="8bac1-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="8bac1-116">在公開預覽期間，DLP 規則相符項目可在稽核記錄 UI 中取得，請參閱 [在合規性中心內搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md) 或透過 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell 存取。</span><span class="sxs-lookup"><span data-stu-id="8bac1-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="8bac1-117">AIP</span><span class="sxs-lookup"><span data-stu-id="8bac1-117">AIP</span></span>

<span data-ttu-id="8bac1-118">探索資料以 csv 格式的本機報表提供，儲存位置為：</span><span class="sxs-lookup"><span data-stu-id="8bac1-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="8bac1-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv 報表**。</span><span class="sxs-lookup"><span data-stu-id="8bac1-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="8bac1-120">請尋找下列欄：</span><span class="sxs-lookup"><span data-stu-id="8bac1-120">Look for the following columns:</span></span>

- <span data-ttu-id="8bac1-121">DLP 模式</span><span class="sxs-lookup"><span data-stu-id="8bac1-121">DLP Mode</span></span>
- <span data-ttu-id="8bac1-122">DLP 狀態</span><span class="sxs-lookup"><span data-stu-id="8bac1-122">DLP Status</span></span>
- <span data-ttu-id="8bac1-123">DLP 註解</span><span class="sxs-lookup"><span data-stu-id="8bac1-123">DLP Comment</span></span>
- <span data-ttu-id="8bac1-124">DLP 規則名稱</span><span class="sxs-lookup"><span data-stu-id="8bac1-124">DLP Rule Name</span></span>
- <span data-ttu-id="8bac1-125">DLP 動作</span><span class="sxs-lookup"><span data-stu-id="8bac1-125">DLP Actions</span></span>
- <span data-ttu-id="8bac1-126">擁有者</span><span class="sxs-lookup"><span data-stu-id="8bac1-126">Owner</span></span>
- <span data-ttu-id="8bac1-127">目前的 NTFS 權限 (SDDL)</span><span class="sxs-lookup"><span data-stu-id="8bac1-127">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="8bac1-128">套用的 NTFS 權限 (SDDL)</span><span class="sxs-lookup"><span data-stu-id="8bac1-128">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="8bac1-129">NTFS 權限類型</span><span class="sxs-lookup"><span data-stu-id="8bac1-129">NTFS permissions type</span></span>

### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="8bac1-130">案例：強制執行 DLP 規則</span><span class="sxs-lookup"><span data-stu-id="8bac1-130">Scenario: Enforce DLP rule</span></span>

<span data-ttu-id="8bac1-131">如果您想要對掃描的檔案強制執行 DLP 規則，則必須在 AIP 中的內容掃描工作以及 DLP 中原則層級上啟用強制執行。</span><span class="sxs-lookup"><span data-stu-id="8bac1-131">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>

#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="8bac1-132">設定 DLP 以強制執行原則動作</span><span class="sxs-lookup"><span data-stu-id="8bac1-132">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="8bac1-133">開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)，然後選取將您在 AIP 中所設定之內部部署位置存放庫作為目標的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="8bac1-133">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span>
2. <span data-ttu-id="8bac1-134">編輯原則。</span><span class="sxs-lookup"><span data-stu-id="8bac1-134">Edit the policy.</span></span>
3. <span data-ttu-id="8bac1-135">在 **測試或開啟原則** 頁面上，選取 **是，立即開啟**。</span><span class="sxs-lookup"><span data-stu-id="8bac1-135">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bac1-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8bac1-136">See also</span></span>

- [<span data-ttu-id="8bac1-137">了解 DLP 內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="8bac1-137">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="8bac1-138">開始使用 DLP 內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="8bac1-138">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="8bac1-139">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="8bac1-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8bac1-140">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="8bac1-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="8bac1-141">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="8bac1-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
