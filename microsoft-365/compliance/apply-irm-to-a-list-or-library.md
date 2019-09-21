---
title: 將資訊版權管理 (IRM) 套用至清單或文件庫
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
description: 您可以使用資訊版權管理 (IRM) 協助控制及保護下載從清單或文件庫的檔案。
ms.openlocfilehash: 3c350a3648b77992dd8e86ee47498efc327b2af8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076734"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="80427-103">將資訊版權管理 (IRM) 套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="80427-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="80427-104">您可以使用資訊版權管理 (IRM) 協助控制及保護下載從清單或文件庫的檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="80427-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="80427-105">Before you begin</span></span>

- <span data-ttu-id="80427-106">Azure 資訊保護，並在內部同等 Active Directory Rights Management Services (AD RMS)，從 Azure 版權管理服務 (Azure RMS) 支援資訊版權管理網站。</span><span class="sxs-lookup"><span data-stu-id="80427-106">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="80427-107">沒有不同或其他安裝所需。</span><span class="sxs-lookup"><span data-stu-id="80427-107">No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="80427-108">您將 IRM 套用至清單或文件庫之前必須先啟用由系統管理員為您的網站。</span><span class="sxs-lookup"><span data-stu-id="80427-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="80427-109">若要將 IRM 套用至清單或文件庫，您必須使用該清單或文件庫的系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="80427-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="80427-110">如果您使用 SharePoint Online，您的使用者可能會下載較大受 IRM 保護的檔案時遇到逾時。</span><span class="sxs-lookup"><span data-stu-id="80427-110">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="80427-111">如果發生這種情況，然後使用您的 Office 程式，來套用 IRM 保護，並將較大的檔案儲存在不使用 IRM 的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="80427-111">If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80427-112">如果您使用 SharePoint Server 2013，伺服器管理員必須針對每個組織中的人員想要使用 IRM 保護的檔案類型的所有前端網頁伺服器上安裝保護裝置。</span><span class="sxs-lookup"><span data-stu-id="80427-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="80427-113">將 IRM 套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="80427-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="80427-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="80427-114"></span></span>

