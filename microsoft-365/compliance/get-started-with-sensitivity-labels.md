---
title: 開始使用敏感度標籤
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 3/05/2020
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 準備開始實作敏感度標籤來協助保護貴組織的資料，但不確定從何處著手？ 閱讀一些實用的指導方針，以協助您開始套用標籤的旅程。
ms.openlocfilehash: 3e9dd5c02b3502eab2d3abfe5d65b5baebe18cda
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2020
ms.locfileid: "42569172"
---
# <a name="get-started-with-sensitivity-labels"></a><span data-ttu-id="981e0-104">開始使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="981e0-104">Get started with sensitivity labels</span></span>

<span data-ttu-id="981e0-105">如需敏感度標籤為何及其如何可協助您保護組織資料的相關資訊，請參閱[了解敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="981e0-105">For information about what sensitivity labels are and how they can help you protect your organization's data, see [Learn about sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="981e0-106">如果您有 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，請判斷是否需要將標籤移轉至統一標籤平台，以及要使用的標籤用戶端：</span><span class="sxs-lookup"><span data-stu-id="981e0-106">If you have [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine whether you need to migrate labels to the unified labeling platform, and which labeling client to use:</span></span>
- [<span data-ttu-id="981e0-107">如何判斷我的租用戶是否在統一標籤平台上？</span><span class="sxs-lookup"><span data-stu-id="981e0-107">How can I determine if my tenant is on the unified labeling platform?</span></span>](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [<span data-ttu-id="981e0-108">選擇要用於 Windows 電腦的標籤用戶端</span><span class="sxs-lookup"><span data-stu-id="981e0-108">Choose which labeling client to use for Windows computers</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

<span data-ttu-id="981e0-109">當您準備好要開始使用敏感度標籤來保護組織的資料時：</span><span class="sxs-lookup"><span data-stu-id="981e0-109">When you're ready to start protecting your organization's data by using sensitivity labels:</span></span>

1. <span data-ttu-id="981e0-110">**建立標籤。**</span><span class="sxs-lookup"><span data-stu-id="981e0-110">**Create the labels.**</span></span> <span data-ttu-id="981e0-111">根據貴組織用於不同內容敏感度層級的分類法，建立您的敏感度標籤並加以命名。</span><span class="sxs-lookup"><span data-stu-id="981e0-111">Create and name your sensitivity labels according to your organization's classification taxonomy for different sensitivity levels of content.</span></span> <span data-ttu-id="981e0-112">使用對您的使用者有意義的一般名稱或字詞。</span><span class="sxs-lookup"><span data-stu-id="981e0-112">Use common names or terms that make sense to your users.</span></span> <span data-ttu-id="981e0-113">如果您還沒有建立分類法，請考慮從 [個人]、[公用]、[一般]、[機密] 和 [高度機密] 等標籤名稱著手。</span><span class="sxs-lookup"><span data-stu-id="981e0-113">If you don't already have an established taxonomy, consider starting with label names such as Personal, Public, General, Confidential, and Highly Confidential.</span></span> <span data-ttu-id="981e0-114">您可以接著使用子標籤，依類別將類似的標籤群組。</span><span class="sxs-lookup"><span data-stu-id="981e0-114">You can then use sublabels to group similar labels by category.</span></span> <span data-ttu-id="981e0-115">當您建立標籤時，請使用工具提示文字來協助使用者選取適當的標籤。</span><span class="sxs-lookup"><span data-stu-id="981e0-115">When you create a label, use the  tooltip text to help users select the appropriate label.</span></span>
    
    <span data-ttu-id="981e0-116">如需用於定義分類法的更廣泛指導方針，請從[服務信任入口網站](https://aka.ms/DataClassificationWhitepaper)下載白皮書《資料分類和敏感度標籤分類》(英文)。</span><span class="sxs-lookup"><span data-stu-id="981e0-116">For more extensive guidance for defining a classificaton taxonomy, download the white paper, "Data Classification & Sensitivity Label Taxonomy" from the [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper).</span></span>

2. <span data-ttu-id="981e0-117">**定義每個標籤的功能。**</span><span class="sxs-lookup"><span data-stu-id="981e0-117">**Define what each label can do.**</span></span> <span data-ttu-id="981e0-118">設定您想要與每個標籤相關聯的保護設定。</span><span class="sxs-lookup"><span data-stu-id="981e0-118">Configure the protection settings you want associated with each label.</span></span> <span data-ttu-id="981e0-119">例如，您可能希望較低敏感度內容 (如「一般」標籤) 只有套用頁首或頁尾，而較高敏感度內容 (如「機密」標籤) 則應套用浮水印、加密及端點保護。</span><span class="sxs-lookup"><span data-stu-id="981e0-119">For example, you might want lower sensitivity content (such as a “General” label) to have just a header or footer applied, while higher sensitivity content (such as a “Confidential” label) should have a watermark, encryption, and endpoint protection applied.</span></span>

3. <span data-ttu-id="981e0-120">**發佈標籤。**</span><span class="sxs-lookup"><span data-stu-id="981e0-120">**Publish the labels.**</span></span> <span data-ttu-id="981e0-121">設定好敏感度標籤之後，請使用標籤原則加以發佈。</span><span class="sxs-lookup"><span data-stu-id="981e0-121">After your sensitivity labels are configured, publish them by using a label policy.</span></span> <span data-ttu-id="981e0-122">決定哪些使用者和群組應具有標籤，以及所要使用的原則設定。</span><span class="sxs-lookup"><span data-stu-id="981e0-122">Decide which users and groups should have the labels and what policy settings to use.</span></span> <span data-ttu-id="981e0-123">單一標籤可重複使用；您只要定義一次，就可以將它納入指派給不同使用者的數個標籤原則中。</span><span class="sxs-lookup"><span data-stu-id="981e0-123">A single label is reusable — you define it once, and then you can include it in several label policies assigned to different users.</span></span> <span data-ttu-id="981e0-124">例如，您可以將標籤原則指派給少數幾個使用者來試驗您的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="981e0-124">So for example, you could pilot your sensitivity labels by assigning a label policy to just a few users.</span></span> <span data-ttu-id="981e0-125">當您準備好在整個組織推出標籤時，您可以為標籤建立新的標籤原則，而這次指定所有使用者。</span><span class="sxs-lookup"><span data-stu-id="981e0-125">Then when you're ready to roll out the labels across your organization, you can create a new label policy for your labels and this time, specify all users.</span></span>

<span data-ttu-id="981e0-126">部署及套用敏感度標籤的基本流程：</span><span class="sxs-lookup"><span data-stu-id="981e0-126">The basic flow for deploying and applying sensitivity labels:</span></span>

![顯示敏感度標籤的工作流程圖](../media/Sensitivity-label-flow.png)

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="981e0-128">建立和管理敏感度標籤所需的權限</span><span class="sxs-lookup"><span data-stu-id="981e0-128">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="981e0-129">合規性小組成員會建立敏感度標籤，這些成員需要 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="981e0-129">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="981e0-130">根據預設，您的租用戶的全域系統管理員可以存取這些系統管理中心，並且授與法務人員和其他人員存取權限，而不需授與他們租用戶系統管理員的所有權限。如需這個委派的受限系統管理員存取權，請移至其中一個系統管理中心的 [權限]\*\*\*\* 頁面，然後將成員新增至 [合規性資料系統管理員]\*\*\*\*、[合規性系統管理員]\*\*\*\* 或 [安全性系統系統管理員]\*\*\*\* 角色群組。</span><span class="sxs-lookup"><span data-stu-id="981e0-130">By default, global administrators for your tenant have access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="981e0-131">除了使用角色以外，您可以建立新的角色群組，並將 [敏感度標籤系統管理員]\*\*\*\* 或 [組織組態]\*\*\*\* 角色新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="981e0-131">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="981e0-132">如需相關指示，請參閱[讓使用者能夠存取 Office 365 安全規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="981e0-132">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="981e0-133">只有建立及設定敏感度標籤及其標籤原則時，才需要這些權限。</span><span class="sxs-lookup"><span data-stu-id="981e0-133">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="981e0-134">您不需要在應用程式或服務中套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="981e0-134">They are not required to apply the labels in apps or services.</span></span>

## <a name="common-scenarios-for-sensitivity-labels"></a><span data-ttu-id="981e0-135">敏感度標籤的常見案例</span><span class="sxs-lookup"><span data-stu-id="981e0-135">Common scenarios for sensitivity labels</span></span>

<span data-ttu-id="981e0-136">使用下列文件來支援您的敏感度標籤部署：</span><span class="sxs-lookup"><span data-stu-id="981e0-136">Use the following documentation to support your sensitivity labeling deployment:</span></span>

|<span data-ttu-id="981e0-137">我想要...</span><span class="sxs-lookup"><span data-stu-id="981e0-137">I want to ...</span></span>|<span data-ttu-id="981e0-138">文件</span><span class="sxs-lookup"><span data-stu-id="981e0-138">Documentation</span></span>|
|----------------|---------------|
|<span data-ttu-id="981e0-139">建立及發佈將協助保護我的組織資料的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="981e0-139">Create and publish sensitivity labels that will help protect my organization's data</span></span>|[<span data-ttu-id="981e0-140">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="981e0-140">Create and configure sensitivity labels and their policies</span></span>](create-sensitivity-labels.md)|
|<span data-ttu-id="981e0-141">使用敏感度標籤加密文件和電子郵件，並限制能夠存取該內容的人員以及使用方式</span><span class="sxs-lookup"><span data-stu-id="981e0-141">Encrypt documents and emails with sensitivity labels and restrict who can access that content and how it can be used</span></span> |[<span data-ttu-id="981e0-142">使用敏感度標籤來套用加密以限制存取內容</span><span class="sxs-lookup"><span data-stu-id="981e0-142">Restrict access to content by using sensitivity labels to apply encryption</span></span>](encryption-sensitivity-labels.md)|
|<span data-ttu-id="981e0-143">在 SharePoint (和 OneDrive) 中針對具有加密標籤的文件啟用共同作業功能</span><span class="sxs-lookup"><span data-stu-id="981e0-143">Enable collaboration capabilities in SharePoint (and OneDrive) for documents that are labeled with encryption</span></span> | [<span data-ttu-id="981e0-144">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="981e0-144">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)
|<span data-ttu-id="981e0-145">管理 Office 應用程式的敏感度標籤，讓內容標示為已建立</span><span class="sxs-lookup"><span data-stu-id="981e0-145">Manage sensitivity labels for Office apps so that content is labeled as it's created</span></span> |[<span data-ttu-id="981e0-146">在 Office 應用程式中使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="981e0-146">Use sensitivity labels in Office apps</span></span>](sensitivity-labels-office-apps.md)|
|<span data-ttu-id="981e0-147">建立內容時自動套用敏感度標籤或向使用者建議標籤</span><span class="sxs-lookup"><span data-stu-id="981e0-147">Automatically apply sensitivity labels or recommend labels to users when content is created</span></span> | [<span data-ttu-id="981e0-148">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="981e0-148">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)|
|<span data-ttu-id="981e0-149">使用敏感度標籤來保護 Teams 和 SharePoint 中的內容</span><span class="sxs-lookup"><span data-stu-id="981e0-149">Use sensitivity labels to protect content in Teams and  SharePoint</span></span> |[<span data-ttu-id="981e0-150">對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="981e0-150">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>](sensitivity-labels-teams-groups-sites.md)|
|<span data-ttu-id="981e0-151">探索、標記和保護儲存在內部部署資料存放區中的檔案</span><span class="sxs-lookup"><span data-stu-id="981e0-151">Discover, label, and protect files stored in data stores that are on premises</span></span> |[<span data-ttu-id="981e0-152">部署 Azure 資訊保護掃描器以自動分類和保護檔案</span><span class="sxs-lookup"><span data-stu-id="981e0-152">Deploying the Azure Information Protection scanner to automatically classify and protect files</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|<span data-ttu-id="981e0-153">探索、標記和保護儲存在雲端的資料存放區中的檔案</span><span class="sxs-lookup"><span data-stu-id="981e0-153">Discover, label, and protect files stored in data stores that are in the cloud</span></span>|[<span data-ttu-id="981e0-154">探索、分類、標記和保護儲存在雲端中的控管和敏感性資料</span><span class="sxs-lookup"><span data-stu-id="981e0-154">Discover, classify, label, and protect regulated and sensitive data stored in the cloud</span></span>](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|<span data-ttu-id="981e0-155">將敏感度標籤的使用情況視覺化，以報告部署狀態和微調標籤組態</span><span class="sxs-lookup"><span data-stu-id="981e0-155">Visualize how sensitivity labels are being used to report deployment status and fine-tune label configuration</span></span>|[<span data-ttu-id="981e0-156">利用標籤分析檢視標籤使用量</span><span class="sxs-lookup"><span data-stu-id="981e0-156">View label usage with label analytics</span></span>](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a><span data-ttu-id="981e0-157">敏感度標籤的使用者文件</span><span class="sxs-lookup"><span data-stu-id="981e0-157">End-user documentation for sensitivity labels</span></span>

<span data-ttu-id="981e0-158">最有效的使用者文件會是您為所選的標籤名稱和組態提供的自訂指導方針和指示。</span><span class="sxs-lookup"><span data-stu-id="981e0-158">The most effective end-user documentation will be customized guidance and instructions you provide for the label names and configurations you choose.</span></span> <span data-ttu-id="981e0-159">不過，您可以使用下列資源來取得基本指示：</span><span class="sxs-lookup"><span data-stu-id="981e0-159">However, you can use the following resources for basic instructions:</span></span>   

- [<span data-ttu-id="981e0-160">在 Office 中將敏感度標籤套用至您的檔案和電子郵件</span><span class="sxs-lookup"><span data-stu-id="981e0-160">Apply sensitivity labels to your files and email in Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [<span data-ttu-id="981e0-161">Office 敏感度標籤的已知問題</span><span class="sxs-lookup"><span data-stu-id="981e0-161">Known issues with sensitivity labels in Office</span></span>](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [<span data-ttu-id="981e0-162">在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件</span><span class="sxs-lookup"><span data-stu-id="981e0-162">Automatically apply or recommend sensitivity labels to your files and emails in Office</span></span>](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [<span data-ttu-id="981e0-163">自動套用或建議敏感度標籤的已知問題</span><span class="sxs-lookup"><span data-stu-id="981e0-163">Known issues with automatically applying or recommending sensitivity labels</span></span>](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [<span data-ttu-id="981e0-164">Azure 資訊保護統一標籤使用者指南</span><span class="sxs-lookup"><span data-stu-id="981e0-164">Azure Information Protection unified labeling user guide</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


