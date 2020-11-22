---
title: 了解敏感度標籤
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 使用 Microsoft 資訊保護架構中的敏感度標籤，以透過加密和浮水印來分類及保護機密內容。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: e881a9178e6b4d4cf703c329dea6f50acb0393c5
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371645"
---
# <a name="learn-about-sensitivity-labels"></a><span data-ttu-id="4b50e-103">了解敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4b50e-103">Learn about sensitivity labels</span></span>

><span data-ttu-id="4b50e-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="4b50e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4b50e-p101">為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不會停留在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而您希望內容以符合組織的商務及合規性原則的安全、受保護的方式進行漫遊。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p101">To get their work done, people in your organization collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall—it can roam everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization's business and compliance policies.</span></span>

<span data-ttu-id="4b50e-108">來自 Microsoft 資訊保護架構的敏感度標籤可讓您分類及保護組織的資料，同時確保使用者生產效率和共同作業能力不受影響。</span><span class="sxs-lookup"><span data-stu-id="4b50e-108">Sensitivity labels from the Microsoft Information Protection framework let you classify and protect your organization's data, while making sure that user productivity and their ability to collaborate isn't hindered.</span></span>

<span data-ttu-id="4b50e-p102">從功能區上的 **[首頁]** 索引標籤顯示 Excel 中可用敏感度標籤的範例。在此範例中，已套用的標籤會顯示在狀態列上：</span><span class="sxs-lookup"><span data-stu-id="4b50e-p102">Example showing available sensitivity labels in Excel, from the **Home** tab on the Ribbon. In this example, the applied label displays on the status bar:</span></span>

![Excel 功能區和狀態列上的敏感度標籤](../media/Sensitivity-label-in-Excel.png)

<span data-ttu-id="4b50e-112">若要套用敏感度標籤，使用者必須使用 Microsoft 365 公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4b50e-112">To apply sensitivity labels, users must be signed in with their Microsoft 365 work or school account.</span></span>

