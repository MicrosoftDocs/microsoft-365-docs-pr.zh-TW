---
title: 適用於 Contoso Corporation 之 Microsoft 365 企業版安全性的摘要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用整個 Microsoft 365 企業版的安全性功能。
ms.openlocfilehash: b49312b94aef35afc5febeae0fd4dc71b7c642af
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672679"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="ca040-103">適用於 Contoso Corporation 之 Microsoft 365 企業版安全性的摘要</span><span class="sxs-lookup"><span data-stu-id="ca040-103">Summary of Microsoft 365 Enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="ca040-p101">為了取得 IT 安全性部門對於 Microsoft 365 企業版部署的簽核，必須執行徹底的安全性檢閱。以下是 Contoso 對於雲端的安全性需求：</span><span class="sxs-lookup"><span data-stu-id="ca040-p101">To obtain the sign-off of the deployment of Microsoft 365 Enterprise by the IT security department, a thorough security review was conducted. Here are Contoso's security requirements for the cloud:</span></span>

- <span data-ttu-id="ca040-106">針對存取雲端資源的員工使用最嚴格的驗證方法</span><span class="sxs-lookup"><span data-stu-id="ca040-106">Use the strongest methods of authentication for employee access to cloud resources</span></span>
- <span data-ttu-id="ca040-107">確定電腦和行動裝置連線與存取應用程式均安全無虞。</span><span class="sxs-lookup"><span data-stu-id="ca040-107">Ensure that PCs and mobile devices connect and access applications in secure ways</span></span>
- <span data-ttu-id="ca040-108">保護電腦和電子郵件不受惡意程式碼侵襲</span><span class="sxs-lookup"><span data-stu-id="ca040-108">PCs and email are protected from malware</span></span>
- <span data-ttu-id="ca040-109">雲端式數位資產的權限，定義誰可以存取哪些項目，可以執行哪些動作，以及指定最低權限存取權</span><span class="sxs-lookup"><span data-stu-id="ca040-109">Permissions on cloud-based digital assets define who can access what and what they can do and are designed for least privilege access</span></span>
- <span data-ttu-id="ca040-110">機密和高管制數位資產會經過標示、加密，並且儲存在安全的位置</span><span class="sxs-lookup"><span data-stu-id="ca040-110">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations</span></span>
- <span data-ttu-id="ca040-111">高管制數位資產會以額外加密和權限進行保護</span><span class="sxs-lookup"><span data-stu-id="ca040-111">Highly regulated digital assets are protected with additional encryption and permissions</span></span>
- <span data-ttu-id="ca040-112">IT 安全性人員可以從中央儀表板監視目前安全性狀態，並取得安全性事件通知，以便快速回應及防護</span><span class="sxs-lookup"><span data-stu-id="ca040-112">IT security staff can monitor the current security posture from central dashboards and get notified of security events for quick response and mitigation</span></span>

## <a name="contosos-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="ca040-113">Contoso 進行 Microsoft 365 安全性整備的途徑</span><span class="sxs-lookup"><span data-stu-id="ca040-113">Contoso's path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="ca040-114">Contoso 會使用下列步驟來準備部署 Microsoft 365 企業版的安全性：</span><span class="sxs-lookup"><span data-stu-id="ca040-114">Contoso used the following steps to ready their security for their deployment of Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="ca040-115">受限制的雲端系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="ca040-115">Limited administrator accounts for the cloud</span></span>

   <span data-ttu-id="ca040-116">Contoso 針對現有的 Active Directory Domain Services (AD DS) 系統管理員帳戶進行全面的審查，並設定了一系列專屬的雲端系統管理員帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="ca040-116">Contoso did an extensive review of the existing Active Directory Domain Services (AD DS) administrator accounts and set up a series of dedicated cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="ca040-117">進行資料分類分析並分為三個層級</span><span class="sxs-lookup"><span data-stu-id="ca040-117">Performed data classification analysis into three levels</span></span>

   <span data-ttu-id="ca040-118">Contoso 進行了謹慎的審查，並區分為三個層級，這三個層級可用來判斷 Microsoft 365 企業版功能以保護 Contoso 最重要的資料。</span><span class="sxs-lookup"><span data-stu-id="ca040-118">Contoso performed a careful review and determined the three levels, which was used to determine the Microsoft 365 Enterprise features to protect Contoso's most valuable data.</span></span>

