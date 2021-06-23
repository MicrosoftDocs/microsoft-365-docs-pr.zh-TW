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
ms.openlocfilehash: bd197a55e5a119263bd9c67716c38010a86e5263
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062188"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a><span data-ttu-id="1ae84-103">針對使用敏感度標籤加密的檔案啟用共同撰寫</span><span class="sxs-lookup"><span data-stu-id="1ae84-103">Enable co-authoring for files encrypted with sensitivity labels</span></span>

><span data-ttu-id="1ae84-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="1ae84-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="1ae84-105">此功能處於預覽階段，可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="1ae84-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="1ae84-106">啟用此設定以支援 Office 桌面應用程式 [共同撰寫](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) ，如此一來，當 [敏感度標籤](sensitivity-labels.md) 標記和加密檔案時，多個使用者可以同時編輯這些檔案。</span><span class="sxs-lookup"><span data-stu-id="1ae84-106">Enable the setting to support [co-authoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) for Office desktop apps so that when documents are labeled and encrypted by [sensitivity labels](sensitivity-labels.md), multiple users can edit these documents at the same time.</span></span>

<span data-ttu-id="1ae84-107">未針對您的租用戶啟用此設定，使用者必須在使用 Office 桌面應用程式時，查看儲存在 SharePoint 或 OneDrive 中的加密檔案。</span><span class="sxs-lookup"><span data-stu-id="1ae84-107">Without this setting enabled for your tenant, users must check out an encrypted document stored in SharePoint or OneDrive when they use Office desktop apps.</span></span> <span data-ttu-id="1ae84-108">因此，他們無法即時共同合作。</span><span class="sxs-lookup"><span data-stu-id="1ae84-108">As a result, they can't collaborate in real time.</span></span> <span data-ttu-id="1ae84-109">或者，當 [SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度](sensitivity-labels-sharepoint-onedrive-files.md) 時，他們必須使用 Office 網頁。</span><span class="sxs-lookup"><span data-stu-id="1ae84-109">Or, they must use Office on the web when [sensitivity labels are enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="1ae84-110">此外，啟用此功能會導致這些已標記和加密的檔案支援 [自動儲存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 功能。</span><span class="sxs-lookup"><span data-stu-id="1ae84-110">In addition, enabling this functionality results in the [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality being supported for these labeled and encrypted files.</span></span>

<span data-ttu-id="1ae84-111">若要閱讀初始發行公告，請參閱這篇部落格文章：[宣佈在 Microsoft 資訊保護加密的文件上共同撰寫並標示更新](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-co-authoring-on-microsoft-information-protection/ba-p/2164162)。</span><span class="sxs-lookup"><span data-stu-id="1ae84-111">To read the initial release announcement, see the blog post [Announcing co-authoring on Microsoft Information Protection-encrypted documents and labeling updates](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-co-authoring-on-microsoft-information-protection/ba-p/2164162).</span></span>

## <a name="metadata-changes-for-sensitivity-labels"></a><span data-ttu-id="1ae84-112">敏感度標籤的中繼資料變更</span><span class="sxs-lookup"><span data-stu-id="1ae84-112">Metadata changes for sensitivity labels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae84-113">啟用共同撰寫的設定之後，未加密檔案的標籤資訊將不再儲存於自訂屬性中。</span><span class="sxs-lookup"><span data-stu-id="1ae84-113">After you enable the setting for co-authoring, labeling information for unencrypted files is no longer saved in custom properties.</span></span>
> 
> <span data-ttu-id="1ae84-114">如果使用任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="1ae84-114">Do not enable this setting if you use any apps, services, scripts, or tools that reads or writes labeling metadata to the old location.</span></span>

<span data-ttu-id="1ae84-115">在啟用設定以支援 Office 桌面應用程式共同撰寫之前，必須了解此動作會變更儲存至 Office 檔案和從 Office 檔案讀取的標籤中繼資料。</span><span class="sxs-lookup"><span data-stu-id="1ae84-115">Before you enable the setting to support co-authoring for Office desktop apps, it's important to understand that this action makes changes to the labeling metadata that is saved to and read from Office files.</span></span>