![資訊版權管理設定](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="80427-116">移至您要設定 IRM 的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="80427-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="80427-117">功能區上，按一下 [**文件庫**] 索引標籤，然後按一下**文件庫設定**。</span><span class="sxs-lookup"><span data-stu-id="80427-117">On the ribbon, click the **Library** tab, and then click **Library Settings**.</span></span> <span data-ttu-id="80427-118">（如果您正在工作清單中，按一下 [**清單**] 索引標籤，然後按一下 [**清單設定**。）</span><span class="sxs-lookup"><span data-stu-id="80427-118">(If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![在功能區上的 SharePoint 文件庫設定按鈕](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="80427-120">在 [**權限與管理**] 按一下 [**資訊版權管理**]。</span><span class="sxs-lookup"><span data-stu-id="80427-120">Under **Permissions and Management**, click **Information Rights Management**.</span></span> <span data-ttu-id="80427-121">如果未出現 [資訊版權管理] 連結，您網站可能未啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="80427-121">If the Information Rights Management link does not appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="80427-122">請連絡您的伺服器管理員，以查看其是否可以用於您的網站啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="80427-122">Contact your server administrator to see if it is possible to enable IRM for your site.</span></span> <span data-ttu-id="80427-123">圖片庫似乎不到 [資訊版權管理] 連結。</span><span class="sxs-lookup"><span data-stu-id="80427-123">The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="80427-124">在 [**資訊版權管理設定**] 頁面上選取 [**限制下載此文件庫中的文件的權限**] 核取方塊，以從這個清單或文件庫下載的文件套用限制權限。</span><span class="sxs-lookup"><span data-stu-id="80427-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="80427-125">在 [**建立權限原則標題**] 方塊中，輸入您可以使用更新版本來區分此原則與其他原則的原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="80427-125">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies.</span></span> <span data-ttu-id="80427-126">例如，您可以輸入**的公司機密**如果您要套用至清單或文件庫，將會包含機密的公司文件的限制權限。</span><span class="sxs-lookup"><span data-stu-id="80427-126">For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="80427-127">在 [**新增權限原則描述**] 方塊中，輸入描述會顯示使用此清單或文件庫，說明他們應該如何處理此清單或文件庫中的文件的人員。</span><span class="sxs-lookup"><span data-stu-id="80427-127">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="80427-128">例如，您可以輸入**討論僅與其他員工此文件的內容**如果您想要限制存取權給內部員工這些文件中的資訊。</span><span class="sxs-lookup"><span data-stu-id="80427-128">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="80427-129">若要將其他限制套用到此清單或文件庫中的文件，按一下 [**顯示選項**]，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="80427-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="80427-130">**若要這麼做：**</span><span class="sxs-lookup"><span data-stu-id="80427-130">**To do this:**</span></span>|<span data-ttu-id="80427-131">**執行這項操作：**</span><span class="sxs-lookup"><span data-stu-id="80427-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80427-132">允許從這個清單或文件庫列印文件的人員</span><span class="sxs-lookup"><span data-stu-id="80427-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="80427-133">選取 [**允許檢視程式才能列印**核取方塊。</span><span class="sxs-lookup"><span data-stu-id="80427-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="80427-134">允許人員具有至少在文件上執行的內嵌程式碼或巨集的 「 檢視項目 」 權限。</span><span class="sxs-lookup"><span data-stu-id="80427-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="80427-135">選取 [**檢視程式才能執行指令碼和螢幕助讀程式來下載文件上的函數**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="80427-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="80427-136">如果您選取此選項，使用者無法執行程式碼來擷取的文件內容。</span><span class="sxs-lookup"><span data-stu-id="80427-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="80427-137">要求使用者確認他們的認證，在特定時間間隔。</span><span class="sxs-lookup"><span data-stu-id="80427-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="80427-138">如果您想要限制存取時間在指定期間內的內容，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="80427-138">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="80427-139">如果您選取此選項，以存取其內容的人員的發行授權而即將到期之後指定的數天及人員都必須以返回確認他們的認證，並下載一份新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="80427-139">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="80427-140">選取 [**的使用者必須先確認認證使用此間隔時間 （天）** 核取方塊，，然後指定您想要檢視的文件的天數。</span><span class="sxs-lookup"><span data-stu-id="80427-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="80427-141">防止人員上傳到此清單或文件庫，不支援 IRM 的文件。</span><span class="sxs-lookup"><span data-stu-id="80427-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="80427-142">如果您選取此選項時，人員無法上載的任何下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="80427-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="80427-143">沒有對應的 IRM 保護裝置在所有前端網頁伺服器上安裝的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="80427-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="80427-144">SharePoint Server 2010 無法解密的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="80427-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="80427-145">會受 IRM 保護之另一個程式中的檔案類型</span><span class="sxs-lookup"><span data-stu-id="80427-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="80427-146">選取**不允許使用者上傳文件，並不支援 IRM**核取方塊。</span><span class="sxs-lookup"><span data-stu-id="80427-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="80427-147">移除受限制的權限此清單或文件庫上特定日期。</span><span class="sxs-lookup"><span data-stu-id="80427-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="80427-148">選取 [**停止限制在庫的存取權**] 核取方塊，然後再選取 [您想要的日期。</span><span class="sxs-lookup"><span data-stu-id="80427-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="80427-149">控制項的程式，授權以開啟文件快取認證的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="80427-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="80427-150">在 [**設定群組保護和認證間隔**，請輸入 theinterval 中的天數的快取認證。</span><span class="sxs-lookup"><span data-stu-id="80427-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="80427-151">允許群組保護，以便使用者可與其共用同一個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="80427-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="80427-152">選取 [**允許群組保護**，然後輸入共用的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="80427-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="80427-153">選取您要的選項之後，請按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="80427-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="80427-154">什麼是資訊版權管理？</span><span class="sxs-lookup"><span data-stu-id="80427-154">What is Information Rights Management?</span></span>
<span data-ttu-id="80427-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="80427-155"></span></span>

<span data-ttu-id="80427-156">資訊版權管理 (IRM) 可讓您以限制使用者可以在已從清單或文件庫下載的檔案採取的動作。</span><span class="sxs-lookup"><span data-stu-id="80427-156">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="80427-157">IRM 會加密下載的檔案，並限制能夠解密這些檔案的使用者及程式。</span><span class="sxs-lookup"><span data-stu-id="80427-157">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="80427-158">IRM 也會限制能夠讀取檔案的使用者權限，如此一來，使用者就無法進行像是列印檔案複本或從檔案複製文字之類的動作。</span><span class="sxs-lookup"><span data-stu-id="80427-158">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="80427-159">您可以在清單或文件庫中使用 IRM，來限制的敏感內容散佈。</span><span class="sxs-lookup"><span data-stu-id="80427-159">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="80427-160">例如，如果您要建立要與選取行銷人員共用資訊即將來臨的產品文件庫，您可以使用 IRM，防止這些人與其他員工在公司中共用此內容。</span><span class="sxs-lookup"><span data-stu-id="80427-160">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="80427-161">在網站上，您將 IRM 套用至整個清單或文件庫，而不是個別的檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-161">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="80427-162">這有助於確保一致的整個集的文件或檔案的保護層級。</span><span class="sxs-lookup"><span data-stu-id="80427-162">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="80427-163">IRM 因此可以協助您的組織來強制執行公司控管的使用和散佈的專利或機密資訊的原則。</span><span class="sxs-lookup"><span data-stu-id="80427-163">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80427-164">資訊版權管理有關此頁面上的資訊會參照 '資訊版權管理' 任何字詞取代任何 Microsoft SharePoint Server 2013 和 SharePoint Server 2016 授權字詞協議中。</span><span class="sxs-lookup"><span data-stu-id="80427-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="80427-165">IRM 可以如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="80427-165">How IRM can help protect content</span></span>
<span data-ttu-id="80427-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="80427-166"></span></span>

<span data-ttu-id="80427-167">IRM 可協助保護受限制的內容如下：</span><span class="sxs-lookup"><span data-stu-id="80427-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="80427-168">這有助於避免複製、 修改、 列印、 傳真，或複製並貼上未經授權的使用的內容從授權檢視器</span><span class="sxs-lookup"><span data-stu-id="80427-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="80427-169">這有助於避免複製內容藉由使用 Microsoft Windows 中的 [列印螢幕] 功能已授權的檢視器</span><span class="sxs-lookup"><span data-stu-id="80427-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="80427-170">有助於防止未經授權的檢視器檢視的內容，如果它從伺服器下載之後，在電子郵件送出</span><span class="sxs-lookup"><span data-stu-id="80427-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="80427-171">限制存取權以一段時間的時間之後，使用者必須確認他們的認證，並再次下載內容的內容</span><span class="sxs-lookup"><span data-stu-id="80427-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="80427-172">協助強制執行公司使用與組織內的內容的散佈，進而管理的原則</span><span class="sxs-lookup"><span data-stu-id="80427-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="80427-173">IRM 無法如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="80427-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="80427-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="80427-174"></span></span>

<span data-ttu-id="80427-175">IRM 無法防止受限制的內容下列：</span><span class="sxs-lookup"><span data-stu-id="80427-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="80427-176">清除、 竊取、 擷取或由特洛伊木馬、 按鍵輸入記錄器等某些類型的間諜軟體的惡意程式的傳輸</span><span class="sxs-lookup"><span data-stu-id="80427-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="80427-177">遺失或損毀，因為電腦有病毒的動作</span><span class="sxs-lookup"><span data-stu-id="80427-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="80427-178">手動複製或重新輸入的內容從螢幕上顯示</span><span class="sxs-lookup"><span data-stu-id="80427-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="80427-179">數位或網片攝影的螢幕顯示的內容</span><span class="sxs-lookup"><span data-stu-id="80427-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="80427-180">透過協力廠商螢幕擷取程式複製</span><span class="sxs-lookup"><span data-stu-id="80427-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="80427-181">複製內容的中繼資料 （資料行的值） 透過協力廠商螢幕擷取程式或複製並貼上巨集指令</span><span class="sxs-lookup"><span data-stu-id="80427-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="80427-182">將資訊版權管理套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="80427-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="80427-183">IRM 的清單和文件庫的運作方式</span><span class="sxs-lookup"><span data-stu-id="80427-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="80427-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="80427-184"></span></span>

<span data-ttu-id="80427-185">IRM 保護套用至清單或文件庫層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="80427-186">文件庫啟用 IRM 時，版權管理套用至所有該文件庫中的檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="80427-187">如需清單啟用 IRM 時，版權管理僅適用於清單項目，不實際清單項目所附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="80427-188">當人員下載中啟用 IRM 的清單或文件庫的檔案時，檔案加密，因此只有授權的使用者可以檢視它們。</span><span class="sxs-lookup"><span data-stu-id="80427-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="80427-189">每個受版權管理檔案也包含會限制檢視檔案的人員的發行授權。</span><span class="sxs-lookup"><span data-stu-id="80427-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="80427-190">一般限制包括唯讀屬性，停用複製文字，防止人員從儲存本機複本，並列印檔案時，防止人員進行檔案。</span><span class="sxs-lookup"><span data-stu-id="80427-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="80427-191">可以讀取 IRM 支援的檔案類型的用戶端程式會使用受版權管理檔案內的發行授權，以強制執行這些限制。</span><span class="sxs-lookup"><span data-stu-id="80427-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="80427-192">這是如何受版權管理檔案會保留其保護即使它從伺服器下載。</span><span class="sxs-lookup"><span data-stu-id="80427-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="80427-193">它會從清單或文件庫下載時，會套用至檔案的限制的類型根據包含檔案的網站上的個別使用者的權限。</span><span class="sxs-lookup"><span data-stu-id="80427-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="80427-194">下表說明如何在網站上的權限對應至 IRM 權限。</span><span class="sxs-lookup"><span data-stu-id="80427-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="80427-195">**權限**</span><span class="sxs-lookup"><span data-stu-id="80427-195">**Permissions**</span></span>|<span data-ttu-id="80427-196">**IRM 權限**</span><span class="sxs-lookup"><span data-stu-id="80427-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80427-197">管理權限、 管理網站</span><span class="sxs-lookup"><span data-stu-id="80427-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="80427-198">**完全控制**（如用戶端程式所定義）： 此權限通常可讓使用者讀取、 編輯、 複製、 儲存及修改受版權管理內容的權限。</span><span class="sxs-lookup"><span data-stu-id="80427-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="80427-199">編輯項目、 管理清單、 新增並自訂頁面</span><span class="sxs-lookup"><span data-stu-id="80427-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="80427-200">**編輯**、**複製**及**儲存**： 使用者可以列印的檔案，才**允許使用者列印文件**] 核取方塊已選取清單或文件庫的資訊版權管理設定] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="80427-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="80427-201">檢視項目</span><span class="sxs-lookup"><span data-stu-id="80427-201">View Items</span></span>  <br/> |<span data-ttu-id="80427-202">**讀取**： 使用者可以讀取文件，但不能複製或修改其內容。</span><span class="sxs-lookup"><span data-stu-id="80427-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="80427-203">只有在清單或文件庫的資訊版權管理設定] 頁面上已選取 [**允許使用者列印文件**核取方塊，可以列印使用者。</span><span class="sxs-lookup"><span data-stu-id="80427-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="80427-204">其他</span><span class="sxs-lookup"><span data-stu-id="80427-204">Other</span></span>  <br/> |<span data-ttu-id="80427-205">沒有其他權限會直接對應到 IRM 權限。</span><span class="sxs-lookup"><span data-stu-id="80427-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="80427-206">當您啟用 IRM 的清單或文件庫在 SharePoint Server 2013 中的時，您可以只會保護該清單或文件庫的所有前端網頁伺服器安裝保護裝置中的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="80427-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers.</span></span> <span data-ttu-id="80427-207">保護裝置是控制項的加密和解密受版權管理特定的檔案格式的檔案的程式。</span><span class="sxs-lookup"><span data-stu-id="80427-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="80427-208">SharePoint 還包含下列檔案類型的保護裝置：</span><span class="sxs-lookup"><span data-stu-id="80427-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="80427-209">Microsoft Office InfoPath 表單</span><span class="sxs-lookup"><span data-stu-id="80427-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="80427-210">下列的 Microsoft Office 程式的 97-2003年檔案格式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="80427-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="80427-211">Office Open XML 格式的下列的 Microsoft Office 程式： Word、 Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="80427-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="80427-212">XML Paper Specification (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="80427-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="80427-213">如果您的組織計劃要用於 IRM 保護除了上面所列的任何其他檔案類型，您的伺服器管理員必須安裝下列其他檔案格式的保護裝置。</span><span class="sxs-lookup"><span data-stu-id="80427-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

