---
title: Office 365 開發/測試環境中的 GDPR 探索、保護和報告
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 展示 Office 365 中的 GDPR 功能。
ms.openlocfilehash: 98339aeec2c89edd4fead1482f98aa3d9f316856
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38749719"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a><span data-ttu-id="bf363-103">Office 365 開發/測試環境中的 GDPR 探索、保護和報告</span><span class="sxs-lookup"><span data-stu-id="bf363-103">GDPR discovery, protection, and reporting in the Office 365 dev/test environment</span></span>

 <span data-ttu-id="bf363-104">**摘要：** 展示 Office 365 中的 GDPR 功能。</span><span class="sxs-lookup"><span data-stu-id="bf363-104">**Summary:** Demonstrate GDPR capabilities in Office 365.</span></span> 
  
<span data-ttu-id="bf363-105">本文將說明如何在 Office 365 開發/測試環境中設定及展示一般資料保護規定 (GDPR) 的個人識別資訊 (PII) 探索、保護及報告。</span><span class="sxs-lookup"><span data-stu-id="bf363-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in an Office 365 dev/test environment.</span></span>
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a><span data-ttu-id="bf363-106">階段 1：建立及設定您的試用版 Office 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="bf363-106">Phase 1: Create and configure your trial Office 365 subscription</span></span>