<span data-ttu-id="1ae84-116">標籤中繼資料包含可識別租用戶和已套用敏感度標籤的資訊。</span><span class="sxs-lookup"><span data-stu-id="1ae84-116">The labeling metadata includes information that identifies your tenant and applied sensitivity label.</span></span> <span data-ttu-id="1ae84-117">此設定所變更的是 Word、Excel 和 PowerPoint 檔案的中繼資料格式和位置。</span><span class="sxs-lookup"><span data-stu-id="1ae84-117">The change that this setting makes is the metadata format and location for Word, Excel, and PowerPoint files.</span></span> <span data-ttu-id="1ae84-118">您不需要對加密的檔案或電子郵件採取任何動作; 加密檔案的中繼資料變更是回溯相容，且電子郵件並沒有變更。</span><span class="sxs-lookup"><span data-stu-id="1ae84-118">You do not need to take any action for encrypted files or emails; the metadata change for encrypted files is backward-compatible and there are no changes for emails.</span></span> <span data-ttu-id="1ae84-119">不過，您必須注意可自動升級但並非回溯相容之加密檔案的中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="1ae84-119">However, you do need to be aware of the metadata changes for encrypted files that can be automatically upgraded but aren't backward-compatible.</span></span>

<span data-ttu-id="1ae84-120">此變更會影響新標記的檔案和已標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="1ae84-120">This change affects both files that are newly labeled and files that are already labeled.</span></span> <span data-ttu-id="1ae84-121">當您使用支援共同撰寫設定的應用程式和服務時：</span><span class="sxs-lookup"><span data-stu-id="1ae84-121">When you use apps and services that support the co-authoring setting:</span></span>
- <span data-ttu-id="1ae84-122">對於新標記的檔案，只會使用新的格式和位置來標記中繼資料。</span><span class="sxs-lookup"><span data-stu-id="1ae84-122">For files that are newly labeled, only the new format and location is used for the labeling metadata.</span></span>
- <span data-ttu-id="1ae84-123">對於已標記的檔案，下次開啟和儲存檔案時，如果檔案有舊格式和位置的中繼資料，它會複製到新的格式和位置。</span><span class="sxs-lookup"><span data-stu-id="1ae84-123">For files that are already labeled, the next time the file is opened and saved, if the file has metadata in the old format and location, it is copied to the new format and location.</span></span>

<span data-ttu-id="1ae84-124">您可以在下列資源中，閱讀有關此中繼資料變更的詳情：</span><span class="sxs-lookup"><span data-stu-id="1ae84-124">You can read more about this metadata change from the following resources:</span></span>

