---
title: 設定為 Microsoft 365 商務版使用者的進階的安全性原則
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663630"
---
# <a name="set-up-advanced-security-policies"></a><span data-ttu-id="03c67-103">設定進階的安全性原則</span><span class="sxs-lookup"><span data-stu-id="03c67-103">Set up advanced security policies</span></span>

<span data-ttu-id="03c67-104">除了您可以在[系統管理中心](security-features.md#microsoft-365-business-admin-center-security-features)中設定的原則，您可以新增額外保護，防範網路威脅設定[Office 365 進階威脅防護](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)(ATP)。</span><span class="sxs-lookup"><span data-stu-id="03c67-104">In addition to the policies you can set up in the [admin center](security-features.md#microsoft-365-business-admin-center-security-features), you can add additional protection against cyber threats by setting up [Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP).</span></span> <span data-ttu-id="03c67-105">您可以也保護敏感的資訊來設定[資料外洩防護](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、 Azure 資訊保護 (AIP)、 [Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)，並也能管理您的裝置[Intune 入口網站](#go-to-intune-admin-center)中。</span><span class="sxs-lookup"><span data-stu-id="03c67-105">You can also guard sensitive information by setting up [Data Loss Prevention](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), [Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email), and also manage your devices in the [Intune portal](#go-to-intune-admin-center).</span></span>

<span data-ttu-id="03c67-106">請參閱[上方的 10 種方法來保護 Microsoft 365 商務版計劃](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的最重要的方式在其中您可以保護您的業務，包括使用 MFA 來建立第二個表單的登入概觀。</span><span class="sxs-lookup"><span data-stu-id="03c67-106">See [top 10 ways to secure Microsoft 365 Business plan](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for an overview of the most important ways in which you can protect your business, including using MFA to create a second form of sign-in.</span></span>

<span data-ttu-id="03c67-107">請參閱[保護您的企業開發人員訓練影片](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787)指示輕鬆依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="03c67-107">See [Secure your business training videos](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) for instructions for easy to follow instructions.</span></span>

## <a name="increase-email-malware-protection"></a><span data-ttu-id="03c67-108">增加電子郵件的惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="03c67-108">Increase email malware protection</span></span>

<span data-ttu-id="03c67-109">惡意程式碼是一種可能危害您的電腦或網路、 軟體、 可能竊取您，包括個人或客戶資訊的資料。</span><span class="sxs-lookup"><span data-stu-id="03c67-109">Malware is software that can damage your computers or network, and possibly to steal data from you, including personal or customer information.</span></span> <span data-ttu-id="03c67-110">Microsoft 365 商務版包含防範惡意程式碼、 的基準層級，但您可以增加此保護設定其他設定。</span><span class="sxs-lookup"><span data-stu-id="03c67-110">Microsoft 365 Business includes a baseline level of protection against malware, but you can increase this protection by setting up additional settings.</span></span> <span data-ttu-id="03c67-111">如需相關指示[開啟惡意程式碼偵測](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)訓練影片，請參閱。</span><span class="sxs-lookup"><span data-stu-id="03c67-111">See [turn on malware detection](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) training video for instructions.</span></span>

## <a name="set-up-advanced-threat-protection-features"></a><span data-ttu-id="03c67-112">設定進階威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="03c67-112">Set up Advanced Threat Protection features</span></span>

- <span data-ttu-id="03c67-113">**不安全附件針對保護：** ATP 會識別惡意內容，藉由在虛擬環境中開啟電子郵件附件以及執行分析所產生的行為。</span><span class="sxs-lookup"><span data-stu-id="03c67-113">**Protect against unsafe attachments:** ATP identifies malicious content by opening email attachments in a virtual environment and performing analysis of the resulting behavior.</span></span> <span data-ttu-id="03c67-114">內容進行評估，以判斷其意圖 （無論是標準還是惡意），並且 ATP 封鎖不安全附件，傳遞致力於保護您抵禦網路釣魚配置和勒索軟體感染。</span><span class="sxs-lookup"><span data-stu-id="03c67-114">The content is evaluated to determine its intent (whether normal or malicious), and ATP blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="03c67-115">若要啟用附件保護，請參閱[設定 Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)協助文件，並[防止惡意檔案](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)簡短的訓練影片。</span><span class="sxs-lookup"><span data-stu-id="03c67-115">To activate attachment protection, see [set up Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) help documentation, and [protect against malicious files](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) short training video.</span></span>
    
- <span data-ttu-id="03c67-116">**保護您的環境，當使用者按一下惡意連結：** ATP 也會在使用者按一下這些階段檢查電子郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="03c67-116">**Protect your environment when users click malicious links:** ATP also examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="03c67-117">不安全連結時，使用者是警告未以瀏覽網站，或通知網站已被封鎖。</span><span class="sxs-lookup"><span data-stu-id="03c67-117">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="03c67-118">這有助於防止網路釣魚配置。</span><span class="sxs-lookup"><span data-stu-id="03c67-118">This helps protect against phishing schemes.</span></span> <span data-ttu-id="03c67-119">若要啟用此，請參閱[設定 Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)協助文件和[防範惡意網站](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)簡短訓練影片。</span><span class="sxs-lookup"><span data-stu-id="03c67-119">To activate this, see [set up Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) help documentation and [protect against malicious sites](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) short training video.</span></span>

- <span data-ttu-id="03c67-120">**網路釣魚嘗試從保護您的環境：** ATP 防網路釣魚機器學習模型搭配模擬偵測演算法的一組套用於防止其他人正在嘗試從您擷取資訊，藉由假冒已知的網路釣魚攻擊的內送郵件請連絡。</span><span class="sxs-lookup"><span data-stu-id="03c67-120">**Protect your enviroment from phishing attempt:**  ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection from phishing attacks where someone is trying to extract information from you by pretending to be a known contact.</span></span> <span data-ttu-id="03c67-121">若要啟用此，請參閱[設定 ATP 防網路釣魚](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)協助文件，並[防止網路釣魚嘗試](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)簡短的訓練影片。</span><span class="sxs-lookup"><span data-stu-id="03c67-121">To Activate this, see [set up ATP anti-phishing](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) help documentation and [protect against phishing attempts](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) short training video.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="03c67-122">設定 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="03c67-122">Set up DLP features</span></span>

<span data-ttu-id="03c67-123">如需有關如何設定的原則，以防止個人識別資訊 (PII) 的範例，請參閱[建立 DLP 原則範本中](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="03c67-123">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="03c67-124">DLP 隨附許多不同的地區設定的許多準備-使用原則範本。</span><span class="sxs-lookup"><span data-stu-id="03c67-124">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="03c67-125">例如，澳洲財務資料、 加拿大個人資訊法案、 美國財務資料，等等。如需完整清單，請參閱[什麼的 DLP 原則範本包含](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="03c67-125">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="03c67-126">所有這些範本可啟用類似 PII 範本範例。</span><span class="sxs-lookup"><span data-stu-id="03c67-126">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="03c67-127">設定搭配 Exchange Online Archiving 的電子郵件保留</span><span class="sxs-lookup"><span data-stu-id="03c67-127">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="03c67-128">**Exchange Online Archiving**授權功能可讓您維持合規性和法規的標準來保留電子郵件內容 eDiscovery 的目的。</span><span class="sxs-lookup"><span data-stu-id="03c67-128">**Exchange Online Archiving** license features give you the ability to help maintain compliance and regulatory standards by preserving email content for the purposes of eDiscovery.</span></span> <span data-ttu-id="03c67-129">它也可協助降低發生訴訟資料暫留時風險，並提供方法來復原資料安全性漏洞之後，或當您要復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="03c67-129">It also helps reduce your risk in the event of litigation and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="03c67-130">若要啟用這些功能，您可以使用訴訟暫止來保留的所有使用者的內容，或使用更大的自訂保留原則。</span><span class="sxs-lookup"><span data-stu-id="03c67-130">To activate these capabilities, you can use litigation hold to preserve all of a user's content, or use retention policies for greater customization.</span></span> 
  
<span data-ttu-id="03c67-131">**訴訟資料暫留：** 您可以保留所有信箱內容，包括已刪除的項目依據] 將使用者的整個信箱放置於訴訟保留。</span><span class="sxs-lookup"><span data-stu-id="03c67-131">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="03c67-132">若要將信箱置於訴訟暫止，在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="03c67-132">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="03c67-133">在左側導覽中，移至 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="03c67-133">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="03c67-134">選取您想要置於 [訴訟暫止的信箱保留的使用者在使用者窗格中展開 [**郵件設定**和**其他設定**旁邊選擇 [**編輯 Exchange 屬性**。</span><span class="sxs-lookup"><span data-stu-id="03c67-134">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="03c67-135">在使用者信箱] 頁面上，選擇 [\* \* 信箱功能 \* \* 在左側導覽中，然後選擇 [在 [**訴訟暫止**] 下的 [**啟用**] 連結。</span><span class="sxs-lookup"><span data-stu-id="03c67-135">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="03c67-136">在**訴訟暫止狀態**對話方塊您可以指定訴訟保留期間在**訴訟暫止持續時間**] 欄位中，將欄位保留空白，如果您想要放置無限期的保留。</span><span class="sxs-lookup"><span data-stu-id="03c67-136">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="03c67-137">您也可以新增備忘稿並導向至網站，您可能必須將說明更多有關訴訟保留的郵件] 方塊中擁有者\>**儲存**。</span><span class="sxs-lookup"><span data-stu-id="03c67-137">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="03c67-138">**保留：** 您可以啟用自訂的保留原則，例如，若要保留經過一段時間，或在保留期間結束永久刪除內容。</span><span class="sxs-lookup"><span data-stu-id="03c67-138">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="03c67-139">若要深入了解，請參閱[保留原則的概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="03c67-139">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="03c67-140">設定 Azure 資訊保護功能</span><span class="sxs-lookup"><span data-stu-id="03c67-140">Set up Azure Information Protection features</span></span>

<span data-ttu-id="03c67-141">Azure 資訊保護 (AIP) 是雲端為基礎的解決方案，可協助組織，以分類，並選擇性地套用標籤，以保護其文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="03c67-141">Azure Information Protection (AIP) is a cloud-based solution that helps an organization to classify and optionally, protect its documents and emails by applying labels.</span></span> <span data-ttu-id="03c67-142">可由系統管理員定義規則和條件，以手動方式由使用者或提供使用者建議的組合會自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="03c67-142">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="03c67-143">能夠在網頁型 Outlook 中傳送電子郵件時，適用下列限制會自動啟用所有使用者：</span><span class="sxs-lookup"><span data-stu-id="03c67-143">The ability to apply the following restrictions when sending emails in Outlook on the web is automatically enabled for all users:</span></span>
  
- <span data-ttu-id="03c67-144">**不要轉寄**： 收件者可以讀取郵件，但他們無法轉寄、 列印或複製內容</span><span class="sxs-lookup"><span data-stu-id="03c67-144">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="03c67-145">**加密**： 加密整封郵件。</span><span class="sxs-lookup"><span data-stu-id="03c67-145">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="03c67-146">收件者必須採取額外的步驟，以確認其身分識別存取加密的內容之前，且無法移除加密。</span><span class="sxs-lookup"><span data-stu-id="03c67-146">Recipients must take extra steps to confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="03c67-147">**2 私人 3 機密**： 授與您的組織中的員工完整權限的電子郵件內容和附件，但不適用於您組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="03c67-147">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="03c67-148">資料擁有者可以追蹤及撤銷的任何一點的內容。</span><span class="sxs-lookup"><span data-stu-id="03c67-148">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="03c67-149">**高度機密**： 此限制可套用至高度機密資料，讓員工能夠檢視、 編輯和回覆，但不是轉寄、 列印或複製資料。</span><span class="sxs-lookup"><span data-stu-id="03c67-149">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="03c67-150">資料擁有者可以追蹤及撤銷的任何一點的內容。</span><span class="sxs-lookup"><span data-stu-id="03c67-150">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="03c67-151">請確定已啟動 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="03c67-151">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="03c67-152">若要確認 AIP 會在啟動：</span><span class="sxs-lookup"><span data-stu-id="03c67-152">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="03c67-153">登入[Azure 入口網站](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="03c67-153">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="03c67-154">*Azure 資訊保護*在**搜尋] 方塊**中，選取 [**所有服務**和類型。</span><span class="sxs-lookup"><span data-stu-id="03c67-154">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="03c67-155">一旦顯示結果，請按一下 [下一步] **Azure 資訊保護**來使其成為我的最愛且更容易尋找稍後開始。</span><span class="sxs-lookup"><span data-stu-id="03c67-155">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="03c67-156">選取 [ **Azure 資訊保護** \> **保護啟用**，並確定狀態設為啟用。</span><span class="sxs-lookup"><span data-stu-id="03c67-156">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="03c67-157">檢視 Azure 資訊保護原則和預設標籤</span><span class="sxs-lookup"><span data-stu-id="03c67-157">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="03c67-158">標籤來檢視及修改，現有：</span><span class="sxs-lookup"><span data-stu-id="03c67-158">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="03c67-159">在 [Azure 資訊保護儀表板中，選取 [**分類** \> **標籤**。</span><span class="sxs-lookup"><span data-stu-id="03c67-159">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="03c67-160">![標準的 Azure 資訊保護標籤。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="03c67-160">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="03c67-161">您可以選擇任何標籤來檢視的選項，您可以變更的顯示名稱、 色彩等等。</span><span class="sxs-lookup"><span data-stu-id="03c67-161">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="03c67-162">請參閱[修改，並建立新的標籤](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)如果您想要建立您自己。</span><span class="sxs-lookup"><span data-stu-id="03c67-162">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="03c67-163">以手動方式安裝 Azure 資訊保護用戶端</span><span class="sxs-lookup"><span data-stu-id="03c67-163">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="03c67-164">若要手動安裝 AIP 用戶端：</span><span class="sxs-lookup"><span data-stu-id="03c67-164">To manually install the AIP client:</span></span>

1. <span data-ttu-id="03c67-165">從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載**AzInfoProtection.exe** 。</span><span class="sxs-lookup"><span data-stu-id="03c67-165">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="03c67-166">您可以確認安裝成功可以檢視 Word 文件，以確定可在 [**首頁**] 索引標籤上 [**保護**] 選項。</span><span class="sxs-lookup"><span data-stu-id="03c67-166">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="03c67-167">![保護索引標籤下拉式清單中的 Word 文件。](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="03c67-167">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="03c67-168">如需詳細資訊，請參閱[安裝用戶端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="03c67-168">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="03c67-169">移至 Intune 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="03c67-169">Go to Intune admin center</span></span>

1. <span data-ttu-id="03c67-170">登入[Azure 入口網站](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="03c67-170">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="03c67-171">*Intune*中的 [**搜尋] 方塊**中，選取 [**所有服務**和類型。</span><span class="sxs-lookup"><span data-stu-id="03c67-171">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="03c67-172">一旦顯示結果，請按一下 [下一步] 以使其最愛的**Microsoft Intune**且更容易尋找稍後開始。</span><span class="sxs-lookup"><span data-stu-id="03c67-172">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="03c67-173">除了系統管理中心中，您可以使用 Intune 來註冊並管理您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="03c67-173">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="03c67-174">如需詳細資訊，請參閱[功能由 Windows 裝置註冊方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和[由 Intune 管理的裝置註冊選項](https://docs.microsoft.com/intune/enrollment-options)。</span><span class="sxs-lookup"><span data-stu-id="03c67-174">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="03c67-175">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="03c67-175">Microsoft Secure Score</span></span>

