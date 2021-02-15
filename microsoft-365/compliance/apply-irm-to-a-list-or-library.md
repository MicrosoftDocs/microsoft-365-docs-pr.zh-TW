---
title: 將資訊版權管理 (IRM) 套用至清單或文件庫
f1.keywords:
- NOCSH
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
- SPO_Content
description: 您可以使用資訊版權管理 (IRM) ，以協助控制和保護從清單或文件庫中下載的檔案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233349"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="c91ac-103">將資訊版權管理 (IRM) 套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="c91ac-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="c91ac-104">您可以使用資訊版權管理 (IRM) ，以協助控制和保護從清單或文件庫中下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span> <span data-ttu-id="c91ac-105">只有 Microsoft global cloud 支援此功能。</span><span class="sxs-lookup"><span data-stu-id="c91ac-105">This feature is only supported in the Microsoft global cloud.</span></span> <span data-ttu-id="c91ac-106">在全國雲端部署中 SharePoint 清單和文件庫不支援 IRM。</span><span class="sxs-lookup"><span data-stu-id="c91ac-106">IRM is not supported for SharePoint lists and libraries in national cloud deployments.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="c91ac-107">套用 IRM 之前的系統管理員準備工作</span><span class="sxs-lookup"><span data-stu-id="c91ac-107">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="c91ac-108">Azure Rights Management service 從 Azure 資訊保護 (Azure RMS) ，以及內部部署對等 Active Directory Rights Management Services (AD RMS) ，支援網站的資訊版權管理。</span><span class="sxs-lookup"><span data-stu-id="c91ac-108">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="c91ac-109">不需要個別或其他安裝。</span><span class="sxs-lookup"><span data-stu-id="c91ac-109">No separate or additional installations are required.</span></span>

- <span data-ttu-id="c91ac-110">將 IRM 套用至清單或文件庫之前，您必須為網站啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c91ac-110">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="c91ac-111">您將需要系統管理員許可權才能啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c91ac-111">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="c91ac-112">若要將 IRM 套用至清單或文件庫，您必須具有該清單或文件庫的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-112">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="c91ac-113">如果您使用的是線上 SharePoint，您的使用者可能會在下載較大的受 IRM 保護的檔案時遇到超時狀況。</span><span class="sxs-lookup"><span data-stu-id="c91ac-113">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="c91ac-114">若要避免超時，請使用 Office 程式來套用 IRM 保護，並在不使用 IRM 的 SharePoint 文件庫中儲存較大的檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-114">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="c91ac-115">如果您使用 SharePoint Server 2013，則伺服器管理員必須在所有的前端網頁伺服器上，針對組織中的人員要使用 IRM 來保護的每一種檔案類型，安裝保護程式。</span><span class="sxs-lookup"><span data-stu-id="c91ac-115">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="c91ac-116">將 IRM 套用至清單或文件庫</span><span class="sxs-lookup"><span data-stu-id="c91ac-116">Apply IRM to a list or library</span></span>
<span data-ttu-id="c91ac-117"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="c91ac-117"><a name="__toc256598179"> </a></span></span>

