---
title: 步驟 5 - 安全性與相容性考量事項
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解重要的 Windows 和 Office 安全性與相容性考量。
ms.openlocfilehash: 003064f521f1a68c01da9d6a2c9fb19eae7d3eaf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636769"
---
# <a name="step-5-security-and-compliance-considerations"></a><span data-ttu-id="4efb4-103">步驟 5：安全性與相容性考量事項</span><span class="sxs-lookup"><span data-stu-id="4efb4-103">Step 5: Security and Compliance Considerations</span></span>

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><span data-ttu-id="4efb4-104"><strong>步驟 5：安全性與相容性考量事項</strong></span><span class="sxs-lookup"><span data-stu-id="4efb4-104"><strong>Step 5: Security and Compliance Considerations</strong></span></span></p>
<p><span data-ttu-id="4efb4-p101">Windows 10 和 Microsoft 365 Apps 企業版提供全新的方式來保護您的資料、裝置和使用者，並快速偵測及回應威脅。此外，了解如何在轉移到 Windows 10 時處理與磁碟加密、反惡意程式碼應用程式和原則相關的常見問題。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p101">Windows 10 and Microsoft 365 Apps for enterprise provide new ways to protect your data, devices and users and quickly detect and respond to threats. Also, learn how to deal with common problems associated with disk encryption, anti-malware apps and policies when moving to Windows 10.</span></span></p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="4efb4-107">安全性與相容性是我們建議的部署程序轉輪中第五個步驟，說明 Windows 10 和 Microsoft 365 Apps 企業版安全性與相容性考量。</span><span class="sxs-lookup"><span data-stu-id="4efb4-107">Security and Compliance is the fifth step in our recommended deployment process wheel covering Windows 10 and Microsoft 365 Apps for enterprise security and compliance considerations.</span></span> <span data-ttu-id="4efb4-108">若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="4efb4-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="4efb4-109">現在是時候檢閱可在部署 Windows 10 和 Microsoft 365 Apps 企業版時以新的安全性及合規性功能作為目標的選項，以及檢閱在從先前版本的 Windows 和 Office 移轉時的考量及常見阻礙。</span><span class="sxs-lookup"><span data-stu-id="4efb4-109">Now it's time to review options for targeting new security and compliance capabilities as part of your Windows 10 and Microsoft 365 Apps for enterprise deployment, along with the considerations and common blockers when moving from previous versions of Windows and Office.</span></span> <span data-ttu-id="4efb4-110">Windows 10 中許多安全性相關功能都在驅動轉換至較新的平台。</span><span class="sxs-lookup"><span data-stu-id="4efb4-110">Many of the security-related capabilities in Windows 10 alone are driving the shift to the newer platform.</span></span> <span data-ttu-id="4efb4-111">此外，使用 Azure Active Directory 與雲端服務和身分識別選項整合能為您的資料、裝置和使用者帶來新的且持續更新保護的存取。</span><span class="sxs-lookup"><span data-stu-id="4efb4-111">Also, integration with cloud services and identity options using Azure Active Directory brings access to new and continually updated protections for your data, devices and users.</span></span>

## <a name="overcoming-potential-security-related-deployment-blockers"></a><span data-ttu-id="4efb4-112">克服潛在的安全性相關部署封鎖</span><span class="sxs-lookup"><span data-stu-id="4efb4-112">Overcoming Potential Security-Related Deployment Blockers</span></span>

<span data-ttu-id="4efb4-113">在說明當您移至 Windows 10 和 Microsoft 365 Apps 企業版及將這些體驗與雲端連線時可新增的功能之前，讓我們從幾個我們所看到通常可能會中斷部署進度的趨勢開始。</span><span class="sxs-lookup"><span data-stu-id="4efb4-113">Before explaining new capabilities that you can add as you move to Windows 10 and Microsoft 365 Apps for enterprise and connect those experiences to the cloud, let’s start with a few trends we’re seeing that can often interrupt deployment progress.</span></span>

### <a name="disk-encryption"></a><span data-ttu-id="4efb4-114">磁碟加密</span><span class="sxs-lookup"><span data-stu-id="4efb4-114">Disk Encryption</span></span>

<span data-ttu-id="4efb4-p104">您可能會遇到的第一次初始挑戰是硬碟加密。許多硬碟加密解決方案無法輕鬆從舊版的 Windows 升級到較新版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p104">First one of the initial challenges you might encounter is hard disk encryption. Many solutions for hard disk encryption cannot easily be upgraded from a previous version of Windows to a newer version of Windows.</span></span>

