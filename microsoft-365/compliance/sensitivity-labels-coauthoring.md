---
title: 在 Microsoft 365 中啟用由敏感度標籤加密的檔案共同撰寫
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
description: 開啟可在桌面應用程式中針對 SharePoint 和 OneDrive 中已標記和加密的檔案啟用共同撰寫和自動儲存的設定。
ms.openlocfilehash: a5c3e84e4ca8874f99a07294dccfd2e4ad7ed81f
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417350"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a><span data-ttu-id="2a5d2-103">針對使用敏感度標籤加密的檔案啟用共同撰寫</span><span class="sxs-lookup"><span data-stu-id="2a5d2-103">Enable co-authoring for files encrypted with sensitivity labels</span></span>

><span data-ttu-id="2a5d2-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="2a5d2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="2a5d2-105">此功能處於預覽階段，可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-105">This feature is in preview and subject to change.</span></span> 
>
> <span data-ttu-id="2a5d2-106">在測試租用戶而非生產租用戶中啟用此功能，原因是：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-106">Enable this feature in a test tenant rather than a production tenant because:</span></span>
> - <span data-ttu-id="2a5d2-107">這項功能會變更標記中繼資料，並非所有平台上的所有應用程式目前都支援這項變更</span><span class="sxs-lookup"><span data-stu-id="2a5d2-107">This feature makes changes to labeling metadata and not all apps on all platforms currently support this change</span></span>
> - <span data-ttu-id="2a5d2-108">啟用此功能後，您無法自己停用此功能</span><span class="sxs-lookup"><span data-stu-id="2a5d2-108">You cannot disable this feature yourself after it is enabled</span></span>

<span data-ttu-id="2a5d2-109">啟用此設定以支援 Office 桌面應用程式 [共同撰寫](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) ，如此一來，當 [敏感度標籤](sensitivity-labels.md) 標記和加密檔案時，多個使用者可以同時編輯這些檔案。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-109">Enable the setting to support [co-authoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) for Office desktop apps so that when documents are labeled and encrypted by [sensitivity labels](sensitivity-labels.md), multiple users can edit these documents at the same time.</span></span>

<span data-ttu-id="2a5d2-110">未針對您的租用戶啟用此設定，使用者必須在使用 Office 桌面應用程式時，查看儲存在 SharePoint 或 OneDrive 中的加密檔案。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-110">Without this setting enabled for your tenant, users must check out an encrypted document stored in SharePoint or OneDrive when they use Office desktop apps.</span></span> <span data-ttu-id="2a5d2-111">因此，他們無法即時共同合作。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-111">As a result, they can't collaborate in real time.</span></span> <span data-ttu-id="2a5d2-112">或者，當 [SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度](sensitivity-labels-sharepoint-onedrive-files.md) 時，他們必須使用 Office 網頁。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-112">Or, they must use Office on the web when [sensitivity labels are enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="2a5d2-113">此外，啟用此功能會導致這些已標記和加密的檔案支援 [自動儲存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 功能。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-113">In addition, enabling this functionality results in the [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality being supported for these labeled and encrypted files.</span></span>

## <a name="metadata-changes-for-sensitivity-labels"></a><span data-ttu-id="2a5d2-114">敏感度標籤的中繼資料變更</span><span class="sxs-lookup"><span data-stu-id="2a5d2-114">Metadata changes for sensitivity labels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a5d2-115">啟用共同撰寫的設定之後，未加密檔案的標籤資訊將不再儲存於自訂屬性中。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-115">After you enable the setting for co-authoring, labeling information for unencrypted files is no longer saved in custom properties.</span></span>
> 
> <span data-ttu-id="2a5d2-116">如果您的組織中有任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-116">Do not enable this setting if you have any apps, services, scripts, or tools in your organization that reads or writes labeling metadata to the old location.</span></span>

<span data-ttu-id="2a5d2-117">在啟用設定以支援 Office 桌面應用程式共同撰寫之前，必須了解此動作會變更儲存至 Office 檔案和從 Office 檔案讀取的標籤中繼資料。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-117">Before you enable the setting to support co-authoring for Office desktop apps, it's important to understand that this action makes changes to the labeling metadata that is saved to and read from Office files.</span></span>