> [!NOTE]
> <span data-ttu-id="4b50e-113">針對美國政府租使用者（GCC、GCC-H，和DoD），目前僅支援 Azure 資訊保護統一標籤用戶端和掃描器的敏感標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-113">For US Government tenants (GCC, GCC-H, and DoD), sensitivity labels are currently supported only for the Azure Information Protection unified labeling client and scanner.</span></span> 
> 
> <span data-ttu-id="4b50e-114">如需詳細資訊，請參閱 [Azure 資訊保護進階版政府服務描述](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-114">For more information, see [Azure Information Protection Premium Government Service Description](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).</span></span>

<span data-ttu-id="4b50e-115">您可以使用敏感度標籤來：</span><span class="sxs-lookup"><span data-stu-id="4b50e-115">You can use sensitivity labels to:</span></span>
  
- <span data-ttu-id="4b50e-p103">**在標記的內容上強制執行保護設定，例如加密或浮水印。** 例如，使用者可以將「機密」標籤套用至文件或電子郵件，該標籤即可加密內容，並套用「機密」浮水印。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p103">**Enforce protection settings such as encryption or watermarks on labeled content.** For example, your users can apply a Confidential label to a document or email, and that label can encrypt the content and apply a Confidential watermark.</span></span>

- <span data-ttu-id="4b50e-p104">**保護不同平台和裝置之間 Office 應用程式中的內容。** 如需支援的應用程式清單，請參閲 [在 Office 應用程式中使用敏感度標籤](sensitivity-labels-office-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p104">**Protect content in Office apps across different platforms and devices.** For a list of supported apps, see [Use sensitivity labels in Office apps](sensitivity-labels-office-apps.md).</span></span>

- <span data-ttu-id="4b50e-p105">使用 Microsoft 雲端 App 安全性 **保護協力廠商應用程式和服務中的內容**。透過雲端 App 安全性，您可以偵測、分類、標記並保護協力廠商應用程式和服務的內容，例如 SalesForce、Box 或 DropBox，即使協力廠商應用程式或服務無法讀取或支援敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p105">**Protect content in third-party apps and services** by using Microsoft Cloud App Security. With Cloud App Security, you can detect, classify, label, and protect content in third-party apps and services, such as SalesForce, Box, or DropBox, even if the third-party app or service does not read or support sensitivity labels.</span></span>

- <span data-ttu-id="4b50e-p106">**保護容器**，其中包括 Teams、Microsoft 365 群組和 SharePoint 網站。例如，設定隱私權設定、外部使用者存取和來自未受管理裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p106">**Protect containers** that include Teams, Microsoft 365 Groups and SharePoint sites. For example, set privacy settings, external user access, and access from unmanaged devices.</span></span>

- <span data-ttu-id="4b50e-p107">**將敏感度標籤擴充至協力廠商應用程式和服務。** 使用 Microsoft 資訊保護 SDK，協力廠商應用程式就可以讀取敏感度標籤，並且套用保護設定。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p107">**Extend sensitivity labels to third-party apps and services.** Using the Microsoft Information Protection SDK, third-party apps can read sensitivity labels and apply protection settings.</span></span>

- <span data-ttu-id="4b50e-p108">**將內容分類而不需使用任何保護設定。** 您只要將分類指派至內容 (就像貼紙)，分類就會在使用及共用內容時保留並跟隨內容。您可以使用此分類產生使用狀況報告，並查看敏感內容的活動資料。根據這項資訊，稍後您可以隨時選擇套用保護設定。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p108">**Classify content without using any protection settings.** You can also simply assign a classification to content (like a sticker) that persists and roams with the content as it's used and shared. You can use this classification to generate usage reports and see activity data for your sensitive content. Based on this information, you can always choose to apply protection settings later.</span></span>

<span data-ttu-id="4b50e-p109">在這些案例中，Microsoft 365 中的敏感度標籤可以幫助您對正確的內容採取正確的動作。使用敏感度標籤，您可以分類整個組織中的資料，並根據該分類強制執行保護設定。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p109">In all these cases, sensitivity labels in Microsoft 365 can help you take the right actions on the right content. With sensitivity labels, you can classify data across your organization, and enforce protection settings based on that classification.</span></span>

## <a name="what-a-sensitivity-label-is"></a><span data-ttu-id="4b50e-132">敏感度標籤是什麼</span><span class="sxs-lookup"><span data-stu-id="4b50e-132">What a sensitivity label is</span></span>

<span data-ttu-id="4b50e-133">當您將敏感度標籤指派給文件或電子郵件，它就像一個戳記套用在內容上，並且是：</span><span class="sxs-lookup"><span data-stu-id="4b50e-133">When you assign a sensitivity label to a document or email, it's like a stamp that's applied to content that is:</span></span>

- <span data-ttu-id="4b50e-p110">**可自訂。** 您可以為組織中不同等級的敏感內容建立類別，例如個人、公用、一般、機密、高度機密。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p110">**Customizable.** You can create categories for different levels of sensitive content in your organization, such as Personal, Public, General, Confidential, and Highly Confidential.</span></span>

- <span data-ttu-id="4b50e-p111">**純文字。** 由於標籤會以純文字形式儲存在內容的中繼資料中，因此第三方應用程式和服務可以讀取它，然後套用自己的保護動作 (如必要)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p111">**Clear text.** Because the label is stored in clear text in the content's metadata, third-party apps and services can read it and then apply their own protective actions, if required.</span></span>

- <span data-ttu-id="4b50e-p112">**持續性。** 將敏感度標籤套用至內容後，標籤會儲存在該電子郵件或文件的中繼資料內。這表示標籤會跟隨內容 (包括保護設定) 漫遊，且此資料成為套用和強制執行原則的基礎。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p112">**Persistent.** After you apply a sensitivity label to content, the label is stored in the metadata of that email or document. This means the label roams with the content, including the protection settings, and this data becomes the basis for applying and enforcing policies.</span></span>

<span data-ttu-id="4b50e-141">在 Office 應用程式中，敏感度標籤就像是在電子郵件或文件上讓使用者看的標記。</span><span class="sxs-lookup"><span data-stu-id="4b50e-141">In Office apps, a sensitivity label appears like a tag to users on an email or document.</span></span>

<span data-ttu-id="4b50e-p113">支援敏感度標籤的每個項目都可以套用單一敏感度標籤。文件和電子郵件可以同時套用敏感度標籤和[保留標籤](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p113">Each item that supports sensitivity labels can have a single sensitivity label applied to it. Documents and emails can have both a sensitivity label and a [retention label](retention.md#retention-labels) applied to them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b50e-144">![套用至電子郵件的敏感度標籤](../media/Sensitivity-label-on-email.png)</span><span class="sxs-lookup"><span data-stu-id="4b50e-144">![Sensitivity label applied to an email](../media/Sensitivity-label-on-email.png)</span></span>

## <a name="what-sensitivity-labels-can-do"></a><span data-ttu-id="4b50e-145">敏感度標籤的功能</span><span class="sxs-lookup"><span data-stu-id="4b50e-145">What sensitivity labels can do</span></span>

<span data-ttu-id="4b50e-p114">敏感度標籤套用至電子郵件或文件後，該標籤的任何已設定保護設定都會對內容強制執行。使用敏感度標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="4b50e-p114">After a sensitivity label is applied to an email or document, any configured protection settings for that label are enforced on the content. With a sensitivity label, you can:</span></span>

- <span data-ttu-id="4b50e-p115">只 **加密** 電子郵件或電子郵件和文件。您可以選擇哪些使用者或群組可以擁有權限來執行哪些動作，以及執行多久。例如，您可以選擇允許另一個組織內特定群組中的使用者有權在標記內容後的七天內檢閱內容。或者，可以讓使用者在套用標籤時，指派權限給內容，而不要使用系統管理員定義的權限。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p115">**Encrypt** email only or both email and documents. You can choose which users or group have permissions to perform which actions and for how long. For example, you can choose to allow users in a specific group in another organization to have permissions to review the content for only seven days after the content is labeled. Alternatively, instead of administrator-defined permissions, you can allow your users to assign permissions to the content when they apply the label.</span></span> 
    
    <span data-ttu-id="4b50e-152">如需建立或編輯敏感度標籤時 **加密** 設定的詳細資訊，請參閱 [使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-152">For more information about the **Encryption** settings when you create or edit a sensitivity label, see [Restrict access to content by using encryption in sensitivity labels](encryption-sensitivity-labels.md).</span></span>

- <span data-ttu-id="4b50e-p116">將浮水印、頁首或頁尾新增至已套用標籤的電子郵件或文件，以在使用 Office 應用程式時 **標記內容**。浮水印可以套用至文件 (而非電子郵件)。頁首和浮水印範例：</span><span class="sxs-lookup"><span data-stu-id="4b50e-p116">**Mark the content** when you use Office apps, by adding watermarks, headers, or footers to email or documents that have the label applied. Watermarks can be applied to documents but not email. Example header and watermark:</span></span>
    
    ![套用至文件的浮水印和頁首](../media/Sensitivity-label-watermark-header.png)
    
    <span data-ttu-id="4b50e-p117">需要檢查何時套用內容標記？請參閱 [Office 應用程式何時套用內容標記和加密](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p117">Need to check when content markings are applied? See [When Office apps apply content marking and encryption](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption).</span></span>
    
    <span data-ttu-id="4b50e-p118">某些 (但並非全部) 應用程式會使用變數來支援動態標記。例如，將標籤名稱或文件名稱插入頁首、頁尾或浮水印。如需詳細資訊，請參閱[使用變數動態標記](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p118">Some, but not all apps support dynamic markings by using variables. For example, insert the label name or document name into the header, footer, or watermark. For more information, see [Dynamic markings with variables](sensitivity-labels-office-apps.md#dynamic-markings-with-variables).</span></span>
    
    <span data-ttu-id="4b50e-p119">儘管您可以為這些內容標記設定自訂字型名稱和包括自訂按 RGB 代碼的各種字型顏色，但這些設定僅受 [Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)支援。除非僅使用此用戶端套用敏感度標籤，否則不要使用自訂字型設定並選取以其中一種顏色：黑色、黃色、藍色、綠色、紅色。</span><span class="sxs-lookup"><span data-stu-id="4b50e-p119">Although you can configure a custom font name for these content markings and a wide range of font colors that include custom by RGB code, these settings are supported only by the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2). Unless you only use this client to apply sensitivity labels, do not use the custom font setting and select one of the following colors: Black, yellow, blue, green, red.</span></span>

    <span data-ttu-id="4b50e-164">字串長度：浮水印限制為 255 個字元。</span><span class="sxs-lookup"><span data-stu-id="4b50e-164">String lengths: Watermarks are limited to 255 characters.</span></span> <span data-ttu-id="4b50e-165">頁首和頁尾均受限於 1024 個字元，但 Excel 除外。</span><span class="sxs-lookup"><span data-stu-id="4b50e-165">Headers and footers are limited to 1024 characters, except in Excel.</span></span> <span data-ttu-id="4b50e-166">對於頁首及頁尾，Excel 的總限制為 255 個字元，但此限制包含看不見的字元，例如格式代碼。</span><span class="sxs-lookup"><span data-stu-id="4b50e-166">Excel has a total limit of 255 characters for headers and footers but this limit includes characters that aren't visible, such as formatting codes.</span></span> <span data-ttu-id="4b50e-167">如果達到該限制，您輸入的字串就不會顯示在 Excel 中。</span><span class="sxs-lookup"><span data-stu-id="4b50e-167">If that limit is reached, the string you enter is not displayed in Excel.</span></span>

- <span data-ttu-id="4b50e-168">當您啟用功能，以 [在 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中使用敏感度標籤](sensitivity-labels-teams-groups-sites.md)時，**保護容器中的內容，例如網站和群組**。</span><span class="sxs-lookup"><span data-stu-id="4b50e-168">**Protect content in containers such as sites and groups** when you enable the capability to [use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites](sensitivity-labels-teams-groups-sites.md).</span></span>
    
    <span data-ttu-id="4b50e-169">您無法設定群組和網站的保護設定，除非您啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b50e-169">You can't configure protection settings for groups and sites until you enable this capability.</span></span> <span data-ttu-id="4b50e-170">此標籤設定並不會導致文件或電子郵件自動加標籤，相反的，標籤設定會透過控制可儲存內容所在容器的存取權，以保護內容。</span><span class="sxs-lookup"><span data-stu-id="4b50e-170">This label configuration doesn't result in documents or emails being automatically labeled but instead, the label settings protect content by controlling access to the container where content can be stored.</span></span> <span data-ttu-id="4b50e-171">這些設定包括隱私權設定、外部使用者存取和來自未受管理裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="4b50e-171">These settings include privacy settings, external user access, and access from unmanaged devices.</span></span>

- <span data-ttu-id="4b50e-172">**在 Office 應用程式中自動套用標籤，或建議標籤。**</span><span class="sxs-lookup"><span data-stu-id="4b50e-172">**Apply the label automatically in Office apps, or recommend a label.**</span></span> <span data-ttu-id="4b50e-173">您可以選擇您要標示的敏感資訊類型，且可以自動套用標籤，或提示使用者套用您建議的標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-173">You can choose what types of sensitive information that you want labeled, and the label can either be applied automatically, or you can prompt users to apply the label that you recommend.</span></span> <span data-ttu-id="4b50e-174">如果您建議使用某個標籤，提示會顯示您選擇的任何文字。</span><span class="sxs-lookup"><span data-stu-id="4b50e-174">If you recommend a label, the prompt displays whatever text you choose.</span></span> <span data-ttu-id="4b50e-175">例如：</span><span class="sxs-lookup"><span data-stu-id="4b50e-175">For example:</span></span>
    
    ![指派必要標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    <span data-ttu-id="4b50e-177">如需有關當您建立或編輯敏感度標籤時 **Office 應用程式的自動標籤** 設定的詳細資訊，請參閱 [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-177">For more information about the **Auto-labeling for Office apps** settings when you create or edit a sensitivity label, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

### <a name="label-scopes"></a><span data-ttu-id="4b50e-178">標籤範圍</span><span class="sxs-lookup"><span data-stu-id="4b50e-178">Label scopes</span></span>

<span data-ttu-id="4b50e-179">建立敏感度標籤時，系統會要求您設定標籤的範圍，其可決定兩個項目：</span><span class="sxs-lookup"><span data-stu-id="4b50e-179">When you create a sensitivity label, you're asked to configure the label's scope which determines two things:</span></span>
- <span data-ttu-id="4b50e-180">您可以針對該標籤設定的標籤設定</span><span class="sxs-lookup"><span data-stu-id="4b50e-180">Which label settings you can configure for that label</span></span>
- <span data-ttu-id="4b50e-181">標籤將向使用者顯示的位置</span><span class="sxs-lookup"><span data-stu-id="4b50e-181">Where the label will be visible to users</span></span>

<span data-ttu-id="4b50e-182">此範圍設定可讓您有僅適用文件和電子郵件的敏感度標籤，而無法為容器選取。</span><span class="sxs-lookup"><span data-stu-id="4b50e-182">This scope configuration lets you have sensitivity labels that are just for documents and emails and can't be selected for containers.</span></span> <span data-ttu-id="4b50e-183">同樣地，僅適用容器的敏感度標籤，亦無法為文件和電子郵件選取。</span><span class="sxs-lookup"><span data-stu-id="4b50e-183">And similarly, sensitivity labels that are just for containers and can't be selected for documents and emails.</span></span> <span data-ttu-id="4b50e-184">預設會選取這兩個範圍：</span><span class="sxs-lookup"><span data-stu-id="4b50e-184">By default, both scopes are selected:</span></span>

![敏感度標籤的範圍選項](../media/sensitivity-labels-scopes.png)

<span data-ttu-id="4b50e-186">當您變更此預設值並僅選取一個範圍時，您仍會看到另一個範圍組態設定的第一頁，但是您無法選取。</span><span class="sxs-lookup"><span data-stu-id="4b50e-186">When you change this default and select just one scope, you still see the first page of the configuration settings for the other scope but you can't select them.</span></span> <span data-ttu-id="4b50e-187">例如，如果未選取檔案和電子郵件的範圍，您就無法在下一頁選取選項：</span><span class="sxs-lookup"><span data-stu-id="4b50e-187">For example, if the scope for files and emails is not selected, you can't select the options on the next page:</span></span>

![敏感度標籤的無法使用選項](../media/sensitivity-labels-unavailable-settings.png)

<span data-ttu-id="4b50e-189">針對有無法使用選項的這些頁面，請選取 [下一步 **]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="4b50e-189">For these pages that have unavailable options, select **Next** to continue.</span></span> <span data-ttu-id="4b50e-190">或者，選取 [上一步 **]** 來變更標籤的範圍。</span><span class="sxs-lookup"><span data-stu-id="4b50e-190">Or, select **Back** to change the label's scope.</span></span>

### <a name="label-priority-order-matters"></a><span data-ttu-id="4b50e-191">標籤優先順序 (順序很重要)</span><span class="sxs-lookup"><span data-stu-id="4b50e-191">Label priority (order matters)</span></span>

<span data-ttu-id="4b50e-192">在您的系統管理中心中建立敏感度標籤時，它們會顯示在 [標籤] 頁面的 [敏感度] 索引標籤上的清單中。</span><span class="sxs-lookup"><span data-stu-id="4b50e-192">When you create your sensitivity labels in your admin center, they appear in a list on the **Sensitivity** tab on the **Labels** page.</span></span> <span data-ttu-id="4b50e-193">在此清單中，標籤的順序很重要，因為它反映的是其優先順序。</span><span class="sxs-lookup"><span data-stu-id="4b50e-193">In this list, the order of the labels is important because it reflects their priority.</span></span> <span data-ttu-id="4b50e-194">您想要讓最具限制性的敏感度標籤，例如 [高度機密性]，顯示在清單的最 **底端**，以及最不具限制性的敏感度標籤，例如公用，顯示在最 **上方**。</span><span class="sxs-lookup"><span data-stu-id="4b50e-194">You want your most restrictive sensitivity label, such as Highly Confidential, to appear at the **bottom** of the list, and your least restrictive sensitivity label, such as Public, to appear at the **top**.</span></span>

<span data-ttu-id="4b50e-195">您只能將一個敏感度標籤套用至一個項目，例如文件、電子郵件或容器。</span><span class="sxs-lookup"><span data-stu-id="4b50e-195">You can apply just one sensitivity label to an item such as a document, email, or container.</span></span> <span data-ttu-id="4b50e-196">如果您設定一個選項，要求使用者提供將標籤變更為較低分類的理由，則此清單的順序會識別分類下限。</span><span class="sxs-lookup"><span data-stu-id="4b50e-196">If you set an option that requires your users to provide a justification for changing a label to a lower classification, the order of this list identifies the lower classifications.</span></span> <span data-ttu-id="4b50e-197">不過，此選項不適用子標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-197">However, this option does not apply to sublabels.</span></span>

<span data-ttu-id="4b50e-198">不過，子標籤的排序會搭配[自動標記](apply-sensitivity-label-automatically.md)使用。</span><span class="sxs-lookup"><span data-stu-id="4b50e-198">The ordering of sublabels is used with [automatic labeling](apply-sensitivity-label-automatically.md), though.</span></span> <span data-ttu-id="4b50e-199">將標籤設定為自動套用或建議時，可能對多個標籤造成相符項目。</span><span class="sxs-lookup"><span data-stu-id="4b50e-199">When you configure labels to be applied automatically or as a recommendation, multiple matches can result for more than one label.</span></span> <span data-ttu-id="4b50e-200">若要判斷要套用或建議的標籤，會使用標籤順序：選取最後一個敏感度標籤，然後在適用時使用最後一個子標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-200">To determine the label to apply or recommend, the label ordering is used: The last sensitive label is selected, and then if applicable, the last sublabel.</span></span>

![建立子標籤的選項](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a><span data-ttu-id="4b50e-202">子標籤 (分組標籤)</span><span class="sxs-lookup"><span data-stu-id="4b50e-202">Sublabels (grouping labels)</span></span>

<span data-ttu-id="4b50e-203">您可以使用子標籤將一或多個標籤分組在 Office 應用程式中的使用者可看到的上層標籤之下。</span><span class="sxs-lookup"><span data-stu-id="4b50e-203">With sublabels, you can group one or more labels below a parent label that a user sees in an Office app.</span></span> <span data-ttu-id="4b50e-204">例如，在 [機密文件] 下，您的組織可能會使用不同的標籤來標示該分類的特定類型。</span><span class="sxs-lookup"><span data-stu-id="4b50e-204">For example, under Confidential, your organization might use several different labels for specific types of that classification.</span></span> <span data-ttu-id="4b50e-205">在此範例中，上層標籤 [機密文件] 只是沒有任何保護設定的文字標籤，且因為它有子標籤，所以無法套用至內容。</span><span class="sxs-lookup"><span data-stu-id="4b50e-205">In this example, the parent label Confidential is simply a text label with no protection settings, and because it has sublabels, it can't be applied to content.</span></span> <span data-ttu-id="4b50e-206">相反地，使用者必須選擇 [機密文件] 來查看子標籤，然後再選擇要套用到內容的子標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-206">Instead, users must choose Confidential to view the sublabels, and then they can choose a sublabel to apply to content.</span></span>

<span data-ttu-id="4b50e-207">子標籤是以邏輯群組方式向使用者呈現標籤的一個簡單方式。</span><span class="sxs-lookup"><span data-stu-id="4b50e-207">Sublabels are simply a way to present labels to users in logical groups.</span></span> <span data-ttu-id="4b50e-208">子標籤不繼承其上層標籤的任何設定。</span><span class="sxs-lookup"><span data-stu-id="4b50e-208">Sublabels don't inherit any settings from their parent label.</span></span> <span data-ttu-id="4b50e-209">當您發佈使用者的子標籤時，該使用者就可以將該子標籤套用到內容，但不能只套用上層標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-209">When you publish a sublabel for a user, that user can then apply that sublabel to content but can't apply just the parent label.</span></span>

<span data-ttu-id="4b50e-210">請勿將上層籤選為預設標籤，或將上層標籤設定為自動套用 (或建議使用)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-210">Don't choose a parent label as the default label, or configure a parent label to be automatically applied (or recommended).</span></span> <span data-ttu-id="4b50e-211">如果這麼做，系統就不會將上層標籤套用至內容。</span><span class="sxs-lookup"><span data-stu-id="4b50e-211">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="4b50e-212">子標籤如何對使用者顯示的範例：</span><span class="sxs-lookup"><span data-stu-id="4b50e-212">Example of how sublabels display for users:</span></span>

![功能區上分組的子標籤](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a><span data-ttu-id="4b50e-214">編輯或刪除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4b50e-214">Editing or deleting a sensitivity label</span></span>

<span data-ttu-id="4b50e-215">如果您從系統管理中心刪除敏感度標籤，此標籤並未從內容中自動移除，且所有保護設定都會繼續在套用該標籤的內容上強制執行。</span><span class="sxs-lookup"><span data-stu-id="4b50e-215">If you delete a sensitivity label from your admin center, the label is not automatically removed from content, and any protection settings continue to be enforced on content that had that label applied.</span></span>

<span data-ttu-id="4b50e-216">如果您編輯敏感度標籤，則當初套用至內容的標籤版本會在內容上強制執行。</span><span class="sxs-lookup"><span data-stu-id="4b50e-216">If you edit a sensitivity label, the version of the label that was applied to content is what's enforced on that content.</span></span>

## <a name="what-label-policies-can-do"></a><span data-ttu-id="4b50e-217">標籤原則的功能</span><span class="sxs-lookup"><span data-stu-id="4b50e-217">What label policies can do</span></span>

<span data-ttu-id="4b50e-218">在您建立敏感度標籤之後，您必須發佈這些標籤，使其可供組織中的人員和服務使用。</span><span class="sxs-lookup"><span data-stu-id="4b50e-218">After you create your sensitivity labels, you need to publish them, to make them available to people and services in your organization.</span></span> <span data-ttu-id="4b50e-219">然後可以將敏感度標籤套用至文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4b50e-219">The sensitivity labels can then be applied to documents and emails.</span></span> <span data-ttu-id="4b50e-220">不同於保留標籤 (發佈到諸如所有 Exchange 信箱的位置)，會對使用者或群組發佈敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-220">Unlike retention labels, which are published to locations such as all Exchange mailboxes, sensitivity labels are published to users or groups.</span></span> <span data-ttu-id="4b50e-221">敏感度標籤接著就會出現在這些使用者和群組的 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="4b50e-221">Sensitivity labels then appear in Office apps for those users and groups.</span></span>

<span data-ttu-id="4b50e-222">使用標籤原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="4b50e-222">With a label policy, you can:</span></span>

- <span data-ttu-id="4b50e-223">**選擇可看見標籤的使用者和群組。**</span><span class="sxs-lookup"><span data-stu-id="4b50e-223">**Choose which users and groups see the labels.**</span></span> <span data-ttu-id="4b50e-224">可以在 Azure AD 中將標籤發佈到任何特定的使用者或啟用電子郵件功能的安全性群組、通訊群組或 Microsoft 365 群組 (可以有 [動態成員資格](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule))。</span><span class="sxs-lookup"><span data-stu-id="4b50e-224">Labels can be published to any specific user or email-enabled security group, distribution group, or Microsoft 365 group (which can have [dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)) in Azure AD.</span></span>

- <span data-ttu-id="4b50e-225">**套用預設標籤** 至由標籤原則中包含的所有使用者和群組所建立的新文件和電子郵件，以及將相同或不同的預設標籤套用至容器 (如果您 [已為 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站啟用敏感度標籤](sensitivity-labels-teams-groups-sites.md))。</span><span class="sxs-lookup"><span data-stu-id="4b50e-225">**Apply a default label** to all new documents and email created by the users and groups included in the label policy, and the same or different default label to containers (if you've [enabled sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites](sensitivity-labels-teams-groups-sites.md)).</span></span> <span data-ttu-id="4b50e-226">如果使用者的文件或電子郵件不是正確的標籤，使用者可以隨時變更預設標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-226">Users can always change the default label if it's not the right label for their document or email.</span></span> 
    
    <span data-ttu-id="4b50e-227">請考慮使用預設標籤來設定您想套用到所有內容中的基本保護設定等級。</span><span class="sxs-lookup"><span data-stu-id="4b50e-227">Consider using a default label to set a base level of protection settings that you want applied to all your content.</span></span> <span data-ttu-id="4b50e-228">不過，若沒有使用者訓練和其他控制項，這項設定也可能導致不正確的標記。</span><span class="sxs-lookup"><span data-stu-id="4b50e-228">However, without user training and other controls, this setting can also result in inaccurate labeling.</span></span> <span data-ttu-id="4b50e-229">選取將套用加密作為對文件之預設標籤的標籤並不是個好主意。</span><span class="sxs-lookup"><span data-stu-id="4b50e-229">It's usually not a good idea to select a label that applies encryption as a default label to documents.</span></span> <span data-ttu-id="4b50e-230">例如，許多組織需要將文件傳送與共用給外部使用者，而這些使用者可能沒有支援加密的應用程式，或可能不會使用可授權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4b50e-230">For example, many organizations need to send and share documents with external users who might not have apps that support the encryption or they might not use an account that can be authorized.</span></span> <span data-ttu-id="4b50e-231">如需此案例的詳細資訊，請參閱 [與外部使用者共用加密檔](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-231">For more information about this scenario, see [Sharing encrypted documents with external users](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).</span></span>

- <span data-ttu-id="4b50e-232">**需要變更標籤的理由。**</span><span class="sxs-lookup"><span data-stu-id="4b50e-232">**Require a justification for changing a label.**</span></span> <span data-ttu-id="4b50e-233">如果使用者嘗試移除標籤，或以較低順序編號的標籤取代其，您可以要求使用者提供理由來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4b50e-233">If a user tries to remove a label or replace it with a label that has a lower-order number, you can require the user provides a justification to perform this action.</span></span> <span data-ttu-id="4b50e-234">例如，使用者開啟標示為 [機密] (順序編號 3) 的文件，並將該標籤取代為 [公開] (順序編號 1)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-234">For example, a user opens a document labeled Confidential (order number 3) and replaces that label with one named Public (order number 1).</span></span> <span data-ttu-id="4b50e-235">目前，正當理由僅由 [Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)所使用，它會將此資訊傳送到 [Azure 資訊保護分析](https://docs.microsoft.com/azure/information-protection/reports-aip)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-235">Currently, the justification reason is used only by the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2), which sends this information to [Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

    ![提示使用者輸入理由](../media/Sensitivity-label-justification-required.png)

- <span data-ttu-id="4b50e-237">**要求使用者套用標籤**，一個選項用於電子郵件和文件，另一個用於容器。</span><span class="sxs-lookup"><span data-stu-id="4b50e-237">**Require users to apply a label** with one option for email and documents, and another for containers.</span></span> <span data-ttu-id="4b50e-238">這些選項也稱為強制標記，可確保必須先套用標籤，使用者才能儲存文件和傳送電子郵件，以及建立新群組或網站。</span><span class="sxs-lookup"><span data-stu-id="4b50e-238">Also known as mandatory labeling, these options ensure a label must be applied before users can save documents and send emails, and create new groups or sites.</span></span>
    
    <span data-ttu-id="4b50e-239">若為文件和電子郵件，標籤可由使用者手動指派、由於您設定的條件而自動指派，或依預設指派 (如上所述的預設標籤選項)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-239">For documents and emails, a label can be assigned manually by the user, automatically as a result of a condition that you configure, or be assigned by default (the default label option described above).</span></span> <span data-ttu-id="4b50e-240">當使用者需要指派標籤時，Outlook 中顯示的提示範例：</span><span class="sxs-lookup"><span data-stu-id="4b50e-240">An example prompt shown in Outlook when a user is required to assign a label:</span></span>

    ![Outlook 中要求使用者套用必要標籤的提示](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > <span data-ttu-id="4b50e-242">文件和電子郵件的強制標記目前需要 [Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-242">Mandatory labeling for documents and emails currently requires the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> <span data-ttu-id="4b50e-243">此用戶端僅能在 Windows 上執行，因此 Mac、iOS 和 Android 上尚不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="4b50e-243">This client runs only on Windows, so this feature is not yet supported on Mac, iOS, and Android.</span></span>
    
    <span data-ttu-id="4b50e-244">對於容器，您必須在建立群組或網站時指派標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-244">For containers, a label must be assigned at the time the group or site is created.</span></span>
    
    <span data-ttu-id="4b50e-245">請考慮使用此選項來協助增加您的標記涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="4b50e-245">Consider using this option to help increase your labeling coverage.</span></span> <span data-ttu-id="4b50e-246">不過，若沒有使用者訓練，這些設定可能導致不正確的標記。</span><span class="sxs-lookup"><span data-stu-id="4b50e-246">However, without user training, these settings can result in inaccurate labeling.</span></span> <span data-ttu-id="4b50e-247">此外，除非您也設定對應的預設標籤，否則強制標籤的常見提示可能會讓使用者感到無益。</span><span class="sxs-lookup"><span data-stu-id="4b50e-247">In addition, unless you also set a corresponding default label, mandatory labeling can frustrate your users with the frequent prompts.</span></span> 

- <span data-ttu-id="4b50e-248">**提供自訂說明頁面的說明連結。**</span><span class="sxs-lookup"><span data-stu-id="4b50e-248">**Provide help link to a custom help page.**</span></span> <span data-ttu-id="4b50e-249">如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供顯示在 Office 應用程式中 **[敏感度標籤]** 功能表底部的 [深入了解] URL：</span><span class="sxs-lookup"><span data-stu-id="4b50e-249">If your users aren't sure what your sensitivity labels mean or how they should be used, you can provide a Learn More URL that appears at the bottom of the **Sensitivity label** menu in the Office apps:</span></span>

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](../media/Sensitivity-label-learn-more.png)

<span data-ttu-id="4b50e-251">建立可將新敏感度標籤指派給使用者和群組的標籤原則之後，使用者在 30 分鐘之內會在他們的 Office 應用程式中看到這些標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-251">After you create a label policy that assigns new sensitivity labels to users and groups, users see those labels in their Office apps within 30 minutes.</span></span> <span data-ttu-id="4b50e-252">不過，請等候最多 24 小時讓這些標籤變更。</span><span class="sxs-lookup"><span data-stu-id="4b50e-252">However, allow up to 24 hours for changes to those labels.</span></span>

<span data-ttu-id="4b50e-253">您可以建立並發佈的敏感度標籤數量沒有任何限制，但有一個例外：如果標籤套用加密，則您可建立的標籤數上限為 500。</span><span class="sxs-lookup"><span data-stu-id="4b50e-253">There is no limit to the number of sensitivity labels that you can create and publish, with one exception: If the label applies encryption, there is a maximum of 500 labels that you can create.</span></span> <span data-ttu-id="4b50e-254">不過，為了降低系統管理負擔並為使用者減少複雜度，最佳做法是試著保持最少的標籤數量。</span><span class="sxs-lookup"><span data-stu-id="4b50e-254">However, as a best practice to lower admin overheads and reduce complexity for your users, try to keep the number of labels to a minimum.</span></span> <span data-ttu-id="4b50e-255">實際情況的部署已證明，當使用者擁有五個以上的主要標籤，或每個主要標籤有超過五個子標籤時，效果會明顯地降低。</span><span class="sxs-lookup"><span data-stu-id="4b50e-255">Real-world deployments have proved effectiveness to be noticeably reduced when users have more than five main labels or more than five sublabels per main label.</span></span>

### <a name="label-policy-priority-order-matters"></a><span data-ttu-id="4b50e-256">標籤原則優先順序 (順序很重要)</span><span class="sxs-lookup"><span data-stu-id="4b50e-256">Label policy priority (order matters)</span></span>

<span data-ttu-id="4b50e-257">您會在敏感度標籤原則中發佈敏感度標籤，以將其提供給使用者使用，而標籤會顯示在 [標籤原則] 頁面上 [敏感度原則] 索引標籤的清單中。</span><span class="sxs-lookup"><span data-stu-id="4b50e-257">You make your sensitivity labels available to users by publishing them in a sensitivity label policy that appears in a list on the **Sensitivity policies** tab on the **Label policies** page.</span></span> <span data-ttu-id="4b50e-258">正如同敏感度標籤 (請參閱[標籤原則優先順序 (順序很重要)](#label-priority-order-matters))，敏感度標籤原則的順序非常重要，因為順序反映的是優先順序。</span><span class="sxs-lookup"><span data-stu-id="4b50e-258">Just like sensitivity labels (see [Label priority (order matters)](#label-priority-order-matters)), the order of the sensitivity label policies is important because it reflects their priority.</span></span> <span data-ttu-id="4b50e-259">優先順序最低的標籤原則會顯示在 **上方**，而優先順序最高的標籤原則會顯示在 **下方**。</span><span class="sxs-lookup"><span data-stu-id="4b50e-259">The label policy with lowest priority is shown at the **top**, and the label policy with the highest priority is shown at the **bottom**.</span></span>

<span data-ttu-id="4b50e-260">標籤原則包含：</span><span class="sxs-lookup"><span data-stu-id="4b50e-260">A label policy consists of:</span></span>

- <span data-ttu-id="4b50e-261">一組標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-261">A set of labels.</span></span>
- <span data-ttu-id="4b50e-262">標籤原則的範圍，表示原則中包含的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="4b50e-262">The scope of the label policy, meaning the users and groups included in the policy.</span></span>
- <span data-ttu-id="4b50e-263">以上所述標籤原則的設定 (預設標籤、對齊、強制標籤和說明連結)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-263">The settings of the label policy described above (default label, justification, mandatory label, and help link).</span></span>

<span data-ttu-id="4b50e-264">您可以將使用者包含在多個標籤原則中，該使用者即會看到來自這些原則的所有敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-264">You can include a user in multiple label policies, and the user will see all the sensitivity labels from those policies.</span></span> <span data-ttu-id="4b50e-265">不過，使用者只會取得來自具有最高優先順序標籤原則的原則設定。</span><span class="sxs-lookup"><span data-stu-id="4b50e-265">However, a user gets the policy settings from only the label policy with the highest priority.</span></span>

<span data-ttu-id="4b50e-266">如果您沒有看到使用者或群組應有的標籤或標籤原則設定，且已等待 30 分鐘，請檢查敏感度標籤原則的順序。</span><span class="sxs-lookup"><span data-stu-id="4b50e-266">If you're not seeing the label or label policy setting that you expect for a user or group, and you have waited 30 minutes, check the order of the sensitivity label policies.</span></span> <span data-ttu-id="4b50e-267">若要重新排序標籤原則，請選取 [敏感度標籤原則] > 選擇右側的省略符號 > **[下移]** 或 **[上移]**。</span><span class="sxs-lookup"><span data-stu-id="4b50e-267">To reorder the label policies, select a sensitivity label policy > choose the ellipsis on the right > **Move down** or **Move up**.</span></span>

![敏感度標籤原則頁面上的移動選項](../media/sensitivity-label-policy-priority.png)

<span data-ttu-id="4b50e-269">如果您除了使用敏感度標籤，還使用了保留標籤，請務必記住優先順序對於敏感度標籤原則，但對於[保留標籤原則](retention.md#the-principles-of-retention-or-what-takes-precedence)則否。</span><span class="sxs-lookup"><span data-stu-id="4b50e-269">If you use retention labels in addition to sensitivity labels, it's important to remember that priority matters for sensitivity label policies, but not for [retention labels](retention.md#the-principles-of-retention-or-what-takes-precedence).</span></span>

## <a name="sensitivity-labels-and-azure-information-protection"></a><span data-ttu-id="4b50e-270">敏感度標籤和 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="4b50e-270">Sensitivity labels and Azure Information Protection</span></span>

<span data-ttu-id="4b50e-271">如果您已使用 Azure 資訊保護部署標籤，請在開始使用敏感度標籤之前，先使用下列各節中的指引。</span><span class="sxs-lookup"><span data-stu-id="4b50e-271">If you have deployed labels with Azure Information Protection, use the following sections for guidance before you start to use sensitivity labels.</span></span>

### <a name="azure-information-protection-labels"></a><span data-ttu-id="4b50e-272">Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="4b50e-272">Azure Information Protection labels</span></span>

> [!NOTE]
> <span data-ttu-id="4b50e-273">Azure 入口網站中 Azure 資訊保護標籤的標籤管理功能即將在 **2021 年 3 月 31 日** 淘汰。</span><span class="sxs-lookup"><span data-stu-id="4b50e-273">Label management for Azure Information Protection labels in the Azure portal is being deprecated **March 31, 2021**.</span></span> <span data-ttu-id="4b50e-274">請透過官方的[淘汰聲明](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179)深入了解。</span><span class="sxs-lookup"><span data-stu-id="4b50e-274">Learn more from the official [deprecation notice](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).</span></span>

<span data-ttu-id="4b50e-275">如果您因為您的租用戶尚不在[整合標籤平台](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)中而使用 Azure 資訊保護標籤，建議您在您啟用整合標籤前，避免建立敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-275">If you are using Azure Information Protection labels because your tenant isn't yet on the [unified labeling platform](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform), we recommend that you avoid creating sensitivity labels until you activate unified labeling.</span></span> <span data-ttu-id="4b50e-276">在此情況下，您在 Azure 入口網站中看到的標籤是 Azure 資訊保護標籤，而不是敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-276">In this scenario, the labels you see in the Azure portal are Azure Information Protection labels rather than sensitivity labels.</span></span> <span data-ttu-id="4b50e-277">這些標籤可由 Windows 電腦上的 Azure 資訊保護用戶端 (傳統) 使用，但不能由執行 macOS、iOS 或 Android 的裝置使用。</span><span class="sxs-lookup"><span data-stu-id="4b50e-277">These labels can be used by the Azure Information Protection client (classic) on Windows computers, but can't be used by devices running macOS, iOS, or Android.</span></span> <span data-ttu-id="4b50e-278">若要解決此問題，請[將這些標籤遷移](/azure/information-protection/configure-policy-migrate-labels)至敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-278">To resolve this, [migrate these labels](/azure/information-protection/configure-policy-migrate-labels) to sensitivity labels.</span></span> 

<span data-ttu-id="4b50e-279">這兩組標籤所套用的中繼資料彼此相容，因此您不須在完成移轉時，重新標記文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4b50e-279">The metadata applied by both sets of labels are compatible, so you don't need to relabel documents and emails when the migration is complete.</span></span>

### <a name="azure-information-protection-clients"></a><span data-ttu-id="4b50e-280">Azure 資訊保護用戶端</span><span class="sxs-lookup"><span data-stu-id="4b50e-280">Azure Information Protection clients</span></span>

<span data-ttu-id="4b50e-281">當您在 Windows 電腦上的 Microsoft 365 Apps 企業版應用程式中使用敏感度標籤時，您可以選擇使用 Azure 資訊保護用戶端，或使用 Office 內建的標記功能。</span><span class="sxs-lookup"><span data-stu-id="4b50e-281">When you use sensitivity labels in Microsoft 365 Apps for enterprise apps on Windows computers, you have a choice of using an Azure Information Protection client, or use labeling that's built into Office.</span></span>

<span data-ttu-id="4b50e-282">根據預設，安裝 Azure 資訊保護用戶端時，這些應用程式中的內建標記功能會關閉。</span><span class="sxs-lookup"><span data-stu-id="4b50e-282">By default, built-in labeling is turned off in these apps when the Azure Information Protection client is installed.</span></span> <span data-ttu-id="4b50e-283">如需詳細資訊，包括如何變更此預設行為，請參閱 [Office 內建標籤用戶端和 Azure 資訊保護用戶端](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-283">For more information, including how to change this default behavior, see [Office built-in labeling client and the Azure Information Protection client](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client).</span></span>

<span data-ttu-id="4b50e-284">即使是在 Office 應用程式中使用內建標籤時，也可以為下列項目使用 Azure 資訊保護的整合標籤用戶端，搭配敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="4b50e-284">Even when you use built-in labeling in Office apps, you can also use the Azure Information Protection unified labeling client with sensitivity labels for the following:</span></span>

- <span data-ttu-id="4b50e-285">掃描器，以探索儲存在內部部署的敏感性資訊，然後選擇性為該內容加上標籤</span><span class="sxs-lookup"><span data-stu-id="4b50e-285">A scanner to discover sensitive information that's stored on-premises, and then optionally, label that content</span></span>

- <span data-ttu-id="4b50e-286">檔案總管中的右鍵選項，讓使用者對所有檔案類型套用標籤</span><span class="sxs-lookup"><span data-stu-id="4b50e-286">Right-click options in File Explorer for users to apply labels to all file types</span></span>

- <span data-ttu-id="4b50e-287">檢視器，以顯示文字、影像或 PDF 文件的加密檔案</span><span class="sxs-lookup"><span data-stu-id="4b50e-287">A viewer to display encrypted files for text, images, or PDF documents</span></span>

- <span data-ttu-id="4b50e-288">PowerShell 模組，以探索內部部署檔案中的敏感性資訊，並對這些檔案套用或移除標籤和加密。</span><span class="sxs-lookup"><span data-stu-id="4b50e-288">A PowerShell module to discover sensitive information in files on premises, and apply or remove labels and encryption from these files.</span></span>

<span data-ttu-id="4b50e-289">如果您是 Azure 資訊保護的新使用者，或您是剛移轉標籤的現有 Azure 資訊保護客戶，請參閱來自 Azure 資訊保護文件的[選擇要用於 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-289">If you are new to Azure Information Protection, or if you are an existing Azure Information Protection customer that has just migrated your labels, see [Choose which labeling client to use for Windows computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection documentation.</span></span>

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a><span data-ttu-id="4b50e-290">敏感性標籤和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4b50e-290">Sensitivity labels and Microsoft Cloud App Security</span></span>

<span data-ttu-id="4b50e-291">您可以使用 Cloud App Security (CAS) 來探索、分類、加標籤，以及保護內容的第三方服務和應用程式 (例如 SalesForce、Box 或 Dropbox) 中的內容。</span><span class="sxs-lookup"><span data-stu-id="4b50e-291">By using Cloud App Security (CAS), you can discover, classify, label, and protect content in third-party services and apps, such as SalesForce, Box, or Dropbox.</span></span> 

<span data-ttu-id="4b50e-292">Cloud App Security 適用於 Azure 資訊保護標籤和敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="4b50e-292">Cloud App Security works with both Azure Information Protection labels and sensitivity labels:</span></span>

- <span data-ttu-id="4b50e-293">如果標籤系統管理中心已將一或多個敏感度標籤[發佈](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)給至少一個使用者：使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-293">If the labeling admin centers have one or more sensitivity labels [published](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) to at least one user: Sensitivity labels are used.</span></span>

- <span data-ttu-id="4b50e-294">如果標籤系統管理中心未發佈敏感度標籤：使用 Azure 資訊保護標籤。</span><span class="sxs-lookup"><span data-stu-id="4b50e-294">If the labeling admin centers don't have sensitivity labels published: Azure Information Protection labels are used.</span></span>

<span data-ttu-id="4b50e-295">如需有關使用 Cloud App Security 搭配這些標籤的指示，請參閱 [Azure 資訊保護整合](https://docs.microsoft.com/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-295">For instructions to use Cloud App Security with these labels, see [Azure Information Protection integration](https://docs.microsoft.com/cloud-app-security/azip-integration).</span></span>

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a><span data-ttu-id="4b50e-296">敏感度標籤和 Microsoft 資訊保護 SDK</span><span class="sxs-lookup"><span data-stu-id="4b50e-296">Sensitivity labels and the Microsoft Information Protection SDK</span></span>

<span data-ttu-id="4b50e-297">由於敏感度標籤是以純文字儲存在文件的中繼資料中，因此協力廠商的應用程式和服務都可讀取和寫入此標籤中繼資料，以補充您的標籤部署。</span><span class="sxs-lookup"><span data-stu-id="4b50e-297">Because a sensitivity label is stored as clear text in the metadata of a document, third-party apps and services can read from and write to this labeling metadata to supplement your labeling deployment.</span></span> <span data-ttu-id="4b50e-298">此外，軟體開發人員可以使用 [Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)，完全支援跨多個平臺的標籤和加密功能。</span><span class="sxs-lookup"><span data-stu-id="4b50e-298">Additionally, software developers can use the [Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk) to fully support labeling and encryption capabilities across multiple platforms.</span></span> <span data-ttu-id="4b50e-299">若要深入了解，請參閱[技術社群部落格上的正式版本公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-299">To learn more, see the [General Availability announcement on the Tech Community blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144).</span></span> 

<span data-ttu-id="4b50e-300">您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-300">You can also learn about [partner solutions that are integrated with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).</span></span>

## <a name="deployment-guidance"></a><span data-ttu-id="4b50e-301">部署指導方針</span><span class="sxs-lookup"><span data-stu-id="4b50e-301">Deployment guidance</span></span>

<span data-ttu-id="4b50e-302">如需部署規劃和指導方針，其中包含授權資訊、權限、部署策略，以及支援的案例和使用者文件的資源清單，請參閱[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="4b50e-302">For deployment planning and guidance that includes licensing information, permissions, deployment strategy, and a list of resources for supported scenarios and end user documentation, see [Get started with sensitivity labels](get-started-with-sensitivity-labels.md).</span></span>

