---
title: 設定試用實驗室環境的 Microsoft 威脅防護支柱
description: 針對您的試用實驗室環境設定 Microsoft 威脅防護支柱、Office 365 ATP、Azure ATP、Microsoft Cloud App 安全性和 Microsoft Defender ATP
keywords: 設定 Microsoft 威脅防護試用版 Microsoft 威脅防護試用設定，設定 Microsoft 威脅防護支柱，Microsoft 威脅防護支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049506"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="6ea3f-104">設定試用實驗室環境的 Microsoft 威脅防護支柱</span><span class="sxs-lookup"><span data-stu-id="6ea3f-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="6ea3f-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6ea3f-105">**Applies to:**</span></span>
- <span data-ttu-id="6ea3f-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="6ea3f-107">建立 Microsoft 威脅防護試用實驗室環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="6ea3f-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="準備您的 Microsoft 威脅防護試用實驗室環境" />
      <br/><span data-ttu-id="6ea3f-109">階段1：準備</a></span><span class="sxs-lookup"><span data-stu-id="6ea3f-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="設定您的 Microsoft 威脅防護試用實驗室環境" />
      <br/><span data-ttu-id="6ea3f-111">階段2：設定</a></span><span class="sxs-lookup"><span data-stu-id="6ea3f-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="針對您的 Microsoft 威脅防護試用實驗室環境和板載端點設定每個 Microsoft 威脅防護 pillar" />
      <br/><span data-ttu-id="6ea3f-113">階段3：設定板載 &</a></span><span class="sxs-lookup"><span data-stu-id="6ea3f-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="6ea3f-114">您目前在設定階段。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="6ea3f-115">準備工作是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="6ea3f-116">在本文中，您將指導您準備部署 Microsoft Defender ATP 時所需考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="6ea3f-117">Microsoft 威脅防護的支柱</span><span class="sxs-lookup"><span data-stu-id="6ea3f-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="6ea3f-118">Microsoft 威脅防護包含四個支柱。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="6ea3f-119">雖然一個 pillar 可以為您的網路組織的安全性提供價值，但是啟用四個 Microsoft 威脅防護的分項會使組織發揮最大的價值。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![影像 of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="6ea3f-121">本節會引導您設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="6ea3f-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="6ea3f-122">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="6ea3f-123">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="6ea3f-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ea3f-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="6ea3f-125">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="6ea3f-126">設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="6ea3f-127">如果您已啟用 Office 365 的高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="6ea3f-128">有一個稱為*Office 365 Advanced 威脅防護*的 PowerShell 模組，建議的設定分析器（ORCA）可協助判斷部分設定。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="6ea3f-129">當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="6ea3f-130">您可以從https://www.powershellgallery.com/packages/ORCA/下載此模組。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="6ea3f-131">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage) > **威脅管理** > **原則**。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="6ea3f-132">![影像 of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="6ea3f-133">按一下 [ **ATP 反網路釣魚**]，選取 [**建立**並填入原則名稱和描述]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="6ea3f-134">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-134">Click **Next**.</span></span>
<span data-ttu-id="6ea3f-135">![影像 of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="6ea3f-136">編輯您的高級 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="6ea3f-137">將**高級網路釣魚閥值**變更為**2-嚴格**。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="6ea3f-138">按一下 [**新增條件**] 下拉式功能表，然後選取您的網域做為收件者網域。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="6ea3f-139">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-139">Click **Next**.</span></span>
<span data-ttu-id="6ea3f-140">![影像 of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="6ea3f-141">請複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-141">Review your settings.</span></span> <span data-ttu-id="6ea3f-142">按一下 [**建立這個原則**] 以確認。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="6ea3f-143">![影像 of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="6ea3f-144">選取 [ **ATP 安全附件**]，然後選取 [**開啟 SharePoint]、[OneDrive] 和 [Microsoft 小組**] 選項的 atp。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="6ea3f-145">![影像 of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="6ea3f-146">按一下 [+] 圖示，以建立新的安全附件原則，並將其套用為網域的收件者網域。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="6ea3f-147">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-147">Click **Save**.</span></span>
<span data-ttu-id="6ea3f-148">![影像 of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="6ea3f-149">接下來，選取 [ **ATP 安全連結**原則]，然後按一下鉛筆圖示以編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="6ea3f-150">請確定未選取 [**不要在使用者按一下安全連結時進行追蹤**] 選項，而會選取其餘的選項。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="6ea3f-151">如需詳細資訊，請參閱[安全連結設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="6ea3f-152">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-152">Click **Save**.</span></span> 
<span data-ttu-id="6ea3f-153">![影像 of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="6ea3f-154">接下來選取**反惡意**代碼原則，選取預設值，然後選擇 [鉛筆] 圖示。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="6ea3f-155">按一下 [**設定**]，然後選取 **[是] 並使用預設通知文字**，以啟用**惡意程式碼偵測回應**。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="6ea3f-156">開啟**通用附件類型 Filter** 。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="6ea3f-157">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-157">Click **Save**.</span></span>
<br><span data-ttu-id="6ea3f-158">![影像 of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="6ea3f-159">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage) > **搜尋** > **審核記錄檔搜尋**，然後開啟審計。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="6ea3f-160">![影像 of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="6ea3f-161">將 Office 365 ATP 與 Microsoft Defender ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="6ea3f-162">流覽至[Office 365 Security & 合規性中心](https://protection.office.com/homepage) > **威脅管理** > **瀏覽器**，然後選取螢幕右上角的 [ **WDATP 設定**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="6ea3f-163">在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="6ea3f-164">![影像 of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="6ea3f-165">設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="6ea3f-166">如果您已啟用 Azure 高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="6ea3f-167">流覽至[Microsoft 365 Security Center](https://security.microsoft.com/info) > 選取**其他資源** > **Azure 高級威脅防護**。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="6ea3f-168">![影像 of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="6ea3f-169">按一下 [**建立**]，啟動 Azure 高級威脅防護嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="6ea3f-170">![影像 of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="6ea3f-171">選擇 [**提供使用者名稱和密碼] 以連線至您的 Active Directory 樹**系。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="6ea3f-172">![影像 of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="6ea3f-173">輸入您的 Active Directory 內部部署認證。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="6ea3f-174">這可以是具有 Active Directory 讀取權限的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="6ea3f-175">![影像 of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="6ea3f-176">接下來，選擇 [將**感應器安裝**和傳輸檔案下載到您的網域控制站]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="6ea3f-177">![影像 of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="6ea3f-178">執行 Azure ATP 感應器設定，然後開始遵循嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="6ea3f-179">![影像 of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="6ea3f-180">在感應器部署類型中按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="6ea3f-181">![影像 of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="6ea3f-182">複製存取機碼，您必須在嚮導中輸入它的下一步。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="6ea3f-183">![影像 of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="6ea3f-184">將存取機碼複製到嚮導，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="6ea3f-185">![影像 of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="6ea3f-186">恭喜，您已在您的網域控制站上成功設定 Azure 高級威脅防護。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="6ea3f-187">![影像 of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="6ea3f-188">在 [ [Azure AZURE ATP](https://go.microsoft.com/fwlink/?linkid=2040449)設定] 區段中，選取 [ **Windows Defender atp**]，然後開啟 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="6ea3f-189">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-189">Click **Save**.</span></span> 
<span data-ttu-id="6ea3f-190">![影像 of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="6ea3f-191">Windows Defender ATP 已 rebranded 為 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="6ea3f-192">所有的入口網站上的 ..org 變更都會針對一致性加以匯總。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="6ea3f-193">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ea3f-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="6ea3f-194">如果您已啟用 Microsoft Cloud App 安全性，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="6ea3f-195">流覽至 microsoft**Cloud App security**的[microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > 。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="6ea3f-196">![影像 of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="6ea3f-197">在資訊提示中，整合 Azure ATP，選取 [**啟用 AZURE atp 資料整合**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="6ea3f-198">![影像 of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="6ea3f-199">如果您未看到此提示，這可能表示您的 Azure ATP 資料整合已經啟用。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="6ea3f-200">不過，如果您不確定，請與您的 IT 系統管理員聯繫以確認。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="6ea3f-201">移至 [**設定**]，然後開啟**Azure ATP 整合**切換開啟，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="6ea3f-202">![影像 of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="6ea3f-203">針對新的 Azure ATP 實例，此整合切換功能會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="6ea3f-204">在您繼續下一個步驟之前，請確認您的 Azure ATP 整合已啟用。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="6ea3f-205">在 [雲端探索設定] 底下，選取 [ **Microsoft DEFENDER ATP 整合**]，然後啟用整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="6ea3f-206">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-206">Click **Save**.</span></span>
<span data-ttu-id="6ea3f-207">![影像 of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="6ea3f-208">在 [雲端探索設定] 底下，選取 [**使用者豐富**]，然後啟用與 Azure Active Directory 的整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="6ea3f-209">![影像 of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="6ea3f-210">設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="6ea3f-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="6ea3f-211">如果您已啟用 Microsoft Defender 高級威脅防護，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="6ea3f-212">流覽至 microsoft**Defender security center**的[microsoft 365 Security center](https://security.microsoft.com/info) > **More Resources** > 。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="6ea3f-213">按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-213">Click **Open**.</span></span>
<br><span data-ttu-id="6ea3f-214">![影像 of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="6ea3f-215">遵循 Microsoft Defender 高級威脅防護嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="6ea3f-216">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-216">Click **Next**.</span></span> 
<br><span data-ttu-id="6ea3f-217">![影像 of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="6ea3f-218">選擇 [根據您慣用的資料儲存位置]、[資料保留原則]、[組織大小] 和 [加入宣告預覽] 功能。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="6ea3f-219">![影像 of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="6ea3f-220">您無法變更某些設定，例如，以後的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="6ea3f-221">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-221">Click **Next**.</span></span> 

4. <span data-ttu-id="6ea3f-222">按一下 [**繼續**]，它會布建您的 MICROSOFT Defender ATP 租使用者。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="6ea3f-223">![影像 of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="6ea3f-224">透過「群組原則」、「Microsoft 端點管理員」或執行本機腳本至 Microsoft Defender ATP，將您的端點上架在一起。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="6ea3f-225">為了簡便起見，本指南使用本機腳本。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="6ea3f-226">按一下 [**下載套件**]，然後將上架腳本複製到您的端點。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="6ea3f-227">![影像 of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="6ea3f-228">在您的端點上，以系統管理員身分執行上架腳本，然後選擇 [Y]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="6ea3f-229">![影像 of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="6ea3f-230">恭喜，您已架您的第一個端點。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![影像 of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="6ea3f-232">從 Microsoft Defender ATP 嚮導複製並貼上偵測測試。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="6ea3f-233">![影像 of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="6ea3f-234">將 PowerShell 腳本複製到提升許可權的命令提示字元，然後執行它。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="6ea3f-235">![影像 of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="6ea3f-236">從嚮導選取 [**開始使用 Microsoft DEFENDER ATP** ]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="6ea3f-237">![影像 of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="6ea3f-238">流覽[Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="6ea3f-239">移至 [**設定**]，然後選取 [**高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="6ea3f-240">![影像 of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="6ea3f-241">開啟與**Azure 高級威脅防護**的整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="6ea3f-242">![影像 of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="6ea3f-243">開啟與**Office 365 威脅情報**的整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="6ea3f-244">![影像 of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="6ea3f-245">開啟與**Microsoft Cloud App Security**的整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="6ea3f-246">![影像 of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="6ea3f-247">向中按向下方，然後按一下 [**儲存偏好**設定] 以確認新的整合。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="6ea3f-248">![影像 of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="6ea3f-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="6ea3f-249">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6ea3f-249">Next steps</span></span>
<span data-ttu-id="6ea3f-250">[開啟 Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service)，然後[產生測試警示](generate-test-alert.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3f-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