<span data-ttu-id="2a5d2-118">標籤中繼資料包含可識別租用戶和已套用敏感度標籤的資訊。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-118">The labeling metadata includes information that identifies your tenant and applied sensitivity label.</span></span> <span data-ttu-id="2a5d2-119">此設定所變更的是 Word、Excel 和 PowerPoint 未加密檔案的中繼資料格式和位置。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-119">The change that this setting makes is the metadata format and location for unencrypted files for Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="2a5d2-120">加密檔案或電子郵件沒有標籤中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-120">There are no labeling metadata changes for encrypted files or emails.</span></span>

<span data-ttu-id="2a5d2-121">此變更會影響新標記的檔案和已標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-121">This change affects both files that are newly labeled and files that are already labeled.</span></span> <span data-ttu-id="2a5d2-122">當您使用支援共同撰寫設定的應用程式和服務時：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-122">When you use apps and services that support the co-authoring setting:</span></span>
- <span data-ttu-id="2a5d2-123">對於新標記的檔案，只會使用新的格式和位置來標記中繼資料。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-123">For files that are newly labeled, only the new format and location is used for the labeling metadata.</span></span>
- <span data-ttu-id="2a5d2-124">對於已標記的檔案，下次開啟和儲存檔案時，如果檔案有舊格式和位置的中繼資料，它會複製到新的格式和位置。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-124">For files that are already labeled, the next time the file is opened and saved, if the file has metadata in the old format and location, it is copied to the new format and location.</span></span>

<span data-ttu-id="2a5d2-125">您可以在下列資源中，閱讀有關此中繼資料變更的詳情：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-125">You can read more about this metadata change from the following resources:</span></span>

