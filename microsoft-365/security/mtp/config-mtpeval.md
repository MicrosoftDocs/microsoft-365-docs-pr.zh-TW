---
title: 為試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎
description: 針對您的試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎，例如適用于 Office 365 的 Microsoft Defender、Microsoft Defender for Identity、Microsoft Cloud App 安全性，以及 Microsoft Defender for Endpoint。
keywords: 設定 Microsoft 威脅防護試用版、Microsoft 威脅防護試用版設定、設定 Microsoft 威脅防護試驗專案、設定 Microsoft 威脅防護基礎、Microsoft 威脅防護基礎
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
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932235"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="75697-104">針對您的試驗實驗室或試驗環境設定 Microsoft 365 Defender 基礎</span><span class="sxs-lookup"><span data-stu-id="75697-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75697-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="75697-105">**Applies to:**</span></span>
- <span data-ttu-id="75697-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75697-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="75697-107">建立 Microsoft 365 Defender 試用版實驗室或試驗環境，並部署此為三階段程式：</span><span class="sxs-lookup"><span data-stu-id="75697-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="75697-108">[![階段 1：準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="75697-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="75697-109">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="75697-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="75697-110">[![階段 2：設定](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="75697-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="75697-111">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="75697-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![階段 3：上機](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="75697-113">階段 3：上機</span><span class="sxs-lookup"><span data-stu-id="75697-113">Phase 3: Onboard</span></span> | <span data-ttu-id="75697-114">[![返回試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="75697-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="75697-115">回到試驗手冊</span><span class="sxs-lookup"><span data-stu-id="75697-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="75697-116">*您目前在這裡！*</span><span class="sxs-lookup"><span data-stu-id="75697-116">*You are here!*</span></span> | |

<span data-ttu-id="75697-117">您目前處於組組階段。</span><span class="sxs-lookup"><span data-stu-id="75697-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="75697-118">準備是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="75697-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="75697-119">本文將引導您瞭解部署 Microsoft Defender for Endpoint 時需要考慮的要點。</span><span class="sxs-lookup"><span data-stu-id="75697-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="75697-120">Microsoft 365 Defender 柱柱</span><span class="sxs-lookup"><span data-stu-id="75697-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="75697-121">Microsoft 365 Defender 由四個石柱組成。</span><span class="sxs-lookup"><span data-stu-id="75697-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="75697-122">雖然一個石柱可以為網路組織的安全性提供值，但啟用四個 Microsoft 365 Defender 基礎會賦予貴組織最大的價值。</span><span class="sxs-lookup"><span data-stu-id="75697-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![適用于of_Microsoft使用者 、Microsoft Defender for Endpoint 端點、雲端應用程式、Microsoft Cloud App 安全性及資料之 Microsoft Defender for Office 365 之使用者的 365 Defender 解決方案影像](../../media/mtp/m365pillars.png)

<span data-ttu-id="75697-124">本節將引導您進行設定：</span><span class="sxs-lookup"><span data-stu-id="75697-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="75697-125">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75697-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="75697-126">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75697-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="75697-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75697-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="75697-128">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75697-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="75697-129">設定 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75697-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="75697-130">如果您已經啟用 Office 365 的 Defender，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="75697-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="75697-131">有一個 PowerShell 模組稱為 *Office 365* 進位威脅防護建議組設定分析程式 (ORCA) ，可協助判斷其中一些設定。</span><span class="sxs-lookup"><span data-stu-id="75697-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="75697-132">當您在租使用者中以系統管理員的系統管理員角色執行時，get-ORCAReport 將可協助產生反垃圾郵件、防網路釣魚和其他郵件內容設定的評估。</span><span class="sxs-lookup"><span data-stu-id="75697-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="75697-133">您可以下載此模組 https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="75697-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="75697-134">流覽至 [Office 365 安全性&](https://protection.office.com/homepage)  >  **合規性中心的威脅管理**  >  **政策**。</span><span class="sxs-lookup"><span data-stu-id="75697-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![365 of_Office安全規範&威脅管理政策頁面的圖像](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="75697-136">按一下 **[防網路釣魚，** 選取 [ **建立** 並填入策略名稱與描述。</span><span class="sxs-lookup"><span data-stu-id="75697-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="75697-137">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75697-137">Click **Next**.</span></span>

   ![Of_Office 365 安全性&合規性中心防網路釣魚政策頁面的圖像，您可以在此命名您的政策](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="75697-139">在適用于 Office 365 的 Microsoft Defender 中編輯您的進位防網路釣魚政策。</span><span class="sxs-lookup"><span data-stu-id="75697-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="75697-140">將 **進位網路釣魚閾值變更** 為 **2 - 進一無二**。</span><span class="sxs-lookup"><span data-stu-id="75697-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="75697-141">按一下 [ **新增條件** 下拉式功能表，然後選取您的網域 (收) 網域。</span><span class="sxs-lookup"><span data-stu-id="75697-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="75697-142">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75697-142">Click **Next**.</span></span>

   ![365 of_Office安全規範中心&網路釣魚政策頁面的圖像，您可以在其中新增其應用程式的條件](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="75697-144">檢查您的設定。</span><span class="sxs-lookup"><span data-stu-id="75697-144">Review your settings.</span></span> <span data-ttu-id="75697-145">按一下 **[建立此策略>** 以確認。</span><span class="sxs-lookup"><span data-stu-id="75697-145">Click **Create this policy** to confirm.</span></span> 

   ![圖像of_Office 365 安全性&合規性中心防網路釣魚政策頁面，您可以在其中檢查您的設定，然後按一下建立此政策按鈕](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="75697-147">選取 **[安全附件** ， **然後開啟 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP 選項。</span><span class="sxs-lookup"><span data-stu-id="75697-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![可of_Office SharePoint、OneDrive 和 Microsoft Teams & ATP 的 365 安全規範中心頁面圖像](../../media/mtp-eval-36.png)

6. <span data-ttu-id="75697-149">按一下 + 圖示以建立新的安全附件原則，然後以收件者網域的網域方式將附件原則應用至您的網域。</span><span class="sxs-lookup"><span data-stu-id="75697-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="75697-150">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="75697-150">Click **Save**.</span></span>

   ![可在 of_Office 365 安全&中心頁面建立新安全附件策略的影像](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="75697-152">接下來，選取 **[安全連結策略** ，然後按一下鉛筆圖示以編輯預設策略。</span><span class="sxs-lookup"><span data-stu-id="75697-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="75697-153">請確定未 **選取 [** 不要追蹤使用者何時點選安全連結選項，同時選取其他選項。</span><span class="sxs-lookup"><span data-stu-id="75697-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="75697-154">請參閱 [安全連結設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 以瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75697-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="75697-155">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="75697-155">Click **Save**.</span></span> 

   ![顯示of_Office 365 安全性&規範中心頁面的圖像，顯示未選取 [使用者按一下安全時不要追蹤選項](../../media/mtp-eval-38.png)

9. <span data-ttu-id="75697-157">接著，選取 **反惡意攻擊** 策略，選取預設值，然後選擇鉛筆圖示。</span><span class="sxs-lookup"><span data-stu-id="75697-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="75697-158">按一下 **[設定** >， **然後選取 [是，並使用預設通知** 文字啟用 **惡意攻擊偵測回應**。</span><span class="sxs-lookup"><span data-stu-id="75697-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="75697-159">開啟 **一般附件類型篩選** 。</span><span class="sxs-lookup"><span data-stu-id="75697-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="75697-160">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="75697-160">Click **Save**.</span></span>

    ![365 of_Office安全&中心頁面的圖像，顯示已預設通知開啟惡意程式碼偵測回應，且一般附件類型篩選器已開啟](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="75697-162">流覽至 [Office 365 安全性&合規性中心](https://protection.office.com/homepage)  >  **搜尋**  >  **稽核記錄搜尋**，並開啟稽核。</span><span class="sxs-lookup"><span data-stu-id="75697-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![可在 of_Office 365 安全性&中心頁面開啟稽核記錄搜尋的圖像](../../media/mtp-eval-40.png)

12. <span data-ttu-id="75697-164">整合 Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="75697-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75697-165">流覽至 [Office 365](https://protection.office.com/homepage)安全性&合規性中心威脅管理總管，然後針對畫面右上角的端點設定選取  >    >  \*\*\*\* **Microsoft Defender。**</span><span class="sxs-lookup"><span data-stu-id="75697-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="75697-166">在 [端點的 Defender for Connection- 對話方塊中，開啟 [**連接至 Microsoft Defender for Endpoint。**</span><span class="sxs-lookup"><span data-stu-id="75697-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![可在 of_Office 365 安全性&中心頁面開啟 Microsoft Defender 端點連結的影像](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="75697-168">設定 Microsoft Defender 的身分識別</span><span class="sxs-lookup"><span data-stu-id="75697-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="75697-169">如果您已經啟用 Microsoft Defender 的身分識別，請略過此步驟</span><span class="sxs-lookup"><span data-stu-id="75697-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="75697-170">流覽至 [Microsoft 365 資訊安全中心，>](https://security.microsoft.com/info)**選取更多** Microsoft  >  **Defender 用於身分識別的資源**。</span><span class="sxs-lookup"><span data-stu-id="75697-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![365 of_Microsoft 365 資訊安全中心頁面上有開啟 Microsoft Defender 身分識別選項的影像](../../media/mtp-eval-42.png)

2. <span data-ttu-id="75697-172">按一下 **[建立** 以啟動 Microsoft Defender 的身分識別精靈。</span><span class="sxs-lookup"><span data-stu-id="75697-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![[of_Microsoft識別精靈的 Defender 頁面圖像，您應該按一下 [建立按鈕](../../media/mtp-eval-43.png)

3. <span data-ttu-id="75697-174">選擇 **提供使用者名稱和密碼，以連接到您的 Active Directory 樹目錄**。</span><span class="sxs-lookup"><span data-stu-id="75697-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![身分of_Microsoft Defender 歡迎頁面的圖像](../../media/mtp-eval-44.png)

4. <span data-ttu-id="75697-176">輸入 Active Directory 內部部署認證。</span><span class="sxs-lookup"><span data-stu-id="75697-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="75697-177">這可以是具有 Active Directory 讀取權限的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="75697-177">This can be any user account that has read access to Active Directory.</span></span>

   ![身分of_Microsoft Defender for Identity Directory 服務頁面的圖像，您應該將認證放在這個頁面](../../media/mtp-eval-45.png)

5. <span data-ttu-id="75697-179">接下來，選擇 **下載感應器設定** ，然後傳輸檔案到您的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="75697-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![圖像of_Microsoft識別的 Defender 頁面，您可以在此選取下載感應器設定](../../media/mtp-eval-46.png)

6. <span data-ttu-id="75697-181">執行 Microsoft Defender for Identity 感應器設定，然後按照精靈執行。</span><span class="sxs-lookup"><span data-stu-id="75697-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![身分of_Microsoft Defender 頁面的圖像，您應該按一下 [Microsoft Defender for Identity 感應器精靈，](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="75697-183">按一下 **感應器** 部署類型的 [下一步。</span><span class="sxs-lookup"><span data-stu-id="75697-183">Click **Next** at the sensor deployment type.</span></span>

   ![身分of_Microsoft Defender 頁面的圖像，您應該按一下旁以前往下一頁](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="75697-185">複製便捷鍵，因為您需要在精靈中輸入下一個。</span><span class="sxs-lookup"><span data-stu-id="75697-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![影像of_the感應器頁面，您應該複製下一個 Microsoft Defender for Identity 感應器設定精靈頁面中輸入的存取鍵](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="75697-187">將便捷鍵複製到精靈，然後按一下 [ **安裝**。</span><span class="sxs-lookup"><span data-stu-id="75697-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![[of_Microsoft識別感應器精靈頁面的影像，您應該在這裡提供便捷鍵，然後按一下安裝按鈕](../../media/mtp-eval-50.png)

10. <span data-ttu-id="75697-189">恭喜您，您已成功在網域控制站上針對身分識別將 Microsoft Defender 設成。</span><span class="sxs-lookup"><span data-stu-id="75697-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![[of_Microsoft識別感應器精靈安裝完成的圖像，您應該按一下完成按鈕](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="75697-191">在 Microsoft [Defender for Identity settings](https://go.microsoft.com/fwlink/?linkid=2040449) 區段下，選取 \*\*Microsoft Defender for Endpoint \*\*，然後開啟切換開關。</span><span class="sxs-lookup"><span data-stu-id="75697-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="75697-192">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="75697-192">Click **Save**.</span></span> 

    ![影像of_the Microsoft Defender 的身分識別設定頁面，您應該將 Microsoft Defender for Endpoint 切換為開啟](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="75697-194">Windows Defender ATP 已重新組織為端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="75697-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75697-195">我們所有入口網站都推出重新建立變更的一致性。</span><span class="sxs-lookup"><span data-stu-id="75697-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="75697-196">設定 Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="75697-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="75697-197">如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="75697-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="75697-198">流覽至 [Microsoft 365 資訊安全中心](https://security.microsoft.com/info)  >  **其他資源** Microsoft 雲端  >  **App 安全性**。</span><span class="sxs-lookup"><span data-stu-id="75697-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![可在 of_Microsoft 365 資訊安全中心頁面看到 Microsoft Cloud App 卡片的影像，應該按一下開啟按鈕](../../media/mtp-eval-53.png)

2. <span data-ttu-id="75697-200">在整合 Microsoft Defender for Identity 的資訊提示中，選取啟用 **Microsoft Defender 進行身分識別資料整合**。</span><span class="sxs-lookup"><span data-stu-id="75697-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![影像of_the資訊提示以整合 Microsoft Defender 的身分識別，您應該在這裡選取啟用 Microsoft Defender 進行身分識別資料整合連結](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="75697-202">如果您沒看到這個提示，可能表示您的 Microsoft Defender 的身分識別資料整合功能已啟用。</span><span class="sxs-lookup"><span data-stu-id="75697-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="75697-203">不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。</span><span class="sxs-lookup"><span data-stu-id="75697-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="75697-204">請前往 [ **設定**，開啟 **Microsoft Defender 的** 身分識別整合切換開關，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="75697-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![影像of_the設定頁面，您應該開啟 Microsoft Defender 的身分識別整合切換，然後按一下 [儲存](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="75697-206">針對新的 Microsoft Defender 身分識別實例，此整合切換開關會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="75697-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="75697-207">繼續下一個步驟之前，請確認您的 Microsoft Defender 身分識別整合功能已啟用。</span><span class="sxs-lookup"><span data-stu-id="75697-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="75697-208">在雲端探索設定下，選取 **Microsoft Defender 進行端點整合**，然後啟用整合。</span><span class="sxs-lookup"><span data-stu-id="75697-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="75697-209">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="75697-209">Click **Save**.</span></span>

   ![影像of_the Microsoft Defender for Endpoint 頁面，其中已選取 Microsoft Defender for Endpoint 整合下的封鎖未封鎖的應用程式核取方塊。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="75697-212">在雲端探索設定下，選取 **使用者擴充**，然後啟用與 Azure Active Directory 的整合。</span><span class="sxs-lookup"><span data-stu-id="75697-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![使用者擴充區段的圖像，其中已選取 Azure Active Directory 使用者名稱核取方塊的豐富探索使用者識別碼](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="75697-214">設定 Microsoft Defender 端點</span><span class="sxs-lookup"><span data-stu-id="75697-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="75697-215">如果您已經啟用端點的 Microsoft Defender，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="75697-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="75697-216">流覽至 [Microsoft 365 資訊安全中心](https://security.microsoft.com/info)  >  **其他資源** Microsoft  >  **Defender 資訊安全中心**。</span><span class="sxs-lookup"><span data-stu-id="75697-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="75697-217">按一下 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="75697-217">Click **Open**.</span></span>

   ![Microsoft 365 of_Microsoft中 Defender 資訊安全中心的影像選項](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="75697-219">請遵循 Microsoft Defender for Endpoint 精靈。</span><span class="sxs-lookup"><span data-stu-id="75697-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="75697-220">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75697-220">Click **Next**.</span></span> 

   ![Microsoft Defender of_the歡迎精靈頁面的影像](../../media/mtp-eval-59.png)

3. <span data-ttu-id="75697-222">根據您的偏好資料儲存位置、資料保留政策、組織規模，以及選擇參加預覽功能來選擇。</span><span class="sxs-lookup"><span data-stu-id="75697-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![選取of_the儲存國家/地區、保留規定和組織大小的圖像頁面。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="75697-225">之後您無法變更某些設定，例如資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="75697-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="75697-226">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="75697-226">Click **Next**.</span></span> 

4. <span data-ttu-id="75697-227">按一下 **[繼續** ，它會針對端點租使用者提供您的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="75697-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![頁面上of_the按一下 [繼續按鈕以建立雲端實例](../../media/mtp-eval-61.png)

5. <span data-ttu-id="75697-229">透過群組原則、Microsoft Endpoint Manager 或執行本地腳本到 Microsoft Defender for Endpoint，來設置端點。</span><span class="sxs-lookup"><span data-stu-id="75697-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75697-230">為了簡化，本指南使用本地腳本。</span><span class="sxs-lookup"><span data-stu-id="75697-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="75697-231">按一下 **[下載套件** ，然後複製設置腳本至 (端點) 。</span><span class="sxs-lookup"><span data-stu-id="75697-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![提示of_page下載套件按鈕以將上線腳本複製到端點或端點的圖像](../../media/mtp-eval-62.png)

7. <span data-ttu-id="75697-233">在端點上，以系統管理員的名次執行設置腳本，然後選擇 Y。</span><span class="sxs-lookup"><span data-stu-id="75697-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![圖像of_the您執行設置腳本並選擇 Y 以繼續進行的命令列](../../media/mtp-eval-63.png)

8. <span data-ttu-id="75697-235">恭喜您，您的第一個端點已經上線。</span><span class="sxs-lookup"><span data-stu-id="75697-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![顯示of_the的影像，您可以在此取得已上線第一個端點的確認。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="75697-238">從 Microsoft Defender for Endpoint 精靈複製貼上偵測測試。</span><span class="sxs-lookup"><span data-stu-id="75697-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![影像of_the偵測測試步驟，您應該按一下 [複製以複製偵測測試腳本，您應該貼到命令提示文字中](../../media/mtp-eval-65.png)

10. <span data-ttu-id="75697-240">將 PowerShell 腳本複製到提升許可權的命令提示文字，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="75697-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![影像of_command提示，您應該將 PowerShell 腳本複製到提升許可權的命令提示文字並加以執行](../../media/mtp-eval-66.png)

11. <span data-ttu-id="75697-242">從 **精靈選取** 開始使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="75697-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![影像of_the精靈中的確認提示，您應該按一下 [開始使用 Microsoft Defender for Endpoint](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="75697-244">請流覽 [Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="75697-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="75697-245">請前往設定 **，** 然後選取進 **一功能**。</span><span class="sxs-lookup"><span data-stu-id="75697-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![圖像of_Microsoft Defender 資訊安全中心設定功能表，您應該選取進一功能](../../media/mtp-eval-68.png)

13. <span data-ttu-id="75697-247">開啟與 Microsoft **Defender 的身分識別整合**。</span><span class="sxs-lookup"><span data-stu-id="75697-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![需要of_Microsoft的 Microsoft Defender 身分識別選項切換按鈕圖像](../../media/mtp-eval-69.png)

14. <span data-ttu-id="75697-249">開啟與 Office **365 威脅情報的整合**。</span><span class="sxs-lookup"><span data-stu-id="75697-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![需要of_Microsoft Defender 資訊安全中心進功能、Office 365 威脅情報選項切換開關的圖像](../../media/mtp-eval-70.png)

15. <span data-ttu-id="75697-251">開啟與 **Microsoft Cloud App 安全性的整合**。</span><span class="sxs-lookup"><span data-stu-id="75697-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![需要of_Microsoft Defender 資訊安全中心進功能、Microsoft 雲端 App 安全性選項切換開關的圖像](../../media/mtp-eval-71.png)

16. <span data-ttu-id="75697-253">向下卷軸並按一下 **[儲存偏好** 設定以確認新的整合。</span><span class="sxs-lookup"><span data-stu-id="75697-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![圖像of_Save您需要按一下的喜好設定按鈕](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="75697-255">開始使用 Microsoft 365 Defender 服務</span><span class="sxs-lookup"><span data-stu-id="75697-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="75697-256">自 2020 年 6 月 1 日起，Microsoft 會自動針對所有合格租使用者啟用 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="75697-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="75697-257">請參閱此 [Microsoft 技術社群文章，瞭解授權資格的詳細資訊](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。</span><span class="sxs-lookup"><span data-stu-id="75697-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="75697-258">請前往 [Microsoft 365 資訊安全中心](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="75697-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="75697-259">流覽至 **設定，** 然後選取 **Microsoft 365 Defender。**</span><span class="sxs-lookup"><span data-stu-id="75697-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="75697-260">Microsoft 365 of_Microsoft設定頁面的影像顯示 365 Defender 選項螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="75697-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="75697-261">有關更全方位的指引，請參閱開啟[Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="75697-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="75697-262">恭喜您！</span><span class="sxs-lookup"><span data-stu-id="75697-262">Congratulations!</span></span> <span data-ttu-id="75697-263">您剛建立 Microsoft 365 Defender 試用版實驗室或試驗環境！</span><span class="sxs-lookup"><span data-stu-id="75697-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="75697-264">現在您可以熟悉 Microsoft 365 Defender 使用者介面了！</span><span class="sxs-lookup"><span data-stu-id="75697-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="75697-265">查看您可從下列 Microsoft 365 Defender 互動式指南中學到什麼，並瞭解如何使用儀表板執行日常的安全性作業工作。</span><span class="sxs-lookup"><span data-stu-id="75697-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="75697-266">接下來，您可以模擬攻擊，並查看交叉產品功能偵測、建立警示，並自動回應端點上的無檔案攻擊。</span><span class="sxs-lookup"><span data-stu-id="75697-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="75697-267">下一步</span><span class="sxs-lookup"><span data-stu-id="75697-267">Next step</span></span>
|[<span data-ttu-id="75697-268">攻擊模擬階段</span><span class="sxs-lookup"><span data-stu-id="75697-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="75697-269">針對您的 Microsoft 365 Defender 試驗環境執行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="75697-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
