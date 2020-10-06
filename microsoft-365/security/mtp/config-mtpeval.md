---
title: 設定試用實驗室或試驗環境的 Microsoft 威脅防護支柱
description: 針對您的試用實驗室或試驗環境，設定 Microsoft 威脅防護支柱，例如 Office 365 ATP、Azure ATP、Microsoft Cloud App Security 和 Microsoft Defender ATP。
keywords: 設定 Microsoft 威脅防護試用版、Microsoft 威脅防護試用版設定、設定 Microsoft 威脅防護試驗專案、設定 microsoft 威脅防護支柱、Microsoft 威脅防護支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 79e141ad85eecab827e0caa98fe022f88335c671
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368146"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="822d9-104">為您的試用實驗室或試驗環境設定 Microsoft 威脅防護支柱</span><span class="sxs-lookup"><span data-stu-id="822d9-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="822d9-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="822d9-105">**Applies to:**</span></span>
- <span data-ttu-id="822d9-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="822d9-107">建立 Microsoft 威脅防護試用實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="822d9-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="準備您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="822d9-109">階段1：準備 </a></span><span class="sxs-lookup"><span data-stu-id="822d9-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="設定您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="822d9-111">階段2：設定 </a></span><span class="sxs-lookup"><span data-stu-id="822d9-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="針對您的 Microsoft 威脅防護試用實驗室或試驗環境和板載端點設定每個 Microsoft 威脅防護 pillar" />
      <br/><span data-ttu-id="822d9-113">階段3：設定板載 & </a></span><span class="sxs-lookup"><span data-stu-id="822d9-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="822d9-114">您目前正在設定階段。</span><span class="sxs-lookup"><span data-stu-id="822d9-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="822d9-115">準備工作是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="822d9-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="822d9-116">在本文中，您將指導您準備部署 Microsoft Defender ATP 時所需考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="822d9-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="822d9-117">Microsoft 威脅防護的支柱</span><span class="sxs-lookup"><span data-stu-id="822d9-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="822d9-118">Microsoft 威脅防護包含四個支柱。</span><span class="sxs-lookup"><span data-stu-id="822d9-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="822d9-119">雖然一個 pillar 可以為您的網路組織的安全性提供價值，但是啟用四個 Microsoft 威脅防護的分項會使組織發揮最大的價值。</span><span class="sxs-lookup"><span data-stu-id="822d9-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="822d9-120">影像 of_Microsoft 威脅防護解決方案，適用于使用者、Azure 高級威脅防護、端點 Microsoft Defender 高級威脅防護、雲端應用程式、Microsoft Cloud App 安全性及資料，Office 365 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="822d9-121">本節會引導您設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="822d9-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="822d9-122">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="822d9-123">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="822d9-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="822d9-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="822d9-125">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="822d9-126">設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="822d9-127">如果您已啟用 Office 365 的高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="822d9-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="822d9-128">有一個稱為「 \*Office 365 高級威脅防護 \* 」的 PowerShell 模組 (ORCA) 可協助判斷部分設定。</span><span class="sxs-lookup"><span data-stu-id="822d9-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="822d9-129">當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。</span><span class="sxs-lookup"><span data-stu-id="822d9-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="822d9-130">您可以從下載此模組 https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="822d9-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="822d9-131">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **原則**。</span><span class="sxs-lookup"><span data-stu-id="822d9-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & 合規性中心威脅管理原則頁面](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="822d9-133">按一下 [ **ATP 反網路釣魚**]，選取 [ **建立** 並填入原則名稱和描述]。</span><span class="sxs-lookup"><span data-stu-id="822d9-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="822d9-134">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-134">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中命名原則](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="822d9-136">編輯您的高級 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="822d9-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="822d9-137">將 **高級網路釣魚閥值** 變更為 **2-嚴格**。</span><span class="sxs-lookup"><span data-stu-id="822d9-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="822d9-138">按一下 [ **新增條件** ] 下拉式功能表，然後選取您的網域 (s) 做為收件者網域。</span><span class="sxs-lookup"><span data-stu-id="822d9-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="822d9-139">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-139">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合規性中心反網路釣魚原則頁面，您可以在其中新增其應用程式的條件](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="822d9-141">請複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="822d9-141">Review your settings.</span></span> <span data-ttu-id="822d9-142">按一下 [ **建立這個原則** ] 以確認。</span><span class="sxs-lookup"><span data-stu-id="822d9-142">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & 相容性中心反網路釣魚原則頁面，您可以在其中檢查您的設定，然後按一下 [建立這個原則] 按鈕](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="822d9-144">選取 [ **ATP 安全附件** ]，然後選取 [ **開啟 SharePoint]、[OneDrive] 和 [Microsoft 小組** ] 選項的 atp。</span><span class="sxs-lookup"><span data-stu-id="822d9-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在其中開啟 SharePoint、OneDrive 及 Microsoft 小組的 ATP](../../media/mtp-eval-36.png)

