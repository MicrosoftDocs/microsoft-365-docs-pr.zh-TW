---
title: 步驟 2：設定環境的分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定在組織中分類資料的不同方式。
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067250"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="05a7e-103">步驟 2：設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="05a7e-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="05a7e-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="05a7e-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![第 6 階段：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="05a7e-106">在此步驟中，您會與法律和法規遵循小組合作，定義組織資料的分類配置。</span><span class="sxs-lookup"><span data-stu-id="05a7e-106">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="05a7e-107">Microsoft 365 分類類型</span><span class="sxs-lookup"><span data-stu-id="05a7e-107">Microsoft 365 classification types</span></span>

<span data-ttu-id="05a7e-108">Microsoft 365 有四種分類：</span><span class="sxs-lookup"><span data-stu-id="05a7e-108">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="05a7e-109">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="05a7e-109">Sensitive information types</span></span>
- <span data-ttu-id="05a7e-110">保留標籤</span><span class="sxs-lookup"><span data-stu-id="05a7e-110">Retention labels</span></span>
- <span data-ttu-id="05a7e-111">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="05a7e-111">Sensitivity labels</span></span>
- <span data-ttu-id="05a7e-112">Azure 資訊保護的標籤和保護</span><span class="sxs-lookup"><span data-stu-id="05a7e-112">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="05a7e-113">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="05a7e-113">Sensitive information types</span></span>

<span data-ttu-id="05a7e-114">Microsoft 365 的敏感資訊類型會定義自動化程序 (例如搜尋) 如何辨識特定的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="05a7e-114">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="05a7e-115">這些類型包含敏感的員工或客戶資料，例如健保號碼和信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="05a7e-115">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="05a7e-116">您可以使用敏感資訊類型來尋找敏感資料，並套用資料外洩防護 (DLP) 規則和原則來保護此資料。</span><span class="sxs-lookup"><span data-stu-id="05a7e-116">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="05a7e-117">如需詳細資訊，請參閱 [DLP 原則的內容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-117">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="05a7e-118">敏感資訊類型特別有助於符合合規性和法規需求，例如一般資料保護規定 (GDPR)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-118">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="05a7e-119">保留標籤</span><span class="sxs-lookup"><span data-stu-id="05a7e-119">Retention labels</span></span>

<span data-ttu-id="05a7e-120">在定義資料管理策略時，其中一項工作是決定應該將特定類型的文件或具有特定內容的文件保留多久，以符合組織的原則和地區的法規。</span><span class="sxs-lookup"><span data-stu-id="05a7e-120">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="05a7e-121">例如，某些類型的文件應該先保留一定時間再刪除，其他類型的文件則必須無限期保留。</span><span class="sxs-lookup"><span data-stu-id="05a7e-121">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="05a7e-122">對於儲存在 Microsoft 365 中的文件，您可以對 Exchange 電子郵件、SharePoint Online、商務用 OneDrive 以及 Teams 聊天和頻道的訊息中所儲存的文件和資料，定義並套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="05a7e-122">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="05a7e-123">如果您使用保留標籤，請對必須套用保留原則的每個檔案類別設定標籤。</span><span class="sxs-lookup"><span data-stu-id="05a7e-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="05a7e-124">在保留標籤內，您可以指定：</span><span class="sxs-lookup"><span data-stu-id="05a7e-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="05a7e-125">一組檔案描述項 (例如，依業務部門、檔案類別或法規)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="05a7e-126">已附加保留標籤的檔案所需的保留設定，例如保留時間和到達保留時間後的行為。</span><span class="sxs-lookup"><span data-stu-id="05a7e-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="05a7e-127">您也可以藉由設定 SharePoint Online 網站來自動對檔案套用保留標籤，以對該網站中的所有新文件套用預設的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="05a7e-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="05a7e-128">如需詳細資訊，請參閱[保留標籤概觀](https://docs.microsoft.com/office365/securitycompliance/labels)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-128">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="05a7e-129">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="05a7e-129">Sensitivity labels</span></span>

<span data-ttu-id="05a7e-130">在為特定類型的文件或具有特定內容的文件提供保護並實作安全性時，其中一項工作是使用標籤來加以標示，以便再套用一層安全性。</span><span class="sxs-lookup"><span data-stu-id="05a7e-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="05a7e-131">使用 Microsoft 365 中的敏感度標籤時，您可以：</span><span class="sxs-lookup"><span data-stu-id="05a7e-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="05a7e-132">強制執行保護設定，例如加密、權限或新增浮水印。</span><span class="sxs-lookup"><span data-stu-id="05a7e-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="05a7e-133">使用 Windows 資訊保護 (WIP) 端點保護來防止該內容遭人複製到第三方應用程式 (例如 Twitter 或 Gmail)，或複製到抽取式儲存體 (例如 USB 磁碟機)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="05a7e-134">使用 Microsoft Cloud App Security (CAS) 來保護第三方應用程式和服務中的內容。</span><span class="sxs-lookup"><span data-stu-id="05a7e-134">Use Microsoft Cloud App Security (CAS) to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="05a7e-135">不使用任何保護設定而將內容分類。</span><span class="sxs-lookup"><span data-stu-id="05a7e-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="05a7e-136">如果您使用敏感度標籤，請為每個安全性和資訊保護層級設定標籤。</span><span class="sxs-lookup"><span data-stu-id="05a7e-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="05a7e-137">例如，為下列項目建立三個敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="05a7e-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="05a7e-138">基準</span><span class="sxs-lookup"><span data-stu-id="05a7e-138">Baseline</span></span>
- <span data-ttu-id="05a7e-139">敏感性</span><span class="sxs-lookup"><span data-stu-id="05a7e-139">Sensitive</span></span>
- <span data-ttu-id="05a7e-140">高管制</span><span class="sxs-lookup"><span data-stu-id="05a7e-140">Highly regulated</span></span>

<span data-ttu-id="05a7e-141">如果您將具有高度管控資料的檔案儲存在 SharePoint Online 網站中，並希望這些檔案的權限與網站相同，如果檔案離開網站，您就需要建立權限與網站相同的額外靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="05a7e-141">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="05a7e-142">如需詳細資訊，請參閱此[敏感度標籤概觀](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-142">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="05a7e-143">Azure 資訊保護的標籤和保護</span><span class="sxs-lookup"><span data-stu-id="05a7e-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="05a7e-144">您可以使用 Azure 資訊保護標籤，將組織的文件和電子郵件進行分類，並選擇是否要提供保護。</span><span class="sxs-lookup"><span data-stu-id="05a7e-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="05a7e-145">這些標籤可以套用至並非儲存在 Microsoft 365 內的文件。</span><span class="sxs-lookup"><span data-stu-id="05a7e-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="05a7e-146">這些標籤可以由定義規則和條件的系統管理員自動套用、由使用者手動完成，或在提供建議給使用者的情況下由系統管理員搭配使用者的組合來完成。</span><span class="sxs-lookup"><span data-stu-id="05a7e-146">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="05a7e-147">若要規劃及套用 Azure 資訊保護的標籤和保護，請這麼做：</span><span class="sxs-lookup"><span data-stu-id="05a7e-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="05a7e-148">檢閱 [Azure 資訊保護的需求](https://docs.microsoft.com/information-protection/get-started/requirements)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="05a7e-149">遵循[分類、標籤、保護的部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="05a7e-150">如需詳細資訊，請參閱 [Azure 資訊保護文件的文件庫](https://docs.microsoft.com/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="05a7e-151">現有的 Azure 資訊保護標籤可與敏感度標籤緊密配合。</span><span class="sxs-lookup"><span data-stu-id="05a7e-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="05a7e-152">例如，您可以將現有的 Azure 資訊保護標籤以及套用至文件和電子郵件的標籤保留下來。</span><span class="sxs-lookup"><span data-stu-id="05a7e-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="05a7e-153">如果您同時擁有敏感度標籤和 Azure 資訊保護標籤，請[將 Azure 資訊保護標籤遷移至敏感度標籤](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="05a7e-154">範例：GDPR 的分類</span><span class="sxs-lookup"><span data-stu-id="05a7e-154">Example: Classification for GDPR</span></span>

<span data-ttu-id="05a7e-155">如需 GDPR 包含個人資料的分類配置範例，請參閱[設計個人資料的分類結構描述](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="05a7e-156">試用產品</span><span class="sxs-lookup"><span data-stu-id="05a7e-156">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="05a7e-158">測試實驗室指南：資料分類</span><span class="sxs-lookup"><span data-stu-id="05a7e-158">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="05a7e-159">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step2)。</span><span class="sxs-lookup"><span data-stu-id="05a7e-159">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="05a7e-160">下一步</span><span class="sxs-lookup"><span data-stu-id="05a7e-160">Next step</span></span>

|||
|:-------|:-----|
|![步驟 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="05a7e-162">設定增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="05a7e-162">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

