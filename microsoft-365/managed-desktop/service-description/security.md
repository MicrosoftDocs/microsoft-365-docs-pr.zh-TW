---
title: Microsoft 受管理電腦中的安全性
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866744"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="c274c-103">Microsoft 受管理電腦中的安全性</span><span class="sxs-lookup"><span data-stu-id="c274c-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="c274c-p101">Microsoft 受管理的桌上型電腦套用之原則的標準設定並使用為了安全 Microsoft 受管理的桌上型電腦裝置、 預存的公司資料及其他許多 Microsoft 技術。下面所列的區域會進一步詳細說明：</span><span class="sxs-lookup"><span data-stu-id="c274c-p101">Microsoft Managed Desktop applies a standard set of policies and utilizes many Microsoft technologies to help secure Microsoft Managed Desktop devices, stored company data, and more. The areas listed below are detailed further:</span></span>  

- <span data-ttu-id="c274c-106">[資料安全性](#data-security)Microsoft 受管理的桌上型電腦及安全地儲存所收集的資料類型</span><span class="sxs-lookup"><span data-stu-id="c274c-106">[Data security](#data-security) - types of data collected by Microsoft Managed Desktop and where it's securely stored</span></span>
- <span data-ttu-id="c274c-107">[裝置安全性](#device-security)– 安全性和保護 Microsoft 受管理的桌上型電腦裝置上</span><span class="sxs-lookup"><span data-stu-id="c274c-107">[Device security](#device-security) – security and protection on Microsoft Managed Desktop devices</span></span>
- <span data-ttu-id="c274c-108">[身分識別與存取管理](#identity-and-access-management)– 管理安全使用的裝置透過 Azure Active Directory 身分識別服務</span><span class="sxs-lookup"><span data-stu-id="c274c-108">[Identity and Access Management](#identity-and-access-management) – managing secure use of devices through Azure Active Directory identity services</span></span>
- <span data-ttu-id="c274c-109">[網路安全性](#network-security)– VPN 資訊和 Microsoft 受管理的桌上型電腦建議的解決方案和設定</span><span class="sxs-lookup"><span data-stu-id="c274c-109">[Network security](#network-security) – VPN information and Microsoft Managed Desktop recommended solution and settings</span></span>
- <span data-ttu-id="c274c-110">[資訊安全性](#information-security)– 進一步保護敏感資訊的選用可用服務</span><span class="sxs-lookup"><span data-stu-id="c274c-110">[Information security](#information-security) – optional available services to further protect sensitive information</span></span> 

## <a name="data-security"></a><span data-ttu-id="c274c-111">資料安全性</span><span class="sxs-lookup"><span data-stu-id="c274c-111">Data security</span></span>

<span data-ttu-id="c274c-112">從客戶承租人收集的資料 （可讓 Microsoft 受管理的桌上型電腦 IT 服務和作業） 會儲存在架設在美國為 Microsoft 租用戶中的 Azure SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c274c-112">Data collected from customer tenants (which enables Microsoft Managed Desktop IT services and operations) is stored in Azure SQL databases in the Microsoft tenant hosted in the United States of America.</span></span>

<span data-ttu-id="c274c-113">如需詳細資訊，請參閱[Microsoft Azure 安全性](https://docs.microsoft.com/azure/security/azure-database-security-overview)。</span><span class="sxs-lookup"><span data-stu-id="c274c-113">For more information, see [Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview).</span></span>

<span data-ttu-id="c274c-114">下面所列是從您的租用戶傳輸的資料類型：</span><span class="sxs-lookup"><span data-stu-id="c274c-114">Listed below are the types of data transmitted from your tenant:</span></span>

- <span data-ttu-id="c274c-115">裝置更新、 使用量及可靠性資料</span><span class="sxs-lookup"><span data-stu-id="c274c-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="c274c-116">應用程式部署及可靠性資料</span><span class="sxs-lookup"><span data-stu-id="c274c-116">App deployment and reliability data</span></span>
- <span data-ttu-id="c274c-117">更新與安全性原則部署資料</span><span class="sxs-lookup"><span data-stu-id="c274c-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="c274c-118">指派給裝置的使用者</span><span class="sxs-lookup"><span data-stu-id="c274c-118">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="c274c-119">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="c274c-119">Device security</span></span>

<span data-ttu-id="c274c-120">Microsoft 受管理的桌上型電腦會確保受管理的所有裝置保護及受到保護，且偵測威脅早儘可能使用下列服務：</span><span class="sxs-lookup"><span data-stu-id="c274c-120">Microsoft Managed Desktop ensures all managed devices are secured and protected, and detects threats as early as possible using the following services:</span></span>

<span data-ttu-id="c274c-121">服務</span><span class="sxs-lookup"><span data-stu-id="c274c-121">Service</span></span> | <span data-ttu-id="c274c-122">描述</span><span class="sxs-lookup"><span data-stu-id="c274c-122">Description</span></span>
--- | ---
<span data-ttu-id="c274c-123">防毒</span><span class="sxs-lookup"><span data-stu-id="c274c-123">Antivirus</span></span> | <span data-ttu-id="c274c-124">安裝及設定 Windows 防禦者 AV</span><span class="sxs-lookup"><span data-stu-id="c274c-124">Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="c274c-125">Windows 防禦者 AV 定義為最新</span><span class="sxs-lookup"><span data-stu-id="c274c-125">Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="c274c-126">完整的磁碟區加密</span><span class="sxs-lookup"><span data-stu-id="c274c-126">Full Volume Encryption</span></span> |    <span data-ttu-id="c274c-127">Windows BitLocker 是 Microsoft 受管理的桌上型電腦裝置的磁碟區加密解決方案。</span><span class="sxs-lookup"><span data-stu-id="c274c-127">Windows BitLocker is the volume encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="c274c-128">後組織 onboarded 服務，裝置會使用與內建信任平台模組 (TPM) Windows BitLocker 防止本機資料未經授權的存取裝置時睡眠模式] 或 [關閉加密。</span><span class="sxs-lookup"><span data-stu-id="c274c-128">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="c274c-129">監視</span><span class="sxs-lookup"><span data-stu-id="c274c-129">Monitoring</span></span> |    <span data-ttu-id="c274c-p102">跨 Microsoft 受管理的桌上型電腦的所有裝置的安全性威脅監視適用於 Windows 防禦者進階威脅保護 (Windows 防禦者 ATP)。Windows 防禦者 ATP 可讓企業客戶偵測、 調查及回應其公司網路中的進階威脅。如需詳細資訊，請參閱[Windows 防禦者進階威脅保護。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="c274c-p102">Windows Defender Advanced Threat Protection (Windows Defender ATP) is used for security threat monitoring across all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate, and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="c274c-133">軟體更新</span><span class="sxs-lookup"><span data-stu-id="c274c-133">Software updates</span></span> |  <span data-ttu-id="c274c-134">Microsoft 受管理的桌上型電腦裝置一律保護使用最新的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="c274c-134">Microsoft Managed Desktop devices are always secured with the latest security updates.</span></span>
<span data-ttu-id="c274c-135">安全的裝置設定</span><span class="sxs-lookup"><span data-stu-id="c274c-135">Secure Device Configuration</span></span> |   <span data-ttu-id="c274c-p103">Microsoft 受管理的桌上型電腦實作 Microsoft 安全性基準。如需詳細資訊，請參閱[Windows 安全性基準。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="c274c-p103">Microsoft Managed Desktop implements the Microsoft Security Baseline. For more information, see [Windows security baselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span></span>



## <a name="identity-and-access-management"></a><span data-ttu-id="c274c-138">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="c274c-138">Identity and access management</span></span>

<span data-ttu-id="c274c-p104">身分識別與存取管理會保護的公司資產及重要商業資料。Microsoft 受管理的桌上型電腦設定以確保安全使用 Azure Active Directory (Azure AD) 受管理的身分識別的裝置。它會維護其 Azure AD 租用戶中的正確資訊的客戶的責任。</span><span class="sxs-lookup"><span data-stu-id="c274c-p104">Identity and access management protects corporate assets and business-critical data. Microsoft Managed Desktop configures devices to ensure secure use with Azure Active Directory (Azure AD) managed identities. It is the customer's responsibility to maintain accurate information in their Azure AD tenant.</span></span> 

<span data-ttu-id="c274c-142">服務</span><span class="sxs-lookup"><span data-stu-id="c274c-142">Service</span></span> | <span data-ttu-id="c274c-143">描述</span><span class="sxs-lookup"><span data-stu-id="c274c-143">Description</span></span>
--- | ---
<span data-ttu-id="c274c-144">生物特徵驗證</span><span class="sxs-lookup"><span data-stu-id="c274c-144">Biometric Authentication</span></span> |  <span data-ttu-id="c274c-p105">Windows Hello 可讓使用者使用其圖像或 PIN 進行更困難忘記或竊取密碼登入。如需詳細資訊，請參閱[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span><span class="sxs-lookup"><span data-stu-id="c274c-p105">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="c274c-147">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="c274c-147">Multi-factor authentication</span></span> | <span data-ttu-id="c274c-148">Azure 的多重要素驗證更緊密控制存取權之 Microsoft 受管理的桌上型電腦服務機密函數提供使用行動電話，以及為自助密碼重設為驗證其他層級。</span><span class="sxs-lookup"><span data-stu-id="c274c-148">Azure multi-factor authentication more tightly controls access to sensitive functions of the Microsoft Managed Desktop service by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="c274c-149">標準使用者權限</span><span class="sxs-lookup"><span data-stu-id="c274c-149">Standard user permission</span></span> |  <span data-ttu-id="c274c-p106">若要保護系統並讓它更安全，使用者會指派標準使用者權限。這會指定為 Windows 自動駕駛儀上的現成體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="c274c-p106">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="c274c-152">網路安全性</span><span class="sxs-lookup"><span data-stu-id="c274c-152">Network security</span></span>

<span data-ttu-id="c274c-153">客戶負責網路安全性。</span><span class="sxs-lookup"><span data-stu-id="c274c-153">Customers are responsible for network security.</span></span> 

<span data-ttu-id="c274c-154">服務</span><span class="sxs-lookup"><span data-stu-id="c274c-154">Service</span></span> | <span data-ttu-id="c274c-155">描述</span><span class="sxs-lookup"><span data-stu-id="c274c-155">Description</span></span>
--- | ---
<span data-ttu-id="c274c-156">VPN</span><span class="sxs-lookup"><span data-stu-id="c274c-156">VPN</span></span> | <span data-ttu-id="c274c-157">客戶擁有其 VPN 基礎結構，以確保有限的公司資源可以公開於內部網路之外。</span><span class="sxs-lookup"><span data-stu-id="c274c-157">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="c274c-p107">最低需求： Microsoft 受管理的桌上型電腦需要 Windows 10 相容和支援 VPN 解決方案。如果您的組織需要 VPN 解決方案，它必須支援 Windows 10 會封裝並可透過 Intune 部署。如需詳細資訊，請洽詢您軟體發行者。</span><span class="sxs-lookup"><span data-stu-id="c274c-p107">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="c274c-161">建議：</span><span class="sxs-lookup"><span data-stu-id="c274c-161">Recommendation:</span></span><br><span data-ttu-id="c274c-p108">Microsoft 建議無法輕鬆地部署到 Intune 至推入 VPN 設定檔的現代 VPN 解決方案。這提供一律在、 順暢、 可靠且安全的方法來存取公司網路。如需詳細資訊，請參閱[[Intune VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="c274c-p108">- Microsoft recommends a modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see [[VPN settings in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).</span></span><br><span data-ttu-id="c274c-165">-粗 VPN 用戶端或舊版 VPN 用戶端，並不建議 microsoft 時使用 Microsoft 受管理的桌上型電腦它可能會影響使用者環境。</span><span class="sxs-lookup"><span data-stu-id="c274c-165">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="c274c-166">Microsoft 建議的外寄的網頁流量前往直接網際網路而不必經由 VPN，以免發生任何效能問題。</span><span class="sxs-lookup"><span data-stu-id="c274c-166">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="c274c-167">-理想狀況下，Microsoft 建議 Azure Active Directory 應用程式 Proxy，而非 VPN 的使用。</span><span class="sxs-lookup"><span data-stu-id="c274c-167">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="c274c-168">資訊安全性</span><span class="sxs-lookup"><span data-stu-id="c274c-168">Information security</span></span>

<span data-ttu-id="c274c-169">客戶可能會設定可協助保護高價值的公司資產這些選用的服務。</span><span class="sxs-lookup"><span data-stu-id="c274c-169">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="c274c-170">服務</span><span class="sxs-lookup"><span data-stu-id="c274c-170">Service</span></span> | <span data-ttu-id="c274c-171">描述</span><span class="sxs-lookup"><span data-stu-id="c274c-171">Description</span></span>
--- | ---
<span data-ttu-id="c274c-172">資料修復</span><span class="sxs-lookup"><span data-stu-id="c274c-172">Data recovery</span></span>  | <span data-ttu-id="c274c-p109">在裝置上的主要資料夾中儲存的資訊備份至 OneDrive for Business。Microsoft 受管理的桌上型電腦不負責含有 OneDrive for Business 不同步的資料。</span><span class="sxs-lookup"><span data-stu-id="c274c-p109">Information stored in key folders on the device is backed up to OneDrive for Business. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="c274c-175">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="c274c-175">Windows Information Protection</span></span> |    <span data-ttu-id="c274c-176">對於需要高的資訊安全性層級的公司，我們建議使用[Windows 資訊保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)及[Azure 資訊保護。](https://www.microsoft.com/cloud-platform/azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="c274c-176">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 

