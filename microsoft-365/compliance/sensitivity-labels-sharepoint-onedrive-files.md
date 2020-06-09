---
title: 對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理員可以在 SharePoint 和 OneDrive 中啟用 Word、Excel 及 PowerPoint 檔案的敏感度標籤支援。
ms.openlocfilehash: 0ad4381d4a4004d89dd35aa59098f26d8f12dd56
ms.sourcegitcommit: bc17d4b2197dd60cdff7c9349bbe19eeaac85ac2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604308"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a><span data-ttu-id="0aa7a-103">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="0aa7a-103">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>

><span data-ttu-id="0aa7a-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="0aa7a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0aa7a-105">在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤之前，您無法將您的[靈敏度卷](sensitivity-labels.md)標套用至網頁上的 office。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-105">Before you enable sensitivity labels for Office files in SharePoint and OneDrive, you can't apply your [sensitivity labels](sensitivity-labels.md) in Office on the web.</span></span> <span data-ttu-id="0aa7a-106">您不會在功能區上看到 [**靈敏度**] 按鈕，或在狀態列上看到已套用的標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-106">You don't see the **Sensitivity** button on the ribbon, or the applied label name on the status bar.</span></span> <span data-ttu-id="0aa7a-107">此外，如果您使用桌面應用程式來標示您的檔案，然後將檔案儲存在 SharePoint 或 OneDrive 上，如果標籤已套用加密，服務就無法處理這些檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-107">In addition, if you use desktop apps to label your files and then save them on SharePoint or OneDrive, the service can't process the content of these files if the label applied encryption.</span></span> <span data-ttu-id="0aa7a-108">在這些情況下，合著、eDiscovery、資料遺失防護、搜尋及其他協同功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-108">Coauthoring, eDiscovery, Data Loss Prevention, search, and other collaborative features won't work under these circumstances.</span></span>

<span data-ttu-id="0aa7a-109">當您在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤時，會啟用所有這些功能。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-109">When you do enable sensitivity labels for Office files in SharePoint and OneDrive, all these capabilities are enabled.</span></span> <span data-ttu-id="0aa7a-110">除了為使用者顯示敏感度標籤之外，針對已套用敏感度標籤（包含以雲端為基礎的金鑰進行加密）的新檔和變更的檔案：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-110">In addition to displaying sensitivity labels to users, for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="0aa7a-111">SharePoint 會辨識套用至 Word、Excel 及 PowerPoint 檔案中 SharePoint 及 OneDrive 的敏感度標籤：當檔案儲存在 SharePoint 中時，會移除來自 Azure 資訊保護的加密，以便處理檔案內容。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-111">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed.</span></span> <span data-ttu-id="0aa7a-112">如需如何在 SharePoint 儲存檔時保護檔的相關資訊，請參閱[OneDrive For Business and SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-112">For information about how documents are protected while they are stored in SharePoint, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>