- <span data-ttu-id="2a5d2-126">部落格文章：[Microsoft 資訊保護中繼資料儲存空間的近期變更](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span><span class="sxs-lookup"><span data-stu-id="2a5d2-126">Blog post: [Upcoming Changes to Microsoft Information Protection Metadata Storage](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span></span>

- <span data-ttu-id="2a5d2-127">開啟規格：[2.6.3 LabelInfo 與自訂檔案屬性](https://docs.microsoft.com/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span><span class="sxs-lookup"><span data-stu-id="2a5d2-127">Open Specifications: [2.6.3 LabelInfo versus Custom Document Properties](https://docs.microsoft.com/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span></span>

<span data-ttu-id="2a5d2-128">由於這些變更，如果您的組織中有任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-128">Because of these changes, do not enable this setting if you have any apps, services, scripts, or tools in your organization that reads or writes labeling metadata to the old location.</span></span> <span data-ttu-id="2a5d2-129">如果您這麼做，可能會產生一些後果，範例如下：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-129">If you do, some example consequences:</span></span>

- <span data-ttu-id="2a5d2-130">已標記的檔案會向使用者顯示為未標記</span><span class="sxs-lookup"><span data-stu-id="2a5d2-130">A document that is labeled appears to users to be unlabeled</span></span>

- <span data-ttu-id="2a5d2-131">檔案向使用者顯示過期的標籤</span><span class="sxs-lookup"><span data-stu-id="2a5d2-131">A document displays an out-of-date label to users</span></span>

- <span data-ttu-id="2a5d2-132">如果其他使用者在不支援新標籤中繼資料的 Office 桌面應用程式中開啟已標記和加密的檔案，共同撰寫和自動儲存將無法用於該檔案</span><span class="sxs-lookup"><span data-stu-id="2a5d2-132">Co-authoring and AutoSave won't work for a labeled and encrypted document if another user has it open in an Office desktop app that doesn't support the new labeling metadata</span></span>

- <span data-ttu-id="2a5d2-133">有一個 [將 Office 附件中的標籤識別為自訂屬性](https://docs.microsoft.com/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) 的 Exchange Online 郵件流程規則，其無法加密電子郵件和附件，或不正確地加密它們</span><span class="sxs-lookup"><span data-stu-id="2a5d2-133">An Exchange Online mail flow rule that [identifies labels as custom properties in Office attachments](https://docs.microsoft.com/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) fails to encrypt the email and attachment, or incorrectly encrypts them</span></span>

<span data-ttu-id="2a5d2-134">請查看下一節，以尋找支援此設定的應用程式和服務清單，以及標籤中繼資料的變更。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-134">Check the following section for a list of apps and services that support this setting and the changes to the labeling metadata.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a5d2-135">必要條件</span><span class="sxs-lookup"><span data-stu-id="2a5d2-135">Prerequisites</span></span>

<span data-ttu-id="2a5d2-136">開啟此功能之前，請確定您了解下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-136">Make sure you understand the following prerequisites before you turn on this feature.</span></span>

- <span data-ttu-id="2a5d2-137">您必須使用測試租用戶來進行此預覽。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-137">You must use a test tenant for this preview.</span></span>

- <span data-ttu-id="2a5d2-138">您必須是全域系統管理員才能開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-138">You must be a global admin to turn on this feature.</span></span>

- <span data-ttu-id="2a5d2-139">必須為租用戶啟用 [SharePoint 和 OneDrive 中 Office 檔案](sensitivity-labels-sharepoint-onedrive-files.md) 的敏感度標記。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-139">Sensitivity labels must be [enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) for the tenant.</span></span> <span data-ttu-id="2a5d2-140">如果此功能尚未啟用，當您選取設定以開啟具有敏感度標籤的檔案共同撰寫時，就會自動啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-140">If this feature isn't already enabled, it will be automatically enabled when you select the setting to turn on co-authoring for files with sensitivity labels.</span></span>

- <span data-ttu-id="2a5d2-141">您租用戶中所有的應用程式、服務和作業工具都必須支援新的應用程式 [標籤中繼資料](#metadata-changes-for-sensitivity-labels)：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-141">All apps, services, and operational tools in your tenant must support the new [labeling metadata](#metadata-changes-for-sensitivity-labels):</span></span>
    
    - <span data-ttu-id="2a5d2-142">**Microsoft 365 Apps 企業版：**</span><span class="sxs-lookup"><span data-stu-id="2a5d2-142">**Microsoft 365 Apps for enterprise:**</span></span>
        - <span data-ttu-id="2a5d2-143">Windows：[目前通道 (預覽)](https://office.com/insider) 搭配最小組建 16.0.13801.20182，或 [Beta 通道](https://office.com/insider) 搭配最小組建 16.0.13819.20006</span><span class="sxs-lookup"><span data-stu-id="2a5d2-143">Windows: [Current Channel (Preview)](https://office.com/insider) with minimum build 16.0.13801.20182, or [Beta Channel](https://office.com/insider) with minimum build 16.0.13819.20006</span></span>
        - <span data-ttu-id="2a5d2-144">macOS：[Beta 通道](https://office.com/insider) 搭配最小組建 16.47.218.0</span><span class="sxs-lookup"><span data-stu-id="2a5d2-144">macOS: [Beta Channel](https://office.com/insider) with minimal build 16.47.218.0</span></span>
        - <span data-ttu-id="2a5d2-145">iOS：尚未支援</span><span class="sxs-lookup"><span data-stu-id="2a5d2-145">iOS: Not yet supported</span></span>
        - <span data-ttu-id="2a5d2-146">Android：尚未支援</span><span class="sxs-lookup"><span data-stu-id="2a5d2-146">Android: Not yet supported</span></span>
    
    - <span data-ttu-id="2a5d2-147">**Azure 資訊保護統一標籤用戶端和掃描器：**</span><span class="sxs-lookup"><span data-stu-id="2a5d2-147">**Azure Information Protection unified labeling client and scanner:**</span></span> 
        - <span data-ttu-id="2a5d2-148">公開預覽版 (最低版本 2.10.45.0)，可從 [Microsoft 下載中心](https://aka.ms/aip-coauth-pp) 安裝，以及上一個項目所列的其中一個 Windows 版 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-148">A public preview version (minimum version of 2.10.45.0) that you can install from the [Microsoft Download Center](https://aka.ms/aip-coauth-pp) and one of the versions of Microsoft 365 Apps for enterprise for Windows listed in the previous item.</span></span>
    
    - <span data-ttu-id="2a5d2-149">**適用於 Windows 或 macOS 的 OneDrive 同步處理應用程式：**</span><span class="sxs-lookup"><span data-stu-id="2a5d2-149">**OneDrive sync app for Windows or macOS:**</span></span>
        - <span data-ttu-id="2a5d2-150">最低版本 19.002.0121.0008</span><span class="sxs-lookup"><span data-stu-id="2a5d2-150">Minimum version of 19.002.0121.0008</span></span>
    
    - <span data-ttu-id="2a5d2-151">**端點資料外洩防護 (端點 DLP)：**</span><span class="sxs-lookup"><span data-stu-id="2a5d2-151">**Endpoint data loss prevention (Endpoint DLP):**</span></span>
        - <span data-ttu-id="2a5d2-152">Windows 10 1809 搭配 KB 4601383</span><span class="sxs-lookup"><span data-stu-id="2a5d2-152">Windows 10 1809 with KB 4601383</span></span>
        - <span data-ttu-id="2a5d2-153">Windows 10 1903 和 1909 搭配 KB 4601380</span><span class="sxs-lookup"><span data-stu-id="2a5d2-153">Windows 10 1903 and 1909 with KB 4601380</span></span>
        - <span data-ttu-id="2a5d2-154">Windows 10 2004 搭配 KB 4601382</span><span class="sxs-lookup"><span data-stu-id="2a5d2-154">Windows 10 2004 with KB 4601382</span></span>
    
    - <span data-ttu-id="2a5d2-155">**使用 Microsoft 資訊保護 SDK 的應用程式和服務：**</span><span class="sxs-lookup"><span data-stu-id="2a5d2-155">**Apps and services that use the Microsoft Information Protection SDK:**</span></span> 
        - <span data-ttu-id="2a5d2-156">最低版本 1.7</span><span class="sxs-lookup"><span data-stu-id="2a5d2-156">Minimum version of 1.7</span></span> 

<span data-ttu-id="2a5d2-157">當您開啟此功能時，Microsoft 365 服務會自動支援新的標籤中繼資料。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-157">Microsoft 365 services automatically support the new labeling metadata when you turn on this feature.</span></span> <span data-ttu-id="2a5d2-158">例如：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-158">For example:</span></span>

- [<span data-ttu-id="2a5d2-159">自動標籤原則</span><span class="sxs-lookup"><span data-stu-id="2a5d2-159">Auto-labeling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [<span data-ttu-id="2a5d2-160">使用敏感度標籤作為條件的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2a5d2-160">DLP policies that use sensitivity labels as conditions</span></span>](dlp-sensitivity-label-as-condition.md)
- [<span data-ttu-id="2a5d2-161">Microsoft Cloud App Security 已設為套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2a5d2-161">Microsoft Cloud App Security configured to apply sensitivity labels</span></span>](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a><span data-ttu-id="2a5d2-162">限制</span><span class="sxs-lookup"><span data-stu-id="2a5d2-162">Limitations</span></span>

<span data-ttu-id="2a5d2-163">在針對使用敏感度標籤加密的檔案啟用共同撰寫的租用戶設定之前，請確定您了解此功能的下列限制。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-163">Before you enable the tenant setting for co-authoring for files encrypted with sensitivity labels, make sure you understand the following limitations of this feature.</span></span>

- <span data-ttu-id="2a5d2-164">由於 [標籤中繼資料變更](#metadata-changes-for-sensitivity-labels)，您租用戶中所有的應用程式、服務和作業工具都必須支援新的標籤中繼資料，以得到一致且可靠的標籤體驗。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-164">Because of the [labeling metadata changes](#metadata-changes-for-sensitivity-labels), all apps, services, and operational tools in your tenant must support the new labeling metadata for a consistent and reliable labeling experience.</span></span>
    
    <span data-ttu-id="2a5d2-165">Excel 專用：如果有人使用不支援敏感度標籤中繼資料變更的 Excel 版本來編輯並保存該檔案，則不應用加密的敏感度標籤中繼資料可以從檔案中刪除。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-165">Specific to Excel: Metadata for a sensitivity label that doesn't apply encryption can be deleted from a file if somebody edits and saves that file by using a version of Excel that doesn't support the metadata changes for sensitivity labels.</span></span>

- <span data-ttu-id="2a5d2-166">不支援共同撰寫和自動儲存，且無法用於使用下列任何 [加密設定](encryption-sensitivity-labels.md#configure-encryption-settings) 的已標記和加密的 Office 檔案：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-166">Co-authoring and AutoSave aren't supported and don't work for labeled and encrypted Office documents that use any of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="2a5d2-167">**讓使用者在套用標籤時指派權限**，且核取方塊 **在 Word、PowerPoint 與 Excel 中提示使用者指定權限** 為選取狀態。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-167">**Let users assign permissions when they apply the label** and the checkbox **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="2a5d2-168">此設定有時稱為「使用者定義的權限」。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-168">This configuration is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="2a5d2-169">**使用者的內容存取權到期日** 設定為 **永不** 以外的值。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-169">**User access to content expires** is set to a value other than **Never**.</span></span>
    - <span data-ttu-id="2a5d2-170">**使用雙重金鑰加密** 已選取。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-170">**Double Key Encryption** is selected.</span></span>
    
    <span data-ttu-id="2a5d2-171">對於具有這些加密設定的標籤，標籤會顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-171">For labels with any of these encryption configurations, the labels display in Office apps.</span></span> <span data-ttu-id="2a5d2-172">不過，當使用者選取這些標籤，且沒有其他人在編輯檔案時，系統會警告他們共同撰寫和自動儲存將無法使用。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-172">However, when users select these labels and nobody else is editing the document, they are warned that co-authoring and AutoSave won't be available.</span></span> <span data-ttu-id="2a5d2-173">如果有其他人在編輯檔案，使用者會看到「無法貼上這些標記」的訊息。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-173">If somebody else is editing the document, users see a message that the labels can't be applied.</span></span>

## <a name="known-issues-for-this-preview"></a><span data-ttu-id="2a5d2-174">此預覽的已知問題</span><span class="sxs-lookup"><span data-stu-id="2a5d2-174">Known issues for this preview</span></span>

<span data-ttu-id="2a5d2-175">此預覽版使用敏感度標籤加密的檔案共同撰寫有下列已知問題：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-175">This preview version of co-authoring for files encrypted with sensitivity labels has the following known issues:</span></span>

- <span data-ttu-id="2a5d2-176">使用者無法針對大於 300 MB 的 Word、Excel 和 PowerPoint 檔案，在 Office 網頁版中為任何的檔案套用任何標籤。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-176">Users won't be able to apply any labels in Office for the web for Word, Excel, and PowerPoint files that are bigger than 300 MB.</span></span> <span data-ttu-id="2a5d2-177">對於這些檔案，您可以使用 Office 桌面應用程式來套用標籤，但您必須是唯一開啟檔案的人。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-177">For these files, you can use the Office desktop apps to apply a label but you must be the only person who has the file open.</span></span>

- <span data-ttu-id="2a5d2-178">當您使用 [將敏感度標籤作為條件的 DLP](dlp-sensitivity-label-as-condition.md) 時，電子郵件的未加密附件不受支援。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-178">When you use [DLP policies that use sensitivity labels as conditions](dlp-sensitivity-label-as-condition.md), unencrypted attachments for emails are not supported.</span></span>

- <span data-ttu-id="2a5d2-179">不支援 iOS 版和 Android 版 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-179">Office apps for iOS and Android are not supported.</span></span>

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a><span data-ttu-id="2a5d2-180">如何啟用具有敏感度標籤的檔案共同撰寫</span><span class="sxs-lookup"><span data-stu-id="2a5d2-180">How to enable co-authoring for files with sensitivity labels</span></span>

> [!CAUTION]
> <span data-ttu-id="2a5d2-181">開啟此設定是單向動作。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-181">Turning on this setting is a one-way action.</span></span> <span data-ttu-id="2a5d2-182">此功能為預覽版時，請只在非生產環境中進行測試，且只有在您閱讀並了解中繼資料變更、必要條件、限制，以及此頁面上記錄的任何已知問題之後，再進行測試。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-182">While the feature is in preview, test it only in a non-production environment and only after you have read and understood the metadata changes, prerequisites, limitations, and any known issues documented on this page.</span></span>

<span data-ttu-id="2a5d2-183">在預覽期間，您必須使用特定的 URL，以在 Microsoft 365 合規性中心存取此設定。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-183">During the preview, you must use a specific URL to access this setting in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2a5d2-184">使用下列連結，以測試租用戶全域系統管理員的身分登入 Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-184">Sign in to the Microsoft 365 compliance center as a global admin for your test tenant, using the following link:</span></span>
    
    ````
    https://compliance.microsoft.com/co-authoring_for_files_with_sensitivity_labels
    ````
    <span data-ttu-id="2a5d2-185">此連結會直接將您帶至租用戶設定，**共同撰寫具有敏感度標記的檔案**。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-185">This link takes you directly to the tenant setting, **Co-authoring for files with sensitivity labels**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2a5d2-186">在您繼續之前，請檢查您是否已登入不會影響您的使用者的測試租用戶：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-186">Before you continue, check you're signed in to a test tenant that won't affect your users:</span></span> 
    >
    > <span data-ttu-id="2a5d2-187">選取合規性中心右上方具有您帳戶縮寫的圓圈，並確認租用戶名稱確實顯示您預期的測試租用戶。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-187">Select the circle with your account initials in the top right of the compliance center, and confirm that the tenant name does display your intended test tenant.</span></span>
    
2. <span data-ttu-id="2a5d2-188">閱讀摘要描述、必要條件、預期項目，以及開啟此設定後無法關閉的警告。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-188">Read the summary description, prerequisites, what to expect, and the warning that you can't turn off this setting after you've turned it on.</span></span> <span data-ttu-id="2a5d2-189">然後依序選取 **開啟具有敏感度標籤的檔案共同撰寫** 以及 **套用**：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-189">Then select **Turn on co-authoring for files with sensitivity labels**, and **Apply**:</span></span>
    
    ![開啟具有敏感度標籤之檔案共同撰寫的選項](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. <span data-ttu-id="2a5d2-191">在您測試這項新功能進行共同撰寫之前，請等候 24 小時，讓此設定在整個環境中進行複製。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-191">Wait 24 hours for this setting to replicate across your environment before you test this new feature for co-authoring.</span></span>

## <a name="contact-support-if-you-need-to-disable-this-feature"></a><span data-ttu-id="2a5d2-192">如果您需要停用此功能，請聯絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="2a5d2-192">Contact Support if you need to disable this feature</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a5d2-193">如果您需要停用此功能，請注意標籤資訊可能會遺失。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-193">If you do need to disable this feature, be aware that labeling information can be lost.</span></span>

<span data-ttu-id="2a5d2-194">為租用戶啟用具有敏感度標籤的檔案共同撰寫之後，您無法自己停用此設定。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-194">After you've enabled co-authoring for files with sensitivity labels for your tenant, you can't disable this setting yourself.</span></span> <span data-ttu-id="2a5d2-195">這就是為什麼在啟用此設定之前，務必先查看並了解必要條件、結果和限制。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-195">That's why it's so important that you check and understand the prerequisites, consequences, and limitations before you enable this setting.</span></span> <span data-ttu-id="2a5d2-196">這也是我們建議您使用測試租用戶而非生產租用戶來測試此功能的原因。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-196">It's also why we recommend that you test this feature with a test tenant rather than a production tenant.</span></span>

![顯示已針對敏感度標籤開啟共同撰寫的選項](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

<span data-ttu-id="2a5d2-198">正如您在此設定開啟時從螢幕擷取畫面中所看到的一樣，您可以聯絡 [Microsoft 支援服務](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) 並要求關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-198">As you see from the screenshot when this setting has been turned on, you can contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) and request to turn off this setting.</span></span> <span data-ttu-id="2a5d2-199">此要求可能需要數天的時間，您必須證明您為租用戶全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-199">This request might take several days and you will need to prove that you are a global administrator for your tenant.</span></span> <span data-ttu-id="2a5d2-200">預期需要支付一般支援費用。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-200">Expect usual support charges to apply.</span></span> 

<span data-ttu-id="2a5d2-201">如果支援工程師針對您的租用戶停用此設定：</span><span class="sxs-lookup"><span data-stu-id="2a5d2-201">If a support engineer disables this setting for your tenant:</span></span>

- <span data-ttu-id="2a5d2-202">對於支援新標籤中繼資料的應用程式和服務，現在當讀取或儲存標籤時，它們會還原為原始的中繼資料格式和位置。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-202">For apps and services that support the new labeling metadata, they now revert to the original metadata format and location when labels are read or saved.</span></span>

- <span data-ttu-id="2a5d2-203">啟用設定時所使用的 Office 檔的新中繼資料格式和位置將不會複製到原始格式和位置。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-203">The new metadata format and location for Office documents that were used while the setting was enabled will not be copied to the original format and location.</span></span> <span data-ttu-id="2a5d2-204">因此，未加密 Word、Excel 和 PowerPoint 檔案的此標籤資訊將會遺失。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-204">As a result, this labeling information for unencrypted Word, Excel, and PowerPoint files will be lost.</span></span>

- <span data-ttu-id="2a5d2-205">共同撰寫和自動儲存功能已無法於租用戶中使用。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-205">Co-authoring and AutoSave no longer work in your tenant.</span></span>

- <span data-ttu-id="2a5d2-206">在 OneDrive 和 SharePoint 中，Office 檔案的敏感度標籤仍維持啟用。</span><span class="sxs-lookup"><span data-stu-id="2a5d2-206">Sensitivity labels remain enabled for Office files in OneDrive and SharePoint.</span></span>