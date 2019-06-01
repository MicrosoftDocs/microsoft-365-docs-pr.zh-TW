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
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 設定 Office 365 進階威脅防護，和保護機密資料。
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668379"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="24c15-103">設定符合性功能</span><span class="sxs-lookup"><span data-stu-id="24c15-103">Set up compliance features</span></span>

<span data-ttu-id="24c15-104">Microsoft 365 商務版隨附功能來保護您的資料和裝置，並協助您保護其他與您的客戶敏感資訊的安全。</span><span class="sxs-lookup"><span data-stu-id="24c15-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="24c15-105">設定 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="24c15-105">Set up DLP features</span></span>

<span data-ttu-id="24c15-106">如需有關如何設定的原則，以防止個人識別資訊 (PII) 的範例，請參閱[建立 DLP 原則範本中](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="24c15-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="24c15-107">DLP 隨附許多不同的地區設定的許多準備-使用原則範本。</span><span class="sxs-lookup"><span data-stu-id="24c15-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="24c15-108">例如，澳洲財務資料、 加拿大個人資訊法案、 美國財務資料，等等。如需完整清單，請參閱[什麼的 DLP 原則範本包含](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="24c15-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="24c15-109">所有這些範本可啟用類似 PII 範本範例。</span><span class="sxs-lookup"><span data-stu-id="24c15-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="24c15-110">設定搭配 Exchange Online Archiving 的電子郵件保留</span><span class="sxs-lookup"><span data-stu-id="24c15-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="24c15-111">**Exchange Online Archiving**授權功能可協助維護合規性和法規的標準來保留電子郵件內容 ediscovery （英文）。</span><span class="sxs-lookup"><span data-stu-id="24c15-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="24c15-112">它也可協助降低發生訴訟風險，並提供方法來復原資料安全性漏洞，或當您要復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="24c15-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="24c15-113">您可以使用訴訟暫止來保留的所有使用者的內容，或使用自訂您要保留的保留原則。</span><span class="sxs-lookup"><span data-stu-id="24c15-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="24c15-114">**訴訟資料暫留：** 您可以保留所有信箱內容，包括已刪除的項目依據] 將使用者的整個信箱放置於訴訟保留。</span><span class="sxs-lookup"><span data-stu-id="24c15-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="24c15-115">若要將信箱置於訴訟暫止，在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="24c15-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="24c15-116">在左側導覽中，移至 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="24c15-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="24c15-117">選取您想要置於 [訴訟暫止的信箱保留的使用者在使用者窗格中展開 [**郵件設定**和**其他設定**旁邊選擇 [**編輯 Exchange 屬性**。</span><span class="sxs-lookup"><span data-stu-id="24c15-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="24c15-118">在使用者信箱] 頁面上，選擇 [\* \* 信箱功能 \* \* 在左側導覽中，然後選擇 [在 [**訴訟暫止**] 下的 [**啟用**] 連結。</span><span class="sxs-lookup"><span data-stu-id="24c15-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="24c15-119">在**訴訟暫止狀態**對話方塊您可以指定訴訟保留期間在**訴訟暫止持續時間**] 欄位中，將欄位保留空白，如果您想要放置無限期的保留。</span><span class="sxs-lookup"><span data-stu-id="24c15-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="24c15-120">您也可以新增備忘稿並導向至網站，您可能必須將說明更多有關訴訟保留的郵件] 方塊中擁有者\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="24c15-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="24c15-121">**保留：** 您可以啟用自訂的保留原則，例如，若要保留經過一段時間，或在保留期間結束永久刪除內容。</span><span class="sxs-lookup"><span data-stu-id="24c15-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="24c15-122">若要深入了解，請參閱[保留原則的概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="24c15-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="24c15-123">設定 Azure 資訊保護功能</span><span class="sxs-lookup"><span data-stu-id="24c15-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="24c15-124">Azure 資訊保護 (AIP) 可協助您分類，並選擇性地套用標籤，以保護您的文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="24c15-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="24c15-125">定義規則和條件的系統管理員，以手動方式的使用者，或使用組合提供使用者的建議，可自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="24c15-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="24c15-126">網頁型 Outlook 中您可以套用到您的電子郵件的下列內建的標籤和限制：</span><span class="sxs-lookup"><span data-stu-id="24c15-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="24c15-127">**不要轉寄**： 收件者可以讀取郵件，但他們無法轉寄、 列印或複製內容</span><span class="sxs-lookup"><span data-stu-id="24c15-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="24c15-128">**加密**： 加密整封郵件。</span><span class="sxs-lookup"><span data-stu-id="24c15-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="24c15-129">收件者存取加密的內容之前，必須先確認其身分識別，且無法移除加密。</span><span class="sxs-lookup"><span data-stu-id="24c15-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="24c15-130">**2 私人 3 機密**： 授與您的組織中的員工完整權限的電子郵件內容和附件，但不適用於您組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="24c15-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="24c15-131">資料擁有者可以追蹤及撤銷的任何一點的內容。</span><span class="sxs-lookup"><span data-stu-id="24c15-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="24c15-132">**高度機密**： 此限制可套用至高度機密資料，讓員工能夠檢視、 編輯和回覆，但不是轉寄、 列印或複製資料。</span><span class="sxs-lookup"><span data-stu-id="24c15-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="24c15-133">資料擁有者可以追蹤及撤銷的任何一點的內容。</span><span class="sxs-lookup"><span data-stu-id="24c15-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="24c15-134">請確定已啟動 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="24c15-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="24c15-135">若要確認 AIP 會在啟動：</span><span class="sxs-lookup"><span data-stu-id="24c15-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="24c15-136">登入[Azure 入口網站](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="24c15-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="24c15-137">*Azure 資訊保護*在**搜尋] 方塊**中，選取 [**所有服務**和類型。</span><span class="sxs-lookup"><span data-stu-id="24c15-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="24c15-138">一旦顯示結果，請按一下 [下一步] **Azure 資訊保護**來使其成為我的最愛且更容易尋找稍後開始。</span><span class="sxs-lookup"><span data-stu-id="24c15-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="24c15-139">選取 [ **Azure 資訊保護** \> **保護啟用**，並確定狀態設為啟用。</span><span class="sxs-lookup"><span data-stu-id="24c15-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="24c15-140">檢視 Azure 資訊保護原則和預設標籤</span><span class="sxs-lookup"><span data-stu-id="24c15-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="24c15-141">標籤來檢視及修改，現有：</span><span class="sxs-lookup"><span data-stu-id="24c15-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="24c15-142">在 [Azure 資訊保護儀表板中，選取 [**分類** \> **標籤**。</span><span class="sxs-lookup"><span data-stu-id="24c15-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="24c15-143">![標準的 Azure 資訊保護標籤。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="24c15-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="24c15-144">您可以選擇任何標籤來檢視的選項，您可以變更的顯示名稱、 色彩等等。</span><span class="sxs-lookup"><span data-stu-id="24c15-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="24c15-145">請參閱[修改，並建立新的標籤](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)如果您想要建立您自己。</span><span class="sxs-lookup"><span data-stu-id="24c15-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="24c15-146">以手動方式安裝 Azure 資訊保護用戶端</span><span class="sxs-lookup"><span data-stu-id="24c15-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="24c15-147">若要手動安裝 AIP 用戶端：</span><span class="sxs-lookup"><span data-stu-id="24c15-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="24c15-148">從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載**AzInfoProtection.exe** 。</span><span class="sxs-lookup"><span data-stu-id="24c15-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="24c15-149">您可以確認安裝成功可以檢視 Word 文件，以確定可在 [**首頁**] 索引標籤上 [**保護**] 選項。</span><span class="sxs-lookup"><span data-stu-id="24c15-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="24c15-150">![保護索引標籤下拉式清單中的 Word 文件。](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="24c15-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="24c15-151">如需詳細資訊，請參閱[安裝用戶端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="24c15-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
