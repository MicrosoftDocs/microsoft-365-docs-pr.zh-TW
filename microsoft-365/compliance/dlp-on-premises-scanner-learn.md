---
title: 深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
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
description: Microsoft 365 資料外洩防護內部部署掃描器可將檔案活動的監視以及這些檔案的保護動作延伸到內部部署檔案共用、SharePoint 資料夾和文件庫。檔案會由 Azure 資訊保護 (AIP) 掃描器掃描並保護
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114161"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="1fa3e-104">深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1fa3e-104">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="1fa3e-105">Microsoft 資料外洩防護內部部署掃描器是 Microsoft 365 資料外洩防護 (DLP) 套件的一部分，您可以使用這些功能探索並保護整個 Microsoft 365 服務的敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-105">Microsoft data loss prevention on-premises scanner is part of the Microsoft 365 data loss prevention (DLP) suite of features that you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="1fa3e-106">如需所有 Microsoft DLP 供應項目的詳細資訊，請參閱[了解資料外洩防護](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-106">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="1fa3e-107">**DLP 內部部署掃描器** 會耙梳檔案共用和 SharePoint 文件庫及資料夾中的內部部署待用資料，並尋找敏感性項目，而這類項目如果外泄會對組織造成風險或造成合規性政策違規的風險。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-107">The **DLP on-premises scanner** crawls on-premises data-at-rest in file shares and SharePoint document libraries and folders for sensitive items that, if leaked, would pose a risk to your organization or pose a risk of compliance policy violation.</span></span> <span data-ttu-id="1fa3e-108">這可提供您所需的可見度和控制，以確保敏感性項目得到正確的使用與保護，並協助防治可能導致威脅入侵的風險行為。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-108">This gives you the visibility and control you need to ensure that sensitive items are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span> <span data-ttu-id="1fa3e-109">DLP 內部部署掃描器會使用 [內建](sensitive-information-type-entity-definitions.md) 或 [自訂敏感性資訊](create-a-custom-sensitive-information-type.md) 類型、 [敏感度標籤](sensitivity-labels.md) 或檔案屬性來偵測敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-109">The DLP on-premises scanner detects sensitive information by using [built-in](sensitive-information-type-entity-definitions.md) or [custom sensitive information](create-a-custom-sensitive-information-type.md) types, [sensitivity labels](sensitivity-labels.md) or file properties.</span></span> <span data-ttu-id="1fa3e-110">您可以在 [活動總管](data-classification-activity-explorer.md) 中查看使用者使用敏感度專案的相關資訊，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)強制執行這些專案上的保護動作。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-110">The information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a><span data-ttu-id="1fa3e-111">DLP 內部部署掃描器依賴 Azure 資訊保護掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-111">The DLP on-premises scanner relies on Azure Information Protection scanner</span></span>

<span data-ttu-id="1fa3e-112">DLP 內部部署掃描器依賴 Azure 資訊保護 (AIP) 掃描器的完整執行來監視、標記和保護敏感性項目。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-112">The DLP on-premises scanner relies on a full implementation of the Azure Information Protection (AIP) scanner to monitor, label and protect sensitive items.</span></span> <span data-ttu-id="1fa3e-113">如果您不熟悉 AIP 掃描器，強烈建議您加以熟悉。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-113">If you aren't familiar with the AIP scanner, we strongly recommend familiarizing yourself with it.</span></span> <span data-ttu-id="1fa3e-114">請參閱這些文章：</span><span class="sxs-lookup"><span data-stu-id="1fa3e-114">See these articles:</span></span>

