---
title: Microsoft 365 企業版測試環境之增強的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，讓其他 Office 365 的安全性設定 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866386"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8ba2a-103">Microsoft 365 企業版測試環境之增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="8ba2a-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8ba2a-104">使用本文中的指示，您可以設定以增加安全性 Microsoft 365 企業版測試環境中的其他 Office 365 設定。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8ba2a-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8ba2a-107">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="8ba2a-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8ba2a-108">如果您只想要設定加強的 Office 365 安全性的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8ba2a-109">如果您要設定模擬企業中加強的 Office 365 安全性，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ba2a-p101">測試加強的 Office 365 安全性不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="8ba2a-112">階段 2： 設定較高的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="8ba2a-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="8ba2a-p102">在此階段中，您可以啟用加強的 Office 365 安全性 Microsoft 365 企業版測試環境。如需其他詳細資料及設定，請參閱[設定您的 Office 365 租用戶增加安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="8ba2a-115">設定 SharePoint Online 封鎖不支援經過驗證的應用程式</span><span class="sxs-lookup"><span data-stu-id="8ba2a-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="8ba2a-116">不支援經過驗證的應用程式不能有[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)套用至他們，這是保護您的 Microsoft 365 訂閱和其數位資產的重要元素。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="8ba2a-117">移至 [Office 入口網站 ([https://office.com](https://office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="8ba2a-118">如果您使用輕量級的 Microsoft 365 測試環境，從您的本機電腦登入。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="8ba2a-119">如果您使用模擬的企業的 Microsoft 365 測試環境，使用[Azure 入口網站](https://portal.azure.com)連線到 CLIENT1 虛擬機器，並從 CLIENT1 登入。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="8ba2a-120">從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="8ba2a-121">在 [新**Microsoft 365 系統管理中心**] 索引標籤上按一下 [**系統中心 > SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="8ba2a-122">在 [新增**SharePoint 系統管理中心**] 索引標籤上按一下 [**存取控制**]。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="8ba2a-123">下 **，不支援經過驗證的應用程式**，[**封鎖**，然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="8ba2a-124">啟用 Advanced 威脅保護） for SharePoint、 OneDrive for Business 和 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="8ba2a-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="8ba2a-p103">Office 365 進階威脅保護 (ATP) 是一種功能的 Exchange Online Protection (EOP) 可協助保留惡意程式碼不在您的電子郵件。ATP，與您建立原則在 Exchange 系統管理中心 (EAC) 或安全性及規範中心有助於確保您的使用者存取僅或連結會被識別為不是惡意的電子郵件中的附件。如需詳細資訊，請參閱 ＜[進階的威脅保護安全附件及安全的連結](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="8ba2a-128">在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="8ba2a-129">在 [新**的安全性與規範**] 索引標籤上按一下 [**威脅管理 > 原則**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="8ba2a-130">按一下 [ **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="8ba2a-131">在 [**安全的附件**] 窗格中，選取 [**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**、] 和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="8ba2a-132">啟用反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="8ba2a-132">Enable anti-malware</span></span>

<span data-ttu-id="8ba2a-p104">惡意程式碼是由病毒和間諜軟體所組成。病毒感染其他程式和資料，且其分配整個尋找程式感染的電腦。間諜軟體指的是收集您的個人資訊，例如登入資訊及個人資料，並傳送回惡意程式碼撰寫的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="8ba2a-p105">Office 365 內建的惡意軟體和垃圾郵件篩選功能，協助保護惡意軟體輸入及輸出郵件並協助您免受垃圾郵件。如需詳細資訊，請參閱[Office 365 中的反垃圾郵件與反惡意程式碼保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="8ba2a-138">若要確定反惡意程式碼處理正在執行與一般的附件檔案類型的檔案上：</span><span class="sxs-lookup"><span data-stu-id="8ba2a-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="8ba2a-139">按一下 [在瀏覽器可以回到 [**原則**] 頁面上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="8ba2a-140">按一下 [**反惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="8ba2a-141">按兩下名為**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="8ba2a-142">在 [**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="8ba2a-143">[**公用附件類型篩選器**] 中，按一下 [**上 > 儲存**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="8ba2a-144">階段 3： 檢查 Office 365 的安全性工具和記錄檔</span><span class="sxs-lookup"><span data-stu-id="8ba2a-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="8ba2a-145">在此階段中，您在查看安全性事件的相關通知您及測量整體的安全性狀況的內建服務。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="8ba2a-146">威脅管理儀表板</span><span class="sxs-lookup"><span data-stu-id="8ba2a-146">Threat management dashboard</span></span>

<span data-ttu-id="8ba2a-p106">Office 365 Threat management 可協助您控制和管理您的組織資料的行動裝置存取、 說明從資料遺失保護您的組織及從惡意軟體和垃圾郵件保護輸入及輸出郵件。您也可以使用 threat management 來保護您的網域信譽並決定要惡意詐騙的寄件者從您的網域帳戶。如需詳細資訊，請參閱[威脅中管理 Office 365 的安全性與規範中心](https://docs.microsoft.com/office365/securitycompliance/threat-management)。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="8ba2a-150">若要檢視 Office 365 威脅管理儀表板中使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8ba2a-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="8ba2a-151">在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="8ba2a-152">在 [新**的安全性與規範**] 索引標籤上按一下 [**威脅管理 > 儀表板**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="8ba2a-153">新增**儀表板**] 索引標籤上瀏覽器中，記下惡意程式碼趨勢、 洞察力及儀表板的其他小節。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="8ba2a-154">Office 365 雲端應用程式安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="8ba2a-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="8ba2a-p107">Office 365 雲端應用程式安全性] 先前稱為 「 Office 365 進階安全性管理，可讓您建立的監控和通知您在 Office 365 訂閱中可疑的活動，讓您可以調查並採取可能的原則修復動作。如需詳細資訊，請參閱[概觀 （英文） 的 Office 365 雲端應用程式安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="8ba2a-157">在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="8ba2a-158">在 [新**的安全性與規範**] 索引標籤上按一下 [**提醒 > 進階提醒的管理 > 移至 Office 365 雲端應用程式安全性**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="8ba2a-159">在新的**雲端應用程式安全性**] 索引標籤，記下儀表板檢視與所監視之 Office 365 訂閱中的各種活動的預設原則清單。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="8ba2a-160">按一下 [儀表板] 圖示以查看所追蹤的雲端應用程式安全性活動的摘要。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="8ba2a-161">按一下 [**調查**（眼鏡圖示） 然後**活動記錄檔**以查看最新的登入的清單和其他活動。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="8ba2a-162">安全的分數</span><span class="sxs-lookup"><span data-stu-id="8ba2a-162">Secure Score</span></span>

1. <span data-ttu-id="8ba2a-163">在瀏覽器中建立新的索引標籤，並移至**securescore.office.com**。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="8ba2a-164">在**儀表板] 索引標籤**中，記下您目前的安全分數與佇列中的動作清單以增加您分數。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="8ba2a-165">請參閱 ＜ [Configure 增加 security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)步驟中的資訊及連結在生產環境中設定這些設定的**資訊保護**階段。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8ba2a-166">下一步</span><span class="sxs-lookup"><span data-stu-id="8ba2a-166">Next step</span></span>

<span data-ttu-id="8ba2a-167">探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。</span><span class="sxs-lookup"><span data-stu-id="8ba2a-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ba2a-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8ba2a-168">See also</span></span>

[<span data-ttu-id="8ba2a-169">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8ba2a-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8ba2a-170">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="8ba2a-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8ba2a-171">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="8ba2a-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