- <span data-ttu-id="1ae84-125">部落格文章：[Microsoft 資訊保護中繼資料儲存空間的近期變更](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span><span class="sxs-lookup"><span data-stu-id="1ae84-125">Blog post: [Upcoming Changes to Microsoft Information Protection Metadata Storage](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span></span>

- <span data-ttu-id="1ae84-126">開啟規格：[2.6.3 LabelInfo 與自訂檔案屬性](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span><span class="sxs-lookup"><span data-stu-id="1ae84-126">Open Specifications: [2.6.3 LabelInfo versus Custom Document Properties](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span></span>

<span data-ttu-id="1ae84-p104">由於這些變更，如果您的組織中有任何將標籤中繼資料讀取或寫入舊位置的應用程式、服務、指令碼或工具，請勿啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="1ae84-p104">Because of these changes, do not enable this setting if you have any apps, services, scripts, or tools in your organization that reads or writes labeling metadata to the old location. If you do, some example consequences:</span></span>

- <span data-ttu-id="1ae84-129">已標記的檔案會向使用者顯示為未標記</span><span class="sxs-lookup"><span data-stu-id="1ae84-129">A document that is labeled appears to users to be unlabeled</span></span>

- <span data-ttu-id="1ae84-130">檔案向使用者顯示過期的標籤</span><span class="sxs-lookup"><span data-stu-id="1ae84-130">A document displays an out-of-date label to users</span></span>

- <span data-ttu-id="1ae84-131">如果其他使用者在不支援新標籤中繼資料的 Office 桌面應用程式中開啟已標記和加密的檔案，共同撰寫和自動儲存將無法用於該檔案</span><span class="sxs-lookup"><span data-stu-id="1ae84-131">Co-authoring and AutoSave won't work for a labeled and encrypted document if another user has it open in an Office desktop app that doesn't support the new labeling metadata</span></span>

- <span data-ttu-id="1ae84-132">有一個 [將 Office 附件中的標籤識別為自訂屬性](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) 的 Exchange Online 郵件流程規則，其無法加密電子郵件和附件，或不正確地加密它們</span><span class="sxs-lookup"><span data-stu-id="1ae84-132">An Exchange Online mail flow rule that [identifies labels as custom properties in Office attachments](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) fails to encrypt the email and attachment, or incorrectly encrypts them</span></span>

<span data-ttu-id="1ae84-133">請查看下一節，以尋找支援此設定的應用程式和服務清單，以及標籤中繼資料的變更。</span><span class="sxs-lookup"><span data-stu-id="1ae84-133">Check the following section for a list of apps and services that support this setting and the changes to the labeling metadata.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ae84-134">必要條件</span><span class="sxs-lookup"><span data-stu-id="1ae84-134">Prerequisites</span></span>

<span data-ttu-id="1ae84-135">開啟此功能之前，請確定您了解下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="1ae84-135">Make sure you understand the following prerequisites before you turn on this feature.</span></span>

- <span data-ttu-id="1ae84-136">您必須是全域系統管理員才能開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="1ae84-136">You must be a global admin to turn on this feature.</span></span>

- <span data-ttu-id="1ae84-137">必須為租用戶啟用 [SharePoint 和 OneDrive 中 Office 檔案](sensitivity-labels-sharepoint-onedrive-files.md) 的敏感度標記。</span><span class="sxs-lookup"><span data-stu-id="1ae84-137">Sensitivity labels must be [enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) for the tenant.</span></span> <span data-ttu-id="1ae84-138">如果此功能尚未啟用，當您選取設定以開啟具有敏感度標籤的檔案共同撰寫時，就會自動啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="1ae84-138">If this feature isn't already enabled, it will be automatically enabled when you select the setting to turn on co-authoring for files with sensitivity labels.</span></span>

- <span data-ttu-id="1ae84-139">Microsoft 365 Apps 企業版：</span><span class="sxs-lookup"><span data-stu-id="1ae84-139">Microsoft 365 Apps for enterprise:</span></span>
    - <span data-ttu-id="1ae84-140">**Windows**：最低版本 2105：6 月 18</span><span class="sxs-lookup"><span data-stu-id="1ae84-140">**Windows**: Minimum version 2105: June 18</span></span>
    - <span data-ttu-id="1ae84-141">**macOS**：最小版本 16.50</span><span class="sxs-lookup"><span data-stu-id="1ae84-141">**macOS**: Minimum version 16.50</span></span>
    - <span data-ttu-id="1ae84-142">**iOS**：尚未支援</span><span class="sxs-lookup"><span data-stu-id="1ae84-142">**iOS**: Not yet supported</span></span>
    - <span data-ttu-id="1ae84-143">**Android**：尚未支援</span><span class="sxs-lookup"><span data-stu-id="1ae84-143">**Android**: Not yet supported</span></span>

- <span data-ttu-id="1ae84-144">您租用戶中所有的應用程式、服務和作業工具都必須支援新的應用程式 [標籤中繼資料](#metadata-changes-for-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="1ae84-144">All apps, services, and operational tools in your tenant must support the new [labeling metadata](#metadata-changes-for-sensitivity-labels).</span></span> <span data-ttu-id="1ae84-145">如果您使用下列任何一項，請檢查所需的最低版本：</span><span class="sxs-lookup"><span data-stu-id="1ae84-145">If you use any of the following, check the minimum versions required:</span></span>
    
    - <span data-ttu-id="1ae84-146">**Azure 資訊保護統一標籤用戶端和掃描：**</span><span class="sxs-lookup"><span data-stu-id="1ae84-146">**Azure Information Protection unified labeling client and scanner:**</span></span>
        - <span data-ttu-id="1ae84-147">可從 [Microsoft 下載中心](https://www.microsoft.com/en-us/download/details.aspx?id=53018)安裝的公開預覽版本 (AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe 的安裝名稱)</span><span class="sxs-lookup"><span data-stu-id="1ae84-147">A public preview version (installation name of AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe) that you can install from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=53018)</span></span>
    
    - <span data-ttu-id="1ae84-148">**適用於 Windows 或 macOS 的 OneDrive 同步處理應用程式：**</span><span class="sxs-lookup"><span data-stu-id="1ae84-148">**OneDrive sync app for Windows or macOS:**</span></span>
        - <span data-ttu-id="1ae84-149">最低版本 19.002.0121.0008</span><span class="sxs-lookup"><span data-stu-id="1ae84-149">Minimum version of 19.002.0121.0008</span></span>
    
    - <span data-ttu-id="1ae84-150">**端點資料外洩防護 (端點 DLP)：**</span><span class="sxs-lookup"><span data-stu-id="1ae84-150">**Endpoint data loss prevention (Endpoint DLP):**</span></span>
        - <span data-ttu-id="1ae84-151">Windows 10 1809 搭配 KB 4601383</span><span class="sxs-lookup"><span data-stu-id="1ae84-151">Windows 10 1809 with KB 4601383</span></span>
        - <span data-ttu-id="1ae84-152">Windows 10 1903 和 1909 搭配 KB 4601380</span><span class="sxs-lookup"><span data-stu-id="1ae84-152">Windows 10 1903 and 1909 with KB 4601380</span></span>
        - <span data-ttu-id="1ae84-153">Windows 10 2004 搭配 KB 4601382</span><span class="sxs-lookup"><span data-stu-id="1ae84-153">Windows 10 2004 with KB 4601382</span></span>
    
    - <span data-ttu-id="1ae84-154">**使用 Microsoft 資訊保護 SDK 的應用程式和服務：**</span><span class="sxs-lookup"><span data-stu-id="1ae84-154">**Apps and services that use the Microsoft Information Protection SDK:**</span></span> 
        - <span data-ttu-id="1ae84-155">最低版本 1.7</span><span class="sxs-lookup"><span data-stu-id="1ae84-155">Minimum version of 1.7</span></span> 

<span data-ttu-id="1ae84-p107">當您開啟此功能時，Microsoft 365 服務會自動支援新的標籤中繼資料。例如：</span><span class="sxs-lookup"><span data-stu-id="1ae84-p107">Microsoft 365 services automatically support the new labeling metadata when you turn on this feature. For example:</span></span>

- [<span data-ttu-id="1ae84-158">自動標籤原則</span><span class="sxs-lookup"><span data-stu-id="1ae84-158">Auto-labeling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [<span data-ttu-id="1ae84-159">使用敏感度標籤作為條件的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="1ae84-159">DLP policies that use sensitivity labels as conditions</span></span>](dlp-sensitivity-label-as-condition.md)
- [<span data-ttu-id="1ae84-160">Microsoft Cloud App Security 已設為套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="1ae84-160">Microsoft Cloud App Security configured to apply sensitivity labels</span></span>](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a><span data-ttu-id="1ae84-161">限制</span><span class="sxs-lookup"><span data-stu-id="1ae84-161">Limitations</span></span>

<span data-ttu-id="1ae84-162">在針對使用敏感度標籤加密的檔案啟用共同撰寫的租用戶設定之前，請確定您了解此功能的下列限制。</span><span class="sxs-lookup"><span data-stu-id="1ae84-162">Before you enable the tenant setting for co-authoring for files encrypted with sensitivity labels, make sure you understand the following limitations of this feature.</span></span>

- <span data-ttu-id="1ae84-163">由於 [標籤中繼資料變更](#metadata-changes-for-sensitivity-labels)，您租用戶中所有的應用程式、服務和作業工具都必須支援新的標籤中繼資料，以得到一致且可靠的標籤體驗。</span><span class="sxs-lookup"><span data-stu-id="1ae84-163">Because of the [labeling metadata changes](#metadata-changes-for-sensitivity-labels), all apps, services, and operational tools in your tenant must support the new labeling metadata for a consistent and reliable labeling experience.</span></span>
    
    <span data-ttu-id="1ae84-164">Excel 專用：如果有人使用不支援敏感度標籤中繼資料變更的 Excel 版本來編輯並保存該檔案，則不應用加密的敏感度標籤中繼資料可以從檔案中刪除。</span><span class="sxs-lookup"><span data-stu-id="1ae84-164">Specific to Excel: Metadata for a sensitivity label that doesn't apply encryption can be deleted from a file if somebody edits and saves that file by using a version of Excel that doesn't support the metadata changes for sensitivity labels.</span></span>

- <span data-ttu-id="1ae84-165">不支援共同撰寫和自動儲存，且無法用於使用下列任何 [加密設定](encryption-sensitivity-labels.md#configure-encryption-settings) 的已標記和加密的 Office 檔案：</span><span class="sxs-lookup"><span data-stu-id="1ae84-165">Co-authoring and AutoSave aren't supported and don't work for labeled and encrypted Office documents that use any of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="1ae84-166">**讓使用者在套用標籤時指派權限**，且核取方塊 **在 Word、PowerPoint 與 Excel 中提示使用者指定權限** 為選取狀態。</span><span class="sxs-lookup"><span data-stu-id="1ae84-166">**Let users assign permissions when they apply the label** and the checkbox **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="1ae84-167">此設定有時稱為「使用者定義的權限」。</span><span class="sxs-lookup"><span data-stu-id="1ae84-167">This configuration is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="1ae84-168">**使用者的內容存取權到期日** 設定為 **永不** 以外的值。</span><span class="sxs-lookup"><span data-stu-id="1ae84-168">**User access to content expires** is set to a value other than **Never**.</span></span>
    - <span data-ttu-id="1ae84-169">**使用雙重金鑰加密** 已選取。</span><span class="sxs-lookup"><span data-stu-id="1ae84-169">**Double Key Encryption** is selected.</span></span>
    
    <span data-ttu-id="1ae84-170">對於具有這些加密設定的標籤，標籤會顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="1ae84-170">For labels with any of these encryption configurations, the labels display in Office apps.</span></span> <span data-ttu-id="1ae84-171">不過，當使用者選取這些標籤，且沒有其他人在編輯檔案時，系統會警告他們共同撰寫和自動儲存將無法使用。</span><span class="sxs-lookup"><span data-stu-id="1ae84-171">However, when users select these labels and nobody else is editing the document, they are warned that co-authoring and AutoSave won't be available.</span></span> <span data-ttu-id="1ae84-172">如果有其他人在編輯文件，使用者會看到「無法套用這些標籤」的訊息。</span><span class="sxs-lookup"><span data-stu-id="1ae84-172">If somebody else is editing the document, users see a message that the labels can't be applied.</span></span>

- <span data-ttu-id="1ae84-173">如果您使用 Azure 資訊保護統一標籤用戶端：請查看此標籤用戶端的文件，以取得[更多需求或限制](/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview)。</span><span class="sxs-lookup"><span data-stu-id="1ae84-173">If you use the Azure Information Protection unified labeling client: Check the documentation for this labeling client for [more requirements or limitations](/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview).</span></span>

## <a name="known-issues-for-this-preview"></a><span data-ttu-id="1ae84-174">此預覽的已知問題</span><span class="sxs-lookup"><span data-stu-id="1ae84-174">Known issues for this preview</span></span>

<span data-ttu-id="1ae84-175">此預覽版使用敏感度標籤加密的檔案共同撰寫有下列已知問題：</span><span class="sxs-lookup"><span data-stu-id="1ae84-175">This preview version of co-authoring for files encrypted with sensitivity labels has the following known issues:</span></span>

- <span data-ttu-id="1ae84-176">使用者無法針對大於 300 MB 的 Word、Excel 和 PowerPoint 檔案，在 Office 網頁版中為任何的檔案套用任何標籤。</span><span class="sxs-lookup"><span data-stu-id="1ae84-176">Users won't be able to apply any labels in Office for the web for Word, Excel, and PowerPoint files that are bigger than 300 MB.</span></span> <span data-ttu-id="1ae84-177">對於這些檔案，您可以使用 Office 桌面應用程式來套用標籤，但您必須是唯一開啟檔案的人。</span><span class="sxs-lookup"><span data-stu-id="1ae84-177">For these files, you can use the Office desktop apps to apply a label but you must be the only person who has the file open.</span></span>

- <span data-ttu-id="1ae84-178">當您使用 [將敏感度標籤作為條件的 DLP](dlp-sensitivity-label-as-condition.md) 時，電子郵件的未加密附件不受支援。</span><span class="sxs-lookup"><span data-stu-id="1ae84-178">When you use [DLP policies that use sensitivity labels as conditions](dlp-sensitivity-label-as-condition.md), unencrypted attachments for emails are not supported.</span></span>

- <span data-ttu-id="1ae84-179">某些文件由於 [密碼保護](https://support.microsoft.com/office/require-a-password-to-open-or-modify-a-workbook-10579f0e-b2d9-4c05-b9f8-4109a6bce643)、 [共用活頁簿](https://support.microsoft.com/office/about-the-shared-workbook-feature-49b833c0-873b-48d8-8bf2-c1c59a628534)，或包含 ActiveX 控制項內容等功能，而與敏感度標籤不相容。</span><span class="sxs-lookup"><span data-stu-id="1ae84-179">Some documents are incompatible with sensitivity labels because of features such as [password-protection](https://support.microsoft.com/office/require-a-password-to-open-or-modify-a-workbook-10579f0e-b2d9-4c05-b9f8-4109a6bce643), [shared workbooks](https://support.microsoft.com/office/about-the-shared-workbook-feature-49b833c0-873b-48d8-8bf2-c1c59a628534), or content that includes ActiveX controls.</span></span> <span data-ttu-id="1ae84-180">其他原因會記錄在 [在 Office 中共同撰寫的疑難排解](https://support.microsoft.com/office/troubleshoot-co-authoring-in-office-bd481512-3f3a-4b6d-b7eb-ebf9d3626ae7)。</span><span class="sxs-lookup"><span data-stu-id="1ae84-180">Other reasons are documented in [Troubleshoot co-authoring in Office](https://support.microsoft.com/office/troubleshoot-co-authoring-in-office-bd481512-3f3a-4b6d-b7eb-ebf9d3626ae7).</span></span> <span data-ttu-id="1ae84-181">針對這些文件，您會看到 **[上傳失敗]** 訊息，且應選取 **[捨棄變更]** 選項。</span><span class="sxs-lookup"><span data-stu-id="1ae84-181">For these documents, you see a message **UPLOAD FAILED** and should select the **Discard Changes** option.</span></span> <span data-ttu-id="1ae84-182">在解決此問題之前，請勿標記這些以此失敗訊息識別的文件。</span><span class="sxs-lookup"><span data-stu-id="1ae84-182">Until this issue is addressed, do not label these documents that are identified with this failure message.</span></span>

- <span data-ttu-id="1ae84-183">不支援 iOS 版和 Android 版 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ae84-183">Office apps for iOS and Android are not supported.</span></span>

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a><span data-ttu-id="1ae84-184">如何啟用具有敏感度標籤的檔案共同撰寫</span><span class="sxs-lookup"><span data-stu-id="1ae84-184">How to enable co-authoring for files with sensitivity labels</span></span>

> [!CAUTION]
> <span data-ttu-id="1ae84-p112">開啟此設定是單向動作。此功能為預覽版時，請只在您閱讀並了解中繼資料變更、必要條件、限制，以及此頁面上記錄的任何已知問題之後，再加以啟用。</span><span class="sxs-lookup"><span data-stu-id="1ae84-p112">Turning on this setting is a one-way action. While the feature is in preview, enable it only after you have read and understood the metadata changes, prerequisites, limitations, and any known issues documented on this page.</span></span>

1. <span data-ttu-id="1ae84-187">以租用戶全域系統管理員的身分登入 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1ae84-187">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global admin for your tenant.</span></span>

2. <span data-ttu-id="1ae84-188">在瀏覽窗格中，選取 **[設定]** > **[共同撰寫具有敏感度等級的檔案]**。</span><span class="sxs-lookup"><span data-stu-id="1ae84-188">From the navigation pane, select **Settings** > **Co-authoring for files with sensitivity files**.</span></span>

2. <span data-ttu-id="1ae84-189">在 **共同撰寫包含敏感度標籤的檔案 (預覽)** 頁面上，閱讀摘要描述、必要條件、預期項目，以及開啟此設定後無法關閉的警告。</span><span class="sxs-lookup"><span data-stu-id="1ae84-189">On the **Co-authoring for files with sensitivity labels (preview)** page, read the summary description, prerequisites, what to expect, and the warning that you can't turn off this setting after you've turned it on.</span></span>
    
    <span data-ttu-id="1ae84-190">然後依序選取 **開啟具有敏感度標籤的檔案共同撰寫** 以及 **套用**：</span><span class="sxs-lookup"><span data-stu-id="1ae84-190">Then select **Turn on co-authoring for files with sensitivity labels**, and **Apply**:</span></span>
    
    ![開啟具有敏感度標籤之檔案共同撰寫的選項](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. <span data-ttu-id="1ae84-192">在您使用這項新功能進行共同撰寫之前，請等候 24 小時，讓此設定在整個環境中進行複製。</span><span class="sxs-lookup"><span data-stu-id="1ae84-192">Wait 24 hours for this setting to replicate across your environment before you use this new feature for co-authoring.</span></span>

## <a name="contact-support-if-you-need-to-disable-this-feature"></a><span data-ttu-id="1ae84-193">如果您需要停用此功能，請聯絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="1ae84-193">Contact Support if you need to disable this feature</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae84-194">如果您需要停用此功能，請注意標籤資訊可能會遺失。</span><span class="sxs-lookup"><span data-stu-id="1ae84-194">If you do need to disable this feature, be aware that labeling information can be lost.</span></span>

<span data-ttu-id="1ae84-195">為租用戶啟用具有敏感度標籤的檔案共同撰寫之後，您無法自己停用此設定。</span><span class="sxs-lookup"><span data-stu-id="1ae84-195">After you've enabled co-authoring for files with sensitivity labels for your tenant, you can't disable this setting yourself.</span></span> <span data-ttu-id="1ae84-196">這就是為什麼在啟用此設定之前，務必先查看並了解必要條件、結果和限制。</span><span class="sxs-lookup"><span data-stu-id="1ae84-196">That's why it's so important that you check and understand the prerequisites, consequences, and limitations before you enable this setting.</span></span>

![顯示已針對敏感度標籤開啟共同撰寫的選項](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

<span data-ttu-id="1ae84-198">正如您在此設定開啟時從螢幕擷取畫面中所看到的一樣，您可以聯絡 [Microsoft 支援服務](../business-video/get-help-support.md) 並要求關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="1ae84-198">As you see from the screenshot when this setting has been turned on, you can contact [Microsoft Support](../business-video/get-help-support.md) and request to turn off this setting.</span></span> <span data-ttu-id="1ae84-199">此要求可能需要數天的時間，您必須證明您為租用戶全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1ae84-199">This request might take several days and you will need to prove that you are a global administrator for your tenant.</span></span> <span data-ttu-id="1ae84-200">預期需要支付一般支援費用。</span><span class="sxs-lookup"><span data-stu-id="1ae84-200">Expect usual support charges to apply.</span></span> 

<span data-ttu-id="1ae84-201">如果支援工程師針對您的租用戶停用此設定：</span><span class="sxs-lookup"><span data-stu-id="1ae84-201">If a support engineer disables this setting for your tenant:</span></span>

- <span data-ttu-id="1ae84-202">對於支援新標籤中繼資料的應用程式和服務，現在當讀取或儲存標籤時，它們會還原為原始的中繼資料格式和位置。</span><span class="sxs-lookup"><span data-stu-id="1ae84-202">For apps and services that support the new labeling metadata, they now revert to the original metadata format and location when labels are read or saved.</span></span>

- <span data-ttu-id="1ae84-203">啟用設定時所使用的 Office 檔的新中繼資料格式和位置將不會複製到原始格式和位置。</span><span class="sxs-lookup"><span data-stu-id="1ae84-203">The new metadata format and location for Office documents that were used while the setting was enabled will not be copied to the original format and location.</span></span> <span data-ttu-id="1ae84-204">因此，未加密 Word、Excel 和 PowerPoint 檔案的此標籤資訊將會遺失。</span><span class="sxs-lookup"><span data-stu-id="1ae84-204">As a result, this labeling information for unencrypted Word, Excel, and PowerPoint files will be lost.</span></span>

- <span data-ttu-id="1ae84-205">對於已標籤和已加密的文件，共同撰寫和自動儲存無法再於您的租用戶中使用。</span><span class="sxs-lookup"><span data-stu-id="1ae84-205">Co-authoring and AutoSave no longer work in your tenant for labeled and encrypted documents.</span></span>

- <span data-ttu-id="1ae84-206">在 OneDrive 和 SharePoint 中，Office 檔案的敏感度標籤仍維持啟用。</span><span class="sxs-lookup"><span data-stu-id="1ae84-206">Sensitivity labels remain enabled for Office files in OneDrive and SharePoint.</span></span>