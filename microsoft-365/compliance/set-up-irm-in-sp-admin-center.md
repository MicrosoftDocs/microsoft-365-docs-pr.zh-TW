---
title: Set up Information Rights Management (IRM) in SharePoint admin center
f1.keywords:
- NOCSH
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
description: 瞭解如何透過 Microsoft Azure Active Directory Rights Management Services （RMS）使用 SharePoint Online IRM，以保護 SharePoint 清單和文件庫。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819193"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="7d3b3-103">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="7d3b3-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="7d3b3-104">在 SharePoint Online 中，IRM 保護會套用至清單和文件庫層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="7d3b3-105">您的組織在使用 IRM 保護之前，必須先設定 Rights Management。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="7d3b3-106">IRM 依賴 azure Rights Management service 從 Azure 資訊保護來加密及指派使用限制。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="7d3b3-107">有些 Microsoft 365 方案包含 Azure 版權管理，但並非全部。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="7d3b3-108">若要深入瞭解，請參閱[Office 應用程式和服務對 Azure 版權管理的支援方式](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-108">To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="7d3b3-109">使用 SharePoint 系統管理中心開啟 IRM 服務</span><span class="sxs-lookup"><span data-stu-id="7d3b3-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="7d3b3-110">您的組織必須先為組織啟用 Rights Management 服務，才能 SharePoint 清單和文件庫進行 IRM 保護。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="7d3b3-111">若要深入瞭解，請參閱[啟用 Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-111">To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="7d3b3-112">您必須使用具有全域系統管理員許可權的工作或學校帳戶，才能啟用 Rights Management 服務。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="7d3b3-113">否則，您將無法在 SharePoint 線上使用 IRM 功能。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="7d3b3-114">在啟動 Rights Management 服務後，請登入 SharePoint 系統管理中心，以開啟 IRM。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="7d3b3-115">以全域管理員身分登入，或 SharePoint 管理員登入。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="7d3b3-116">在左上角選取應用程式啟動器圖示 ![Office 365 中的應用程式啟動器圖示](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然後選擇 [系統管理員]\*\*\*\* 來開啟 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="7d3b3-117">（如果您沒有看到 [系統管理] 磚，表示您的組織不具備系統管理員許可權。）</span><span class="sxs-lookup"><span data-stu-id="7d3b3-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="7d3b3-118">在左窗格中，選擇 [系統**管理中心**] \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="7d3b3-119">在左窗格中，選擇 [**設定**]，然後選擇 [**傳統設定] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="7d3b3-120">在 [**資訊版權管理（IRM）** ] 區段中，選擇 [**使用您設定中指定的 IRM 服務**]，然後選擇 [重新整理**irm 設定**]。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="7d3b3-121">重新整理 IRM 設定之後，您組織中的人員可以在其 SharePoint 清單和文件庫中開始使用 IRM。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7d3b3-122">不過，若要執行此動作的選項，可能需要長達一個小時，才會出現在文件庫設定和清單設定中。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="7d3b3-123">IRM-啟用 SharePoint 文件庫與清單</span><span class="sxs-lookup"><span data-stu-id="7d3b3-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="7d3b3-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7d3b3-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7d3b3-125">重新整理 IRM 設定之後，網站擁有者便可對其 SharePoint 清單和文件庫進行 IRM 保護。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7d3b3-126">如需詳細資訊，請參閱[將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7d3b3-127">當網站擁有者對清單或文件庫啟用 IRM 時，他們可以保護該清單或文件庫中任何支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="7d3b3-128">針對文件庫啟用 IRM 時，版權管理會套用至該文件庫中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="7d3b3-129">當您為清單啟用 IRM 時，版權管理只會套用至清單專案附加的檔案，而非實際的清單專案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="7d3b3-130">當使用者在已啟用 IRM 的清單或文件庫中下載檔案時，這些檔案會進行加密，只有經過授權的人員才能加以查看。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="7d3b3-131">每個版權管理檔案也包含發行授權，對查看檔案的人員有限制。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="7d3b3-132">一般限制包括將檔案設為唯讀、停用文字的複製、防止使用者儲存本機副本，以及防止使用者列印檔案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="7d3b3-133">可讀取 IRM 支援之檔案類型的用戶端程式會使用版權管理檔案中的發行授權，以強制執行這些限制。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="7d3b3-134">這是版權管理檔案在下載之後，如何保留其保護。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="7d3b3-135">若要在清單或文件庫上啟用 IRM，請參閱[將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7d3b3-136">您無法在瀏覽器中使用 Office 來建立或編輯已啟用 IRM 之文件庫中的檔。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="7d3b3-137">相反地，一次只能有一個人下載及編輯 IRM 加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="7d3b3-138">使用存回及取出，以管理*共同撰寫*或在多個使用者中製作。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="7d3b3-139">當您從受 IRM 保護的程式庫下載 PDF 檔案時，Microsoft 365 會建立受保護的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="7d3b3-140">檔案的副檔名不會變更，但檔會受到保護。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="7d3b3-141">若要查看此檔案，您需要有 Azure 資訊保護檢視器、完整 Azure 資訊保護用戶端或其他支援查看受保護 PDF 檔案的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="7d3b3-142">線上 SharePoint 支援下列檔案類型的加密：</span><span class="sxs-lookup"><span data-stu-id="7d3b3-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="7d3b3-143">PDF</span><span class="sxs-lookup"><span data-stu-id="7d3b3-143">PDF</span></span>
    
- <span data-ttu-id="7d3b3-144">下列 Microsoft Office 程式的97-2003 檔案格式： Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7d3b3-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7d3b3-145">下列 Microsoft Office 程式的 Office Open XML 格式： Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7d3b3-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7d3b3-146">XML 紙張規格（XPS）格式</span><span class="sxs-lookup"><span data-stu-id="7d3b3-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="7d3b3-147">IRM 保護無法套用至受保護的檔（例如數位簽署的 PDF 檔案），因為 SharePoint 需要在上傳檔時開啟該檔。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7d3b3-148">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7d3b3-148">Next steps</span></span>
<span data-ttu-id="7d3b3-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7d3b3-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7d3b3-150">在您為線上 SharePoint 啟用 IRM 之後，您可以開始將 rights management 套用至清單和文件庫。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="7d3b3-151">如需詳細資訊，請參閱[將資訊版權管理套用至清單或文件庫](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7d3b3-152">新的 Windows OneDrive 同步處理用戶端現在支援同步 IRM 保護 SharePoint 文件庫和 OneDrive 位置（只要該庫的 IRM 設定不會設為 [到期檔存取權]）。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="7d3b3-153">如需詳細資訊，或若要開始部署新的同步處理用戶端，請參閱[Deploy new OneDrive sync client For Windows](https://docs.microsoft.com/onedrive/deploy-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://docs.microsoft.com/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="7d3b3-154">頁首</span><span class="sxs-lookup"><span data-stu-id="7d3b3-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)