<span data-ttu-id="4efb4-p105">在特定版本的平台上使用 ‘/reflectdrivers’ 選項搭配 Windows 安裝程式時，某些磁碟加密解決方案可讓您執行升級，但其他版本可能會要求您在部署之前解密磁碟機，然後在安裝 Windows 10 之後再重新加密。某些解決方案也不允許您使用舊版的 BIOS 從主開機記錄 (MBR) 移動至 UEFI 所需的 GUID 分割表格 (GPT)。這是很重要的，因為 Windows 10 中新的虛擬化為基礎安全性功能需要包含 UEFI 的 64 位元版 Windows 10，這些會說明如下。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p105">Some disk encryption solutions allow you to perform the upgrades when using the ‘/reflectdrivers’ option with Windows Setup on certain versions of their platforms, but others may require you to unencrypt the drive prior to deployment, then re-encrypt after Windows 10 is installed. Some solutions also do not allow you to move from Master Boot Record (MBR), using legacy BIOS, to GUID Partition Table (GPT), required for UEFI. This is important because a 64-bit version of Windows 10 with UEFI is required for the new virtualization-based security capabilities in Windows 10 and those are explained below.</span></span>

<span data-ttu-id="4efb4-p106">解決這些問題的其中一個選項是使用 Windows 10 中的 BitLocker，其包含在 Windows 10 專業版以及更高版本。BitLocker 可讓您暫停作業系統升級保護和功能更新作為程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p106">One option to resolve these issues is using BitLocker in Windows 10, which is included in Windows 10 Pro and higher editions. BitLocker allows you to suspend protection for OS upgrades and Feature Updates as part of the process.</span></span>

<span data-ttu-id="4efb4-122">[Bitlocker 基本部署](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-basic-deployment) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-122">[Bitlocker basic deployment](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)</span></span>

### <a name="antivirus-and-antimalware-application-compatibility"></a><span data-ttu-id="4efb4-123">防毒和反惡意程式碼應用程式相容性</span><span class="sxs-lookup"><span data-stu-id="4efb4-123">Antivirus and Antimalware Application Compatibility</span></span>

<span data-ttu-id="4efb4-p107">第二，儘管我們已看過 Windows 7 與 Windows 10 之間超過 [99% 的 Windows 應用程式的相容](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) (英文)，例外狀況通常就是防毒軟體 (AV) 應用程式或虛擬私人網路 (VPN) 用戶端。這些應用程式通常會實作非標準的開發方式和 API，通常使用未記載的方法來保護您的系統或是將您連線到網路資源。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p107">Second, while we’ve seen that more than [99% of Windows applications are compatible](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) between Windows 7 and Windows 10, the exceptions are often anti-virus (AV) apps or Virtual Private Network (VPN) clients. These applications often implement non-standard development practices and APIs, using often undocumented ways to protect your system or connect you to network resources.</span></span>

<span data-ttu-id="4efb4-p108">如此一來，這些應用程式的本質會在轉換到新版的 Windows 時變得易於變更。如果 AV 或 VPN 軟體無法在 Windows 10 中或在升級之後使用，修正方式通常是將您在使用的應用程式取代為在 Windows 10 上支援及測試的項目。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p108">As a result, these apps by nature can be fragile to changes when shifting to a new version of Windows. If your AV or VPN software doesn’t work in Windows 10 or after upgrading, the fix is typically to replace the app you’re using with something supported and tested on Windows 10.</span></span>

### <a name="security-policies"></a><span data-ttu-id="4efb4-128">安全性原則</span><span class="sxs-lookup"><span data-stu-id="4efb4-128">Security Policies</span></span>

<span data-ttu-id="4efb4-p109">您用於較舊版 Windows 和 Office 的 Active Directory 群組原則設定可能不會直接翻譯為 Windows 10 及 Microsoft 365 Apps 企業版，且較新的安全性與相容性功能會有不同的考量。最好使用 Microsoft 安全性相容性工具組取得最新版 Windows 及 Office 的安全性原則基準。此外，值得一探究竟行動裝置管理原則作為 Microsoft Intune 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p109">Your Active Directory Group Policy settings used for older versions of Windows and Office may not translate directly to Windows 10 and Microsoft 365 Apps for enterprise, and there are different considerations with newer security and compliance capabilities. It’s a good idea to use the Microsoft Security Compliance Toolkit to get a baseline of the security policies for current versions of Windows and Office. Additionally, it’s worth looking into Mobile Device Management policies as part of Microsoft Intune.</span></span>

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a><span data-ttu-id="4efb4-132">Microsoft 365 中新的安全性和相容性功能</span><span class="sxs-lookup"><span data-stu-id="4efb4-132">New Security and Compliance Capabilities in Microsoft 365</span></span>

