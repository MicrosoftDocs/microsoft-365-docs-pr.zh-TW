---
title: 為 Microsoft 受管理的電腦準備認證和網路設定檔
description: 憑證需求和 wi-fi 連線能力
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574580"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a><span data-ttu-id="c163a-104">為 Microsoft 受管理的電腦準備認證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="c163a-104">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>  
 
<span data-ttu-id="c163a-105">憑證型驗證是使用 Microsoft 受管理電腦的客戶的常見需求。</span><span class="sxs-lookup"><span data-stu-id="c163a-105">Certificate-based authentication is a common requirement for customers using Microsoft Managed Desktop.</span></span> <span data-ttu-id="c163a-106">您可能需要憑證來存取 Wi-Fi 或 LAN，以連線至 VPN 方案，或存取組織中的內部資源。</span><span class="sxs-lookup"><span data-stu-id="c163a-106">You might require certificates to access Wi-Fi or LAN, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>   
 
<span data-ttu-id="c163a-107">因為 Microsoft 受管理的桌面裝置已加入 Azure Active Directory (Azure AD) 且由 Microsoft Intune 管理，所以您必須使用簡易憑證註冊通訊協定 (SCEP) 或公開金鑰密碼編譯標準 (與 Intune 整合的憑證基礎結構，部署這類憑證。</span><span class="sxs-lookup"><span data-stu-id="c163a-107">Because Microsoft Managed Desktop devices are joined to Azure Active Directory (Azure AD) and are managed by Microsoft Intune, you must deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with Intune.</span></span>    
 
## <a name="certificate-requirements"></a><span data-ttu-id="c163a-108">憑證需求</span><span class="sxs-lookup"><span data-stu-id="c163a-108">Certificate requirements</span></span> 
 
<span data-ttu-id="c163a-109">需要有根憑證，才能透過 SCEP 或 PKCS 基礎結構部署憑證。</span><span class="sxs-lookup"><span data-stu-id="c163a-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="c163a-110">您組織中的其他應用程式和服務可能需要將根憑證部署至您的 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="c163a-110">Other applications and services in your organization might require root certificates to be deployed to your Microsoft Managed Desktop devices.</span></span>    
 
<span data-ttu-id="c163a-111">在您將 SCEP 或 PKCS 憑證部署至 Microsoft Managed Desktop 之前，您應該收集組織中需要使用者或裝置憑證的每個服務需求。</span><span class="sxs-lookup"><span data-stu-id="c163a-111">Before you deploy SCEP or PKCS certificates to Microsoft Managed Desktop, you should gather requirements for each service that requires a user or device certificate in your organization.</span></span> <span data-ttu-id="c163a-112">若要簡化此活動，您可以使用下列其中一個規劃範本：</span><span class="sxs-lookup"><span data-stu-id="c163a-112">To make this activity easier, you can use one of the following planning templates:</span></span>  
 
- [<span data-ttu-id="c163a-113">PKCS 憑證範本</span><span class="sxs-lookup"><span data-stu-id="c163a-113">PKCS certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [<span data-ttu-id="c163a-114">SCEP 憑證範本</span><span class="sxs-lookup"><span data-stu-id="c163a-114">SCEP certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="c163a-115">Wi-Fi 連通性需求</span><span class="sxs-lookup"><span data-stu-id="c163a-115">Wi-Fi connectivity requirements</span></span>

<span data-ttu-id="c163a-116">若要讓您的商業網路所需的 Wi-Fi 設定自動提供裝置，您可能需要 Wi-Fi 設定檔。</span><span class="sxs-lookup"><span data-stu-id="c163a-116">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you might need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="c163a-117">您可以設定 Microsoft Managed Desktop，將這些設定檔部署至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="c163a-117">You can configure Microsoft Managed Desktop to deploy these profiles to your devices.</span></span> <span data-ttu-id="c163a-118">如果您的網路安全性需要裝置成為本機網域的一部分，您可能也需要評估 Wi-Fi 網路基礎結構，以確保其與 Microsoft 受管理的桌面裝置相容 (Microsoft 受管理的桌面裝置只會加入 Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="c163a-118">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with Microsoft Managed Desktop devices (Microsoft Managed Desktop devices are Azure AD-joined only).</span></span> 
 
<span data-ttu-id="c163a-119">在您將 Wi-Fi 設定部署至 Microsoft 受管理的桌面裝置之前，您需要收集每個 Wi-Fi 網路的組織需求。</span><span class="sxs-lookup"><span data-stu-id="c163a-119">Before you deploy a Wi-Fi configuration to Microsoft Managed Desktop devices, you will be required to gather your organization’s requirements for each Wi-Fi network.</span></span> <span data-ttu-id="c163a-120">若要讓此活動變得更簡單，您可以使用此 [WiFi 設定檔範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="c163a-120">To make this activity easier, you can use this [WiFi profile template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).</span></span>
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a><span data-ttu-id="c163a-121">有線連線需求和 802.1 x 驗證</span><span class="sxs-lookup"><span data-stu-id="c163a-121">Wired connectivity requirements and 802.1x authentication</span></span> 
 
<span data-ttu-id="c163a-122">如果您使用 802.1 x authentication 來保護從裝置接入局域網 (LAN) ，您必須將必要的設定詳細資料推送至您的 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="c163a-122">If you use 802.1x authentication to secure access from devices to your local area network (LAN), you will need to push the required configuration details to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c163a-123">Microsoft 受管理的桌面裝置執行 Windows 10，版本1809或更新版本支援透過 WiredNetwork configuration service provider (CSP) 部署 802.1 x 設定。</span><span class="sxs-lookup"><span data-stu-id="c163a-123">Microsoft Managed Desktop devices running Windows 10, version 1809 or later support deploying an 802.1x configuration through the WiredNetwork configuration service provider (CSP).</span></span> <span data-ttu-id="c163a-124">如需詳細資訊，請參閱 [WIREDNETWORK CSP](/windows/client-management/mdm/wirednetwork-csp) 檔。</span><span class="sxs-lookup"><span data-stu-id="c163a-124">For more information, see [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation.</span></span> 
 
<span data-ttu-id="c163a-125">將有線網路設定設定檔部署至 Microsoft 受管理的桌面裝置之前，請先收集您組織的有線公司網路需求。</span><span class="sxs-lookup"><span data-stu-id="c163a-125">Before you deploy a wired network configuration profile to Microsoft Managed Desktop devices, gather your organization’s requirements for your wired corporate network.</span></span> <span data-ttu-id="c163a-126">其步驟如下：</span><span class="sxs-lookup"><span data-stu-id="c163a-126">To do so, follow these steps:</span></span> 
 
 
1. <span data-ttu-id="c163a-127">登入已設定現有 802.1 x 設定檔的裝置，並連接至局域網網路。</span><span class="sxs-lookup"><span data-stu-id="c163a-127">Sign on to a device that has your existing 802.1x profile configured and is connected to the LAN network.</span></span>  
2. <span data-ttu-id="c163a-128">使用系統管理認證開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="c163a-128">Open a command prompt with administrative credentials.</span></span> 
3. <span data-ttu-id="c163a-129">執行 **netsh interface show interface**，以尋找 LAN 介面名稱。</span><span class="sxs-lookup"><span data-stu-id="c163a-129">Find the LAN interface name by running **netsh interface show interface**.</span></span> 
4. <span data-ttu-id="c163a-130">執行 **netsh LAN 匯出設定檔資料夾，以匯出 LAN 設定檔 XML。 Interface = "interface_name"**。</span><span class="sxs-lookup"><span data-stu-id="c163a-130">Export the LAN profile XML by running **netsh lan export profile folder=.  Interface=”interface_name”**.</span></span> 
5. <span data-ttu-id="c163a-131">如果您需要在 Microsoft 受管理的電腦裝置上測試匯出的設定檔，請執行 **netsh lan add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"**。</span><span class="sxs-lookup"><span data-stu-id="c163a-131">If you need to test your exported profile on Microsoft Managed Desktop device, run **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**.</span></span> 
 
 
## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="c163a-132">部署憑證基礎結構</span><span class="sxs-lookup"><span data-stu-id="c163a-132">Deploy certificate infrastructure</span></span>  
 
<span data-ttu-id="c163a-133">如果您已有使用 Intune 的 SCEP 或 PKCS 基礎結構，且此方法符合您的需求，您也可以將它用於 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="c163a-133">If you already have an existing SCEP or PKCS infrastructure with Intune and this approach meets your requirements, you can also use it for Microsoft Managed Desktop.</span></span> <span data-ttu-id="c163a-134">如果沒有 SCEP 或 PKCS 基礎結構已經存在，您必須準備一個。</span><span class="sxs-lookup"><span data-stu-id="c163a-134">If no SCEP or PKCS infrastructure already exists, you'll have to prepare one.</span></span>  
 
<span data-ttu-id="c163a-135">如需詳細資訊，請參閱 [在 Microsoft Intune 中為您的裝置設定憑證設定檔](/intune/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="c163a-135">For more information, see [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure).</span></span> 
 
 
 
## <a name="deploy-a-lan-profile"></a><span data-ttu-id="c163a-136">部署 LAN 設定檔</span><span class="sxs-lookup"><span data-stu-id="c163a-136">Deploy a LAN profile</span></span> 
 
<span data-ttu-id="c163a-137">匯出 LAN 設定檔之後，您可以遵循下列步驟，準備用於 Microsoft Managed 桌面的原則：</span><span class="sxs-lookup"><span data-stu-id="c163a-137">Once your LAN profile has been exported, you can prepare the policy for Microsoft Managed Desktop by following these steps:</span></span>   
 
1. <span data-ttu-id="c163a-138">使用下列設定在 Microsoft Intune 中為 LAN 設定檔建立自訂設定檔。請參閱在 [Intune) 中使用 Windows 10 裝置的自訂設定](/intune/custom-settings-windows-10) (。</span><span class="sxs-lookup"><span data-stu-id="c163a-138">Create a custom profile in Microsoft Intune for the LAN profile using the following settings (see [Use custom settings for Windows 10 devices in Intune](/intune/custom-settings-windows-10)).</span></span> <span data-ttu-id="c163a-139">在 [ **自訂 OMA URI 設定**] 中，選取 [ **新增**]，然後輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="c163a-139">In **Custom OMA-URI Settings**, select **Add**, and then enter the following values:</span></span> 
    - <span data-ttu-id="c163a-140">名稱： *現代 Workplace-Windows 10 LAN 設定檔*</span><span class="sxs-lookup"><span data-stu-id="c163a-140">Name: *Modern Workplace-Windows 10 LAN Profile*</span></span> 
    - <span data-ttu-id="c163a-141">描述：輸入提供設定概述的描述，以及任何其他重要的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c163a-141">Description: Enter a description that gives an overview of the setting, and any other important details.</span></span> 
    - <span data-ttu-id="c163a-142">OMA URI (區分大小寫) ： Enter *。/Device/Vendor/MSFT/WiredNetwork/LanXML*</span><span class="sxs-lookup"><span data-stu-id="c163a-142">OMA-URI (case sensitive): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*</span></span>
    - <span data-ttu-id="c163a-143">資料類型： **) 選取字串 (的 XML** 檔案。</span><span class="sxs-lookup"><span data-stu-id="c163a-143">Data type: select **String (XML file)**.</span></span> 
    - <span data-ttu-id="c163a-144">自訂 XML：上傳匯出的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="c163a-144">Custom XML: Upload the exported XML file.</span></span>
2. <span data-ttu-id="c163a-145">使用 Microsoft Managed Desktop Admin 入口網站，將支援要求提交至 Microsoft 管理的桌面 IT 作業，以複查及部署「新式工作」裝置–測試」的設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="c163a-145">Submit a Support request to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="c163a-146">Microsoft 受管理的桌面 IT 作業可讓您在系統管理員入口網站中的支援要求完成要求時，通知您。</span><span class="sxs-lookup"><span data-stu-id="c163a-146">Microsoft Managed Desktop IT Operations will let you know when the request is completed via the Support request in the Admin portal.</span></span>
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="c163a-147">部署憑證和 Wi-Fi/VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="c163a-147">Deploy certificates and Wi-Fi/VPN profile</span></span> 
 
 
<span data-ttu-id="c163a-148">若要部署憑證和設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c163a-148">To deploy certificates and profiles, follow these steps:</span></span>

1. <span data-ttu-id="c163a-149">建立每個根和中級憑證的設定檔 (請參閱 [建立信任的憑證設定檔](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。</span><span class="sxs-lookup"><span data-stu-id="c163a-149">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles).</span></span> <span data-ttu-id="c163a-150">每個設定檔都必須有包含到期日為 DD/MM/YYYY 格式的描述。</span><span class="sxs-lookup"><span data-stu-id="c163a-150">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="c163a-151">**不會部署不含到期日的憑證設定檔。**</span><span class="sxs-lookup"><span data-stu-id="c163a-151">**Certificate profiles without an expiration date will not be deployed.**</span></span>
2. <span data-ttu-id="c163a-152">建立每個 SCEP 或 PKCS 憑證的設定檔 (請參閱 [create a scep certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 或 [create a PKCS Certificate Profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 每個設定檔都必須有一個包含到期日的描述，其格式為 DD/MM/YYYY 格式。</span><span class="sxs-lookup"><span data-stu-id="c163a-152">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or [Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="c163a-153">**不會部署不含到期日的憑證設定檔。**</span><span class="sxs-lookup"><span data-stu-id="c163a-153">**Certificate profiles without an expiration date will not be deployed.**</span></span>
3. <span data-ttu-id="c163a-154">為每個公司 WiFi 網路建立設定檔 (請參閱 [Wi-Fi 設定 Windows 10 和更新版本的裝置](/intune/wi-fi-settings-windows)) 。</span><span class="sxs-lookup"><span data-stu-id="c163a-154">Create a profile for each corporate WiFi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span>
4. <span data-ttu-id="c163a-155">為每個公司 VPN 建立設定檔 (請參閱 [windows 10 和 Windows 全息裝置設定，以使用 Intune) 新增 VPN](/intune/vpn-settings-windows-10) 連線。</span><span class="sxs-lookup"><span data-stu-id="c163a-155">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/intune/vpn-settings-windows-10)).</span></span>
5. <span data-ttu-id="c163a-156">使用 Microsoft Managed Desktop Admin 入口網站，將名為「憑證部署」或「Wi-Fi 設定檔部署」的支援要求提交至 Microsoft 受管理的桌面系統管理員入口網站，以複查及部署「新式工作」裝置–測試」的設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="c163a-156">Submit a Support request titled “Certificate Deployment” or “Wi-Fi Profile Deployment” to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="c163a-157">Microsoft 受管理的桌面 IT 作業可讓您在系統管理員入口網站中透過支援要求完成要求時，告知您。</span><span class="sxs-lookup"><span data-stu-id="c163a-157">Microsoft Managed Desktop IT Operations will let you know when the request has been completed via the Support request in the Admin portal.</span></span> 
 
## <a name="steps-to-get-ready"></a><span data-ttu-id="c163a-158">準備就緒的步驟</span><span class="sxs-lookup"><span data-stu-id="c163a-158">Steps to get ready</span></span>

1. <span data-ttu-id="c163a-159">檢查 [Microsoft 受管理的桌面的必要條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="c163a-159">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="c163a-160">使用 [準備工作評估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="c163a-160">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="c163a-161">來賓帳戶的先決條件</span><span class="sxs-lookup"><span data-stu-id="c163a-161">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="c163a-162">Microsoft 受管理電腦的網路設定</span><span class="sxs-lookup"><span data-stu-id="c163a-162">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. <span data-ttu-id="c163a-163">[為 Microsoft 受管理的桌面準備憑證和網路設定檔](certs-wifi-lan.md) (本文) </span><span class="sxs-lookup"><span data-stu-id="c163a-163">[Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md) (This article)</span></span>
6. [<span data-ttu-id="c163a-164">為 Microsoft 受管理的電腦準備備內部部署資源存取權</span><span class="sxs-lookup"><span data-stu-id="c163a-164">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="c163a-165">Microsoft 受管理電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="c163a-165">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="c163a-166">為 Microsoft 受管理的電腦準備對應磁碟機</span><span class="sxs-lookup"><span data-stu-id="c163a-166">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="c163a-167">為 Microsoft 受管理的電腦準備列印資源</span><span class="sxs-lookup"><span data-stu-id="c163a-167">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md) 
