---
title: 提高您的 Microsoft 365 for enterprise 測試環境的 Microsoft 365 安全性
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南來啟用 Microsoft 365 for enterprise 測試環境中的其他 Microsoft 365 安全性設定。
ms.openlocfilehash: 7c3300111f5999714b87a176087207a1651cdcaf
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487397"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1425-103">提高您的 Microsoft 365 for enterprise 測試環境的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="d1425-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1425-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="d1425-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d1425-105">透過本文中的指示，您可以設定其他 Microsoft 365 設定，以提升 Microsoft 365 for enterprise 測試環境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="d1425-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d1425-107">按一下[這裡](../downloads/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="d1425-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1425-108">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="d1425-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1425-109">如果您只想以輕量的方式設定增加的 Microsoft 365 安全性，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="d1425-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d1425-110">如果您想要在模擬的企業中設定增加的 Microsoft 365 安全性，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="d1425-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1425-111">測試增加的 Microsoft 365 安全性不需要模擬的企業測試環境，包括連接至網際網路的模擬內部網路和目錄同步處理 (AD DS) 樹系中的 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="d1425-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d1425-112">這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="d1425-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="d1425-113">階段2：設定增加的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="d1425-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="d1425-114">在此階段中，您可以為企業測試環境啟用增強的 Microsoft 365 安全性，以供 Microsoft 365 使用。</span><span class="sxs-lookup"><span data-stu-id="d1425-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="d1425-115">如需詳細資訊和設定，請參閱 [Configure a 租使用者以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="d1425-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="d1425-116">設定線上 SharePoint 封鎖不支援新式驗證的應用程式</span><span class="sxs-lookup"><span data-stu-id="d1425-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="d1425-117">不支援新式驗證的應用程式不能有套用身分 [識別和裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md) 設定，這是保護您的 Microsoft 365 訂閱及其數位資產的重要元素。</span><span class="sxs-lookup"><span data-stu-id="d1425-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="d1425-118">移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) 並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。</span><span class="sxs-lookup"><span data-stu-id="d1425-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="d1425-119">如果您使用的是輕量 Microsoft 365 測試環境，請從您的本機電腦登入。</span><span class="sxs-lookup"><span data-stu-id="d1425-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="d1425-120">如果您使用模擬的企業 Microsoft 365 測試環境，請使用 [Azure 入口網站](https://portal.azure.com) 連線至 CLIENT1 虛擬機器，然後從 CLIENT1 登入。</span><span class="sxs-lookup"><span data-stu-id="d1425-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="d1425-121">在 [新增 **Microsoft 365 系統管理中心** ] 索引標籤的左導覽 **窗格中，** 按一下 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="d1425-122">在 [新增 **SharePoint 系統管理中心** ] 索引標籤上，按一下 [ **原則] > 存取控制**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="d1425-123">按一下 [ **不支援新式驗證的應用程式**]，選取 [ **封鎖存取**]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="d1425-124">為 SharePoint、商務 OneDrive 公司和 Microsoft 團隊啟用高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="d1425-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="d1425-125">Office 365 的高級威脅防護 (SharePoint、OneDrive 和 Microsoft 團隊的 ATP) ，可防止您的組織意外共用惡意檔。</span><span class="sxs-lookup"><span data-stu-id="d1425-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="d1425-126">移至 [安全性 & 合規性中心](https://protection.office.com) ，並以全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="d1425-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="d1425-127">在左功能窗格中的 [ **威脅管理**] 底下，按一下 [ **原則**]，然後按一下 [ **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="d1425-128">在 [ **保護 SharePoint、OneDrive 和 Microsoft 小組中的**檔案] 底下。</span><span class="sxs-lookup"><span data-stu-id="d1425-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="d1425-129">選取 [ **開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP**。</span><span class="sxs-lookup"><span data-stu-id="d1425-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="d1425-130">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d1425-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="d1425-131">啟用反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="d1425-131">Enable anti-malware</span></span>

<span data-ttu-id="d1425-132">惡意程式碼是由病毒和間諜軟體組成。</span><span class="sxs-lookup"><span data-stu-id="d1425-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="d1425-133">病毒會感染其他程式和資料，同時會擴散到整個電腦，找尋可攻擊的程式。</span><span class="sxs-lookup"><span data-stu-id="d1425-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="d1425-134">間諜軟體會收集您的個人資訊 (如登入資訊和個人資料)，並將其傳回給惡意程式碼作者。</span><span class="sxs-lookup"><span data-stu-id="d1425-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="d1425-135">Microsoft 365 具有內建的惡意程式碼和垃圾郵件篩選功能，可協助保護來自惡意軟體的輸入和輸出郵件，並協助您防範垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d1425-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="d1425-136">如需詳細資訊，請參閱 [反垃圾郵件 & 反惡意程式碼保護](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d1425-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="d1425-137">若要確定在具有共同附件檔案類型的檔案上執行反惡意程式碼處理：</span><span class="sxs-lookup"><span data-stu-id="d1425-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="d1425-138">按一下瀏覽器上的 [上一步] 按鈕，以回到 [ **原則** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d1425-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="d1425-139">按一下 [ **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="d1425-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="d1425-140">按兩下名為 **Default**的原則。</span><span class="sxs-lookup"><span data-stu-id="d1425-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="d1425-141">在 [ **反惡意程式碼原則** ] 視窗中，按一下 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="d1425-142">在 [ **一般附件類型篩選**] 底下，選取 [ **開啟**]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="d1425-143">階段3：檢查安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="d1425-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="d1425-144">Microsoft 365 中的威脅管理可協助您控制和管理行動裝置對組織資料的存取、協助保護組織避免資料遺失，以及協助保護輸入和輸出郵件免受惡意軟體和垃圾郵件的攻擊。</span><span class="sxs-lookup"><span data-stu-id="d1425-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="d1425-145">您也可以使用威脅管理來保護您網域的信譽，並判斷寄件者是否從您的網域中有惡意的電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="d1425-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="d1425-146">若要查看安全性儀表板：</span><span class="sxs-lookup"><span data-stu-id="d1425-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="d1425-147">如有需要，請移至 [安全性 & 合規性中心](https://protection.office.com) ，並以全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="d1425-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="d1425-148">在左功能窗格中的 [ **威脅管理**] 底下，按一下 [ **儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="d1425-149">請密切瞭解儀表板上的所有卡片，以熟悉所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d1425-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="d1425-150">如需詳細資訊，請參閱 [安全性儀表板](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="d1425-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="d1425-151">階段4：檢查 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="d1425-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="d1425-152">Microsoft Secure 得分會將您的安全性狀況顯示為數字，這表示您目前的層次相對於您訂閱中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="d1425-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="d1425-153">此外，它還提供您可以採取以提升分數的改進動作清單。</span><span class="sxs-lookup"><span data-stu-id="d1425-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="d1425-154">在您的瀏覽器中建立新的索引標籤，然後移至 [Microsoft 365 的安全性中心](https://security.microsoft.com/)，然後按一下 [ **安全計分**]。</span><span class="sxs-lookup"><span data-stu-id="d1425-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="d1425-155">在 [ **一覽表**  ] 索引標籤上，記下目前的安全分數，以及其與全域平均及訂閱數量相似之授權的比較方式。</span><span class="sxs-lookup"><span data-stu-id="d1425-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="d1425-156">在 [ **改進動作** ] 索引標籤上，通讀您可以採取的動作清單，以提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="d1425-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="d1425-157">如需詳細資訊，請參閱 [Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="d1425-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1425-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d1425-158">Next steps</span></span>

<span data-ttu-id="d1425-159">在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="d1425-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1425-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d1425-160">See also</span></span>

[<span data-ttu-id="d1425-161">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="d1425-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d1425-162">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="d1425-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d1425-163">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="d1425-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
