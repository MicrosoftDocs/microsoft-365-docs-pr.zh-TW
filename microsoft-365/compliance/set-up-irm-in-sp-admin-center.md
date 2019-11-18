---
title: Set up Information Rights Management (IRM) in SharePoint admin center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: 了解如何使用 SharePoint Online IRM 透過 Microsoft Azure Active Directory Rights Management Services (RMS) 來保護 SharePoint 清單與文件庫。
ms.openlocfilehash: 4ed50b5c683215394222628153c03c58ee23e6a0
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2019
ms.locfileid: "38685553"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="a36d3-103">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="a36d3-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

## <a name="introduction"></a><span data-ttu-id="a36d3-104">簡介</span><span class="sxs-lookup"><span data-stu-id="a36d3-104">Introduction</span></span>

<span data-ttu-id="a36d3-105">在 SharePoint Online 中，IRM 保護會套用至清單與文件庫層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-105">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="a36d3-106">您的組織可以使用 IRM 保護之前，您必須先設定版權管理。</span><span class="sxs-lookup"><span data-stu-id="a36d3-106">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="a36d3-107">IRM 會取決於從 Azure 資訊保護來加密及指派流量限制的 Azure 版權管理服務。</span><span class="sxs-lookup"><span data-stu-id="a36d3-107">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="a36d3-108">某些 Office 365 方案包含 Azure Rights Management，但並非所有。</span><span class="sxs-lookup"><span data-stu-id="a36d3-108">Some Office 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="a36d3-109">若要了解更多，請閱讀[如何 Office 應用程式和服務支援 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-109">To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="a36d3-110">開啟 IRM 使用 SharePoint 管理中心的 [服務]</span><span class="sxs-lookup"><span data-stu-id="a36d3-110">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="a36d3-111">您的組織可以 IRM 保護的 SharePoint 清單與文件庫之前，您必須先啟動您的組織的版權管理服務。</span><span class="sxs-lookup"><span data-stu-id="a36d3-111">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="a36d3-112">若要了解如何查看[啟動 Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-112">To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="a36d3-113">您必須使用公司或學校帳戶已啟用的版權管理服務的 Office 365 全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="a36d3-113">You must use a work or school account that has Office 365 global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="a36d3-114">否則，您無法使用 SharePoint Online 中使用 IRM 功能。</span><span class="sxs-lookup"><span data-stu-id="a36d3-114">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="a36d3-115">之後啟動版權管理服務，登入 SharePoint 系統管理中心來開啟 IRM。</span><span class="sxs-lookup"><span data-stu-id="a36d3-115">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="a36d3-116">以全域管理員或 SharePoint 系統管理員身分登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a36d3-116">Sign in to Office 365 as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="a36d3-117">在左上角選取應用程式啟動器圖示 ![Office 365 中的應用程式啟動器圖示](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然後選擇 [系統管理員]\*\*\*\* 來開啟 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a36d3-117">Select the app launcher icon ![The app launcher icon in Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="a36d3-118">(如果您沒有看到 [系統管理員] 磚，則您沒有組織中的 Office 365 系統管理員權限。)</span><span class="sxs-lookup"><span data-stu-id="a36d3-118">(If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="a36d3-119">在左窗格中，選擇 [**系統管理中心** \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="a36d3-119">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="a36d3-120">在左窗格中，選擇 [**設定**]，然後選擇**傳統設定] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="a36d3-120">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="a36d3-121">在 [**資訊版權管理 (IRM)** ] 區段中，選擇 [**使用您的組態中指定的 IRM 服務**，，然後選擇 [**重新整理 IRM 設定**。</span><span class="sxs-lookup"><span data-stu-id="a36d3-121">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="a36d3-122">重新整理 IRM 設定後，您組織中的人員可以開始在其 SharePoint 清單與文件庫中使用 IRM。</span><span class="sxs-lookup"><span data-stu-id="a36d3-122">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="a36d3-123">不過，若要這麼做的選項可能會佔用 1 小時的時間來顯示在文件庫設定與清單設定。</span><span class="sxs-lookup"><span data-stu-id="a36d3-123">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="a36d3-124">啟用 IRM 功能 SharePoint 文件庫與清單</span><span class="sxs-lookup"><span data-stu-id="a36d3-124">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="a36d3-125"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="a36d3-125"></span></span>

<span data-ttu-id="a36d3-126">在重新整理 IRM 設定之後, 網站擁有人可以 IRM 保護其 SharePoint 清單及文件庫。</span><span class="sxs-lookup"><span data-stu-id="a36d3-126">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="a36d3-127">如需詳細資訊，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-127">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="a36d3-128">當網站擁有者的清單或文件庫啟用 IRM 時，請他們可以保護該清單或文件庫中任何支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a36d3-128">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="a36d3-129">文件庫啟用 IRM 時，版權管理套用至所有該文件庫中的檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-129">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="a36d3-130">當您啟用 IRM 的清單時，版權管理僅適用於檔案附加至清單項目，不實際清單項目。</span><span class="sxs-lookup"><span data-stu-id="a36d3-130">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="a36d3-131">當人員下載中啟用 IRM 的清單或文件庫的檔案時，檔案加密，因此只有授權的使用者可以檢視它們。</span><span class="sxs-lookup"><span data-stu-id="a36d3-131">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="a36d3-132">每個受版權管理檔案也包含會限制檢視檔案的人員的發行授權。</span><span class="sxs-lookup"><span data-stu-id="a36d3-132">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="a36d3-133">一般限制包括唯讀屬性，停用複製文字，防止人員從儲存本機複本，並列印檔案時，防止人員進行檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-133">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="a36d3-134">可以讀取 IRM 支援的檔案類型的用戶端程式會使用受版權管理檔案內的發行授權，以強制執行這些限制。</span><span class="sxs-lookup"><span data-stu-id="a36d3-134">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="a36d3-135">這是如何受版權管理檔案會保留其保護即使之後就會下載。</span><span class="sxs-lookup"><span data-stu-id="a36d3-135">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="a36d3-136">若要在清單或文件庫啟用 IRM，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-136">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="a36d3-137">您無法建立或編輯文件中啟用 IRM 的文件庫的瀏覽器中使用 Office。</span><span class="sxs-lookup"><span data-stu-id="a36d3-137">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="a36d3-138">相反地，一次一個人可以下載並編輯之中 IRM 加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-138">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="a36d3-139">使用 [存回和取出管理*共同撰寫*，或製作跨多個使用者。</span><span class="sxs-lookup"><span data-stu-id="a36d3-139">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="a36d3-140">當您從受 IRM 保護文件庫下載 PDF 檔案時，Office 365 會建立受保護的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-140">When you download a PDF file from an IRM-protected library, Office 365 creates a protected PDF file.</span></span> <span data-ttu-id="a36d3-141">也不會變更檔案的副檔名，但受保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-141">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="a36d3-142">若要檢視此檔案中，您將需要 Azure 資訊保護檢視器中，完整的 Azure 資訊保護用戶端，或支援檢視的另一個應用程式保護 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="a36d3-142">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="a36d3-143">SharePoint Online 支援下列檔案類型的加密：</span><span class="sxs-lookup"><span data-stu-id="a36d3-143">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="a36d3-144">PDF</span><span class="sxs-lookup"><span data-stu-id="a36d3-144">PDF</span></span>
    
- <span data-ttu-id="a36d3-145">下列的 Microsoft Office 程式的 97-2003年檔案格式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a36d3-145">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="a36d3-146">Office Open XML 格式的下列的 Microsoft Office 程式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a36d3-146">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="a36d3-147">XML Paper Specification (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="a36d3-147">The XML Paper Specification (XPS) format</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="a36d3-148">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a36d3-148">Next steps</span></span>
<span data-ttu-id="a36d3-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="a36d3-149"></span></span>

<span data-ttu-id="a36d3-150">一旦您已啟用 IRM 的 SharePoint Online，您可以開始將版權管理套用至清單和文件庫。</span><span class="sxs-lookup"><span data-stu-id="a36d3-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="a36d3-151">如需資訊，請參閱[資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="a36d3-152">Windows 的新版 OneDrive 同步處理用戶端現在可支援同步處理受 IRM 保護的 SharePoint 文件庫和 OneDrive 位置 （只要程式庫的 IRM 設定不設過期文件的存取權限）。</span><span class="sxs-lookup"><span data-stu-id="a36d3-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="a36d3-153">如需詳細資訊，或若要開始部署新的同步處理用戶端，請參閱[部署 Windows 的新版 OneDrive 同步處理用戶端](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)。</span><span class="sxs-lookup"><span data-stu-id="a36d3-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).</span></span>
  
[<span data-ttu-id="a36d3-154">頁首</span><span class="sxs-lookup"><span data-stu-id="a36d3-154">Top of page</span></span>](#introduction)  

