---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866744"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="6f4e0-103">Microsoft 受管理電腦中的安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="6f4e0-p101">藉由使用許多 Microsoft 技術，我們可以確保 Microsoft 受管理的桌上型電腦裝置是安全與 Microsoft 受管理的桌上型電腦安全性 ops 小組可防止、 偵測、 及回應進階的威脅。不允許使用協力廠商安全性產品、 應用程式] 及服務。Microsoft 將會套用標準原則比較基準以確保裝置、 身分識別、 網路與公司資料安全，並且保護。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p101">By using many Microsoft technologies, we can ensure that Microsoft Managed Desktop devices are secure and that the Microsoft Managed Desktop security ops team can prevent, detect, and respond to advanced threats. Third-party security products, apps, and services are not allowed. Microsoft will apply a standard policy baseline to ensure devices, identity, network, and corporate data are secured and protected.</span></span>

<span data-ttu-id="6f4e0-107">下列各節中記載的安全性保護這些類別：</span><span class="sxs-lookup"><span data-stu-id="6f4e0-107">These categories of security enforcement are documented in the following sections:</span></span>

- <span data-ttu-id="6f4e0-108">[資料安全性](#data-security)-我們要如何確保您的資料會儲存並符合的 Azure 安全性位置需求</span><span class="sxs-lookup"><span data-stu-id="6f4e0-108">[Data security](#data-security) - how we ensure your data is stored and meets requirements for Azure security positioning</span></span>
- <span data-ttu-id="6f4e0-109">[裝置安全性](#device-security)– 我們要如何確保 Microsoft 受管理的桌上型電腦裝置的安全</span><span class="sxs-lookup"><span data-stu-id="6f4e0-109">[Device security](#device-security) – how we ensure Microsoft Managed Desktop devices are secure</span></span>
- <span data-ttu-id="6f4e0-110">[身分識別安全性](#identity-security)– 我們要如何確保現代工作週年中的使用者不會危害</span><span class="sxs-lookup"><span data-stu-id="6f4e0-110">[Identity security](#identity-security) – how we ensure users in the modern workplace are not compromised</span></span>
- <span data-ttu-id="6f4e0-111">[網路安全性](#network-security)– 我們要如何確保安全存取公司資源</span><span class="sxs-lookup"><span data-stu-id="6f4e0-111">[Network security](#network-security) – how we ensure a secure access to corporate resources</span></span>
- <span data-ttu-id="6f4e0-112">[資訊安全性](#information-security)– 我們要如何確保公司資料是安全</span><span class="sxs-lookup"><span data-stu-id="6f4e0-112">[Information security](#information-security) – how we ensure corporate data is secure</span></span>
- <span data-ttu-id="6f4e0-113">[使用權限的帳戶存取](#privileged-account-access)-我們如何限制存取</span><span class="sxs-lookup"><span data-stu-id="6f4e0-113">[Privileged account access](#privileged-account-access) - how we restrict access</span></span>

## <a name="data-security"></a><span data-ttu-id="6f4e0-114">資料安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-114">Data security</span></span>

<span data-ttu-id="6f4e0-p102">從您的租用戶傳輸的資料會儲存在 Azure SQL 資料庫裝載於 USA Microsoft 租用戶中。將資料儲存，並符合需求 Azure 安全性位置。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p102">Data transmitted from your tenant is stored in Azure SQL databases in the Microsoft tenant hosted in the USA. Your data is stored and meets requirements for Azure security positioning.</span></span> 

<span data-ttu-id="6f4e0-117">如需詳細資訊，請參閱[Microsoft Azure 安全性](https://www.microsoft.com/TrustCenter/Security/azure-security)。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-117">For more information, see [Microsoft Azure security](https://www.microsoft.com/TrustCenter/Security/azure-security).</span></span>

<span data-ttu-id="6f4e0-118">這份清單摘要說明 Microsoft 和您的租用戶之間傳輸資料的類型。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-118">This list summarizes the types of data transmitted between Microsoft and your tenant.</span></span> 

- <span data-ttu-id="6f4e0-119">從 Microsoft 租用戶</span><span class="sxs-lookup"><span data-stu-id="6f4e0-119">From Microsoft to your tenant</span></span>
    - <span data-ttu-id="6f4e0-120">群組名稱</span><span class="sxs-lookup"><span data-stu-id="6f4e0-120">Group names</span></span>
    - <span data-ttu-id="6f4e0-121">安全性原則設定</span><span class="sxs-lookup"><span data-stu-id="6f4e0-121">Security policy configuration</span></span>
    - <span data-ttu-id="6f4e0-122">裝置訂單</span><span class="sxs-lookup"><span data-stu-id="6f4e0-122">Device orders</span></span>
    - <span data-ttu-id="6f4e0-123">使用者帳戶 （msadmin、 mstest Microsoft 受管理的 Desktop_soc_ro、 Microsoft 受管理的 Desktop_wdgsoc）</span><span class="sxs-lookup"><span data-stu-id="6f4e0-123">User accounts (msadmin, mstest, Microsoft Managed Desktop_soc_ro, Microsoft Managed Desktop_wdgsoc)</span></span>
    - <span data-ttu-id="6f4e0-124">E5 授權指派給上述 4 位使用者</span><span class="sxs-lookup"><span data-stu-id="6f4e0-124">E5 License assignment to the above 4 users</span></span>
    - <span data-ttu-id="6f4e0-125">Windows 更新更新鈴響的原則</span><span class="sxs-lookup"><span data-stu-id="6f4e0-125">Windows update policies for update rings</span></span>
    - <span data-ttu-id="6f4e0-126">未來，進一步功能將會被開發以供其他類型的組態內容包括應用程式、 原則與設定的張貼。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-126">In the future, further capabilities will be developed to allow for posting of other types of configuration content including apps, policies, and settings.</span></span>
- <span data-ttu-id="6f4e0-127">從您的租用戶給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="6f4e0-127">From your tenant to Microsoft</span></span>
    - <span data-ttu-id="6f4e0-128">裝置更新、 使用量及可靠性資料</span><span class="sxs-lookup"><span data-stu-id="6f4e0-128">Device update, usage and reliability data</span></span>
    - <span data-ttu-id="6f4e0-129">應用程式部署及可靠性資料</span><span class="sxs-lookup"><span data-stu-id="6f4e0-129">App deployment and reliability data</span></span>
    - <span data-ttu-id="6f4e0-130">更新與安全性原則部署資料</span><span class="sxs-lookup"><span data-stu-id="6f4e0-130">Update and security policy deployment data</span></span>
    - <span data-ttu-id="6f4e0-131">指派給裝置的使用者</span><span class="sxs-lookup"><span data-stu-id="6f4e0-131">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="6f4e0-132">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-132">Device security</span></span>

<span data-ttu-id="6f4e0-p103">若要防止安全性缺口，務必確定所有的 Microsoft 受管理的桌上型電腦裝置正常且安全。同樣也請務必以確保我們可以偵測狀況不良的裝置和盡早降低風險。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p103">To prevent security breaches, it’s important to ensure all Microsoft Managed Desktop devices are healthy and secured. It’s equally important to ensure we can detect unhealthy devices and mitigate the risk as early as possible.</span></span>

<span data-ttu-id="6f4e0-135">下表列出以確保 Microsoft 受管理的桌上型電腦裝置信任、 正常且為安全提供的服務。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-135">The following table lists the services provided to ensure Microsoft Managed Desktop devices are trusted, healthy and secured.</span></span>

<span data-ttu-id="6f4e0-136">服務</span><span class="sxs-lookup"><span data-stu-id="6f4e0-136">Service</span></span> | <span data-ttu-id="6f4e0-137">描述</span><span class="sxs-lookup"><span data-stu-id="6f4e0-137">Description</span></span>
--- | ---
<span data-ttu-id="6f4e0-138">防毒</span><span class="sxs-lookup"><span data-stu-id="6f4e0-138">Antivirus</span></span> | <span data-ttu-id="6f4e0-139">我們將確認：</span><span class="sxs-lookup"><span data-stu-id="6f4e0-139">We will ensure that:</span></span><br><span data-ttu-id="6f4e0-140">安裝及設定 Windows 防禦者 AV</span><span class="sxs-lookup"><span data-stu-id="6f4e0-140">- Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="6f4e0-141">Windows 防禦者 AV 定義為最新</span><span class="sxs-lookup"><span data-stu-id="6f4e0-141">- Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="6f4e0-142">完整的磁碟區加密</span><span class="sxs-lookup"><span data-stu-id="6f4e0-142">Full Volume Encryption</span></span> |    <span data-ttu-id="6f4e0-143">Windows BitLocker 是 Microsoft 受管理的桌上型電腦裝置資料加密解決方案。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-143">Windows BitLocker is the data encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="6f4e0-144">後組織 onboarded 服務，裝置會使用與內建信任平台模組 (TPM) Windows BitLocker 防止本機資料未經授權的存取裝置時睡眠模式] 或 [關閉加密。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-144">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="6f4e0-145">監視</span><span class="sxs-lookup"><span data-stu-id="6f4e0-145">Monitoring</span></span> |    <span data-ttu-id="6f4e0-p104">Windows 防禦者進階威脅保護 (Windows 防禦者 ATP) 是監視解決方案的 Microsoft 受管理的桌上型電腦的所有裝置的安全性威脅。Windows 防禦者 ATP 可讓企業客戶偵測、 調查及應對其公司網路中的進階威脅。如需詳細資訊，請參閱[Windows 防禦者進階威脅保護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p104">Windows Defender Advanced Threat Protection (Windows Defender ATP) is the security threat monitoring solution for all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="6f4e0-149">軟體更新</span><span class="sxs-lookup"><span data-stu-id="6f4e0-149">Software updates</span></span> |  <span data-ttu-id="6f4e0-150">Microsoft 可確保 Microsoft 受管理的桌上型電腦裝置一律安全的最新的安全性更新、 Windows 及 Office、 使用 Windows Update for Business。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-150">Microsoft will ensure that Microsoft Managed Desktop devices are always secured with the latest security update, for Windows and Office, using Windows Update for Business.</span></span>
<span data-ttu-id="6f4e0-151">[復原]</span><span class="sxs-lookup"><span data-stu-id="6f4e0-151">Recovery</span></span> |  <span data-ttu-id="6f4e0-p105">公司資料儲存於 OneDrive for business 與可以輕鬆地還原 Microsoft 受管理的桌上型電腦裝置。如需詳細資訊，請參閱[OneDrive for Business。](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p105">Corporate data is stored on OneDrive for business and can be easily restored for Microsoft Managed Desktop devices. For more information, see [OneDrive for Business.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US)</span></span> 



## <a name="identity-security"></a><span data-ttu-id="6f4e0-154">身分識別安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-154">Identity security</span></span>

<span data-ttu-id="6f4e0-p106">身分識別與存取管理會保護的公司資產及重要商業資料。Azure Active Directory (Azure AD) 提供在雲端身分識別服務並啟用雲端式驗證可確保僅信任的個人可以從 Microsoft 受管理的桌上型電腦的裝置存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p106">Identity and access management protects corporate assets and business-critical data. Azure Active Directory (Azure AD) provides identity services in the cloud and enable cloud-based authentication that ensures only trusted individuals can access corporate resources from Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="6f4e0-157">服務</span><span class="sxs-lookup"><span data-stu-id="6f4e0-157">Service</span></span> | <span data-ttu-id="6f4e0-158">描述</span><span class="sxs-lookup"><span data-stu-id="6f4e0-158">Description</span></span>
--- | ---
<span data-ttu-id="6f4e0-159">企業等級驗證提供者</span><span class="sxs-lookup"><span data-stu-id="6f4e0-159">Enterprise grade authentication provider</span></span> |  <span data-ttu-id="6f4e0-p107">使用 Microsoft azure AD Premium 版本提供高可用性服務主控的全域分散式資料中心。服務處理的驗證十億做從多個 200 萬個作用中使用者每日，讓您達 99.9 %sla。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p107">Azure AD Premium editions used by Microsoft give you a high-availability service hosted in globally-distributed datacenters. The service handles billions of authentications each day from more than 200 million active users and gives you a 99.9% SLA.</span></span>
<span data-ttu-id="6f4e0-162">生物特徵驗證</span><span class="sxs-lookup"><span data-stu-id="6f4e0-162">Biometric Authentication</span></span> |  <span data-ttu-id="6f4e0-p108">Windows Hello 可讓使用者使用其圖像或 PIN 進行更困難忘記或竊取密碼登入。這可能需要額外的工作來設定。如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p108">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. This might require additional work to configure. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="6f4e0-166">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="6f4e0-166">Multi factor authentication</span></span> | <span data-ttu-id="6f4e0-167">Azure 的多重要素驗證避免未經授權的存取內部部署及雲端應用程式以提供額外的層級的驗證使用行動電話，也為自助密碼重設。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-167">Azure multi-factor authentication prevents unauthorized access to on-premises and cloud applications by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="6f4e0-168">標準使用者權限</span><span class="sxs-lookup"><span data-stu-id="6f4e0-168">Standard user permission</span></span> |  <span data-ttu-id="6f4e0-p109">若要保護系統並讓它更安全，使用者會指派標準使用者權限。這會指定為 Windows 自動駕駛儀上的現成體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p109">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="6f4e0-171">網路安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-171">Network security</span></span>

<span data-ttu-id="6f4e0-172">客戶負責網路安全性。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-172">Customers are responsible for network security.</span></span> 

<span data-ttu-id="6f4e0-173">服務</span><span class="sxs-lookup"><span data-stu-id="6f4e0-173">Service</span></span> | <span data-ttu-id="6f4e0-174">描述</span><span class="sxs-lookup"><span data-stu-id="6f4e0-174">Description</span></span>
--- | ---
<span data-ttu-id="6f4e0-175">VPN</span><span class="sxs-lookup"><span data-stu-id="6f4e0-175">VPN</span></span> | <span data-ttu-id="6f4e0-176">客戶擁有其 VPN 基礎結構，以確保有限的公司資源可以公開於內部網路之外。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-176">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="6f4e0-p110">最低需求： Microsoft 受管理的桌上型電腦需要 Windows 10 相容和支援 VPN 解決方案。如果您的組織需要 VPN 解決方案，它必須支援 Windows 10 會封裝並可透過 Intune 部署。如需詳細資訊，請洽詢您軟體發行者。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p110">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="6f4e0-180">建議：</span><span class="sxs-lookup"><span data-stu-id="6f4e0-180">Recommendation:</span></span><br><span data-ttu-id="6f4e0-p111">Microsoft 建議無法輕鬆地部署到 Intune 至推入 VPN 設定檔的現代 VPN 解決方案。這提供一律在、 順暢、 可靠且安全的方法來存取公司網路。如需詳細資訊，請參閱 VPN settings in Intune。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p111">- Microsoft recommends a Modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see VPN settings in Intune.</span></span><br><span data-ttu-id="6f4e0-184">-粗 VPN 用戶端或舊版 VPN 用戶端，並不建議 microsoft 時使用 Microsoft 受管理的桌上型電腦它可能會影響使用者環境。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-184">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="6f4e0-185">Microsoft 建議的外寄的網頁流量前往直接網際網路而不必經由 VPN，以免發生任何效能問題。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-185">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="6f4e0-186">-理想狀況下，Microsoft 建議 Azure Active Directory 應用程式 Proxy，而非 VPN 的使用。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-186">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="6f4e0-187">資訊安全性</span><span class="sxs-lookup"><span data-stu-id="6f4e0-187">Information security</span></span>

<span data-ttu-id="6f4e0-188">客戶可能會設定可協助保護高價值的公司資產這些選用的服務。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-188">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="6f4e0-189">服務</span><span class="sxs-lookup"><span data-stu-id="6f4e0-189">Service</span></span> | <span data-ttu-id="6f4e0-190">描述</span><span class="sxs-lookup"><span data-stu-id="6f4e0-190">Description</span></span>
--- | ---
<span data-ttu-id="6f4e0-191">條件式存取</span><span class="sxs-lookup"><span data-stu-id="6f4e0-191">Conditional access</span></span> |    <span data-ttu-id="6f4e0-192">只有當裝置符合時允許存取公司資源和服務。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-192">Allow access to corporate resources and services only when the device is compliant.</span></span>
<span data-ttu-id="6f4e0-193">資料修復</span><span class="sxs-lookup"><span data-stu-id="6f4e0-193">Data recovery</span></span>  | <span data-ttu-id="6f4e0-p112">在裝置上的主要資料夾中儲存的資訊備份至 OneDrive for Bbusiness。Microsoft 受管理的桌上型電腦不負責含有 OneDrive for Business 不同步的資料。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p112">Information stored in key folders on the device is backed up to OneDrive for Bbusiness. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="6f4e0-196">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="6f4e0-196">Windows Information Protection</span></span> |    <span data-ttu-id="6f4e0-197">對於需要高的資訊安全性層級的公司，我們建議使用[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)及[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-197">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 


## <a name="privileged-account-access"></a><span data-ttu-id="6f4e0-198">權限的帳戶存取權</span><span class="sxs-lookup"><span data-stu-id="6f4e0-198">Privileged account access</span></span>

<span data-ttu-id="6f4e0-199">今天，我們限制存取權的客戶 MSAdmin 認證及應用程式透過這些機制：</span><span class="sxs-lookup"><span data-stu-id="6f4e0-199">Today, we restrict access to the customer MSAdmin credentials and the application through these mechanisms:</span></span>

- <span data-ttu-id="6f4e0-200">**運算子**-Microsoft 整-次-員工位於美國順利完成定期背景與安全性檢查。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-200">**Operators** – Microsoft full-time-employees located in the US who have successfully completed a periodic background and security check.</span></span>
- <span data-ttu-id="6f4e0-p113">根據 Microsoft 所設定的標準受保護**運算子 identity** –。如需詳細資訊，請參閱[Managing 使用者身分識別和 microsoft 安全存取](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p113">**Operator identity** – Protected according to the standards set by Microsoft. For more information, see [Managing user identities and secure access at Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft).</span></span> 
- <span data-ttu-id="6f4e0-p114">**記錄**以及客戶的租用戶中的運算子環境中執行。記錄資料和個人資訊都會保留在各自的環境中並不會周遊環境。</span><span class="sxs-lookup"><span data-stu-id="6f4e0-p114">**Logging** is performed within the operator environment and within the customer’s tenant. Log data and personal information are retained within the respective environments and do not traverse environments.</span></span> 