<span data-ttu-id="4efb4-p110">現在，將您目前保護向前移動有一些考量，以及在您轉變前有些要注意的事項。現在讓我們來看一下從 EMS 和更新版本移至 Windows 10、Microsoft 365 Apps 企業版和雲端選項時，您可以善加利用的新功能。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p110">Now, those were considerations for moving your current protections forward and things to be aware of before your shift. Now let’s take a look at new capabilities that you can take advantage of when moving to Windows 10, Microsoft 365 Apps for enterprise and cloud-based options from EMS and beyond.</span></span>

### <a name="identity-and-access-management"></a><span data-ttu-id="4efb4-135">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="4efb4-135">Identity and Access Management</span></span>

<span data-ttu-id="4efb4-p111">開始進行身分識別與存取管理。Azure Active Directory 是適用於應用程式、裝置和雲端服務的身分識別控制平面，且是連線到 Microsoft 365 及其他雲端服務的現代化方法。條件式存取可讓您根據您的登入位置、您使用的裝置，以及異常行為等來定義不同的驗證需求。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p111">Starting with identity and access management. Azure Active Directory is the identity control plane for apps, devices and Cloud services and is the modern way to connect to Microsoft 365 and other Cloud services. Conditional access allows you to define different authentication requirements based on where you are logging in from, which device you're using, as well as things like anomalous behaviors.</span></span>

<span data-ttu-id="4efb4-p112">在裝置層級，生物識別技術能提供唯一識別項以更輕鬆、更安全地存取您的裝置和應用程式 - 在您移動至排除密碼的目標時。Windows Hello 提供裝置型多重要素驗證。必須仰賴裝置本身、PIN 或唯一的生物識別識別碼，例如您可以透過原則強制執行的臉孔或指紋。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p112">At the device level, biometrics can provide unique identifiers for simpler and more secure access to your devices and apps - as you move toward the goal of eliminating passwords. Windows Hello offers device-based, multi-factor authentication. It relies on the device itself, your PIN, or unique biometric identifier such as your face or fingerprint, which you can enforce via policy.</span></span>

<span data-ttu-id="4efb4-142">[Azure 身分識別管理的基本概念](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-fundamentals) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-142">[Fundamentals of Azure identity management](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-fundamentals)</span></span>

