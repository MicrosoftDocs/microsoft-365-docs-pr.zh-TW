---
title: 存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何取得行商務應用程式]，檔案共用，例如在內部資源的存取權，以及從 Azure Active Directory 的印表機加入 Windows 10 裝置。
ms.openlocfilehash: 89ac38f3da9cbdd3ff1a5eb33dc129d2e83521c7
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967156"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="a6413-103">存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源</span><span class="sxs-lookup"><span data-stu-id="a6413-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="a6413-104">任何已加入 Azure Active Directory 的 Windows 10 裝置有權存取所有的雲端式資源，例如您的 Office 365 應用程式，並會受到 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="a6413-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Office 365 apps, and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="a6413-105">您也可以允許存取內部資源的企業營運 (LOB) 應用程式、 檔案共用和印表機的行，如。</span><span class="sxs-lookup"><span data-stu-id="a6413-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="a6413-106">若要允許存取，請使用[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)與 Azure Active Directory 同步處理您的內部部署 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a6413-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="a6413-107">若要深入了解，請參閱[在 Azure Active Directory 中的裝置管理的簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="a6413-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="a6413-108">下列各節也摘要說明的步驟。</span><span class="sxs-lookup"><span data-stu-id="a6413-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6413-109">此程序只適用於 OAuth] 和 [NTLM。</span><span class="sxs-lookup"><span data-stu-id="a6413-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="a6413-110">不支援 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="a6413-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="a6413-111">執行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="a6413-111">Run Azure AD Connect</span></span>

<span data-ttu-id="a6413-112">完成下列步驟，以讓您的組織已加入 Azure AD 裝置能夠存取內部部署的資源。</span><span class="sxs-lookup"><span data-stu-id="a6413-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="a6413-113">若要同步處理您的使用者，群組和連絡人從本機的 Active Directory 至 Azure Active Directory 中，執行 Azure AD Connect 與目錄同步處理精靈中[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)所述。</span><span class="sxs-lookup"><span data-stu-id="a6413-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="a6413-114">目錄同步處理完成後，請確定您組織的 Windows 10 裝置加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a6413-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="a6413-115">每個 Windows 10 裝置上分別執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="a6413-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="a6413-116">如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="a6413-116">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="a6413-117">一旦 Windows 10 裝置加入 Azure AD，其裝置和以其 Microsoft 365 商務版認證登入，必須重新啟動每位使用者。</span><span class="sxs-lookup"><span data-stu-id="a6413-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="a6413-118">所有的裝置現在有以及內部資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="a6413-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="a6413-119">沒有額外的步驟，才能取得已加入 Azure AD 裝置的存取內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="a6413-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="a6413-120">這項功能是內建於 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="a6413-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="a6413-121">如果您計劃設定 pin 碼/簡介-評量像透過 WHFB 認證登入的密碼方法以外 AADJ 裝置登入]，然後存取內部資源 （共用、 印表機..等），請遵循https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="a6413-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="a6413-122">如果您的組織尚未準備好在上面所述的 Azure AD 加入的裝置組態中部署，請考慮[混合式 Azure AD Joined 裝置組態](manage-windows-devices.md)設定。</span><span class="sxs-lookup"><span data-stu-id="a6413-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="a6413-123">當您將 Windows 裝置加入 Azure AD 的考量</span><span class="sxs-lookup"><span data-stu-id="a6413-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="a6413-124">如果您的 Azure AD 加入的 Windows 裝置已先前已加入網域或工作群組中，請考慮下列限制：</span><span class="sxs-lookup"><span data-stu-id="a6413-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="a6413-125">當 Azure AD 裝置加入時，它會建立新的使用者，而不參照現有的設定檔。</span><span class="sxs-lookup"><span data-stu-id="a6413-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="a6413-126">必須以手動方式移轉設定檔。</span><span class="sxs-lookup"><span data-stu-id="a6413-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="a6413-127">使用者設定檔包含如我的最愛、 本機檔案、 瀏覽器設定，以及開始功能表中的設定。</span><span class="sxs-lookup"><span data-stu-id="a6413-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="a6413-128">最好的方法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="a6413-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="a6413-129">如果裝置使用群組原則物件 (GPO)，有些 Gpo 可能沒有可以比較[設定服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) 在 Intune 中。</span><span class="sxs-lookup"><span data-stu-id="a6413-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="a6413-130">執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)，以尋找現有的 Gpo 相當於今年。</span><span class="sxs-lookup"><span data-stu-id="a6413-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="a6413-131">使用者將無法驗證依賴 Active Directory 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="a6413-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="a6413-132">評估舊版應用程式，並考慮更新以盡可能使用新式驗證、 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a6413-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="a6413-133">Active Directory 印表機探索將無法運作。</span><span class="sxs-lookup"><span data-stu-id="a6413-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="a6413-134">您可以為所有使用者提供直接的印表機路徑，或使用[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="a6413-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
