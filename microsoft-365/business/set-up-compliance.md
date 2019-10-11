---
title: Microsoft 365 商務版的增加威脅防護
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: 設定符合性功能，以防止資料遺失和標籤敏感資料。
ms.openlocfilehash: a0ba2fa6dbe7c786d577ad7098c1790f569f5acc
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453902"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="5ce13-103">設定合規性功能</span><span class="sxs-lookup"><span data-stu-id="5ce13-103">Set up compliance features</span></span>

<span data-ttu-id="5ce13-104">Microsoft 365 商務版隨附功能來保護您的資料和裝置，並協助您保護其他與您的客戶敏感資訊的安全。</span><span class="sxs-lookup"><span data-stu-id="5ce13-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="5ce13-105">設定 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="5ce13-105">Set up DLP features</span></span>

<span data-ttu-id="5ce13-106">如需有關如何設定的原則，以防止個人識別資訊 (PII) 的範例，請參閱[建立 DLP 原則範本中](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="5ce13-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="5ce13-107">DLP 隨附許多不同的地區設定的許多準備-使用原則範本。</span><span class="sxs-lookup"><span data-stu-id="5ce13-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="5ce13-108">例如，澳洲財務資料、 加拿大個人資訊法案、 美國財務資料，等等。如需完整清單，請參閱[什麼的 DLP 原則範本包含](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="5ce13-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="5ce13-109">所有這些範本可啟用類似 PII 範本範例。</span><span class="sxs-lookup"><span data-stu-id="5ce13-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="5ce13-110">設定搭配 Exchange Online Archiving 的電子郵件保留</span><span class="sxs-lookup"><span data-stu-id="5ce13-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="5ce13-111">**Exchange Online Archiving**授權功能可協助維護合規性和法規的標準來保留電子郵件內容 ediscovery （英文）。</span><span class="sxs-lookup"><span data-stu-id="5ce13-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="5ce13-112">它也可協助降低發生訴訟風險，並提供方法來復原資料安全性漏洞，或當您要復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="5ce13-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="5ce13-113">您可以使用訴訟暫止來保留的所有使用者的內容，或使用自訂您要保留的保留原則。</span><span class="sxs-lookup"><span data-stu-id="5ce13-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="5ce13-114">**訴訟資料暫留：** 您可以保留所有信箱內容，包括已刪除的項目依據] 將使用者的整個信箱放置於訴訟保留。</span><span class="sxs-lookup"><span data-stu-id="5ce13-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="5ce13-115">若要將信箱置於訴訟暫止，在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="5ce13-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="5ce13-116">在左側導覽中，移至 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="5ce13-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="5ce13-117">選取您想要置於 [訴訟暫止的信箱保留的使用者在使用者窗格中展開 [**郵件設定**和**其他設定**旁邊選擇 [**編輯 Exchange 屬性**。</span><span class="sxs-lookup"><span data-stu-id="5ce13-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="5ce13-118">在使用者信箱] 頁面上，選擇 [\* \* 信箱功能 \* \* 在左側導覽中，然後選擇 [在 [**訴訟暫止**] 下的 [**啟用**] 連結。</span><span class="sxs-lookup"><span data-stu-id="5ce13-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="5ce13-119">在**訴訟暫止狀態**對話方塊您可以指定訴訟保留期間在**訴訟暫止持續時間**] 欄位中，將欄位保留空白，如果您想要放置無限期的保留。</span><span class="sxs-lookup"><span data-stu-id="5ce13-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="5ce13-120">您也可以新增備忘稿並導向至網站，您可能必須將說明更多有關訴訟保留的郵件] 方塊中擁有者\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="5ce13-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="5ce13-121">**保留：** 您可以啟用自訂的保留原則，例如，若要保留經過一段時間，或在保留期間結束永久刪除內容。</span><span class="sxs-lookup"><span data-stu-id="5ce13-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="5ce13-122">若要深入了解，請參閱[保留原則的概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="5ce13-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="5ce13-123">敏感度標籤設定</span><span class="sxs-lookup"><span data-stu-id="5ce13-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="5ce13-124">敏感度標籤來自與 Azure 資訊保護 (AIP) 計劃 1，並有助於分類及選擇性地套用標籤，以保護您的文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5ce13-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="5ce13-125">定義規則和條件的系統管理員，以手動方式的使用者，或使用組合提供使用者的建議，可自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="5ce13-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="5ce13-126">若要設定敏感度標籤，檢視[建立及管理敏感度標籤](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)的影片。</span><span class="sxs-lookup"><span data-stu-id="5ce13-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="5ce13-127">以手動方式安裝 Azure 資訊保護用戶端</span><span class="sxs-lookup"><span data-stu-id="5ce13-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="5ce13-128">若要手動安裝 AIP 用戶端：</span><span class="sxs-lookup"><span data-stu-id="5ce13-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="5ce13-129">從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載**AzinfoProtection_UL.exe** 。</span><span class="sxs-lookup"><span data-stu-id="5ce13-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="5ce13-130">您可以確認安裝成功可以檢視 Word 文件，以確定可在 [**首頁**] 索引標籤上 [**敏感度**] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ce13-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="5ce13-131">![保護索引標籤下拉式清單中的 Word 文件。](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="5ce13-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="5ce13-132">如需詳細資訊，請參閱[安裝用戶端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="5ce13-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