3. <span data-ttu-id="ca040-119">判別各資料層級的存取權、保留期和資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="ca040-119">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="ca040-120">Contoso 會根據資料層級來決定詳細的要求，這些要求將運用於限定未來移至雲端的 IT 工作負載。</span><span class="sxs-lookup"><span data-stu-id="ca040-120">Based on the data levels, Contoso determined detailed requirements, which will be used to qualify future IT workloads being moved to the cloud.</span></span>

<span data-ttu-id="ca040-121">根據安全性最佳做法和 Microsoft 365 企業版部署需求，Contoso 的安全性管理員和 IT 部門已部署許多安全性功能，如下列章節所述。</span><span class="sxs-lookup"><span data-stu-id="ca040-121">In accordance with security best practices and Microsoft 365 Enterprise deployment requirements, Contoso's security administrators and IT department have deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity--access-management"></a><span data-ttu-id="ca040-122">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="ca040-122">Identity & access management</span></span> 

- <span data-ttu-id="ca040-123">專用的全域管理員帳戶 (具有 MFA 和 PIM)</span><span class="sxs-lookup"><span data-stu-id="ca040-123">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="ca040-124">Contoso 並非將全域管理角色指派給每日使用者帳戶，而是建立三個、專屬的全域管理員帳戶，具有強式密碼，並且以 Azure 多重要素驗證 (MFA) 和 Azure Active Directory (Azure AD) Privileged Identity Management (PIM) 加以保護。</span><span class="sxs-lookup"><span data-stu-id="ca040-124">Rather than assign the global admin role to everyday user accounts, Contoso created three, dedicated global administrator accounts with strong passwords and protected them with Azure Multi-Factor Authentication (MFA) and Azure Active Directory (Azure AD) Privileged Identity Management (PIM).</span></span> <span data-ttu-id="ca040-125">PIM 僅在 Microsoft 365 企業版 E5 中提供。</span><span class="sxs-lookup"><span data-stu-id="ca040-125">PIM is only available with Microsoft 365 Enterprise E5.</span></span>

  <span data-ttu-id="ca040-126">使用全域管理員帳戶登入只能執行特定系統管理工作，只有指定的人員才知道密碼，且只能在使用 Azure AD PIM 設定的時間內使用。</span><span class="sxs-lookup"><span data-stu-id="ca040-126">Signing in with a global administrator account is only done for specific administrative tasks, the passwords are only known to designated staff, and can only be used within the time configured with Azure AD PIM.</span></span> 

  <span data-ttu-id="ca040-127">Contoso 的安全性管理員相較於該 IT 人員作業功能和責任的適當帳戶，獲指派較少的管理角色。</span><span class="sxs-lookup"><span data-stu-id="ca040-127">Contoso's security administrators have assigned lesser admin roles to accounts that are appropriate to that IT person's job function and responsibility.</span></span>

  <span data-ttu-id="ca040-128">如需詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ca040-128">For more information, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="ca040-129">適用於所有使用者帳戶的 MFA</span><span class="sxs-lookup"><span data-stu-id="ca040-129">MFA for all user accounts</span></span>

  <span data-ttu-id="ca040-p103">MFA 會藉由要求使用者在正確輸入其密碼之後，確認電話來電、簡訊或智慧型手機上的應用程式通知，為登入程序新增多一層的保護。使用 MFA，Azure AD 使用者帳戶就會受保護，即使帳戶密碼遭到洩漏，也能防止未獲授權的登入。</span><span class="sxs-lookup"><span data-stu-id="ca040-p103">MFA adds an additional layer of protection to the sign-in process by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA, Azure AD user accounts are protected against unauthorized sign-in even if an account password is compromised.</span></span>

   - <span data-ttu-id="ca040-132">為了防護 Microsoft 365 訂閱遭入侵，Contoso 在所有全域管理員帳戶上都需要 MFA。</span><span class="sxs-lookup"><span data-stu-id="ca040-132">To protect against a compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="ca040-133">為了防範網路釣魚攻擊，在此類攻擊中攻擊者會入侵組織中受信任人員的認證，並且傳送惡意電子郵件，Contoso 在所有使用者帳戶上啟用了 MFA，包括經理和決策階層。</span><span class="sxs-lookup"><span data-stu-id="ca040-133">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including managers and executives.</span></span> 