<span data-ttu-id="4efb4-143">[了解 Azure 識別解決方案](https://docs.microsoft.com/azure/active-directory/fundamentals/understand-azure-identity-solutions) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-143">[Understand Azure identity solutions](https://docs.microsoft.com/azure/active-directory/fundamentals/understand-azure-identity-solutions)</span></span>

<span data-ttu-id="4efb4-144">[Azure Active Directory 條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-144">[Azure Active Directory Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)</span></span>

<span data-ttu-id="4efb4-145">[Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-145">[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)</span></span>

### <a name="virtualization-based-security"></a><span data-ttu-id="4efb4-146">虛擬化為基礎的安全性</span><span class="sxs-lookup"><span data-stu-id="4efb4-146">Virtualization-based security</span></span>

<span data-ttu-id="4efb4-p113">現在除了身分識別，您也可以啟用持續保護已知或未知的威脅，為了這麼做，Windows 10 會在核心使用虛擬化為基礎的安全性以確保使用安全開機時的開機完整性以及程式碼完整性。我們也可以協助利用認證保護阻止認證失竊，方法是從 Windows 獨立維護使用者機密資訊。此外，應用程式保護可以找出並降低瀏覽器型威脅，方法是在獨立容器中執行瀏覽器。這所有的技術都是使用 Windows 10 中虛擬化為基礎的安全性，且為無法在 Windows 7 系統上複製的基礎變更 – 請注意，這些也需要 UEFI、64 位元 Windows，及透過 SLAT 的虛擬化延伸支援 – 位於硬體層級。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p113">Now beyond identity, you can also enable continuous protection against both known and unknown threats and to do this Windows 10 uses virtualization-based security at the core to ensure boot integrity and code integrity using Secure Boot. We can help also stop credential theft with Credential Guard by maintaining user secrets in isolation from Windows. And, Application Guard can isolate and mitigate browser-based threats by running the browser in an isolated container. All of these technologies use virtualization-based security in Windows 10 and are foundational changes that cannot be replicated on a Windows 7 system – note that these also require UEFI, 64-bit Windows and virtualization extension support with SLAT – at the hardware level.</span></span>

<span data-ttu-id="4efb4-151">[更多虛擬化為基礎的安全性相關資訊](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-vbs) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-151">[More on Virtualization-based Security](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-vbs)</span></span>

### <a name="security-enhancements-from-cloud-services"></a><span data-ttu-id="4efb4-152">雲端服務中的安全性加強功能</span><span class="sxs-lookup"><span data-stu-id="4efb4-152">Security enhancements from cloud services</span></span>

<span data-ttu-id="4efb4-p114">雲端服務提供另一層的選用防護，以提升 Windows 及 Office 安全性。這些可為您提供新層級的經常即時控制項，可立即偵測、抗拒及回應新的攻擊和攻擊類型 – 特別是相較於傳統軟體更新和 AV 簽章檔案 – 其中的回應與更新部署時間原本就比較慢。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p114">Cloud services provide another layer of optional protection to improve Windows and Office security. These can give you a new level of often real-time control that can instantly detect, resist and respond to new attacks and attack types – especially compared to traditional software updating and AV signature files – where response and update deployment times are inherently slower.</span></span>

<span data-ttu-id="4efb4-p115">透過 Microsoft Intelligent Security Graph，您可以更快速地存取新興威脅的資訊和保護。以下是您可以善加利用的幾個功能，從 Office 開始。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p115">Along with the Microsoft Intelligent Security Graph, you have faster access to both information and protections from emerging threats. Here are a few examples of what you can take advantage of, starting with Office.</span></span>

<span data-ttu-id="4efb4-p116">**[資料外洩防護](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** (英文) 內建於 Microsoft 365 Apps 企業版，可協助在偵測到高風險內容 (例如信用卡或識別碼) 時告知使用者安全性原則。通知使用者後，原則可以通知或封鎖傳送及共用。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p116">**[Data Loss Prevention](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** built into Microsoft 365 Apps for enterprise, helps inform users of security policies when high risk content like credit card or identification numbers are detected. Policies can inform or block sending and sharing after notifying users.</span></span>

<span data-ttu-id="4efb4-p117">**[Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** (英文) 是一種互補服務，可與 Office 搭配使用，讓使用者可輕鬆地分類及將 Office 檔案標籤。它會在標籤的檔案上觸發自動動作，例如加密或鎖定共用。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p117">**[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** is a complementary service that can be used with Office, allowing users to easily classify and label their Office files. It can trigger automatic action on labeled files, such as encryption or locking down sharing.</span></span>

<span data-ttu-id="4efb4-161">我們也已推出跨 Office 應用程式的**[安全連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)** (英文) 保護來保護您免於已知惡意網站的動態清單攻擊。</span><span class="sxs-lookup"><span data-stu-id="4efb4-161">We've also introduced **[Safe Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)** protection across Office apps to protect you against a dynamic list of known malicious websites.</span></span>

<span data-ttu-id="4efb4-p118">此外，Outlook 中及 Exchange Online 所屬的**[安全附件](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)**，會超越電子郵件篩選以檢查附件。如果識別到高風險的附件，安全附件將會通知使用者已知的惡意附件，並從電子郵件中將其移除。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p118">Additionally, **[Safe Attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)** in Outlook and as part of Exchange Online goes beyond email filtering to inspect attachments. If a high-risk attachment is identified, Safe Attachments will inform the user of known malicious attachments and remove them from email.</span></span>

<span data-ttu-id="4efb4-p119">**[Office 365 郵件加密](https://docs.microsoft.com/office365/securitycompliance/encryption)** (OME) (英文) 也可用來保護所傳送的電子郵件和附件，確保只有預定的收件者可以檢視電子郵件內容。OME 與 Google、Yahoo 和 Microsoft 消費者帳戶驗證緊密運作，一次性密碼可讓其他電子郵件服務的使用者也安全地接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p119">**[Office 365 Message Encryption](https://docs.microsoft.com/office365/securitycompliance/encryption)** (OME) can also be used to safeguard email and attachments sent, ensuring only intended recipients can view email content. OME works seamlessly with Google, Yahoo, and Microsoft consumer account authentication, and one-time passcodes allow users of other email services to securely receive email as well.</span></span>

#### <a name="additional-windows-10-protections"></a><span data-ttu-id="4efb4-166">其他 Windows 10 保護</span><span class="sxs-lookup"><span data-stu-id="4efb4-166">Additional Windows 10 protections</span></span>

<span data-ttu-id="4efb4-167">Windows 10 中的 **[Windows Defender 應用程式控制](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** (英文) 會運作 Microsoft 已檢查安全性的核准應用程式允許與拒絕清單，全部都是使用 Microsoft Intune 受端點保護原則管理。</span><span class="sxs-lookup"><span data-stu-id="4efb4-167">**[Windows Defender Application Control](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** in Windows 10 operates off an approved allow and deny list of applications that Microsoft has checked for safety and all that is managed by endpoint protection policies using Microsoft Intune.</span></span>

<span data-ttu-id="4efb4-p120">**[Microsoft Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** (英文) 是一個整合式預防保護、入侵後偵測、自動調查及回應平台。它會保護端點免於網路威脅；偵測進階攻擊與資料入侵、自動化安全性事件，並提高安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p120">**[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** is a unified platform for preventative protection, post-breach detection, automated investigation, and response. It protects endpoints from cyber threats; detects advanced attacks and data breaches, automates security incidents and improves security posture.</span></span>

<span data-ttu-id="4efb4-170">**[利用保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** (英文) 可協助減少執行應用程式的受攻擊面，方法為防止惡意程式碼進入 Windows 及封鎖不受信任的程序存取受保護資料夾。</span><span class="sxs-lookup"><span data-stu-id="4efb4-170">**[Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** helps reduce the attack surface for running applications by preventing malware from getting into Windows and blocking untrusted processes from accessing protected folders.</span></span>

#### <a name="microsoft-intune"></a><span data-ttu-id="4efb4-171">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4efb4-171">Microsoft Intune</span></span>

<span data-ttu-id="4efb4-p121">[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) (英文) 作為行動裝置情況下的雲端式管理服務，包括 IOS、Android 和 Windows 裝置，且現在可以設定為共同管理以加強及擴充 Configuration Manager 所管理特定工作負載的控制項。此處的其中一個優點是，可能需要註冊到裝置管理，裝置才能存取受保護的資源 – 即使未受管理、非網域聯結或非 Azure AD 聯結裝置。您也可以利用作業系統和應用程式層級的細微設定與合規性原則強制執行。應用程式原則與設定可以使用 Microsoft Intune 在 Windows 10 中集中設定和強制執行 Microsoft 365 Apps 企業和 Microsoft Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4efb4-p121">[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) serves as a Cloud based management service for mobile scenarios, including IOS, Android and Windows devices, and can now be configured for co-management to complement and extend controls for specific workloads managed by Configuration Manager. One advantage here is that, devices accessing protected resources can be required to enroll into device management – even non-managed, non-domain joined or non-Azure AD joined devices. You can also take advantage of granular configuration and compliance policy enforcement at the operating system and application level. Application policies and settings can be configured centrally and enforced for Microsoft 365 Apps for enterprise and Store apps in Windows 10 using Microsoft Intune.</span></span>

## <a name="next-step"></a><span data-ttu-id="4efb4-176">下一步</span><span class="sxs-lookup"><span data-stu-id="4efb4-176">Next Step</span></span>

## <a name="step-6-os-deployment-and-feature-updates"></a><span data-ttu-id="4efb4-177">[步驟 6：作業系統部署與功能更新](https://aka.ms/mdd6) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-177">[Step 6: OS Deployment and Feature Updates](https://aka.ms/mdd6)</span></span>

## <a name="previous-step"></a><span data-ttu-id="4efb4-178">上一步</span><span class="sxs-lookup"><span data-stu-id="4efb4-178">Previous Step</span></span> 

## <a name="step-4-user-files-and-settings"></a><span data-ttu-id="4efb4-179">[步驟 4：使用者檔案和設定](https://aka.ms/mdd4) (英文)</span><span class="sxs-lookup"><span data-stu-id="4efb4-179">[Step 4: User Files and Settings](https://aka.ms/mdd4)</span></span>