6. <span data-ttu-id="822d9-146">按一下 [+] 圖示，以建立新的安全附件原則，並將其套用為網域的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="822d9-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="822d9-147">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-147">Click **Save**.</span></span>

   ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上建立新的安全附件原則](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="822d9-149">接下來，選取 [ **ATP 安全連結** 原則]，然後按一下鉛筆圖示以編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="822d9-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="822d9-150">請確定未選取 [ **不要在使用者按一下安全連結時進行追蹤** ] 選項，而會選取其餘的選項。</span><span class="sxs-lookup"><span data-stu-id="822d9-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="822d9-151">如需詳細資訊，請參閱 [安全連結設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 。</span><span class="sxs-lookup"><span data-stu-id="822d9-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="822d9-152">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-152">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & 相容性中心] 頁面，顯示未選取 [使用者按一下安全時不會追蹤] 選項](../../media/mtp-eval-38.png)

9. <span data-ttu-id="822d9-154">接下來選取 **反惡意** 代碼原則，選取預設值，然後選擇 [鉛筆] 圖示。</span><span class="sxs-lookup"><span data-stu-id="822d9-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="822d9-155">按一下 [ **設定** ]，然後選取 **[是] 並使用預設通知文字** ，以啟用 **惡意程式碼偵測回應**。</span><span class="sxs-lookup"><span data-stu-id="822d9-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="822d9-156">開啟 **通用附件類型 Filter** 。</span><span class="sxs-lookup"><span data-stu-id="822d9-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="822d9-157">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-157">Click **Save**.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，顯示惡意程式碼偵測回應開啟時會啟用預設通知，而一般附件類型篩選已開啟](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="822d9-159">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **搜尋**  >  **審核記錄檔搜尋**，然後開啟審計。</span><span class="sxs-lookup"><span data-stu-id="822d9-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此開啟審核記錄搜尋](../../media/mtp-eval-40.png)

12. <span data-ttu-id="822d9-161">將 Office 365 ATP 與 Microsoft Defender ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="822d9-162">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage)  >  **威脅管理**  >  **瀏覽器**，然後選取螢幕右上角的 [ **WDATP 設定**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="822d9-163">在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Image of_Office 365 Security & 合規性中心] 頁面，您可以在此頁面上開啟 Windows Defender ATP 連接](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="822d9-165">設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="822d9-166">如果您已經啟用 Azure 高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="822d9-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="822d9-167">流覽至[Microsoft 365 Security Center](https://security.microsoft.com/info) > 選取**其他資源**  >  **Azure 高級威脅防護**。</span><span class="sxs-lookup"><span data-stu-id="822d9-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![影像 of_Microsoft 365 Security Center 頁面，其中有開啟 Azure 高級威脅防護的選項](../../media/mtp-eval-42.png)

2. <span data-ttu-id="822d9-169">按一下 [ **建立** ]，啟動 Azure 高級威脅防護嚮導。</span><span class="sxs-lookup"><span data-stu-id="822d9-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![影像 of_Azure 高級威脅防護嚮導] 頁面，您應該按一下此頁面上的 [建立] 按鈕](../../media/mtp-eval-43.png)

3. <span data-ttu-id="822d9-171">選擇 [ **提供使用者名稱和密碼] 以連線至您的 Active Directory 樹**系。</span><span class="sxs-lookup"><span data-stu-id="822d9-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![影像 of_Azure 高級威脅防護歡迎頁面](../../media/mtp-eval-44.png)

4. <span data-ttu-id="822d9-173">輸入您的 Active Directory 內部部署認證。</span><span class="sxs-lookup"><span data-stu-id="822d9-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="822d9-174">這可以是具有 Active Directory 讀取權限的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="822d9-174">This can be any user account that has read access to Active Directory.</span></span>

   ![影像 of_Azure 高級威脅防護目錄服務] 頁面，您應該在這裡放置您的認證](../../media/mtp-eval-45.png)