![資訊版權管理設定](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="c91ac-119">移至您要設定 IRM 的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="c91ac-119">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="c91ac-120">在功能區上，選取 [文檔 **庫** ] 索引標籤，然後選取 [文檔 **庫設定**]。</span><span class="sxs-lookup"><span data-stu-id="c91ac-120">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="c91ac-121"> (如果您正在使用清單，請選取 [ **清單** ] 索引標籤，然後選取 [ **清單設定** ]) 。</span><span class="sxs-lookup"><span data-stu-id="c91ac-121">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![功能區上的 SharePoint 文件庫設定] 按鈕](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="c91ac-123">在 [ **許可權與管理**] 底下，選取 [ **資訊版權管理**]。</span><span class="sxs-lookup"><span data-stu-id="c91ac-123">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="c91ac-124">若未出現 [資訊版權管理] 連結，表示您的網站可能並未啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c91ac-124">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="c91ac-125">請與您的伺服器管理員聯繫，以查看您是否可以為您的網站啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c91ac-125">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="c91ac-126">圖片庫未出現 [ **資訊版權管理** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="c91ac-126">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="c91ac-127">在 [ **資訊版權管理設定** ] 頁面上，選取 [ **在下載時限制此程式庫中檔的許可權** ] 核取方塊，即可將限制許可權套用至使用者從此清單或文件庫下載的檔。</span><span class="sxs-lookup"><span data-stu-id="c91ac-127">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="c91ac-128">在 [ **建立許可權原則標題** ] 方塊中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="c91ac-128">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="c91ac-129">請使用可協助您從其他原則識別此原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c91ac-129">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="c91ac-130">例如，使用 **公司機密** 將限制的許可權套用至包含機密公司檔的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="c91ac-130">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="c91ac-131">在 [ **新增許可權原則描述** ] 方塊中，輸入將向使用此清單或文件庫之使用者顯示的描述，以說明他們應如何處理此清單或文件庫中的檔。</span><span class="sxs-lookup"><span data-stu-id="c91ac-131">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="c91ac-132">例如，如果您想要將這些檔中的資訊存取許可權制為內部員工，您可以輸入 **[只與其他員工討論此檔的內容** ]。</span><span class="sxs-lookup"><span data-stu-id="c91ac-132">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="c91ac-133">若要將其他限制套用至此清單或文件庫中的檔，請選取 [ **顯示選項**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="c91ac-133">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="c91ac-134">**若要執行這項作業：**</span><span class="sxs-lookup"><span data-stu-id="c91ac-134">**To do this:**</span></span>|<span data-ttu-id="c91ac-135">**執行這項作業：**</span><span class="sxs-lookup"><span data-stu-id="c91ac-135">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c91ac-136">允許人員列印此清單或文件庫中的檔</span><span class="sxs-lookup"><span data-stu-id="c91ac-136">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="c91ac-137">選取 [ **允許查看者列印** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c91ac-137">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="c91ac-138">允許具有至少「查看專案」許可權的人員執行檔上的內嵌程式碼或宏。</span><span class="sxs-lookup"><span data-stu-id="c91ac-138">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="c91ac-139">選取 [ **允許查看者執行腳本和螢幕讀取器于已下載檔案的功能** ] 核取方塊。如果您選取此選項，則使用者可以執行程式碼來解壓縮檔的內容。</span><span class="sxs-lookup"><span data-stu-id="c91ac-139">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="c91ac-140">如果您想要限制對內容的存取一段指定的時間，請選取這個選項。</span><span class="sxs-lookup"><span data-stu-id="c91ac-140">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="c91ac-141">如果您選取此選項，則使用者的發行授權會在指定的天數後到期，並且需要人員傳回伺服器以驗證其認證，並下載新的副本。</span><span class="sxs-lookup"><span data-stu-id="c91ac-141">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="c91ac-142">選取 [ **下載後，檔訪問權力會在這些天數後到期 (1-365)** ] 核取方塊，然後指定您想要的檔可供查看的天數。</span><span class="sxs-lookup"><span data-stu-id="c91ac-142">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="c91ac-143">防止人員將不支援 IRM 的檔上傳至此清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="c91ac-143">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="c91ac-144">如果您選取此選項，則使用者將無法上傳下列任何檔案類型：所有前端網頁伺服器上都沒有安裝對應的 IRM 保護程式的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c91ac-144">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="c91ac-145">SharePoint Server 2010 的檔案類型無法解密。</span><span class="sxs-lookup"><span data-stu-id="c91ac-145">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="c91ac-146">在另一個程式中受 IRM 保護的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c91ac-146">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="c91ac-147">選取 [ **不允許使用者上傳不支援 IRM 的檔** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c91ac-147">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="c91ac-148">在特定日期移除此清單或文件庫的限制許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-148">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="c91ac-149">選取 [ **停止限制存取程式庫** ] 核取方塊，然後選取您想要的日期。</span><span class="sxs-lookup"><span data-stu-id="c91ac-149">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="c91ac-150">控制為開啟檔授權之程式快取認證的間隔。</span><span class="sxs-lookup"><span data-stu-id="c91ac-150">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="c91ac-151">選取 [ **使用者必須使用此間隔驗證其認證] (天)** ] 核取方塊，然後輸入以天數為單位的快取身分單位。</span><span class="sxs-lookup"><span data-stu-id="c91ac-151">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="c91ac-152">允許群組保護，讓使用者可以與相同群組的成員共用。</span><span class="sxs-lookup"><span data-stu-id="c91ac-152">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="c91ac-153">選取 [ **允許群組保護**]，然後輸入群組的共用名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c91ac-153">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="c91ac-154">選取您想要的選項之後，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c91ac-154">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="c91ac-155">何謂「資訊版權管理」？</span><span class="sxs-lookup"><span data-stu-id="c91ac-155">What is Information Rights Management?</span></span>
<span data-ttu-id="c91ac-156"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="c91ac-156"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="c91ac-157">資訊版權管理 (IRM) 可讓您限制使用者可對從清單或文件庫下載之檔案採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c91ac-157">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="c91ac-158">IRM 會加密下載的檔案，並限制能夠解密這些檔案的使用者及程式。</span><span class="sxs-lookup"><span data-stu-id="c91ac-158">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="c91ac-159">IRM 也會限制能夠讀取檔案的使用者權限，如此一來，使用者就無法進行像是列印檔案複本或從檔案複製文字之類的動作。</span><span class="sxs-lookup"><span data-stu-id="c91ac-159">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="c91ac-160">您可以在清單或文件庫上使用 IRM，以限制機密內容的散播。</span><span class="sxs-lookup"><span data-stu-id="c91ac-160">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="c91ac-161">例如，如果您要建立文件庫，以與選取的行銷代表共用即將推出之產品的資訊，您可以使用 IRM 來防止這些個人與公司中的其他員工共用此內容。</span><span class="sxs-lookup"><span data-stu-id="c91ac-161">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="c91ac-162">在網站上，您可以將 IRM 套用到整個清單或文件庫，而不是個別檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-162">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="c91ac-163">這可讓您更容易確定整個檔或檔案集的一致性層級。</span><span class="sxs-lookup"><span data-stu-id="c91ac-163">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="c91ac-164">因此，IRM 可協助您的組織強制實施公司原則，以管理機密或專有資訊的使用和傳播。</span><span class="sxs-lookup"><span data-stu-id="c91ac-164">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c91ac-165">此頁面上有關資訊版權管理的資訊會取代任何 Microsoft SharePoint Server 2013 中參照「資訊版權管理」的字詞，並 SharePoint 伺服器2016授權條款協定。</span><span class="sxs-lookup"><span data-stu-id="c91ac-165">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="c91ac-166">IRM 如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-166">How IRM can help protect content</span></span>
<span data-ttu-id="c91ac-167"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="c91ac-167"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="c91ac-168">IRM 協助以下列方式保護限制內容：</span><span class="sxs-lookup"><span data-stu-id="c91ac-168">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="c91ac-169">協助防止授權的檢視器複製、修改、列印、傳真或複製並貼上未經授權使用的內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-169">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="c91ac-170">協助防止授權的檢視器使用 Microsoft Windows 中的 [列印畫面] 功能來複製內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-170">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="c91ac-171">協助防止未經授權的檢視器在從伺服器下載後以電子郵件傳送內容來查看內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-171">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="c91ac-172">在指定的時間內限制存取內容，使用者必須先確認其認證，然後再次下載內容。</span><span class="sxs-lookup"><span data-stu-id="c91ac-172">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="c91ac-173">協助強制執行公司原則，以控制組織內的內容的使用和散播</span><span class="sxs-lookup"><span data-stu-id="c91ac-173">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="c91ac-174">IRM 無法如何協助保護內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-174">How IRM cannot help protect content</span></span>
<span data-ttu-id="c91ac-175"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="c91ac-175"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="c91ac-176">IRM 無法保護下列專案中的限制內容：</span><span class="sxs-lookup"><span data-stu-id="c91ac-176">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="c91ac-177">惡意程式（如特洛伊馬、按鍵記錄檔和某些類型的間諜軟體）的擦除、盜竊、捕獲或傳輸</span><span class="sxs-lookup"><span data-stu-id="c91ac-177">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="c91ac-178">因電腦病毒的動作而遺失或損毀</span><span class="sxs-lookup"><span data-stu-id="c91ac-178">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="c91ac-179">手動複製或重新鍵入螢幕上顯示的內容</span><span class="sxs-lookup"><span data-stu-id="c91ac-179">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="c91ac-180">螢幕上顯示內容的數位或膠片攝影</span><span class="sxs-lookup"><span data-stu-id="c91ac-180">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="c91ac-181">使用協力廠商的螢幕捕捉程式進行複製</span><span class="sxs-lookup"><span data-stu-id="c91ac-181">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="c91ac-182">透過使用協力廠商的畫面捕獲程式或複製和貼上動作) ，將內容中繼資料複製 (欄值</span><span class="sxs-lookup"><span data-stu-id="c91ac-182">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="c91ac-183">IRM 對於清單和文件庫的運作方式</span><span class="sxs-lookup"><span data-stu-id="c91ac-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="c91ac-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="c91ac-184"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="c91ac-185">IRM 保護適用于清單或文件庫層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="c91ac-186">針對文件庫啟用 IRM 時，版權管理會套用至該文件庫中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="c91ac-187">當您為清單啟用 IRM 時，版權管理只會套用至清單專案附加的檔案，而非實際的清單專案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="c91ac-188">當使用者在已啟用 IRM 的清單或文件庫中下載檔案時，這些檔案會進行加密，只有經過授權的人員才能加以查看。</span><span class="sxs-lookup"><span data-stu-id="c91ac-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="c91ac-189">每個版權管理檔案也包含發行授權，對查看檔案的人員有限制。</span><span class="sxs-lookup"><span data-stu-id="c91ac-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="c91ac-190">一般限制包括將檔案設為唯讀、停用文字的複製、防止使用者儲存本機副本，以及防止使用者列印檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="c91ac-191">可讀取 IRM 支援之檔案類型的用戶端程式會使用版權管理檔案中的發行授權，以強制執行這些限制。</span><span class="sxs-lookup"><span data-stu-id="c91ac-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="c91ac-192">這是版權管理檔案在從伺服器下載之後，如何保留其保護。</span><span class="sxs-lookup"><span data-stu-id="c91ac-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="c91ac-193">從清單或文件庫下載檔案時，套用至該檔案的限制類型，取決於包含檔案之網站上的個別使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="c91ac-194">下表說明網站許可權如何對應至 IRM 許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="c91ac-195">**權限**</span><span class="sxs-lookup"><span data-stu-id="c91ac-195">**Permissions**</span></span>|<span data-ttu-id="c91ac-196">**IRM 許可權**</span><span class="sxs-lookup"><span data-stu-id="c91ac-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c91ac-197">管理許可權、管理網站</span><span class="sxs-lookup"><span data-stu-id="c91ac-197">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="c91ac-198">由用戶端) 程式所定義 (**完全控制**：此許可權通常可讓使用者讀取、編輯、複製、儲存及修改受版權管理內容的許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="c91ac-199">編輯專案、管理清單、新增和自訂頁面</span><span class="sxs-lookup"><span data-stu-id="c91ac-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="c91ac-200">**編輯**、 **複製** 及 **儲存**：只有在清單或文件庫的 [資訊版權管理設定] 頁面上選取 [ **允許使用者列印** 檔] 核取方塊時，使用者才可以列印檔案。</span><span class="sxs-lookup"><span data-stu-id="c91ac-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="c91ac-201">檢視項目</span><span class="sxs-lookup"><span data-stu-id="c91ac-201">View Items</span></span>|<span data-ttu-id="c91ac-202">已 **閱讀**：使用者可以讀取檔，但無法複製或修改其內容。</span><span class="sxs-lookup"><span data-stu-id="c91ac-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="c91ac-203">只有在清單或文件庫的 [資訊版權管理設定] 頁面上選取 [ **允許使用者列印檔案** ] 核取方塊時，使用者才可以列印。</span><span class="sxs-lookup"><span data-stu-id="c91ac-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="c91ac-204">其他</span><span class="sxs-lookup"><span data-stu-id="c91ac-204">Other</span></span>|<span data-ttu-id="c91ac-205">其他許可權都不會直接對應至 IRM 許可權。</span><span class="sxs-lookup"><span data-stu-id="c91ac-205">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="c91ac-206">當您為 SharePoint Server 2013 中的清單或文件庫啟用 IRM 時，您只能保護在所有前端網頁伺服器上安裝保護裝置的清單或文件庫中的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c91ac-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="c91ac-207">保護裝置是一種程式，可控制特定檔案格式之受版權管理之檔案的加密和解密。</span><span class="sxs-lookup"><span data-stu-id="c91ac-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="c91ac-208">SharePoint 包含下列檔案類型的保護器：</span><span class="sxs-lookup"><span data-stu-id="c91ac-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="c91ac-209">Microsoft Office InfoPath 表單</span><span class="sxs-lookup"><span data-stu-id="c91ac-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="c91ac-210">下列 Microsoft Office 程式的97-2003 檔案格式： Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c91ac-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c91ac-211">下列 Microsoft Office 程式的 Office Open XML 格式： Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c91ac-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c91ac-212">XML 紙張規格 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="c91ac-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="c91ac-213">如果您的組織打算使用 IRM 來保護其他檔案類型，除了上述所列之外，您的伺服器管理員必須安裝其他檔案格式的保護程式。</span><span class="sxs-lookup"><span data-stu-id="c91ac-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

