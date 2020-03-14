---
title: 對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 3/11/2020
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理員可以在 SharePoint 和 OneDrive 中啟用 Word、Excel 及 PowerPoint 檔案的敏感度標籤支援。
ms.openlocfilehash: ef97215480949c8dec841fc857bed8945e26cacc
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637276"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="efc48-103">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="efc48-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="efc48-104">在此預覽之前，當您套用對儲存在 SharePoint 和 OneDrive 中的 Office 檔案所加入的靈敏度標籤時，服務無法處理這些檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="efc48-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="efc48-105">在這些情況下，合著、eDiscovery、資料遺失防護、搜尋、Delve 及其他協同功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="efc48-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="efc48-106">此預覽可針對已套用敏感度標籤（包含以雲端為基礎的金鑰進行加密）的新檔和變更的檔案，啟用這些功能：</span><span class="sxs-lookup"><span data-stu-id="efc48-106">This preview enables these features for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="efc48-107">SharePoint 會辨識套用至 Word、Excel 及 PowerPoint 檔案中 SharePoint 及 OneDrive 的敏感度標籤：當檔案儲存在 SharePoint 中時，會移除來自 Azure 資訊保護的加密，以便處理檔案內容。</span><span class="sxs-lookup"><span data-stu-id="efc48-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed.</span></span> <span data-ttu-id="efc48-108">如需如何在 SharePoint 儲存檔時保護檔的相關資訊，請參閱[OneDrive For Business and SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="efc48-108">For information about how documents are protected while they are stored in SharePoint, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>

