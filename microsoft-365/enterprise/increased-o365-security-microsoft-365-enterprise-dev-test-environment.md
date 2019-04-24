---
title: 適用於 Microsoft 365 企業版測試環境的增強的 Microsoft 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南來啟用其他 Microsoft 365 安全性設定 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283653"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8394c-103">適用於 Microsoft 365 企業版測試環境的增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="8394c-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8394c-104">透過本文中的指示，您設定其他 Microsoft 365 若要提高安全性，Microsoft 365 企業版測試環境中。</span><span class="sxs-lookup"><span data-stu-id="8394c-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8394c-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="8394c-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8394c-107">階段 1： 建置 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="8394c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8394c-108">如果您只想以具有最小需求的輕量型方式設定增強的 Microsoft 365 安全性，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="8394c-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8394c-109">如果您想要在模擬的企業中設定增強的 Microsoft 365 安全性，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="8394c-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8394c-110">測試增強的 Microsoft 365 安全性不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。</span><span class="sxs-lookup"><span data-stu-id="8394c-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8394c-111">它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="8394c-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="8394c-112">階段 2： 設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="8394c-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="8394c-113">在這個階段，您可以啟用增強的 Microsoft 365 安全性適用於 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="8394c-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="8394c-114">如需詳細資訊及設定，請參閱 < <b0>Configure Office 365 租用戶以提高安全性</b0>。</span><span class="sxs-lookup"><span data-stu-id="8394c-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="8394c-115">設定 SharePoint Online 來封鎖不支援新式驗證的應用程式</span><span class="sxs-lookup"><span data-stu-id="8394c-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="8394c-116">不支援新式驗證的應用程式不能有[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)套用至它們，也就是保護您的 Microsoft 365 訂閱和其數位資產的重要元素。</span><span class="sxs-lookup"><span data-stu-id="8394c-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="8394c-117">移至 Office 入口網站 ([https://office.com](https://office.com)) 並登入 Office 365 試用訂閱以全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="8394c-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="8394c-118">如果您使用輕量級 Microsoft 365 測試環境，從您本機電腦登入。</span><span class="sxs-lookup"><span data-stu-id="8394c-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="8394c-119">如果您使用 Microsoft 365 模擬企業版測試環境，使用[Azure 入口網站](https://portal.azure.com)連線至 CLIENT1 虛擬機器，然後從 CLIENT1 登入。</span><span class="sxs-lookup"><span data-stu-id="8394c-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="8394c-120">從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**系統**]。</span><span class="sxs-lookup"><span data-stu-id="8394c-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="8394c-121">在 [新的**Microsoft 365 系統管理中心**] 索引標籤，按一下 [**系統管理中心 > SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="8394c-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="8394c-122">在 [新的**SharePoint 系統管理中心**] 索引標籤，按一下 [**存取控制**。</span><span class="sxs-lookup"><span data-stu-id="8394c-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="8394c-123">[] 下 **，不支援新式驗證的應用程式**，按一下 [**封鎖**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="8394c-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="8394c-124">啟用進階的威脅防護 for SharePoint、 OneDrive for Business 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8394c-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="8394c-125">Office 365 進階威脅防護 (ATP) 的 SharePoint、 OneDrive 及 Microsoft Teams 會保護您的組織不小心共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="8394c-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="8394c-126">移至[Office 365 安全性 & 合規性中心](https://protection.office.com)，並使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="8394c-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="8394c-127">在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則 > 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="8394c-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="8394c-128">選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**。</span><span class="sxs-lookup"><span data-stu-id="8394c-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="8394c-129">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8394c-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="8394c-130">啟用反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="8394c-130">Enable anti-malware</span></span>

<span data-ttu-id="8394c-131">惡意程式碼是由病毒和間諜軟體組成。</span><span class="sxs-lookup"><span data-stu-id="8394c-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="8394c-132">病毒會感染其他程式和資料，同時會擴散到整個電腦，找尋可攻擊的程式。</span><span class="sxs-lookup"><span data-stu-id="8394c-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="8394c-133">間諜軟體會收集您的個人資訊 (如登入資訊和個人資料)，並將其傳回給惡意程式碼作者。</span><span class="sxs-lookup"><span data-stu-id="8394c-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="8394c-134">Office 365 具有內建的惡意軟體和垃圾郵件篩選功能，可協助防止惡意軟體的輸入及輸出郵件，並協助保護您免於垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8394c-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="8394c-135">如需詳細資訊，請參閱[在 Office 365 中的反垃圾郵件 & 反惡意程式碼保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="8394c-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="8394c-136">若要確保反惡意程式碼處理正在執行常見的附件檔案類型的檔案：</span><span class="sxs-lookup"><span data-stu-id="8394c-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="8394c-137">按一下 [若要返回 [**原則**] 頁面上的瀏覽器的上一頁按鈕。</span><span class="sxs-lookup"><span data-stu-id="8394c-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="8394c-138">按一下 [**反惡意程式碼**]。</span><span class="sxs-lookup"><span data-stu-id="8394c-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="8394c-139">連按兩下 [名為**預設**的原則。</span><span class="sxs-lookup"><span data-stu-id="8394c-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="8394c-140">在**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8394c-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="8394c-141">[**常見的附件類型篩選器**] 中，按一下 [**在 > 儲存**。</span><span class="sxs-lookup"><span data-stu-id="8394c-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="8394c-142">階段 3： 檢查 Office 365 安全性工具和記錄檔</span><span class="sxs-lookup"><span data-stu-id="8394c-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="8394c-143">在這個階段，您查看安全性事件的相關通知您以及測量您的整體安全性狀態的內建服務。</span><span class="sxs-lookup"><span data-stu-id="8394c-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="8394c-144">威脅管理儀表板</span><span class="sxs-lookup"><span data-stu-id="8394c-144">Threat management dashboard</span></span>

<span data-ttu-id="8394c-145">Office 365 威脅管理，可協助您控制和管理行動裝置存取您的組織資料，協助保護組織免於資料遺失，並協助防止惡意軟體和垃圾郵件的輸入及輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="8394c-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="8394c-146">您也會使用威脅保護您的網域信譽，並判斷已遭到惡意詐騙的寄件者的管理帳戶從您的網域。</span><span class="sxs-lookup"><span data-stu-id="8394c-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="8394c-147">如需詳細資訊，請參閱 <<c0>在 Microsoft 365 安全性中心中的威脅管理。</span><span class="sxs-lookup"><span data-stu-id="8394c-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="8394c-148">Office 365 雲端 App 安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="8394c-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="8394c-149">Office 365 雲端 App 安全性，先前稱為 Office 365 進階安全性管理，可讓您建立原則來監視並通知您的 Office 365 訂閱中的可疑活動，讓您進行調查，並採取可能修復動作。</span><span class="sxs-lookup"><span data-stu-id="8394c-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="8394c-150">如需詳細資訊，請參閱[概觀的 Office 365 雲端 App 安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。</span><span class="sxs-lookup"><span data-stu-id="8394c-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="8394c-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8394c-151">Next steps</span></span>

<span data-ttu-id="8394c-152">請參閱[Configure 增加的 Microsoft 365 安全性](infoprotect-configure-increased-security-office-365.md)步驟中的資訊和連結，以在生產環境中設定這些設定的**資訊保護**階段。</span><span class="sxs-lookup"><span data-stu-id="8394c-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="8394c-153">瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="8394c-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8394c-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8394c-154">See also</span></span>

[<span data-ttu-id="8394c-155">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8394c-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8394c-156">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="8394c-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8394c-157">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="8394c-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