- [<span data-ttu-id="1fa3e-115">什麼是 Azure 資訊保護？</span><span class="sxs-lookup"><span data-stu-id="1fa3e-115">What is Azure Information Protection</span></span>](/azure/information-protection/what-is-information-protection)
- [<span data-ttu-id="1fa3e-116">什麼是 Azure 資訊保護統一標籤掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-116">What is the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="1fa3e-117">安裝和部署 Azure 資訊保護統一標籤掃描器的需求</span><span class="sxs-lookup"><span data-stu-id="1fa3e-117">Requirements for installing and deploying the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-prereqs)
- [<span data-ttu-id="1fa3e-118">教學課程：安裝 Azure 資訊保護 (AIP) 統一標籤掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-118">Tutorial: Installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/tutorial-install-scanner)
- [<span data-ttu-id="1fa3e-119">設定和安裝 Azure 資訊保護統一標籤掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-119">Configuring and installing the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install)
- [<span data-ttu-id="1fa3e-120">Azure 資訊保護統一標籤用戶端-版本發行歷程記錄及支援原則</span><span class="sxs-lookup"><span data-stu-id="1fa3e-120">Azure Information Protection unified labeling client - Version release history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a><span data-ttu-id="1fa3e-121">DLP 內部部署掃描器動作</span><span class="sxs-lookup"><span data-stu-id="1fa3e-121">DLP on-premises scanner actions</span></span>

<span data-ttu-id="1fa3e-122">DLP 內部部署掃描器會利用以下四種方法的其中一項來偵測檔案：</span><span class="sxs-lookup"><span data-stu-id="1fa3e-122">DLP on-premises scanner detects files by one of these four methods:</span></span>

- <span data-ttu-id="1fa3e-123">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="1fa3e-123">sensitive information types</span></span>
- <span data-ttu-id="1fa3e-124">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="1fa3e-124">sensitivity labels</span></span>
- <span data-ttu-id="1fa3e-125">檔案副檔名</span><span class="sxs-lookup"><span data-stu-id="1fa3e-125">file extension</span></span>
- <span data-ttu-id="1fa3e-126">僅 Office 檔案上的自訂文件屬性</span><span class="sxs-lookup"><span data-stu-id="1fa3e-126">custom document properties on Office files only</span></span> 

<span data-ttu-id="1fa3e-127">當偵測到的檔案在外泄時具有潛在風險，或違反合規性政策時，DLP 內部部署掃描器可以採取這四個動作中的其中一個動作。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-127">When a detected file poses a potential risk if leaked or a compliance policy violation, the DLP on-premises scanner can take one of these four actions.</span></span>

|<span data-ttu-id="1fa3e-128">動作</span><span class="sxs-lookup"><span data-stu-id="1fa3e-128">Action</span></span> |<span data-ttu-id="1fa3e-129">描述</span><span class="sxs-lookup"><span data-stu-id="1fa3e-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1fa3e-130">**禁止這些人存取儲存在內部部署掃描器中的檔案 - 所有人**</span><span class="sxs-lookup"><span data-stu-id="1fa3e-130">**Block these people from accessing file stored in  on-premises scanner - Everyone**</span></span> | <span data-ttu-id="1fa3e-131">強制執行時，此動作會禁止所有帳戶的存取權限，唯有內容擁有者、最後一個修改專案的帳戶，以及系統管理員除外。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-131">When enforced, this action blocks access to all accounts except the content owner, the last account that modified the item and the administrator.</span></span> <span data-ttu-id="1fa3e-132">它會在檔案層級自 NTFS/SharePoint 權限移除所有帳戶，但檔案擁有者、存放庫擁有者 (在內容掃描工作中的 [設定存放庫擁有者](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) 設定中所設）、最後修改者 (只能在 SharePoint 中識別) 和系統管理員除外。掃描器帳戶也會獲得檔案的 FC 權限。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-132">It does this by removing all accounts from NTFS/SharePoint permissions at the file level except the file owner, repository owner (set in the [Set repository owner](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) setting in content scan job), last modifier (can be identified in SharePoint only) and admin. The scanner account is also granted FC rights on the file.</span></span>|
|<span data-ttu-id="1fa3e-133">**封鎖這些人員，使其無法存取儲存在內部部署掃描器中的檔案 - 封鎖全組織 (公用) 存取**</span><span class="sxs-lookup"><span data-stu-id="1fa3e-133">**Block these people from accessing file stored in  on-premises scanner - block org-wide (public) access**</span></span>    |<span data-ttu-id="1fa3e-134">強制執行時，此動作會從檔案存取控制清單 (ACL) 移除 **_所有人_*_、_*_NT AUTHORITY\已驗證的使用者_*_和 _*_網域使用者_** SID。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-134">When enforced, this action removes the **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SIDs from the file access control list (ACL).</span></span> <span data-ttu-id="1fa3e-135">只有明確獲得檔案或父資料夾權限的使用者和群組才能存取檔案。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-135">Only users and groups that have been explicitly granted rights to the file or parent folder will be able to access the file.</span></span>|
|<span data-ttu-id="1fa3e-136">**設定檔案的權限**</span><span class="sxs-lookup"><span data-stu-id="1fa3e-136">**Set permissions on the file**</span></span>|<span data-ttu-id="1fa3e-137">強制執行時，此動作會強制檔案繼承其父資料夾的權限。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-137">When enforced, this action forces the file to inherit the permissions of its parent folder.</span></span> <span data-ttu-id="1fa3e-138">根據預設，只有在父資料夾的權限比檔案上已有的權限限制更嚴格時，才能強制執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-138">Be default, this action will only be enforced if the permissions on the parent folder are more restrictive than the permissions that are already on the file.</span></span> <span data-ttu-id="1fa3e-139">例如，如果檔案上的 ACL 設定為只允許 **_特定使用者_*_，且父資料夾設定為允許 _\*_網域使用者_*_ 群組，則檔案不會繼承父資料夾權限。您可以選取 _* 即使父項權限較不嚴格也繼承*\* 選項來覆寫此行為。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-139">For example, if the ACL on the file is set to only allow **_specific users_*_ and the parent folder is configured to allow _*_Domain Users_*_ group, the parent folder permissions would not be inherited by the file. You can override this behavior by selecting the _\* Inherit even if parent permissions are less restrictive*\* option.</span></span>|
|<span data-ttu-id="1fa3e-140">**從不當位置移除檔案**</span><span class="sxs-lookup"><span data-stu-id="1fa3e-140">**Remove the file from improper location**</span></span>|<span data-ttu-id="1fa3e-141">強制執行時，此動作會以 .txt 副檔名取代原始檔案，並且將原始檔案的一份副本位於隔離資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-141">When enforced, this action replaces the original file with a stub file with .txt extension and places a copy of the original file in a quarantine folder.</span></span> 

## <a name="whats-different-in-the-on-premises-scanner"></a><span data-ttu-id="1fa3e-142">內部部署掃描器的不同處</span><span class="sxs-lookup"><span data-stu-id="1fa3e-142">What's different in the on-premises scanner</span></span>

<span data-ttu-id="1fa3e-143">在您深入了解內部部署掃描器之前，您必須先注意一些額外的概念。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-143">There are a few extra concepts that you need to be aware of before you dig into the on-premises scanner.</span></span>

### <a name="aip-repositories-and-content-scan-jobs"></a><span data-ttu-id="1fa3e-144">AIP 存放庫和內容掃描工作</span><span class="sxs-lookup"><span data-stu-id="1fa3e-144">AIP repositories and content scan jobs</span></span>

<span data-ttu-id="1fa3e-145">您必須建立 AIP 內容掃描工作，並識別出裝載著您希望 DLP 引擎評估之檔案的存放庫。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-145">You must create an AIP content scan jobs and identify the repositories that host the files that you want to be evaluated by DLP engine.</span></span> <span data-ttu-id="1fa3e-146">請確定在已建立之 AIP 內容掃描工作中啟用 DLP 規則。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-146">Make sure you enable DLP rules in the created AIP content scan job.</span></span>

### <a name="policy-tips"></a><span data-ttu-id="1fa3e-147">原則提示</span><span class="sxs-lookup"><span data-stu-id="1fa3e-147">Policy tips</span></span>

<span data-ttu-id="1fa3e-148">內部掃描器中未提供 [原則提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-148">[Policy tips](use-notifications-and-policy-tips.md) are not available in on-premises scanner.</span></span>


### <a name="viewing-dlp-on-premises-scanner-events"></a><span data-ttu-id="1fa3e-149">檢視 DLP 內部部署掃描器事件</span><span class="sxs-lookup"><span data-stu-id="1fa3e-149">Viewing DLP on-premises scanner events</span></span>

<span data-ttu-id="1fa3e-150">您可以在 M365 合規性中心或 [活動總管](data-classification-activity-explorer.md) 中查看 DLP 內部部署掃描器。</span><span class="sxs-lookup"><span data-stu-id="1fa3e-150">You view DLP on-premises scanner data in the M365 Compliance Center [activity explorer](data-classification-activity-explorer.md).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="1fa3e-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1fa3e-151">Next steps</span></span>

<span data-ttu-id="1fa3e-152">現在您已了解 DLP 內部部署掃描器，接下來的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="1fa3e-152">Now that you've learned about DLP on-premises scanner, your next steps are:</span></span>

1. [<span data-ttu-id="1fa3e-153">開始使用 DLP 內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-153">Get started with the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
2. [<span data-ttu-id="1fa3e-154">使用 DLP 內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-154">Use the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="1fa3e-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1fa3e-155">See also</span></span>

- [<span data-ttu-id="1fa3e-156">開始使用 Microsoft 資料外洩防護內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-156">Getting started with the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="1fa3e-157">使用 Microsoft 資料外洩防護內部部署掃描器</span><span class="sxs-lookup"><span data-stu-id="1fa3e-157">Use the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="1fa3e-158">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="1fa3e-158">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="1fa3e-159">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="1fa3e-159">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1fa3e-160">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="1fa3e-160">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)