- <span data-ttu-id="efc48-109">當您從 SharePoint 或 OneDrive 中下載或存取此檔案時，標籤的靈敏度標籤及標籤的任何加密設定會重新與檔案一起使用，而且在儲存檔的任何地方都會保留這些設定的強制執行。</span><span class="sxs-lookup"><span data-stu-id="efc48-109">When you download or access this file from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span> <span data-ttu-id="efc48-110">由於這種行為，請確定您提供的使用者指引只使用標籤來保護檔。</span><span class="sxs-lookup"><span data-stu-id="efc48-110">Because of this behavior, ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="efc48-111">如需詳細資訊，請參閱[資訊版權管理（IRM）選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="efc48-111">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="efc48-112">若要 SharePoint 在上傳時從檔案中移除加密，上傳已標記及已加密檔案的使用者，必須至少要有查看檔案的使用許可權。</span><span class="sxs-lookup"><span data-stu-id="efc48-112">For SharePoint to remove the encryption from the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="efc48-113">如果使用者無法在 SharePoint 外開啟檔案，SharePoint 不會從檔案中移除加密。</span><span class="sxs-lookup"><span data-stu-id="efc48-113">SharePoint doesn't remove encryption from files if the user can't open them outside SharePoint.</span></span>

- <span data-ttu-id="efc48-114">使用網頁上的 Office （Word、Excel、PowerPoint）開啟及編輯具有敏感度標籤的 Office 檔案，以套用加密。</span><span class="sxs-lookup"><span data-stu-id="efc48-114">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="efc48-115">會強制執行以加密指派的許可權。</span><span class="sxs-lookup"><span data-stu-id="efc48-115">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="efc48-116">透過網頁上的 Word，您也可以在編輯這些檔時使用自動標籤。</span><span class="sxs-lookup"><span data-stu-id="efc48-116">With Word on the web, you can also use auto labeling when you edit these documents.</span></span>

- <span data-ttu-id="efc48-117">Office 365 eDiscovery 支援這些檔案的全文搜尋。</span><span class="sxs-lookup"><span data-stu-id="efc48-117">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="efc48-118">資料遺失防護（DLP）原則涵蓋這些檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="efc48-118">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="efc48-119">有三個新的[審計事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)可供使用網頁上的 Office 來監視敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="efc48-119">Three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied using Office on the web:</span></span>
  - <span data-ttu-id="efc48-120">**已將敏感度標籤套用到檔案**</span><span class="sxs-lookup"><span data-stu-id="efc48-120">**Applied sensitivity label to file**</span></span>
  - <span data-ttu-id="efc48-121">**已變更套用到檔案的敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="efc48-121">**Changed sensitivity label applied to file**</span></span>
  - <span data-ttu-id="efc48-122">**已將敏感度標籤從檔案移除**</span><span class="sxs-lookup"><span data-stu-id="efc48-122">**Removed sensitivity label from file**</span></span>

> [!NOTE]
> <span data-ttu-id="efc48-123">若尚未使用雲端型金鑰（內部部署金鑰）套用加密，則主要的管理拓撲通常稱為「保留您自己的金鑰」（HYOK），SharePoint 行為不會隨此預覽而變更。</span><span class="sxs-lookup"><span data-stu-id="efc48-123">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span>
>
> <span data-ttu-id="efc48-124">在您啟用預覽之前，SharePoint 行為也不會針對 SharePoint 中的現有標籤和加密檔變更。</span><span class="sxs-lookup"><span data-stu-id="efc48-124">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint before you enable the preview.</span></span> <span data-ttu-id="efc48-125">若要讓這些檔案受益于新功能，必須下載並上傳這些檔案，或在啟用預覽之後加以編輯。</span><span class="sxs-lookup"><span data-stu-id="efc48-125">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you enable the preview.</span></span> <span data-ttu-id="efc48-126">例如，他們會在搜尋和 eDiscovery 結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="efc48-126">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="efc48-127">現在您也可以將敏感度標籤套用至 Microsoft 團隊、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="efc48-127">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="efc48-128">如需此個別預覽的詳細資訊，請參閱[使用敏感度標籤與 Microsoft 團隊、Office 365 群組和 SharePoint 網站（公開預覽）](sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="efc48-128">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="efc48-129">您隨時都可以選擇自願退出此預覽。</span><span class="sxs-lookup"><span data-stu-id="efc48-129">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="efc48-130">觀賞下列影片（無音訊）以查看這些新功能的動作：</span><span class="sxs-lookup"><span data-stu-id="efc48-130">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="efc48-131">需求</span><span class="sxs-lookup"><span data-stu-id="efc48-131">Requirements</span></span>

<span data-ttu-id="efc48-132">這些功能僅適用于[敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="efc48-132">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="efc48-133">如果您目前已具備 Azure 資訊保護標籤，請先將它們遷移至靈敏度標籤，讓您可以針對您上傳的新檔案啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="efc48-133">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="efc48-134">如需相關指示，請參閱 how [to 將 Azure 資訊保護標籤遷移至統一敏感度標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="efc48-134">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="efc48-135">在此預覽中，請在 Windows 上使用 OneDrive 同步處理應用程式版本19.002.0121.0008 或更新版本，在 Mac 上使用19.002.0107.0008 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="efc48-135">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="efc48-136">這兩個版本都發行于2019年1月28日，而且目前已發佈給所有的振鈴。</span><span class="sxs-lookup"><span data-stu-id="efc48-136">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="efc48-137">如需詳細資訊，請參閱[OneDrive 發行附注](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="efc48-137">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="efc48-138">啟用此預覽後，系統會提示執行舊版本的 sync 應用程式的使用者進行更新。</span><span class="sxs-lookup"><span data-stu-id="efc48-138">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="efc48-139">限制</span><span class="sxs-lookup"><span data-stu-id="efc48-139">Limitations</span></span>

- <span data-ttu-id="efc48-140">當您啟用此預覽時，在 OneDrive 同步處理資料夾中的檔案上變更標籤的使用者，可能無法儲存對檔案所做的其他變更。</span><span class="sxs-lookup"><span data-stu-id="efc48-140">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="efc48-141">使用者看到[紅色圓圈時出現白色的交叉圖示錯誤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，並且要求您將新的變更儲存為個別的副本。</span><span class="sxs-lookup"><span data-stu-id="efc48-141">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="efc48-142">除了使用者所初始化的標籤變更之外，如果系統管理員變更已套用至使用者同步處理用戶端之檔案的已發行標籤設定，就會發生相同的行為。</span><span class="sxs-lookup"><span data-stu-id="efc48-142">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="efc48-143">若要避免這些案例中的工作遺失，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="efc48-143">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="efc48-144">若要套用標籤，請使用 web 版本的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="efc48-144">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="efc48-145">套用標籤後關閉檔案，然後重新開啟檔案以進行其他變更。</span><span class="sxs-lookup"><span data-stu-id="efc48-145">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="efc48-146">SharePoint 不會自動將敏感度標籤套用至您已使用 Azure 資訊保護標籤加密的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-146">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="efc48-147">相反地，若要在啟用此預覽後取得功能，請完成下列工作：</span><span class="sxs-lookup"><span data-stu-id="efc48-147">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="efc48-148">確定您已將 Azure 資訊保護標籤遷移至靈敏度標籤，並已從 Microsoft 365 規範中心（或對等標上的標記系統管理中心）發行。</span><span class="sxs-lookup"><span data-stu-id="efc48-148">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="efc48-149">下載檔案，然後將檔案上傳至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="efc48-149">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="efc48-150">當套用加密的標籤有下列兩種加密設定時，SharePoint 無法處理加密的檔案：</span><span class="sxs-lookup"><span data-stu-id="efc48-150">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="efc48-151">**讓使用者在套用標籤**和 [ **Word、PowerPoint 及 Excel 中**的核取方塊時，指定許可權，並選取 [提示使用者指定許可權]。</span><span class="sxs-lookup"><span data-stu-id="efc48-151">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="efc48-152">此設定有時稱為「使用者定義的許可權」。</span><span class="sxs-lookup"><span data-stu-id="efc48-152">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="efc48-153">對**內容到期的使用者存取權**設定為**永不**值以外的值。</span><span class="sxs-lookup"><span data-stu-id="efc48-153">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="efc48-154">如果是具有上述任一種加密設定的標籤，則網頁上的 Office 使用者不會看到標籤。</span><span class="sxs-lookup"><span data-stu-id="efc48-154">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="efc48-155">此外，此預覽的新功能也無法用於已經具有這些加密設定的已標記檔。</span><span class="sxs-lookup"><span data-stu-id="efc48-155">Additionally, the new capabilities from this preview can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="efc48-156">例如，即使更新這些檔，這些檔也不會在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="efc48-156">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="efc48-157">針對授與使用者編輯許可權的加密檔，在 Office 應用程式的 web 版本中無法封鎖複製。</span><span class="sxs-lookup"><span data-stu-id="efc48-157">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="efc48-158">不支援 Azure 資訊保護檔追蹤網站。</span><span class="sxs-lookup"><span data-stu-id="efc48-158">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="efc48-159">Office 桌面應用程式和行動應用程式不支援共同撰寫。</span><span class="sxs-lookup"><span data-stu-id="efc48-159">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="efc48-160">相反地，這些應用程式會繼續以獨佔編輯模式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-160">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="efc48-161">如果已標示的檔上傳至 SharePoint，而標籤是使用服務主體名稱中的帳戶來套用加密，則無法在網頁上的 Office 中開啟該檔。</span><span class="sxs-lookup"><span data-stu-id="efc48-161">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="efc48-162">範例案例包括 Microsoft Cloud App Security，以及透過電子郵件傳送給小組的檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-162">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="efc48-163">使用者可能會在離線或轉入睡眠模式後遇到儲存問題，而不是使用 web Office 時，他們會使用桌面和行動應用程式進行 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="efc48-163">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="efc48-164">針對這些使用者，當他們繼續其 Office 應用程式會話並嘗試儲存變更時，會看到上傳失敗訊息，並有一個選項可儲存副本，而不是儲存原始檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-164">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="efc48-165">以下列方式加密的檔無法在 web 上的 Office 中開啟：</span><span class="sxs-lookup"><span data-stu-id="efc48-165">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="efc48-166">使用內部部署機碼的加密（「保留您自己的金鑰」或 HYOK）</span><span class="sxs-lookup"><span data-stu-id="efc48-166">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="efc48-167">獨立于標籤所套用的加密，例如直接套用 Rights Management protection 範本。</span><span class="sxs-lookup"><span data-stu-id="efc48-167">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="efc48-168">如果您刪除的標籤已套用至 SharePoint 中的檔，而不是從適當的標籤原則中移除標籤，則下載的檔不會標示或加密。</span><span class="sxs-lookup"><span data-stu-id="efc48-168">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="efc48-169">相比之下，如果標籤的檔儲存在 SharePoint 之外，當標籤刪除時，該檔仍會保持加密狀態。</span><span class="sxs-lookup"><span data-stu-id="efc48-169">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="efc48-170">請注意，雖然您可以在測試階段刪除標籤，但很少需要在實際執行環境中刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="efc48-170">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="efc48-171">為預覽準備 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="efc48-171">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="efc48-172">啟用預覽之前，請確定您正在執行 SharePoint 線上管理命令介面版本16.0.19418.12000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="efc48-172">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="efc48-173">如果您已有最新版本，則可以繼續進行並啟用預覽。</span><span class="sxs-lookup"><span data-stu-id="efc48-173">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="efc48-174">如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。</span><span class="sxs-lookup"><span data-stu-id="efc48-174">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="efc48-175">或者，如果您已從 Microsoft 下載中心安裝舊版的 SharePoint Online 管理命令介面，您也可以移至 [**新增或移除程式**]，並卸載 SharePoint 線上管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="efc48-175">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="efc48-176">在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="efc48-176">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="efc48-177">選取語言，然後按一下 [下載]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efc48-177">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="efc48-178">在 x64 和 x86 .msi 檔案之間選擇。</span><span class="sxs-lookup"><span data-stu-id="efc48-178">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="efc48-179">如果您執行的是64位版本的 Windows 或 x86 檔案（如果您執行32位版本），請下載 x64 檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-179">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="efc48-180">如果您不知道，請參閱[我要執行哪一個 Windows 作業系統版本？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="efc48-180">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="efc48-181">下載檔案之後，請執行檔，然後依照安裝精靈中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="efc48-181">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="efc48-182">使用 Microsoft PowerShell 啟用預覽（自願加入）</span><span class="sxs-lookup"><span data-stu-id="efc48-182">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="efc48-183">若要啟用預覽，請使用 Set-SPOTenant Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="efc48-183">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="efc48-184">在 Office 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="efc48-184">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="efc48-185">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="efc48-185">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="efc48-186">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="efc48-186">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="efc48-187">在您建立或變更靈敏度標籤之後排程部署</span><span class="sxs-lookup"><span data-stu-id="efc48-187">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="efc48-188">在 Microsoft 365 規範中心內建立或變更靈敏度標籤之後，請分階段發佈。</span><span class="sxs-lookup"><span data-stu-id="efc48-188">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="efc48-189">如果您發佈尚未完全同步處理的標籤，當使用者將標籤套用至檔案，並將其上傳至 SharePoint 時，就無法在網頁版的 Office 應用程式中開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-189">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="efc48-190">搜尋和 eDiscovery 也不適用於檔案。</span><span class="sxs-lookup"><span data-stu-id="efc48-190">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="efc48-191">我們建議您遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="efc48-191">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="efc48-192">僅將新的或修改過的敏感度標籤發佈給一或兩個人。</span><span class="sxs-lookup"><span data-stu-id="efc48-192">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="efc48-193">在初始出版物過後等候至少24小時。</span><span class="sxs-lookup"><span data-stu-id="efc48-193">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="efc48-194">確認標籤已完全同步處理。</span><span class="sxs-lookup"><span data-stu-id="efc48-194">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="efc48-195">更廣泛地發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="efc48-195">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="efc48-196">使用 Microsoft PowerShell 停用預覽（自願檢出）</span><span class="sxs-lookup"><span data-stu-id="efc48-196">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="efc48-197">如果您停用此預覽，您在預覽期間上傳的檔案會繼續受到標籤的保護。</span><span class="sxs-lookup"><span data-stu-id="efc48-197">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="efc48-198">會繼續強制執行對應的設定。</span><span class="sxs-lookup"><span data-stu-id="efc48-198">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="efc48-199">當您停用預覽後，將標籤套用至新的檔案時，全文搜尋、eDiscovery 和合著功能將不再運作。</span><span class="sxs-lookup"><span data-stu-id="efc48-199">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="efc48-200">若要停用預覽，請使用 Set-SPOTenant Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="efc48-200">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="efc48-201">在 Office 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="efc48-201">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="efc48-202">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="efc48-202">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="efc48-203">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="efc48-203">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