5. <span data-ttu-id="822d9-176">接下來，選擇 [將 **感應器安裝** 和傳輸檔案下載到您的網域控制站]。</span><span class="sxs-lookup"><span data-stu-id="822d9-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![影像 of_Azure 高級威脅防護] 頁面，您可以在其中選取 [下載感應器設定]](../../media/mtp-eval-46.png)

6. <span data-ttu-id="822d9-178">執行 Azure ATP 感應器設定，然後開始遵循嚮導。</span><span class="sxs-lookup"><span data-stu-id="822d9-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![影像 of_Azure 高級威脅防護] 頁面，您應該在此按一下 [下一步] 依照 Azure ATP 感應器嚮導](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="822d9-180">在感應器部署類型中按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="822d9-180">Click **Next** at the sensor deployment type.</span></span>

   ![影像 of_Azure 高級威脅防護] 頁面，您應該在此頁面上，按一下 [下一步] 以移至下一頁](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="822d9-182">複製存取機碼，因為您需要在嚮導的下一步輸入它。</span><span class="sxs-lookup"><span data-stu-id="822d9-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![影像 of_the 感應器頁面，您應該在此頁面上複製您需要在下一個 Azure ATP 感應器安裝精靈中輸入的訪問金鑰。](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="822d9-184">將存取機碼複製到嚮導，然後按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Azure Advanced 威脅防護 Azure ATP 感應器嚮導] 頁面，您應該在此頁面上提供存取機碼，然後按一下 [安裝] 按鈕](../../media/mtp-eval-50.png)

10. <span data-ttu-id="822d9-186">恭喜，您已在您的網域控制站上成功設定 Azure 高級威脅防護。</span><span class="sxs-lookup"><span data-stu-id="822d9-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![影像 of_Azure 高級威脅防護 Azure ATP 感應器嚮導安裝完成，您應該按一下 [完成] 按鈕](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="822d9-188">在 [ [Azure AZURE ATP](https://go.microsoft.com/fwlink/?linkid=2040449) 設定] 區段中，選取 [ **Windows Defender atp**]，然後開啟切換。</span><span class="sxs-lookup"><span data-stu-id="822d9-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="822d9-189">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-189">Click **Save**.</span></span> 

    ![Image of_the Azure Azure ATP 設定頁面，您應該在此頁面上開啟 Windows Defender ATP 切換](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="822d9-191">Windows Defender ATP 已 rebranded 為 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="822d9-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="822d9-192">所有的入口網站上的 ..org 變更都會針對一致性加以匯總。</span><span class="sxs-lookup"><span data-stu-id="822d9-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="822d9-193">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="822d9-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="822d9-194">如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="822d9-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="822d9-195">流覽至[microsoft](https://security.microsoft.com/info)  >  **More Resources**  >  **Cloud App security**的 microsoft 365 Security Center More Resources。</span><span class="sxs-lookup"><span data-stu-id="822d9-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 Security Center 頁面，您可以在其中看到 Microsoft Cloud App 卡片，應該按一下 [開啟] 按鈕](../../media/mtp-eval-53.png)

2. <span data-ttu-id="822d9-197">在資訊提示中，整合 Azure ATP，選取 [ **啟用 AZURE atp 資料整合**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Image of_the information prompt 整合 Azure ATP 應選取 [啟用 Azure ATP 資料整合] 連結](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="822d9-199">如果您未看到此提示，這可能表示您的 Azure ATP 資料整合已經啟用。</span><span class="sxs-lookup"><span data-stu-id="822d9-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="822d9-200">不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。</span><span class="sxs-lookup"><span data-stu-id="822d9-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="822d9-201">移至 [ **設定**]，開啟 **Azure ATP 整合** 切換，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![您應開啟 Azure ATP 整合切換的 [影像 of_the 設定] 頁面，然後按一下 [儲存]](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="822d9-203">針對新的 Azure ATP 實例，此整合切換功能會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="822d9-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="822d9-204">在您繼續下一個步驟之前，請確認您的 Azure ATP 整合已啟用。</span><span class="sxs-lookup"><span data-stu-id="822d9-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="822d9-205">在 [雲端探索設定] 底下，選取 [ **Microsoft DEFENDER ATP 整合**]，然後啟用整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="822d9-206">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-206">Click **Save**.</span></span>

   ![Unsanctioned Microsoft Defender ATP 頁面上的 of_the 影像，其中會選取 [Microsoft Defender ATP 整合] 底下的 [封鎖應用程式] 核取方塊。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="822d9-209">在 [雲端探索設定] 底下，選取 [ **使用者豐富**]，然後啟用與 Azure Active Directory 的整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![[使用者豐富] 區段中的 [濃縮已發現使用者識別碼與 Azure Active Directory 使用者識別碼] 核取方塊的影像](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="822d9-211">設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="822d9-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="822d9-212">如果您已啟用 Microsoft Defender 高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="822d9-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="822d9-213">流覽至 microsoft Defender security center 的[microsoft 365 Security center](https://security.microsoft.com/info)  >  **More Resources**  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="822d9-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="822d9-214">按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822d9-214">Click **Open**.</span></span>

   ![Microsoft 365 Security Center 頁面中的影像 of_Microsoft Defender Security Center 選項](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="822d9-216">遵循 Microsoft Defender 高級威脅防護嚮導。</span><span class="sxs-lookup"><span data-stu-id="822d9-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="822d9-217">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-217">Click **Next**.</span></span> 

   ![Microsoft Defender 安全中心歡迎使用嚮導頁面上的影像 of_the](../../media/mtp-eval-59.png)

3. <span data-ttu-id="822d9-219">選擇 [根據您慣用的資料儲存位置]、[資料保留原則]、[組織大小] 和 [加入宣告預覽] 功能。</span><span class="sxs-lookup"><span data-stu-id="822d9-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Image of_the] 頁面上，選取您的資料儲存國家、保留原則及組織規模。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="822d9-222">您無法變更某些設定，例如，以後的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="822d9-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="822d9-223">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822d9-223">Click **Next**.</span></span> 

4. <span data-ttu-id="822d9-224">按一下 [ **繼續** ]，它會布建您的 MICROSOFT Defender ATP 租使用者。</span><span class="sxs-lookup"><span data-stu-id="822d9-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![影像 of_the 頁面提示您按一下 [繼續] 按鈕以建立您的雲端實例](../../media/mtp-eval-61.png)

5. <span data-ttu-id="822d9-226">透過「群組原則」、「Microsoft 端點管理員」或執行本機腳本至 Microsoft Defender ATP，將您的端點上架在一起。</span><span class="sxs-lookup"><span data-stu-id="822d9-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="822d9-227">為了簡便起見，本指南使用本機腳本。</span><span class="sxs-lookup"><span data-stu-id="822d9-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="822d9-228">按一下 [ **下載套件** ]，然後將上架腳本複製到端點 (s) 。</span><span class="sxs-lookup"><span data-stu-id="822d9-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![影像 of_page 提示您按一下 [下載套件] 按鈕，將上架腳本複製到您的端點或端點](../../media/mtp-eval-62.png)

7. <span data-ttu-id="822d9-230">在您的端點上，以系統管理員身分執行上架腳本，然後選擇 [Y]。</span><span class="sxs-lookup"><span data-stu-id="822d9-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the 命令列，您可以在其中執行上架腳本，然後選擇 [Y] 繼續](../../media/mtp-eval-63.png)

8. <span data-ttu-id="822d9-232">恭喜，您已架您的第一個端點。</span><span class="sxs-lookup"><span data-stu-id="822d9-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the 命令列，您可以在其中取得您已架第一個端點的確認。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="822d9-235">從 Microsoft Defender ATP 嚮導複製並貼上偵測測試。</span><span class="sxs-lookup"><span data-stu-id="822d9-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![影像 of_the 執行偵測測試步驟，您應該按一下 [複製] 以複製您應該在命令提示字元中貼上的偵測測試腳本。](../../media/mtp-eval-65.png)

10. <span data-ttu-id="822d9-237">將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="822d9-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![影像 of_command 提示，您應該將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它](../../media/mtp-eval-66.png)

11. <span data-ttu-id="822d9-239">從嚮導選取 [ **開始使用 Microsoft DEFENDER ATP** ]。</span><span class="sxs-lookup"><span data-stu-id="822d9-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![在您應該按一下 [開始使用 Microsoft Defender ATP] 的嚮導中 of_the 確認提示](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="822d9-241">流覽 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="822d9-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="822d9-242">移至 [ **設定** ]，然後選取 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![您應選取 [高級功能] 的 [of_Microsoft Defender 安全性中心設定] 功能表中的影像](../../media/mtp-eval-68.png)

13. <span data-ttu-id="822d9-244">開啟與 **Azure 高級威脅防護**的整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced 功能，需要開啟的 Azure 高級威脅防護選項切換功能](../../media/mtp-eval-69.png)

14. <span data-ttu-id="822d9-246">開啟與 **Office 365 威脅情報**的整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features，Office 365 威脅情報選項切換，您必須開啟](../../media/mtp-eval-70.png)

15. <span data-ttu-id="822d9-248">開啟與 **Microsoft Cloud App Security**的整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced 功能，您需要開啟的 Microsoft Cloud App Security 選項切換功能](../../media/mtp-eval-71.png)

16. <span data-ttu-id="822d9-250">向中按向下方，然後按一下 [ **儲存偏好** 設定] 以確認新的整合。</span><span class="sxs-lookup"><span data-stu-id="822d9-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![您需要按一下的影像 of_Save 偏好設定按鈕](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="822d9-252">啟動 Microsoft 威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="822d9-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="822d9-253">從2020年6月1日開始，Microsoft 會自動為所有合格的承租人啟用 Microsoft 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="822d9-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="822d9-254">如需詳細資訊，請參閱此 [Microsoft 技術小組文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。</span><span class="sxs-lookup"><span data-stu-id="822d9-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="822d9-255">移至 [Microsoft 365 Security Center](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="822d9-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="822d9-256">流覽至 [ **設定** ]，然後選取 [ **Microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="822d9-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="822d9-257">Microsoft 365 安全性中心設定頁面中的影像 of_Microsoft 威脅防護選項螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="822d9-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="822d9-258">如需更完整的指導，請參閱 [開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="822d9-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="822d9-259">恭喜！</span><span class="sxs-lookup"><span data-stu-id="822d9-259">Congratulations!</span></span> <span data-ttu-id="822d9-260">您剛剛建立的是 Microsoft 威脅防護試用實驗室或試驗環境！</span><span class="sxs-lookup"><span data-stu-id="822d9-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="822d9-261">現在，您可以熟悉 Microsoft 威脅防護使用者介面！</span><span class="sxs-lookup"><span data-stu-id="822d9-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="822d9-262">查看您可以從下列 Microsoft 威脅防護互動指南中學到的內容，並瞭解如何使用每個儀表板做為日常安全性作業工作。</span><span class="sxs-lookup"><span data-stu-id="822d9-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="822d9-263">接下來，您可以模擬攻擊，並查看「向量積」功能如何偵測、建立提醒，以及自動回應端點上的 fileless 攻擊。</span><span class="sxs-lookup"><span data-stu-id="822d9-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="822d9-264">下一步</span><span class="sxs-lookup"><span data-stu-id="822d9-264">Next step</span></span>
|<span data-ttu-id="822d9-265">![攻擊模擬階段](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="822d9-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="822d9-266">攻擊模擬階段</span><span class="sxs-lookup"><span data-stu-id="822d9-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="822d9-267">針對您的 Microsoft 威脅防護試驗環境執行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="822d9-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