<span data-ttu-id="bf363-107">首先，請遵循 [Office 365 開發/測試環境階段 2](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) 一文中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="bf363-107">First, follow the steps in [Phase 2 of the Office 365 dev/test environment](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="bf363-108">接下來，請使用下列步驟來設定電子文件探索管理員：</span><span class="sxs-lookup"><span data-stu-id="bf363-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="bf363-109">使用全域管理員帳戶登入 Office 365 試用版租用戶。</span><span class="sxs-lookup"><span data-stu-id="bf363-109">Sign in to your Office 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="bf363-110">從 Office 365 首頁上，按一下 [安全性與合規性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-110">From the Office 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="bf363-111">在新的 [安全性與合規性] 索引標籤中，按一下 [權限] \*\*\*\* >  [電子文件探索管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="bf363-112">按一下 [電子文件探索管理員] 的 [編輯]\*\*\*\*，然後按一下 [選擇電子文件探索管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="bf363-113">按一下 [+ 新增]\*\*\*\*、搜尋您的全域系統管理員帳戶名稱，然後以電子文件探索管理員身分新增您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="bf363-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="bf363-114">按一下 [完成] \*\*\*\* >  [儲存] \*\*\*\* >  [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-114">Click **Done** > **Save** > **Close**.</span></span>
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="bf363-115">階段 2：將個人識別資訊新增至租用戶</span><span class="sxs-lookup"><span data-stu-id="bf363-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="bf363-116">在這個階段中，您要使用 PII 建立一組範例國際銀行帳號 (IBAN) 的文件，並將其儲存在您 Office 365 開發/測試環境中的 SharePoint Online 網站上。</span><span class="sxs-lookup"><span data-stu-id="bf363-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Office 365 dev/test environment.</span></span>

1. <span data-ttu-id="bf363-117">在本機電腦上，開啟 Microsoft Word。</span><span class="sxs-lookup"><span data-stu-id="bf363-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="bf363-118">在 Word 檔案中將下表貼上，並在本機電腦上將它儲存為 'IBANs.docx'。</span><span class="sxs-lookup"><span data-stu-id="bf363-118">Paste the following table in the Word file and save it as ‘IBANs.docx’ on your local computer.</span></span>
    
    <span data-ttu-id="bf363-119">數字</span><span class="sxs-lookup"><span data-stu-id="bf363-119">Number</span></span>  |<span data-ttu-id="bf363-120">國家/地區</span><span class="sxs-lookup"><span data-stu-id="bf363-120">Country</span></span>  |<span data-ttu-id="bf363-121">代碼</span><span class="sxs-lookup"><span data-stu-id="bf363-121">Code</span></span> |<span data-ttu-id="bf363-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="bf363-122">IBAN</span></span>  |
    |---------|---------|---------|---------|
    |<span data-ttu-id="bf363-123">1</span><span class="sxs-lookup"><span data-stu-id="bf363-123">1</span></span>     |  <span data-ttu-id="bf363-124">奧地利 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-124">Austria SEPA</span></span>      | <span data-ttu-id="bf363-125">AT</span><span class="sxs-lookup"><span data-stu-id="bf363-125">AT</span></span>            |<span data-ttu-id="bf363-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="bf363-126">AT611904300234573201</span></span>       |
    |<span data-ttu-id="bf363-127">2</span><span class="sxs-lookup"><span data-stu-id="bf363-127">2</span></span>     |  <span data-ttu-id="bf363-128">保加利亞 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-128">Bulgaria SEPA</span></span>       |<span data-ttu-id="bf363-129">BG</span><span class="sxs-lookup"><span data-stu-id="bf363-129">BG</span></span>    |<span data-ttu-id="bf363-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="bf363-130">BG80BNBG96611020345678</span></span>      |
    |<span data-ttu-id="bf363-131">3</span><span class="sxs-lookup"><span data-stu-id="bf363-131">3</span></span>     |  <span data-ttu-id="bf363-132">丹麥 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-132">Denmark SEPA</span></span>      |   <span data-ttu-id="bf363-133">DK</span><span class="sxs-lookup"><span data-stu-id="bf363-133">DK</span></span>      |<span data-ttu-id="bf363-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="bf363-134">DK5000400440116243</span></span>      |
    |<span data-ttu-id="bf363-135">4</span><span class="sxs-lookup"><span data-stu-id="bf363-135">4</span></span>     |  <span data-ttu-id="bf363-136">芬蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-136">Finland SEPA</span></span>      |   <span data-ttu-id="bf363-137">FI</span><span class="sxs-lookup"><span data-stu-id="bf363-137">FI</span></span>      |<span data-ttu-id="bf363-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="bf363-138">FI2112345600000785</span></span>         |
    |<span data-ttu-id="bf363-139">5</span><span class="sxs-lookup"><span data-stu-id="bf363-139">5</span></span>     |  <span data-ttu-id="bf363-140">法國 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-140">France SEPA</span></span>       |   <span data-ttu-id="bf363-141">FR</span><span class="sxs-lookup"><span data-stu-id="bf363-141">FR</span></span>      |<span data-ttu-id="bf363-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="bf363-142">FR1420041010050500013M02606</span></span>         |
    |<span data-ttu-id="bf363-143">6</span><span class="sxs-lookup"><span data-stu-id="bf363-143">6</span></span>     |  <span data-ttu-id="bf363-144">德國 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-144">Germany SEPA</span></span>      |   <span data-ttu-id="bf363-145">DE</span><span class="sxs-lookup"><span data-stu-id="bf363-145">DE</span></span>      |<span data-ttu-id="bf363-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="bf363-146">DE89370400440532013000</span></span>         |
    |<span data-ttu-id="bf363-147">7</span><span class="sxs-lookup"><span data-stu-id="bf363-147">7</span></span>     |  <span data-ttu-id="bf363-148">希臘 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-148">Greece SEPA</span></span>       |   <span data-ttu-id="bf363-149">GR</span><span class="sxs-lookup"><span data-stu-id="bf363-149">GR</span></span>      |<span data-ttu-id="bf363-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="bf363-150">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="bf363-151">8</span><span class="sxs-lookup"><span data-stu-id="bf363-151">8</span></span>     |  <span data-ttu-id="bf363-152">義大利 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-152">Italy SEPA</span></span>       |    <span data-ttu-id="bf363-153">IT</span><span class="sxs-lookup"><span data-stu-id="bf363-153">IT</span></span>     |<span data-ttu-id="bf363-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="bf363-154">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="bf363-155">9</span><span class="sxs-lookup"><span data-stu-id="bf363-155">9</span></span>     |  <span data-ttu-id="bf363-156">荷蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-156">Netherlands SEPA</span></span>      |   <span data-ttu-id="bf363-157">NL</span><span class="sxs-lookup"><span data-stu-id="bf363-157">NL</span></span>      |    <span data-ttu-id="bf363-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="bf363-158">NL91ABNA0417164300</span></span>     |
    |<span data-ttu-id="bf363-159">10</span><span class="sxs-lookup"><span data-stu-id="bf363-159">10</span></span>     | <span data-ttu-id="bf363-160">波蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-160">Poland SEPA</span></span>       |  <span data-ttu-id="bf363-161">PL</span><span class="sxs-lookup"><span data-stu-id="bf363-161">PL</span></span>       | <span data-ttu-id="bf363-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="bf363-162">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="bf363-163">附註：此範例資料集衍生自公開提供的資訊，而且旨在用於測試目的而已。</span><span class="sxs-lookup"><span data-stu-id="bf363-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="bf363-164">在瀏覽器的新索引標籤中，輸入：**https://**\<YourTenantName\>**.sharepoint.com**</span><span class="sxs-lookup"><span data-stu-id="bf363-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="bf363-p101">按一下 [文件]\*\*\*\* 以開啟此網站的文件庫。如果系統提示您進行新的清單體驗導覽，請按 [下一步]\*\*\*\*，直到完成為止。</span><span class="sxs-lookup"><span data-stu-id="bf363-p101">Click **Documents** to open the document library for this site. If you’re prompted for a new list experience tour, click **Next** until it’s finished.</span></span>
5.  <span data-ttu-id="bf363-167">按一下 [上傳] \*\*\*\* >  [檔案]\*\*\*\*，然後選取您在步驟 2 中建立的 IBANs.docx。</span><span class="sxs-lookup"><span data-stu-id="bf363-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

  
## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="bf363-168">階段 3：展示資料探索</span><span class="sxs-lookup"><span data-stu-id="bf363-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="bf363-169">在這個階段中，您展示的搜尋會根據包含 IBAN 的內容，尋找在階段 2 中所建立及儲存的文件。</span><span class="sxs-lookup"><span data-stu-id="bf363-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="bf363-170">在 [安全性與合規性] 索引標籤中，按一下 [首頁]\*\*\*\*，然後按一下 [搜尋與調查] \*\*\*\* >  [內容搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="bf363-171">按一下 [+]\*\*\*\* 來建立新的搜尋項目。</span><span class="sxs-lookup"><span data-stu-id="bf363-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="bf363-172">請在新的視窗中提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bf363-172">In a new window, provide the following information:</span></span>  
    <span data-ttu-id="bf363-p102">a. 名稱：IBAN 搜尋</span><span class="sxs-lookup"><span data-stu-id="bf363-p102">a. Name: IBAN Search</span></span>  
    <span data-ttu-id="bf363-p103">b. 您需要我們查看哪裡？：**選擇要搜尋的特定網站**(按一下 [+]\*\*\*\*)，然後輸入網站的 URL：**https://**\<您的租用戶名稱\>**.sharepoint.com/**</span><span class="sxs-lookup"><span data-stu-id="bf363-p103">b. Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/**</span></span>  
    <span data-ttu-id="bf363-p104">c. 按一下 [新增]\*\*\*\*，然後按一下 [確定]\*\*\*\*。如果您看到警告，請按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-p104">c. Click **Add**, and then click **OK**. If you see a Warning, click **OK**.</span></span>  
    <span data-ttu-id="bf363-p105">d. 在 [新的搜尋]\*\*\*\* 視窗上按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-p105">d. Click **Next** on a **New search** window.</span></span>  
    <span data-ttu-id="bf363-p106">e. 針對**您需要我們尋找什麼？**：**SensitiveType：「國際銀行帳號 (IBAN)」**，然後按一下 [搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-p106">e. For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="bf363-184">請確定您看到至少一個項目列在 **IBAN 搜尋**結果中。</span><span class="sxs-lookup"><span data-stu-id="bf363-184">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="bf363-185">階段 4：透過 PowerShell 建立自訂的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bf363-185">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="bf363-p107">在這個階段中，您要使用 Microsoft PowerShell 來建立虛構 Contoso 公司的自訂敏感資訊類型。Contoso 會使用 Contoso 客戶編號 (CCN) 來識別其客戶資料庫中的每位客戶。CCN 包含下列結構：</span><span class="sxs-lookup"><span data-stu-id="bf363-p107">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>
- <span data-ttu-id="bf363-189">兩位數表示記錄所建立的年份。</span><span class="sxs-lookup"><span data-stu-id="bf363-189">Two digits to represent the year that the record was created.</span></span>
    - <span data-ttu-id="bf363-190">Contoso 成立於 2002 年；因此，可能的最早值是 02。</span><span class="sxs-lookup"><span data-stu-id="bf363-190">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span> 
- <span data-ttu-id="bf363-191">三位數代表建立記錄的夥伴機構。</span><span class="sxs-lookup"><span data-stu-id="bf363-191">Three digits to represent the partner agency that created the record.</span></span>
    - <span data-ttu-id="bf363-192">可能的機構值範圍介於 000 到 999。</span><span class="sxs-lookup"><span data-stu-id="bf363-192">Possible agency values range from 000 to 999.</span></span> 
- <span data-ttu-id="bf363-193">以字母字元來代表企業營運。</span><span class="sxs-lookup"><span data-stu-id="bf363-193">An alphabetic character to represent the line of business.</span></span>
    - <span data-ttu-id="bf363-194">可能的值是 a 到 z，且應該不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="bf363-194">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="bf363-195">一個四位數序號。</span><span class="sxs-lookup"><span data-stu-id="bf363-195">A four-digit serial number.</span></span> 
    - <span data-ttu-id="bf363-196">可能的序號值範圍從 0000 到 9999。</span><span class="sxs-lookup"><span data-stu-id="bf363-196">Possible serial number values range from 0000 to 9999.</span></span>   

<span data-ttu-id="bf363-p108">Contoso 一律會以內部通信、外部通信、文件和其他形式使用 CCN 來參照客戶。Contoso 需要自訂的敏感項目類型來偵測 Office 365 內容中的 CCN 使用情形，以便他們可在使用此形式的個人識別資訊時提供保護。</span><span class="sxs-lookup"><span data-stu-id="bf363-p108">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Office 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="bf363-199">使用[使用多重要素驗證連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) 中的指示，並使用您全域系統管理員帳戶的 UPN 連線至安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="bf363-199">Use the instructions in [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>
2. <span data-ttu-id="bf363-200">執行下列 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="bf363-200">Run the following PowerShell commands.</span></span>

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. <span data-ttu-id="bf363-201">請執行下列 PowerShell 命令，並以產生的 GUID 所列出的順序，將 GUID 複製到電腦上 [記事本] 的開啟執行個體。</span><span class="sxs-lookup"><span data-stu-id="bf363-201">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. <span data-ttu-id="bf363-202">在您的本機電腦上，開啟另一個 [記事本] 的執行個體，並將下列內容貼入：</span><span class="sxs-lookup"><span data-stu-id="bf363-202">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. <span data-ttu-id="bf363-203">將步驟 4 的 XML 文字中 GUID1、GUID2 和 GUID3 的值取代為其在步驟 3 中的值，然後使用 ContosoCCN.xml 的名稱，將內容儲存在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="bf363-203">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>
6. <span data-ttu-id="bf363-204">填入您 ContosoCCN.xml 檔案的路徑，然後執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="bf363-204">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. <span data-ttu-id="bf363-p109">在 [安全性與合規性] 索引標籤中，按一下 [分類] \*\*\*\* >  [敏感資訊類型]\*\*\*\*。您應該會在清單中看到 Contoso 客戶編號 (CCN)。</span><span class="sxs-lookup"><span data-stu-id="bf363-p109">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="bf363-207">階段 5：展示資料保護</span><span class="sxs-lookup"><span data-stu-id="bf363-207">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="bf363-208">Office 365 中個人資訊的保護，包括使用資料外洩防護 (DLP) 功能。</span><span class="sxs-lookup"><span data-stu-id="bf363-208">Protection of personal information in Office 365 includes using data loss prevention (DLP) capabilities.</span></span>  <span data-ttu-id="bf363-209">您可以使用 DLP 原則自動保護整個 Office 365 的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="bf363-209">With DLP policies, you can automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="bf363-p111">您可以多種方式來提供保護。教育並提高以下認知：歐盟居民資料應儲存在您環境的何處以及您的員工被允許處理這些資料的方式，上述方式即代表一種使用 Office 365 DLP 的資訊保護層級。</span><span class="sxs-lookup"><span data-stu-id="bf363-p111">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="bf363-212">在這個階段中，您會建立新的 DLP 原則，並展示如何將其套用至您在階段 2 的 SharePoint Online 中儲存的 IBANs.docx 檔案，以及您何時要嘗試傳送包含 IBAN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bf363-212">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="bf363-213">從瀏覽器的 [安全性與合規性] 索引標籤中，按一下 [首頁]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-213">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="bf363-214">按一下 [資料遺失防護] \*\*\*\* >  [原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-214">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="bf363-215">按一下 [+ 建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-215">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="bf363-216">在 [從範本開始] 或 [建立自訂原則]\*\*\*\* 中，按一下 [自訂] \*\*\*\* >  [自訂原則] \*\*\*\* >  [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-216">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="bf363-p112">在 [命名原則]\*\*\*\* 中，提供下列詳細資料，然後按 [下一步]\*\*\*\*：a. 名稱：**歐盟市民 PII 原則** b. 描述：**保護歐洲市民的個人識別資訊**</span><span class="sxs-lookup"><span data-stu-id="bf363-p112">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="bf363-p113">在 [選擇位置]\*\*\*\* 中，選取 [Office 365 中的所有位置]\*\*\*\*。這將包含 Exchange 電子郵件中的內容和 OneDrive 與 SharePoint 文件。然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-p113">In **Choose locations**, select **All locations in Office 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="bf363-223">在 [自訂您要保護的內容類型]\*\*\*\* 中，按一下 [尋找內容中包含：]\*\*\*\*，然後按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-223">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="bf363-224">在 [選擇要保護的內容類型]\*\*\*\* 中，按一下 [新增] \*\*\*\* >  [敏感資訊類型]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-224">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="bf363-225">在 [敏感資訊類型]\*\*\*\* 中，按一下 [+ 新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-225">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="bf363-226">在 [敏感資訊類型]\*\*\*\* 中，搜尋 **IBAN**、選取 [國際銀行帳號 (IBAN)]\*\*\*\* 的核取方塊，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-226">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="bf363-227">請確認已新增 [國際銀行帳號 (IBAN)]\*\*\*\* 敏感資訊類型，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-227">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="bf363-228">在 [內容包含]\*\*\*\* 中，確認已新增敏感資訊類型，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-228">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="bf363-229">在 [自訂您要保護的內容類型]\*\*\*\* 中，確認 [尋找內容中包含：]\*\*\*\* 包含 [國際銀行帳號 (IBAN)]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-229">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="bf363-230">在 [當共用的內容中包含以下項目時進行偵測：]\*\*\*\*，將值從 **10** 變更為 **1**，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-230">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="bf363-231">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 中，選擇下列設定，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-231">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>  
    <span data-ttu-id="bf363-p114">a. 選取 [我想要先進行測試]\*\*\*\* 的選項</span><span class="sxs-lookup"><span data-stu-id="bf363-p114">a. Select the option for **I'd like to test it out first**</span></span>  
    <span data-ttu-id="bf363-p115">b. 選取 [在測試模式中顯示原則提示]\*\*\*\* 的核取方塊</span><span class="sxs-lookup"><span data-stu-id="bf363-p115">b. Select the check box for **Show policy tips while in test mode**</span></span> 
16. <span data-ttu-id="bf363-p116">檢視設定之後，在 [檢視您的設定]\*\*\*\* 中，按一下 [建立]\*\*\*\*。附註：建立新的 DLP 原則之後，需要一段時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="bf363-p116">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="bf363-238">在本機電腦上，開啟瀏覽器的私人執行個體。</span><span class="sxs-lookup"><span data-stu-id="bf363-238">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="bf363-239">在網址列中，輸入 **https://**\<您的租用戶名稱\>**.sharepoint.com**，並使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="bf363-239">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="bf363-240">按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-240">Click **Documents**.</span></span>
20. <span data-ttu-id="bf363-p117">按一下名為 'IBANs.docx' 的檔案。您應該會看到「IBANs.docx 的原則提示」。IBANs.docx 檔案曾與外部收件者共用，因此會違反 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="bf363-p117">Click the file named ‘IBANs.docx’. You should see ‘Policy tip for IBANs.docx’.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span> 
21. <span data-ttu-id="bf363-244">在網址列中，輸入：`https://outlook.office365.com`</span><span class="sxs-lookup"><span data-stu-id="bf363-244">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="bf363-245">按一下 [新增] \*\*\*\* -  [電子郵件訊息]\*\*\*\*，並提供下列內容：</span><span class="sxs-lookup"><span data-stu-id="bf363-245">Click **New** - **Email message** and provide the following:</span></span>  
    - <span data-ttu-id="bf363-246">**收件者：**\<個人電子郵件地址\></span><span class="sxs-lookup"><span data-stu-id="bf363-246">**To:** \<a personal email address\></span></span>  
    - <span data-ttu-id="bf363-247">**主旨：** GDPR 測試</span><span class="sxs-lookup"><span data-stu-id="bf363-247">**Subject:** GDPR Test</span></span>  
    - <span data-ttu-id="bf363-248">**本文：** 複製值表格，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bf363-248">**Body:** Copy in the table of values shown below.</span></span>
  
        |<span data-ttu-id="bf363-249">數字</span><span class="sxs-lookup"><span data-stu-id="bf363-249">Number</span></span>  |<span data-ttu-id="bf363-250">國家/地區</span><span class="sxs-lookup"><span data-stu-id="bf363-250">Country</span></span>  |<span data-ttu-id="bf363-251">代碼</span><span class="sxs-lookup"><span data-stu-id="bf363-251">Code</span></span> |<span data-ttu-id="bf363-252">IBAN</span><span class="sxs-lookup"><span data-stu-id="bf363-252">IBAN</span></span>  |
        |---------|---------|---------|---------|
        |<span data-ttu-id="bf363-253">1</span><span class="sxs-lookup"><span data-stu-id="bf363-253">1</span></span>     |  <span data-ttu-id="bf363-254">奧地利 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-254">Austria SEPA</span></span>      | <span data-ttu-id="bf363-255">AT</span><span class="sxs-lookup"><span data-stu-id="bf363-255">AT</span></span>            |<span data-ttu-id="bf363-256">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="bf363-256">AT611904300234573201</span></span>       |
        |<span data-ttu-id="bf363-257">2</span><span class="sxs-lookup"><span data-stu-id="bf363-257">2</span></span>     |  <span data-ttu-id="bf363-258">保加利亞 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-258">Bulgaria SEPA</span></span>       |<span data-ttu-id="bf363-259">BG</span><span class="sxs-lookup"><span data-stu-id="bf363-259">BG</span></span>    |<span data-ttu-id="bf363-260">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="bf363-260">BG80BNBG96611020345678</span></span>      |
        |<span data-ttu-id="bf363-261">3</span><span class="sxs-lookup"><span data-stu-id="bf363-261">3</span></span>     |  <span data-ttu-id="bf363-262">丹麥 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-262">Denmark SEPA</span></span>      |   <span data-ttu-id="bf363-263">DK</span><span class="sxs-lookup"><span data-stu-id="bf363-263">DK</span></span>      |<span data-ttu-id="bf363-264">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="bf363-264">DK5000400440116243</span></span>      |
        |<span data-ttu-id="bf363-265">4</span><span class="sxs-lookup"><span data-stu-id="bf363-265">4</span></span>     |  <span data-ttu-id="bf363-266">芬蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-266">Finland SEPA</span></span>      |   <span data-ttu-id="bf363-267">FI</span><span class="sxs-lookup"><span data-stu-id="bf363-267">FI</span></span>      |<span data-ttu-id="bf363-268">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="bf363-268">FI2112345600000785</span></span>         |
        |<span data-ttu-id="bf363-269">5</span><span class="sxs-lookup"><span data-stu-id="bf363-269">5</span></span>     |  <span data-ttu-id="bf363-270">法國 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-270">France SEPA</span></span>       |   <span data-ttu-id="bf363-271">FR</span><span class="sxs-lookup"><span data-stu-id="bf363-271">FR</span></span>      |<span data-ttu-id="bf363-272">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="bf363-272">FR1420041010050500013M02606</span></span>         |
        |<span data-ttu-id="bf363-273">6</span><span class="sxs-lookup"><span data-stu-id="bf363-273">6</span></span>     |  <span data-ttu-id="bf363-274">德國 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-274">Germany SEPA</span></span>      |   <span data-ttu-id="bf363-275">DE</span><span class="sxs-lookup"><span data-stu-id="bf363-275">DE</span></span>      |<span data-ttu-id="bf363-276">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="bf363-276">DE89370400440532013000</span></span>         |
        |<span data-ttu-id="bf363-277">7</span><span class="sxs-lookup"><span data-stu-id="bf363-277">7</span></span>     |  <span data-ttu-id="bf363-278">希臘 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-278">Greece SEPA</span></span>       |   <span data-ttu-id="bf363-279">GR</span><span class="sxs-lookup"><span data-stu-id="bf363-279">GR</span></span>      |<span data-ttu-id="bf363-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="bf363-280">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="bf363-281">8</span><span class="sxs-lookup"><span data-stu-id="bf363-281">8</span></span>     |  <span data-ttu-id="bf363-282">義大利 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-282">Italy SEPA</span></span>       |    <span data-ttu-id="bf363-283">IT</span><span class="sxs-lookup"><span data-stu-id="bf363-283">IT</span></span>     |<span data-ttu-id="bf363-284">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="bf363-284">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="bf363-285">9</span><span class="sxs-lookup"><span data-stu-id="bf363-285">9</span></span>     |  <span data-ttu-id="bf363-286">荷蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-286">Netherlands SEPA</span></span>      |   <span data-ttu-id="bf363-287">NL</span><span class="sxs-lookup"><span data-stu-id="bf363-287">NL</span></span>      |   <span data-ttu-id="bf363-288">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="bf363-288">NL91ABNA0417164300</span></span>      |
        |<span data-ttu-id="bf363-289">10</span><span class="sxs-lookup"><span data-stu-id="bf363-289">10</span></span>     | <span data-ttu-id="bf363-290">波蘭 SEPA</span><span class="sxs-lookup"><span data-stu-id="bf363-290">Poland SEPA</span></span>       |  <span data-ttu-id="bf363-291">PL</span><span class="sxs-lookup"><span data-stu-id="bf363-291">PL</span></span>       | <span data-ttu-id="bf363-292">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="bf363-292">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="bf363-293">附註：此範例資料集衍生自公開提供的資訊，而且旨在用於測試目的而已。</span><span class="sxs-lookup"><span data-stu-id="bf363-293">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="bf363-294">您會看到 DLP 原則已辨識出電子郵件內文包含 IBAN ，並會在郵件視窗頂端提供原則提示。</span><span class="sxs-lookup"><span data-stu-id="bf363-294">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="bf363-295">關閉瀏覽器的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="bf363-295">Close the private instance of your browser.</span></span>


## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="bf363-296">階段 6：展示報告</span><span class="sxs-lookup"><span data-stu-id="bf363-296">Phase 6: Demonstrate reporting</span></span>
 
<span data-ttu-id="bf363-297">在這個階段中，您要根據階段 5 中所設定的 DLP 原則來展示 Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="bf363-297">In this phase, you demonstrate Office 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="bf363-298">從瀏覽器的 [安全性與合規性] 索引標籤中，按一下 [首頁]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-298">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="bf363-299">按一下 [報告] \*\*\*\* >  [儀表板] \*\*\*\* >  [DLP 原則相符項目]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf363-299">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="bf363-p118">DLP 原則可協助您識別及保護組織的敏感資訊。例如，您會在報告中看到原則已識別包含在 SharePoint Online 中儲存之 IBAN 的文件。</span><span class="sxs-lookup"><span data-stu-id="bf363-p118">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf363-302">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bf363-302">See Also</span></span>

[<span data-ttu-id="bf363-303">GDPR 的 Office 365 資訊保護</span><span class="sxs-lookup"><span data-stu-id="bf363-303">Office 365 Information Protection for GDPR</span></span>](office-365-information-protection-for-gdpr.md)

[<span data-ttu-id="bf363-304">GDPR for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf363-304">GDPR for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
