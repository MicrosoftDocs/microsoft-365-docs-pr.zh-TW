---
title: 設定試用實驗室或試驗環境的 Microsoft 365 Defender 支柱
description: 針對您的試用實驗室或試驗環境，設定 Microsoft 365 Defender 支柱，例如 Microsoft Defender for Office 365、Microsoft Defender 身分識別、Microsoft Cloud App Security 及 Microsoft Defender for Endpoint。
keywords: 設定 Microsoft 威脅防護試用版、Microsoft 威脅防護試用版設定、設定 Microsoft 威脅防護試驗專案、設定 microsoft 威脅防護支柱、Microsoft 威脅防護支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6b6ff23ef888c167385ad127d3eb0addb66aebc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929183"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="9b674-104">為您的試用實驗室或試驗環境設定 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="9b674-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b674-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="9b674-105">**Applies to:**</span></span>
- <span data-ttu-id="9b674-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b674-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="9b674-107">建立 Microsoft 365 Defender 試驗實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="9b674-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="9b674-108">[![階段1：準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9b674-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="9b674-109">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="9b674-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="9b674-110">[![階段2：設定](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9b674-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="9b674-111">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="9b674-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![階段3：板載](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="9b674-113">階段3：板載</span><span class="sxs-lookup"><span data-stu-id="9b674-113">Phase 3: Onboard</span></span> | <span data-ttu-id="9b674-114">[![回到試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="9b674-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="9b674-115">回到試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="9b674-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="9b674-116">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="9b674-116">*You are here!*</span></span> | |

<span data-ttu-id="9b674-117">您目前正在設定階段。</span><span class="sxs-lookup"><span data-stu-id="9b674-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="9b674-118">準備工作是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="9b674-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="9b674-119">在本文中，您將指導您準備部署 Microsoft Defender 做為端點時所需考慮的點數。</span><span class="sxs-lookup"><span data-stu-id="9b674-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="9b674-120">Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="9b674-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="9b674-121">Microsoft 365 Defender 包含四個支柱。</span><span class="sxs-lookup"><span data-stu-id="9b674-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="9b674-122">雖然一個 pillar 可以為您的網路組織的安全性提供價值，但是啟用四個 Microsoft 365 Defender 支柱會為組織提供最大的價值。</span><span class="sxs-lookup"><span data-stu-id="9b674-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![影像 of_Microsoft 365 Defender 解決方案，適用于使用者、Microsoft Defender 身分識別、端點 Microsoft Defender for Endpoint、雲端應用程式、Microsoft Cloud App Security 及 data、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="9b674-124">本節會引導您設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="9b674-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="9b674-125">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b674-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="9b674-126">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b674-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="9b674-127">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="9b674-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="9b674-128">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b674-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="9b674-129">設定 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9b674-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="9b674-130">如果您已啟用 Office 365 的 Defender，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="9b674-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="9b674-131">有一個稱為「 *Office 365 高級威脅防護* 」的 PowerShell 模組 (ORCA) 可協助判斷部分設定。</span><span class="sxs-lookup"><span data-stu-id="9b674-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="9b674-132">當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。</span><span class="sxs-lookup"><span data-stu-id="9b674-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="9b674-133">您可以從下載此模組 https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="9b674-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="9b674-134">流覽至 [Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **原則**。</span><span class="sxs-lookup"><span data-stu-id="9b674-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & 合規性中心威脅管理原則頁面](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="9b674-136">按一下 [ **反網路釣魚**]，選取 [ **建立** 並填入原則名稱和描述]。</span><span class="sxs-lookup"><span data-stu-id="9b674-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="9b674-137">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中命名原則](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="9b674-139">在 Microsoft Defender for Office 365 中編輯您的高級防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="9b674-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9b674-140">將 **高級網路釣魚閥值** 變更為 **2-嚴格**。</span><span class="sxs-lookup"><span data-stu-id="9b674-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="9b674-141">按一下 [ **新增條件** ] 下拉式功能表，然後選取您的網域 (s) 做為收件者網域。</span><span class="sxs-lookup"><span data-stu-id="9b674-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="9b674-142">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中新增其應用程式的條件](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="9b674-144">請複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="9b674-144">Review your settings.</span></span> <span data-ttu-id="9b674-145">按一下 [ **建立這個原則** ] 以確認。</span><span class="sxs-lookup"><span data-stu-id="9b674-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & 相容性中心反網路釣魚原則頁面，您可以在其中檢查您的設定，然後按一下 [建立這個原則] 按鈕](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="9b674-147">選取 [ **安全附件** ]，然後選取 [ **開啟 SharePoint]、[OneDrive] 和 [Microsoft 小組** ] 選項的 ATP。</span><span class="sxs-lookup"><span data-stu-id="9b674-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在其中開啟 SharePoint、OneDrive 及 Microsoft 小組的 ATP](../../media/mtp-eval-36.png)

6. <span data-ttu-id="9b674-149">按一下 [+] 圖示，以建立新的安全附件原則，並將其套用為網域的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="9b674-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="9b674-150">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-150">Click **Save**.</span></span>

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上建立新的安全附件原則](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="9b674-152">接下來，選取 [ **安全連結** 原則]，然後按一下鉛筆圖示以編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="9b674-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="9b674-153">請確定未選取 [ **不要在使用者按一下安全連結時進行追蹤** ] 選項，而會選取其餘的選項。</span><span class="sxs-lookup"><span data-stu-id="9b674-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="9b674-154">如需詳細資訊，請參閱 [安全連結設定](../office-365-security/recommended-settings-for-eop-and-office365-atp.md) 。</span><span class="sxs-lookup"><span data-stu-id="9b674-154">See [Safe Links settings](../office-365-security/recommended-settings-for-eop-and-office365-atp.md) for details.</span></span> <span data-ttu-id="9b674-155">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-155">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & 相容性中心] 頁面，顯示未選取 [使用者按一下安全時不會追蹤] 選項](../../media/mtp-eval-38.png)

9. <span data-ttu-id="9b674-157">接下來選取 **反惡意** 代碼原則，選取預設值，然後選擇 [鉛筆] 圖示。</span><span class="sxs-lookup"><span data-stu-id="9b674-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="9b674-158">按一下 [ **設定** ]，然後選取 **[是] 並使用預設通知文字** ，以啟用 **惡意程式碼偵測回應**。</span><span class="sxs-lookup"><span data-stu-id="9b674-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="9b674-159">開啟 **通用附件類型 Filter** 。</span><span class="sxs-lookup"><span data-stu-id="9b674-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="9b674-160">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-160">Click **Save**.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，顯示惡意程式碼偵測回應開啟時會啟用預設通知，而一般附件類型篩選已開啟](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="9b674-162">流覽至 [Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **搜尋**  >  **審核記錄檔搜尋**，然後開啟審計。</span><span class="sxs-lookup"><span data-stu-id="9b674-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此開啟審核記錄搜尋](../../media/mtp-eval-40.png)

12. <span data-ttu-id="9b674-164">整合 Microsoft Defender for Office 365 搭配 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="9b674-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9b674-165">流覽至 [Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **瀏覽器**，然後選取螢幕右上角的 [ **Microsoft Defender for Endpoint] 設定**。</span><span class="sxs-lookup"><span data-stu-id="9b674-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="9b674-166">在 [Defender for Endpoint connection] 對話方塊中，開啟 **[連線至 Microsoft Defender For endpoint**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上開啟 Microsoft Defender for Endpoint connection。](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="9b674-168">設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="9b674-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="9b674-169">如果您已啟用 Microsoft Defender 身分識別，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="9b674-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="9b674-170">流覽至 [microsoft 365 Security Center](https://security.microsoft.com/info) > 選取 [microsoft Defender 身分識別] 的 [**更多資源**]  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b674-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365 Security Center 頁面，其中有一個可為身分識別開啟 Microsoft Defender 的選項](../../media/mtp-eval-42.png)

2. <span data-ttu-id="9b674-172">按一下 [ **建立** ]，以啟動 Microsoft Defender 身分識別嚮導。</span><span class="sxs-lookup"><span data-stu-id="9b674-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Image of_Microsoft 身分識別嚮導的 Defender] 頁面，您應該按一下 [建立] 按鈕](../../media/mtp-eval-43.png)

3. <span data-ttu-id="9b674-174">選擇 [ **提供使用者名稱和密碼] 以連線至您的 Active Directory 樹** 系。</span><span class="sxs-lookup"><span data-stu-id="9b674-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![鏡像 of_Microsoft 身分識別的 Defender 頁面](../../media/mtp-eval-44.png)

4. <span data-ttu-id="9b674-176">輸入您的 Active Directory 內部部署認證。</span><span class="sxs-lookup"><span data-stu-id="9b674-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="9b674-177">這可以是具有 Active Directory 讀取權限的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="9b674-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft 用於身分識別目錄服務的 Defender 目錄服務] 頁面，您應該在這裡放置您的認證](../../media/mtp-eval-45.png)

5. <span data-ttu-id="9b674-179">接下來，選擇 [將 **感應器安裝** 和傳輸檔案下載到您的網域控制站]。</span><span class="sxs-lookup"><span data-stu-id="9b674-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![影像 of_Microsoft 身分識別] 頁面，您可以在其中選取 [下載感應器設定]](../../media/mtp-eval-46.png)

6. <span data-ttu-id="9b674-181">針對身分識別感應器安裝執行 Microsoft Defender，並開始遵循此嚮導。</span><span class="sxs-lookup"><span data-stu-id="9b674-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Image of_Microsoft 用於身分識別的 Defender] 頁面，您應該按 [下一步] 遵循 Microsoft Defender for Identity 感應器嚮導](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="9b674-183">在感應器部署類型中按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="9b674-183">Click **Next** at the sensor deployment type.</span></span>

   ![影像 of_Microsoft 身分識別] 頁面，您應該在此按 [下一步] 移至下一頁面](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="9b674-185">複製存取機碼，因為您需要在嚮導的下一步輸入它。</span><span class="sxs-lookup"><span data-stu-id="9b674-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![影像 of_the 感應器頁面，您應該在下一個 Microsoft Defender for Identity 感應器安裝精靈] 頁面中複製您需要輸入的訪問機碼。](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="9b674-187">將存取機碼複製到嚮導，然後按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Microsoft 用於身分識別感應器的 Defender 嚮導] 頁面，您應該在此頁面上提供存取機碼，然後按一下 [安裝] 按鈕](../../media/mtp-eval-50.png)

10. <span data-ttu-id="9b674-189">恭喜，您已在您的網域控制站上成功設定 Microsoft Defender 身分識別。</span><span class="sxs-lookup"><span data-stu-id="9b674-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft 用於身分識別感應器的 Defender 安裝程式安裝完成，您應該按一下 [完成] 按鈕](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="9b674-191">在 [ [Microsoft defender 身分識別](https://go.microsoft.com/fwlink/?linkid=2040449) 設定] 區段中，選取 [\* \* microsoft Defender for Endpoint \* \*]，然後開啟切換。</span><span class="sxs-lookup"><span data-stu-id="9b674-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="9b674-192">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-192">Click **Save**.</span></span> 

    ![Image of_the Microsoft Defender 身分識別設定] 頁面，您應該在此頁面上開啟 Microsoft Defender 的端點切換功能](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="9b674-194">Windows Defender ATP 已 rebranded 為 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="9b674-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9b674-195">所有的入口網站上的 ..org 變更都會針對一致性加以匯總。</span><span class="sxs-lookup"><span data-stu-id="9b674-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="9b674-196">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9b674-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="9b674-197">如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="9b674-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="9b674-198">流覽至 [microsoft](https://security.microsoft.com/info)  >    >  **Cloud App security** 的 microsoft 365 Security Center More Resources。</span><span class="sxs-lookup"><span data-stu-id="9b674-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 Security Center 頁面，您可以在其中看到 Microsoft Cloud App 卡片，應該按一下 [開啟] 按鈕](../../media/mtp-eval-53.png)

2. <span data-ttu-id="9b674-200">在資訊提示中，針對身分識別整合 Microsoft Defender，請選取 [ **啟用 Microsoft defender 以進行識別資料整合**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the 資訊提示，針對識別整合 Microsoft Defender 以供您選取 [啟用 Microsoft Defender 身分識別資料整合] 連結](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="9b674-202">如果您未看到此提示，這可能表示您的 Microsoft Defender 的身分識別資料整合已經啟用。</span><span class="sxs-lookup"><span data-stu-id="9b674-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="9b674-203">不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。</span><span class="sxs-lookup"><span data-stu-id="9b674-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="9b674-204">移至 [ **設定**]，開啟 **Microsoft Defender 的身分識別整合** 切換，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![影像 of_the 設定] 頁面，您應該在此頁面上開啟「Microsoft Defender 身分識別整合」切換，然後按一下 [儲存]](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="9b674-206">針對新的 Microsoft Defender for Identity 實例，此整合切換功能會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="9b674-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="9b674-207">在繼續進行下一個步驟之前，請確認已啟用 Microsoft Defender 的身分識別整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="9b674-208">在 [雲端探索設定] 底下，選取 [ **Microsoft Defender For Endpoint integration**]，然後啟用整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="9b674-209">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-209">Click **Save**.</span></span>

   ![Image of_the Microsoft Defender for Endpoint] 頁面，選取 [Microsoft defender for Endpoint integration] 下的 [封鎖 unsanctioned 應用程式] 核取方塊。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="9b674-212">在 [雲端探索設定] 底下，選取 [ **使用者豐富**]，然後啟用與 Azure Active Directory 的整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[使用者豐富] 區段中的 [濃縮已發現使用者識別碼與 Azure Active Directory 使用者識別碼] 核取方塊的影像](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="9b674-214">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b674-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="9b674-215">如果您已啟用 Microsoft Defender for Endpoint，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="9b674-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="9b674-216">流覽至 microsoft Defender security center 的 [microsoft 365 Security center](https://security.microsoft.com/info)  >  **More Resources**  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b674-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="9b674-217">按一下 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="9b674-217">Click **Open**.</span></span>

   ![Microsoft 365 Security Center 頁面中的影像 of_Microsoft Defender Security Center 選項](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="9b674-219">遵循 Microsoft Defender for Endpoint 嚮導。</span><span class="sxs-lookup"><span data-stu-id="9b674-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="9b674-220">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-220">Click **Next**.</span></span> 

   ![Microsoft Defender 安全中心歡迎使用嚮導頁面上的影像 of_the](../../media/mtp-eval-59.png)

3. <span data-ttu-id="9b674-222">選擇 [根據您慣用的資料儲存位置]、[資料保留原則]、[組織大小] 和 [加入宣告預覽] 功能。</span><span class="sxs-lookup"><span data-stu-id="9b674-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Image of_the] 頁面上，選取您的資料儲存國家、保留原則及組織規模。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="9b674-225">您無法變更某些設定，例如，以後的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="9b674-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="9b674-226">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="9b674-226">Click **Next**.</span></span> 

4. <span data-ttu-id="9b674-227">按一下 [ **繼續** ]，它會布建您的 Microsoft Defender for Endpoint 租使用者。</span><span class="sxs-lookup"><span data-stu-id="9b674-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![影像 of_the 頁面提示您按一下 [繼續] 按鈕以建立您的雲端實例](../../media/mtp-eval-61.png)

5. <span data-ttu-id="9b674-229">透過「群組原則」、「Microsoft 端點管理員」或執行本機腳本至 Microsoft Defender for Endpoint，將端點架上。</span><span class="sxs-lookup"><span data-stu-id="9b674-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9b674-230">為了簡便起見，本指南使用本機腳本。</span><span class="sxs-lookup"><span data-stu-id="9b674-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="9b674-231">按一下 [ **下載套件** ]，然後將上架腳本複製到端點 (s) 。</span><span class="sxs-lookup"><span data-stu-id="9b674-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![影像 of_page 提示您按一下 [下載套件] 按鈕，將上架腳本複製到您的端點或端點](../../media/mtp-eval-62.png)

7. <span data-ttu-id="9b674-233">在您的端點上，以系統管理員身分執行上架腳本，然後選擇 [Y]。</span><span class="sxs-lookup"><span data-stu-id="9b674-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the 命令列，您可以在其中執行上架腳本，然後選擇 [Y] 繼續](../../media/mtp-eval-63.png)

8. <span data-ttu-id="9b674-235">恭喜，您已架您的第一個端點。</span><span class="sxs-lookup"><span data-stu-id="9b674-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the 命令列，您可以在其中取得您已架第一個端點的確認。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="9b674-238">從 Microsoft Defender for Endpoint 嚮導複製並貼上偵測測試。</span><span class="sxs-lookup"><span data-stu-id="9b674-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![影像 of_the 執行偵測測試步驟，您應該按一下 [複製] 以複製您應該在命令提示字元中貼上的偵測測試腳本。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="9b674-240">將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="9b674-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![影像 of_command 提示，您應該將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它](../../media/mtp-eval-66.png)

11. <span data-ttu-id="9b674-242">選取 [ **開始使用 Microsoft Defender For Endpoint** ] 從嚮導。</span><span class="sxs-lookup"><span data-stu-id="9b674-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![從嚮導中 of_the 的確認提示，您應該按一下 [開始使用 Microsoft Defender for Endpoint]](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="9b674-244">流覽 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="9b674-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="9b674-245">移至 [ **設定** ]，然後選取 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![您應選取 [高級功能] 的 [of_Microsoft Defender 安全性中心設定] 功能表中的影像](../../media/mtp-eval-68.png)

13. <span data-ttu-id="9b674-247">開啟與 **Microsoft Defender 身分識別** 的整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced 功能，您需要開啟的 Microsoft Defender 身分識別選項切換功能](../../media/mtp-eval-69.png)

14. <span data-ttu-id="9b674-249">開啟與 **Office 365 威脅情報** 的整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features，Office 365 威脅情報選項切換，您必須開啟](../../media/mtp-eval-70.png)

15. <span data-ttu-id="9b674-251">開啟與 **Microsoft Cloud App Security** 的整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced 功能，您需要開啟的 Microsoft Cloud App Security 選項切換功能](../../media/mtp-eval-71.png)

16. <span data-ttu-id="9b674-253">向中按向下方，然後按一下 [ **儲存偏好** 設定] 以確認新的整合。</span><span class="sxs-lookup"><span data-stu-id="9b674-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![您需要按一下的影像 of_Save 偏好設定按鈕](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="9b674-255">開始使用 Microsoft 365 Defender 服務</span><span class="sxs-lookup"><span data-stu-id="9b674-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="9b674-256">從2020年6月1日開始，Microsoft 會自動為所有合格的承租人啟用 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="9b674-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="9b674-257">如需詳細資訊，請參閱此 [Microsoft 技術小組文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。</span><span class="sxs-lookup"><span data-stu-id="9b674-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="9b674-258">移至 [Microsoft 365 Security Center](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="9b674-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="9b674-259">流覽至 [ **設定** ]，然後選取 [ **Microsoft 365 Defender**]。</span><span class="sxs-lookup"><span data-stu-id="9b674-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="9b674-260">從 Microsoft 365 安全性中心設定頁面影像 of_Microsoft 365 Defender 選項螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="9b674-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="9b674-261">如需更完整的指導，請參閱 [開啟 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="9b674-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="9b674-262">恭喜！</span><span class="sxs-lookup"><span data-stu-id="9b674-262">Congratulations!</span></span> <span data-ttu-id="9b674-263">您剛剛建立 Microsoft 365 Defender 試用實驗室或試驗環境！</span><span class="sxs-lookup"><span data-stu-id="9b674-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="9b674-264">現在，您可以熟悉 Microsoft 365 Defender 使用者介面！</span><span class="sxs-lookup"><span data-stu-id="9b674-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="9b674-265">查看您可以從下列 Microsoft 365 Defender 互動版指南中學到的內容，並瞭解如何使用每個儀表板做為日常安全性作業工作。</span><span class="sxs-lookup"><span data-stu-id="9b674-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="9b674-266">接下來，您可以模擬攻擊，並查看「向量積」功能如何偵測、建立提醒，以及自動回應端點上的 fileless 攻擊。</span><span class="sxs-lookup"><span data-stu-id="9b674-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="9b674-267">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9b674-267">Next step</span></span>

- <span data-ttu-id="9b674-268">[產生測試警示](generate-test-alert.md) -在您的 Microsoft 365 Defender 試用版實驗室中執行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="9b674-268">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>