- <span data-ttu-id="0aa7a-113">當您從 SharePoint 或 OneDrive 中下載或存取此檔案時，標籤的靈敏度標籤及標籤的任何加密設定會重新與檔案一起使用，而且在儲存檔的任何地方都會保留這些設定的強制執行。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-113">When you download or access this file from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span> <span data-ttu-id="0aa7a-114">由於這種行為，請確定您提供的使用者指引只使用標籤來保護檔。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-114">Because of this behavior, ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="0aa7a-115">如需詳細資訊，請參閱[資訊版權管理（IRM）選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-115">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="0aa7a-116">若要 SharePoint 在上傳時從檔案中移除加密，上傳已標記及已加密檔案的使用者，必須至少要有查看檔案的使用許可權。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-116">For SharePoint to remove the encryption from the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="0aa7a-117">如果使用者無法在 SharePoint 外開啟檔案，SharePoint 不會從檔案中移除加密。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-117">SharePoint doesn't remove encryption from files if the user can't open them outside SharePoint.</span></span>

- <span data-ttu-id="0aa7a-118">使用網頁上的 Office （Word、Excel、PowerPoint）開啟及編輯具有敏感度標籤的 Office 檔案，以套用加密。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-118">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="0aa7a-119">會強制執行以加密指派的許可權。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-119">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="0aa7a-120">透過網頁上的 Word，您也可以在編輯這些檔時使用自動標籤。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-120">With Word on the web, you can also use auto-labeling when you edit these documents.</span></span>

- <span data-ttu-id="0aa7a-121">外部使用者可以使用 guest 帳戶存取以加密標記的檔。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-121">External users can access documents that are labeled with encryption by using guest accounts.</span></span> <span data-ttu-id="0aa7a-122">如需詳細資訊，請參閱[對外部使用者的支援和標示的內容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-122">For more information, see [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).</span></span> 

- <span data-ttu-id="0aa7a-123">Office 365 eDiscovery 支援這些檔案的全文搜尋。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-123">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="0aa7a-124">資料遺失防護（DLP）原則涵蓋這些檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-124">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa7a-125">若尚未使用雲端型金鑰（內部部署金鑰）套用加密，通常稱為「保留您自己的金鑰」（HYOK）的金鑰管理拓撲，處理檔內容的 SharePoint 行為不會改變。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-125">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior for processing the file contents doesn't change.</span></span>
>
> <span data-ttu-id="0aa7a-126">SharePoint 行為也不會變更 SharePoint 中的現有標籤和加密檔。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-126">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint.</span></span> <span data-ttu-id="0aa7a-127">為了讓這些檔案受益于新功能，在您執行此命令以啟用 SharePoint 和 OneDrive 的靈敏度標籤之後，必須下載並上傳或編輯這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-127">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you run the command to enable sensitivity labels for SharePoint and OneDrive.</span></span> <span data-ttu-id="0aa7a-128">例如，他們會在搜尋和 eDiscovery 結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-128">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="0aa7a-129">在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會有三個新的[審計事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)可用於監視 SharePoint 和 OneDrive 中的檔之敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-129">After you enable sensitivity labels for Office files in SharePoint and OneDrive, three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied to documents in SharePoint and OneDrive:</span></span>
- <span data-ttu-id="0aa7a-130">**已將敏感度標籤套用到檔案**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-130">**Applied sensitivity label to file**</span></span>
- <span data-ttu-id="0aa7a-131">**已變更套用到檔案的敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-131">**Changed sensitivity label applied to file**</span></span>
- <span data-ttu-id="0aa7a-132">**已將敏感度標籤從檔案移除**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-132">**Removed sensitivity label from file**</span></span>

<span data-ttu-id="0aa7a-133">觀賞下列影片（無音訊），以查看動作中的新功能：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-133">Watch the following video (no audio) to see the new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

<span data-ttu-id="0aa7a-134">在 SharePoint 和 OneDrive 中，您可以隨時停用 Office 檔案的靈敏度標籤（隨時[自願退出）](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-134">You always have the choice to disable sensitivity labels for Office files in SharePoint and OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) at any time.</span></span>

<span data-ttu-id="0aa7a-135">如果您目前使用 SharePoint 資訊版權管理（IRM）保護 SharePoint 中的檔，請務必檢查此頁面上的 [ [SharePoint 資訊版權管理（irm）和敏感度標籤](#sharepoint-information-rights-management-irm-and-sensitivity-labels)] 區段。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-135">If you are currently protecting documents in SharePoint by using SharePoint Information Rights Management (IRM), be sure to check the [SharePoint Information Rights Management (IRM) and sensitivity labels](#sharepoint-information-rights-management-irm-and-sensitivity-labels) section on this page.</span></span> 

## <a name="requirements"></a><span data-ttu-id="0aa7a-136">需求</span><span class="sxs-lookup"><span data-stu-id="0aa7a-136">Requirements</span></span>

<span data-ttu-id="0aa7a-137">這些新功能僅適用于[敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-137">These new capabilities work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="0aa7a-138">如果您目前已具備 Azure 資訊保護標籤，請先將它們遷移至靈敏度標籤，讓您可以針對您上傳的新檔案啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-138">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="0aa7a-139">如需相關指示，請參閱 how [to 將 Azure 資訊保護標籤遷移至統一敏感度標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="0aa7a-139">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="0aa7a-140">使用 Windows 上的 OneDrive 同步處理應用程式版本19.002.0121.0008 或更新版本，以及 Mac 版19.002.0107.0008 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-140">Use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="0aa7a-141">這兩個版本都發行于2019年1月28日，而且目前已發佈給所有的振鈴。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-141">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="0aa7a-142">如需詳細資訊，請參閱[OneDrive 發行附注](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-142">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="0aa7a-143">在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會提示執行舊版本的 sync 應用程式的使用者進行更新。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-143">After you enable sensitivity labels for Office files in SharePoint and OneDrive, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="0aa7a-144">限制</span><span class="sxs-lookup"><span data-stu-id="0aa7a-144">Limitations</span></span>

- <span data-ttu-id="0aa7a-145">SharePoint 不會自動將敏感度標籤套用至您已使用 Azure 資訊保護標籤加密的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-145">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="0aa7a-146">相反地，若要在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，取得功能，請完成下列工作：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-146">Instead, to get the features to work after you enable sensitivity labels for Office files in SharePoint and OneDrive, complete these tasks:</span></span>
    
    1. <span data-ttu-id="0aa7a-147">確定您已將[Azure 資訊保護標籤遷移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)至靈敏度標籤，並已從 Microsoft 365 規範中心（或對等標上的標記系統管理中心）[發行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-147">Make sure you have [migrated the Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) to sensitivity labels and [published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="0aa7a-148">下載檔案，然後將檔案上傳至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-148">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="0aa7a-149">當套用加密的標籤有下列兩種[加密](encryption-sensitivity-labels.md#configure-encryption-settings)設定時，SharePoint 無法處理加密的檔案：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-149">SharePoint can't process encrypted files when the label that applied the encryption has either of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="0aa7a-150">**讓使用者在套用標籤**和 [ **Word、PowerPoint 及 Excel 中**的核取方塊時，指定許可權，並選取 [提示使用者指定許可權]。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-150">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="0aa7a-151">此設定有時稱為「使用者定義的許可權」。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-151">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="0aa7a-152">對**內容到期的使用者存取權**設定為**永不**值以外的值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-152">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="0aa7a-153">如果是具有上述任一種加密設定的標籤，則網頁上的 Office 使用者不會看到標籤。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-153">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="0aa7a-154">此外，新功能也無法與已有這些加密設定的已標記檔一起使用。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-154">Additionally, the new capabilities can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="0aa7a-155">例如，即使更新這些檔，這些檔也不會在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-155">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="0aa7a-156">針對授與使用者編輯許可權的加密檔，在 Office 應用程式的 web 版本中無法封鎖複製。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-156">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="0aa7a-157">不支援 Azure 資訊保護檔追蹤網站。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-157">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="0aa7a-158">Office 桌面應用程式和行動應用程式不支援共同撰寫以加密標示的檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-158">Office desktop apps and mobile apps don't support coauthoring for files that are labeled with encryption.</span></span> <span data-ttu-id="0aa7a-159">這些應用程式會繼續以獨佔編輯模式開啟標籤和加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-159">These apps continue to open labeled and encrypted files in exclusive editing mode.</span></span>

- <span data-ttu-id="0aa7a-160">如果系統管理員變更已套用至使用者同步處理用戶端之檔案的已發行標籤設定，則使用者可能無法在其 OneDrive Sync 資料夾中儲存對檔案所做的變更。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-160">If an admin changes settings for a published label that's already applied to files downloaded to users' sync client, users might be unable to save changes they make to the file in their OneDrive Sync folder.</span></span> <span data-ttu-id="0aa7a-161">此案例適用于以加密標示標籤的檔案，也就是從沒有套用加密標籤的標籤所做的標籤變更時。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-161">This scenario applies to files that are labeled with encryption, and also when the label change is from a label that didn't apply encryption to a label that does apply encryption.</span></span> <span data-ttu-id="0aa7a-162">使用者看到[紅色圓圈時出現白色的交叉圖示錯誤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，並且要求您將新的變更儲存為個別的副本。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-162">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span> <span data-ttu-id="0aa7a-163">相反地，他們可以關閉並重新開啟檔案，或在網頁上使用 Office。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-163">Instead, they can close and reopen the file, or use Office on the web.</span></span>

- <span data-ttu-id="0aa7a-164">如果已標示的檔上傳至 SharePoint，而標籤是使用服務主體名稱中的帳戶來套用加密，則無法在網頁上的 Office 中開啟該檔。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-164">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="0aa7a-165">範例案例包括 Microsoft Cloud App Security，以及透過電子郵件傳送給小組的檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-165">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="0aa7a-166">使用者可能會在離線或轉入睡眠模式後遇到儲存問題，而不是使用 web Office 時，他們會使用桌面和行動應用程式進行 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-166">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="0aa7a-167">針對這些使用者，當他們繼續其 Office 應用程式會話並嘗試儲存變更時，會看到上傳失敗訊息，並有一個選項可儲存副本，而不是儲存原始檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-167">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="0aa7a-168">以下列方式加密的檔無法在 web 上的 Office 中開啟：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-168">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="0aa7a-169">使用內部部署機碼的加密（「保留您自己的金鑰」或 HYOK）</span><span class="sxs-lookup"><span data-stu-id="0aa7a-169">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="0aa7a-170">獨立于標籤所套用的加密，例如直接套用 Rights Management protection 範本。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-170">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="0aa7a-171">如果您刪除的標籤已套用至 SharePoint 中的檔，而不是從適當的標籤原則中移除標籤，則下載的檔不會標示或加密。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-171">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="0aa7a-172">相比之下，如果標籤的檔儲存在 SharePoint 之外，當標籤刪除時，該檔仍會保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-172">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="0aa7a-173">請注意，雖然您可以在測試階段刪除標籤，但很少需要在實際執行環境中刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-173">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a><span data-ttu-id="0aa7a-174">如何啟用 SharePoint 和 OneDrive 的敏感度標籤（自願加入）</span><span class="sxs-lookup"><span data-stu-id="0aa7a-174">How to enable sensitivity labels for SharePoint and OneDrive (opt-in)</span></span>

<span data-ttu-id="0aa7a-175">您可以使用 Microsoft 365 規範中心或使用 PowerShell 來啟用新功能。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-175">You can enable the new capabilities by using the Microsoft 365 compliance center, or by using PowerShell.</span></span>

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="0aa7a-176">使用規範中心來啟用敏感度標籤支援</span><span class="sxs-lookup"><span data-stu-id="0aa7a-176">Use the compliance center to enable support for sensitivity labels</span></span>

<span data-ttu-id="0aa7a-177">這個選項是為 SharePoint 和 OneDrive 啟用敏感度標籤的最簡單方式。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-177">This option is the easiest way to enable sensitivity labels for SharePoint and OneDrive.</span></span>

<span data-ttu-id="0aa7a-178">組織的全域系統管理員擁有建立及管理敏感度標籤所有層面的完整權限。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-178">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="0aa7a-179">如果您未以全域系統管理員身分登入，請參閱[建立和管理敏感度標籤所需的權限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-179">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

1. <span data-ttu-id="0aa7a-180">登入[Microsoft 365 規範中心](https://compliance.microsoft.com/)，並流覽至**解決方案**  >  **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-180">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com/), and navigate to **Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="0aa7a-181">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-181">If you don't immediately see this option, first select **Show all**.</span></span> 

2. <span data-ttu-id="0aa7a-182">如果您看到可在 Office online 檔案中處理內容之功能的訊息，請選取 [**立即開啟**]：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-182">If you see a message to turn on the ability to process content in Office online files, select **Turn on now**:</span></span>
    
    ![開啟 [立即開啟] 按鈕，以啟用 Office Online 的敏感度標籤](../media/sensitivity-labels-turn-on-banner.png)
    
    <span data-ttu-id="0aa7a-184">命令會立即執行，並在下一次重新整理頁面時，您就不會再看到訊息或按鈕。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-184">The command runs immediately and when the page is next refreshed, you no longer see the message or button.</span></span> 

> [!NOTE]
> <span data-ttu-id="0aa7a-185">如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的功能。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-185">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable these capabilities for all your geo-locations.</span></span> <span data-ttu-id="0aa7a-186">如需詳細資料，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-186">See the next section for details.</span></span>

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="0aa7a-187">使用 PowerShell 啟用敏感度標籤支援</span><span class="sxs-lookup"><span data-stu-id="0aa7a-187">Use PowerShell to enable support for sensitivity labels</span></span>

<span data-ttu-id="0aa7a-188">除了使用規範中心之外，您還可以使用[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 從 SharePoint 線上 PowerShell 中，啟用敏感度標籤支援。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-188">As an alternative to using the compliance center, you can enable support for sensitivity labels by using the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet from SharePoint Online PowerShell.</span></span> 

<span data-ttu-id="0aa7a-189">如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的支援。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-189">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable this support for all your geo-locations.</span></span>

#### <a name="prepare-the-sharepoint-online-management-shell"></a><span data-ttu-id="0aa7a-190">準備 SharePoint 線上管理命令介面</span><span class="sxs-lookup"><span data-stu-id="0aa7a-190">Prepare the SharePoint Online Management Shell</span></span>

<span data-ttu-id="0aa7a-191">在您執行 PowerShell 命令以啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤之前，請確定您執行 SharePoint 線上管理命令介面版本16.0.19418.12000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-191">Before you run the PowerShell command to enable sensitivity labels for Office files in SharePoint and OneDrive, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or later.</span></span> <span data-ttu-id="0aa7a-192">如果您已有最新版本，則可以略過[下一個](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)程式執行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-192">If you already have the latest version, you can skip to [next procedure](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) to run the PowerShell command.</span></span>

1. <span data-ttu-id="0aa7a-193">如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-193">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="0aa7a-194">或者，如果您已從 Microsoft 下載中心安裝舊版的 SharePoint Online 管理命令介面，您也可以移至 [**新增或移除程式**]，並卸載 SharePoint 線上管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-194">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="0aa7a-195">在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-195">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="0aa7a-196">選取語言，然後按一下 [下載]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-196">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="0aa7a-197">在 x64 和 x86 .msi 檔案之間選擇。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-197">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="0aa7a-198">如果您執行的是64位版本的 Windows 或 x86 檔案（如果您執行32位版本），請下載 x64 檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-198">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="0aa7a-199">如果您不知道，請參閱[我要執行哪一個 Windows 作業系統版本？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="0aa7a-199">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>

6. <span data-ttu-id="0aa7a-200">下載檔案之後，請執行檔，然後依照安裝精靈中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-200">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="0aa7a-201">執行 PowerShell 命令以啟用敏感度標籤支援</span><span class="sxs-lookup"><span data-stu-id="0aa7a-201">Run the PowerShell command to enable support for sensitivity labels</span></span>

<span data-ttu-id="0aa7a-202">若要啟用新功能，請搭配使用[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 搭配*EnableAIPIntegration*參數：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-202">To enable the new capabilities, use the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *EnableAIPIntegration* parameter:</span></span>

1. <span data-ttu-id="0aa7a-203">在 Microsoft 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-203">Using a work or school account that has global administrator or SharePoint admin privileges in Microsoft 365, connect to SharePoint.</span></span> <span data-ttu-id="0aa7a-204">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-204">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
    
    <span data-ttu-id="0aa7a-205">附注：如果您有 Microsoft 365 多地理位置，請搭配使用-Url 參數和[Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，並指定其中一個地理位置的 [SharePoint] 線上管理中心網站 Url。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-205">Note: If you have Microsoft 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="0aa7a-206">執行下列命令，然後按**Y**確認：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-206">Run the following command and press **Y** to confirm:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. <span data-ttu-id="0aa7a-207">針對 Microsoft 365 多地理位置：針對您餘下的地理位置重複步驟1和2。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-207">For Microsoft 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="0aa7a-208">在您建立或變更靈敏度標籤之後排程部署</span><span class="sxs-lookup"><span data-stu-id="0aa7a-208">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="0aa7a-209">在 Microsoft 365 規範中心內建立或變更靈敏度標籤之後，請分階段發佈。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-209">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="0aa7a-210">如果您發佈尚未完全同步處理的標籤，當使用者將標籤套用至檔案，並將其上傳至 SharePoint 時，就無法在網頁版的 Office 應用程式中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-210">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="0aa7a-211">搜尋和 eDiscovery 也不適用於檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-211">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="0aa7a-212">我們建議您遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-212">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="0aa7a-213">僅將新的或修改過的敏感度標籤發佈給一或兩個人。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-213">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="0aa7a-214">在初始出版物過後等候至少24小時。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-214">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="0aa7a-215">確認標籤已完全同步處理。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-215">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="0aa7a-216">更廣泛地發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-216">Publish the label more broadly.</span></span>

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a><span data-ttu-id="0aa7a-217">SharePoint 資訊版權管理（IRM）和敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="0aa7a-217">SharePoint Information Rights Management (IRM) and sensitivity labels</span></span>

<span data-ttu-id="0aa7a-218">[SharePoint 資訊版權管理（IRM）](set-up-irm-in-sp-admin-center.md)是一種較舊的技術，可在下載檔案時套用加密和限制，以保護清單和文件庫層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-218">[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) is an older technology to protect files at the list and library level by applying encryption and restrictions when files are downloaded.</span></span> <span data-ttu-id="0aa7a-219">這種舊版保護技術的設計是為了防止未經授權的使用者在 SharePoint 之外的地方開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-219">This older protection technology is designed to prevent unauthorized users from opening the file while it's outside SharePoint.</span></span>

<span data-ttu-id="0aa7a-220">在比較中，敏感度標籤會提供視覺標記（標頭、頁尾、浮水印）的保護設定，以及加密。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-220">In comparison, sensitivity labels provide the protection settings of visual markings (headers, footers, watermarks) in addition to encryption.</span></span> <span data-ttu-id="0aa7a-221">加密設定支援所有的[使用權力](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)，以限制使用者可對內容執行的動作，[許多案例](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)也支援相同的靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-221">The encryption settings support the full range of [usage rights](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) to restrict what users can do with the content, and the same sensitivity labels are supported for [many scenarios](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels).</span></span> <span data-ttu-id="0aa7a-222">在不同的工作負載和應用程式中使用具有一致設定的相同保護方法，會產生一致的保護原則。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-222">Using the same protection method with consistent settings across workloads and apps results in a consistent protection strategy.</span></span>

<span data-ttu-id="0aa7a-223">不過，您可以同時使用這兩種保護解決方案，行為如下：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-223">However, you can use both protection solutions together and the behavior is as follows:</span></span> 

- <span data-ttu-id="0aa7a-224">如果您上傳的檔案包含套用加密的靈敏度標籤，則不會移除加密，因此不支援這些檔案、合著、eDiscovery、DLP 和 search。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-224">If you upload a file with a sensitivity label that applies encryption, the encryption is not removed so for these files, coauthoring, eDiscovery, DLP, and search are not supported.</span></span>

- <span data-ttu-id="0aa7a-225">如果您使用 web 上的 Office 來標記檔案，則會強制執行標籤的任何加密設定。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-225">If you label a file using Office on the web, any encryption settings from the label are enforced.</span></span> <span data-ttu-id="0aa7a-226">支援這些檔案、共同撰寫、eDiscovery、DLP 及搜尋。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-226">For these files, coauthoring, eDiscovery, DLP, and search are supported.</span></span>

- <span data-ttu-id="0aa7a-227">如果您下載使用網頁上的 Office 標示的檔案，則會保留標籤，並強制執行標籤的任何加密設定，而不是 IRM 限制設定。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-227">If you download a file that's labeled by using Office on the web, the label is retained and any encryption settings from the label are enforced rather than the IRM restriction settings.</span></span>

- <span data-ttu-id="0aa7a-228">如果您下載未使用敏感度標籤加密的 Office 或 PDF 檔案，則會套用 IRM 設定。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-228">If you download an Office or PDF file that isn't encrypted with a sensitivity label, IRM settings are applied.</span></span>

- <span data-ttu-id="0aa7a-229">如果您已啟用任何其他 IRM 程式庫設定（包括防止使用者上傳不支援 IRM 的檔），則會強制執行這些設定。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-229">If you have enabled any of the additional IRM library settings, which includes preventing users from uploading documents that don't support IRM, these settings are enforced.</span></span>

<span data-ttu-id="0aa7a-230">使用此行為時，您可以保證所有的 Office 和 PDF 檔案在下載時受到保護，即使未進行標記，也能避免未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-230">With this behavior, you can be assured that all Office and PDF files are protected from unauthorized access if they are downloaded, even if they aren't labeled.</span></span> <span data-ttu-id="0aa7a-231">不過，已上傳的已標示檔案不會受益于新功能。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-231">However, labeled files that are uploaded won't benefit from the new capabilities.</span></span>

## <a name="search-for-documents-by-sensitivity-label"></a><span data-ttu-id="0aa7a-232">依敏感度標籤搜尋檔</span><span class="sxs-lookup"><span data-stu-id="0aa7a-232">Search for documents by sensitivity label</span></span>

<span data-ttu-id="0aa7a-233">您可以使用 managed 屬性**InformationProtectionLabelId** ，在具有特定敏感度標籤的 SharePoint 或 OneDrive 中尋找所有檔。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-233">Use the managed property **InformationProtectionLabelId** to find all documents in SharePoint or OneDrive that have a specific sensitivity label.</span></span> <span data-ttu-id="0aa7a-234">請使用下列語法：`InformationProtectionLabelId:<GUID>`</span><span class="sxs-lookup"><span data-stu-id="0aa7a-234">Use the following syntax: `InformationProtectionLabelId:<GUID>`</span></span>

<span data-ttu-id="0aa7a-235">例如，若要搜尋所有已標示為「機密」的檔，且該標籤的 GUID 為 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"，請在搜尋方塊中輸入：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-235">For example, to search for all documents that have been labeled as "Confidential", and that label has a GUID of "8faca7b8-8d20-48a3-8ea2-0f96310a848e", in the search box, type:</span></span>

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

<span data-ttu-id="0aa7a-236">若要取得敏感度標籤的 Guid，請使用「[取得標籤](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)」 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-236">To get the GUIDs for your sensitivity labels, use the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
1. <span data-ttu-id="0aa7a-237">第一，[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-237">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="0aa7a-238">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-238">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="0aa7a-239">然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-239">Then run the following command:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

<span data-ttu-id="0aa7a-240">如需使用 managed 屬性的詳細資訊，請參閱[管理 SharePoint 中的搜尋架構](https://docs.microsoft.com/sharepoint/manage-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-240">For more information about using managed properties, see [Manage the search schema in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a><span data-ttu-id="0aa7a-241">如何停用 SharePoint 和 OneDrive 的敏感度標籤（自願拉出）</span><span class="sxs-lookup"><span data-stu-id="0aa7a-241">How to disable sensitivity labels for SharePoint and OneDrive (opt-out)</span></span>

<span data-ttu-id="0aa7a-242">如果您停用這些新功能，當您為 SharePoint 和 OneDrive 啟用敏感度標籤之後，您上傳的檔案會繼續受到標籤的保護，因為標籤設定會繼續強制執行。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-242">If you disable these new capabilities, files that you uploaded after you enabled sensitivity labels for SharePoint and OneDrive continue to be protected by the label because the label settings continue to be enforced.</span></span> <span data-ttu-id="0aa7a-243">當您停用這些新功能之後，當您將敏感度標籤套用至新的檔案時，全文搜尋、eDiscovery 和合著將不再運作。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-243">When you apply sensitivity labels to new files after you disable these new capabilities, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="0aa7a-244">若要停用這些新功能，您必須使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-244">To disable these new capabilities, you must use PowerShell.</span></span> <span data-ttu-id="0aa7a-245">使用 SharePoint 線上管理命令介面和[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)指令程式，指定與[使用 PowerShell 以啟用敏感度標籤](#use-powershell-to-enable-support-for-sensitivity-labels)] 區段中所述的相同*EnableAIPIntegration*參數。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-245">Using the SharePoint Online Management Shell and the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet, specify the same *EnableAIPIntegration* parameter as described in the [Use PowerShell to enable support for sensitivity labels](#use-powershell-to-enable-support-for-sensitivity-labels) section.</span></span> <span data-ttu-id="0aa7a-246">不過這段時間，請將參數值設為 false，然後按**Y**確認：</span><span class="sxs-lookup"><span data-stu-id="0aa7a-246">But this time, set the parameter value to false and press **Y** to confirm:</span></span>

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

<span data-ttu-id="0aa7a-247">如果您有 Microsoft 365 多地理位置，您必須針對每個地理位置執行此命令。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-247">If you have Microsoft 365 Multi-Geo, you must run this command for each of your geo-locations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0aa7a-248">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0aa7a-248">Next steps</span></span>

<span data-ttu-id="0aa7a-249">在 SharePoint 和 OneDrive 中為 Office 檔案啟用敏感度標籤之後，請考慮使用自動標記原則自動標記這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-249">After you've enabled sensitivity labels for Office files in SharePoint and OneDrive, consider automatically labeling these files by using auto-labeling policies.</span></span> <span data-ttu-id="0aa7a-250">如需詳細資訊，請參閱[自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-250">For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>