- <span data-ttu-id="ca040-134">使用條件式存取原則獲得更安全的裝置和應用程式存取</span><span class="sxs-lookup"><span data-stu-id="ca040-134">Safer device and application access with Conditional Access policies</span></span>

  <span data-ttu-id="ca040-p104">Contoso 針對身分識別、裝置、Exchange Online 和 SharePoint 使用[條件式存取原則](microsoft-365-policies-configurations.md)。身分識別條件式存取原則包含針對高風險使用者要求密碼變更，並且阻止用戶端使用未支援新式驗證的應用程式。裝置存取原則包含已核准應用程式的定義，會要求相容的電腦和行動裝置。Exchange Online 條件式存取原則包含封鎖 ActiveSync 用戶端並設定 Office 365 訊息加密。SharePoint 條件式存取原則包含機密和高管制網站的額外保護。</span><span class="sxs-lookup"><span data-stu-id="ca040-p104">Contoso is using [Conditional Access policies](microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint. Identity Conditional Access policies include requiring password changes for high-risk users and blocking clients from using apps that don’t support modern authentication. Device policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online Conditional Access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Conditional Access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="ca040-140">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="ca040-140">Windows Hello for Business</span></span>

  <span data-ttu-id="ca040-141">Contoso 已部署並要求 [Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)，最終會在執行Windows 10 企業版的電腦和行動裝置上使用雙因素驗證，消除密碼的需求。</span><span class="sxs-lookup"><span data-stu-id="ca040-141">Contoso has deployed and requires [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords with strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="ca040-142">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="ca040-142">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="ca040-143">為了封鎖在作業系統上使用系統管理權限執行的已設定目標攻擊和惡意程式碼，Contoso 已透過 AD DS 群組原則啟用 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)。</span><span class="sxs-lookup"><span data-stu-id="ca040-143">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso has enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through AD DS group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="ca040-144">威脅防護</span><span class="sxs-lookup"><span data-stu-id="ca040-144">Threat protection</span></span>

- <span data-ttu-id="ca040-145">使用 Windows Defender 防毒軟體防護惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="ca040-145">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="ca040-146">Contoso 使用 [Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)，針對執行 Windows 10 企業版的電腦和裝置執行惡意程式碼防護和反惡意程式碼管理。</span><span class="sxs-lookup"><span data-stu-id="ca040-146">Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="ca040-147">使用 Office 365 進階威脅防護來保護電子郵件流程和信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="ca040-147">Secure email flow and mailbox audit logging with Office 365 Advanced Threat Protection</span></span> 

  <span data-ttu-id="ca040-148">Contoso 使用 Exchange Online Protection 和 [Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)，來防護未知惡意程式碼、病毒及透過電子郵件傳輸的惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="ca040-148">Contoso is using Exchange Online Protection and [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span> 

  <span data-ttu-id="ca040-149">Contoso 也已啟用信箱稽核記錄，判斷誰已登入使用者信箱、傳送訊息，以及由信箱擁有者、委派使用者或系統管理員執行的其他活動。</span><span class="sxs-lookup"><span data-stu-id="ca040-149">Contoso has also enabled mailbox audit logging to determine who has logged into user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="ca040-150">使用 Office 365 威脅調查及回應來進行攻擊監視和防護</span><span class="sxs-lookup"><span data-stu-id="ca040-150">Attack monitoring and prevention with Office 365 threat investigation and response</span></span>

  <span data-ttu-id="ca040-151">Contoso 使用 [Office 365 威脅調查及回應](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)，讓識別和解決攻擊以及防範未來的攻擊變得簡單，藉此來保護其 Office 365 使用者。</span><span class="sxs-lookup"><span data-stu-id="ca040-151">Contoso uses [Office 365 threat investigation and response](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect their Office 365 users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="ca040-152">使用 Advanced Threat Analytics 來防護縝密的攻擊</span><span class="sxs-lookup"><span data-stu-id="ca040-152">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="ca040-p105">Contoso 使用 [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata)，來保護自身免於進階設定目標的攻擊。ATA 會自動分析、學習及識別正常和異常實體 (使用者、裝置及資源) 行為。</span><span class="sxs-lookup"><span data-stu-id="ca040-p105">Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span> 

## <a name="information-protection"></a><span data-ttu-id="ca040-155">資訊保護</span><span class="sxs-lookup"><span data-stu-id="ca040-155">Information protection</span></span>

- <span data-ttu-id="ca040-156">使用 Azure 資訊保護標籤來保護機密和高管制數位資產</span><span class="sxs-lookup"><span data-stu-id="ca040-156">Protect sensitive and highly regulated digital assets with Azure Information Protection labels</span></span>

  <span data-ttu-id="ca040-p106">Contoso 決定三個層級的資料保護，並且部署 [Office 365 敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)，讓使用者套用至數位資產。針對其營業秘密和其他智慧財產權，Contoso 使用敏感度子標籤高度管制資料，該資料會對內容進行加密並限制對特定使用者帳戶和群組的存取。</span><span class="sxs-lookup"><span data-stu-id="ca040-p106">Contoso determined three levels of data protection and deployed [Office 365 sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) that users apply to digital assets. For its trade secrets and other intellectual property, Contoso uses sensitivity sublabels highly regulated data that encrypts content and restricts access to specific user accounts and groups.</span></span>

- <span data-ttu-id="ca040-159">使用 Office 365 資料外洩防護來防止內部網路資料外洩</span><span class="sxs-lookup"><span data-stu-id="ca040-159">Prevent intranet data leaks with Office 365 Data Loss Prevention</span></span>

  <span data-ttu-id="ca040-160">Contoso 已針對 Exchange Online、SharePoint 和商務用 OneDrive 設定[資料外洩防護](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)原則，以防止使用者意外或故意共用機密資料。</span><span class="sxs-lookup"><span data-stu-id="ca040-160">Contoso has configured [Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="ca040-161">使用 Windows 資訊保護來防止裝置資料外洩</span><span class="sxs-lookup"><span data-stu-id="ca040-161">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="ca040-162">Contoso 使用 [Windows 資訊保護 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)，來防護下列形式的資料外洩：透過網際網路型應用程式和服務、企業應用程式、企業所擁有裝置上的資料，以及員工帶到職場的個人裝置。</span><span class="sxs-lookup"><span data-stu-id="ca040-162">Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through Internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="ca040-163">使用 Microsoft Cloud App Security 來進行雲端監視</span><span class="sxs-lookup"><span data-stu-id="ca040-163">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="ca040-164">Contoso 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)，來對應其雲端環境、監視其使用量，以及偵測安全性事件。</span><span class="sxs-lookup"><span data-stu-id="ca040-164">Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> <span data-ttu-id="ca040-165">Microsoft Cloud App Security 僅在 Microsoft 365 企業版 E5 中提供。</span><span class="sxs-lookup"><span data-stu-id="ca040-165">Microsoft Cloud App Security is only available with Microsoft 365 Enterprise E5.</span></span>

- <span data-ttu-id="ca040-166">使用 Microsoft Intune 來進行裝置管理</span><span class="sxs-lookup"><span data-stu-id="ca040-166">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="ca040-p108">Contoso 使用 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) 來註冊、管理及設定對於行動裝置及在其上執行之應用程式的存取權。裝置型條件式存取原則也會要求核准的應用程式和相容的電腦和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="ca040-p108">Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based Conditional Access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="ca040-169">安全性管理</span><span class="sxs-lookup"><span data-stu-id="ca040-169">Security management</span></span>

- <span data-ttu-id="ca040-170">具有 Azure 資訊安全中心的 IT 中央安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="ca040-170">Central security dashboard for IT with Azure Security Center</span></span>

  <span data-ttu-id="ca040-171">Contoso 使用 [Azure 資訊安全中心](https://azure.microsoft.com/services/security-center/)以取得安全性和威脅保護的整合檢視，來管理工作負載之間的安全性原則，以及回應網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="ca040-171">Contoso uses the [Azure Security Center](https://azure.microsoft.com/services/security-center/) for a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="ca040-172">適用於具有 Windows Defender 資訊安全中心之使用者的中央安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="ca040-172">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="ca040-173">Contoso 已將 [Windows 安全性應用程式](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 部署至其執行 Windows 10 企業版的電腦和裝置，讓使用者可以一眼瀏覽其安全性狀態並採取動作。</span><span class="sxs-lookup"><span data-stu-id="ca040-173">Contoso has deployed the [Windows Security app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>


## <a name="next-step"></a><span data-ttu-id="ca040-174">下一步</span><span class="sxs-lookup"><span data-stu-id="ca040-174">Next step</span></span>

<span data-ttu-id="ca040-175">[了解](contoso-sharepoint-online-site-for-highly-confidential-assets.md) Contoso 如何建立用於高管制資料的 Sharepoint 網站，使其研究小組之間能夠共同作業。</span><span class="sxs-lookup"><span data-stu-id="ca040-175">[Learn](contoso-sharepoint-online-site-for-highly-confidential-assets.md) how Contoso created a SharePoint site for highly regulated data to enable collaboration among its research teams.</span></span>

