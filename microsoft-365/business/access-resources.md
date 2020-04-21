---
title: 從 Microsoft 365 商務版中已加入 Azure AD 的裝置存取內部部署資源
f1.keywords:
- NOCSH
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
description: 瞭解如何從已加入 Azure Active Directory 的 Windows 10 裝置，存取內部部署資源（如商務線應用程式、檔案共用及印表機）。
ms.openlocfilehash: c1e04e5ca0d36c32a55a9819140356db5093e3a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627447"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="1a01e-103">從 Microsoft 365 商務版 Premium 中已加入 Azure AD 的裝置存取內部部署資源</span><span class="sxs-lookup"><span data-stu-id="1a01e-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1a01e-104">任何已加入 Azure Active Directory 的 Windows 10 裝置都能存取所有雲端架構資源（如您的 Microsoft 365 應用程式），並可由 Microsoft 365 商務版 Premium 進行保護。</span><span class="sxs-lookup"><span data-stu-id="1a01e-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="1a01e-105">您也可以允許存取內部部署資源（如商務線（LOB）應用程式、檔案共用及印表機）。</span><span class="sxs-lookup"><span data-stu-id="1a01e-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="1a01e-106">若要允許存取，請使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) ，將您的內部部署 Active Directory 與 Azure active directory 同步。</span><span class="sxs-lookup"><span data-stu-id="1a01e-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="1a01e-107">若要深入瞭解，請參閱[Azure Active Directory 中的裝置管理簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="1a01e-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="1a01e-108">下列各節也會摘要說明這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1a01e-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a01e-109">此程式僅適用于 OAuth 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="1a01e-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="1a01e-110">不支援 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="1a01e-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="1a01e-111">執行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="1a01e-111">Run Azure AD Connect</span></span>

<span data-ttu-id="1a01e-112">完成下列步驟，讓您組織的 Azure AD 加入裝置能夠存取內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="1a01e-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="1a01e-113">若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請依照[設定 Office 365 的目錄同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)處理中所述，執行目錄同步處理嚮導和 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="1a01e-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="1a01e-114">目錄同步處理完成後，請確定您組織的 Windows 10 裝置已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1a01e-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="1a01e-115">此步驟會在每個 Windows 10 裝置上進行個別的執行。</span><span class="sxs-lookup"><span data-stu-id="1a01e-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="1a01e-116">如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者設定 Windows 裝置](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="1a01e-116">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="1a01e-117">在 Windows 10 裝置加入 Azure AD 後，每個使用者都必須重新開機其裝置，並使用 Microsoft 365 商務版優質認證登入。</span><span class="sxs-lookup"><span data-stu-id="1a01e-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="1a01e-118">所有裝置現在也可以存取內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="1a01e-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="1a01e-119">不需要額外的步驟即可存取 Azure AD 已加入裝置的內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="1a01e-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="1a01e-120">此功能已內置於 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="1a01e-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="1a01e-121">如果您計畫登入 AADJ 裝置，但密碼方法（如 PIN 碼/Bio-公制）經由 WHFB 認證登入，則會存取內部部署資源（共用、印表機）。等等），請遵循https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="1a01e-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="1a01e-122">如果您的組織未準備好在上述 Azure AD 聯結裝置設定中進行部署，請考慮設定[混合式 AZURE Ad join 裝置](manage-windows-devices.md)設定。</span><span class="sxs-lookup"><span data-stu-id="1a01e-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="1a01e-123">將 Windows 裝置加入 Azure AD 時的考慮</span><span class="sxs-lookup"><span data-stu-id="1a01e-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="1a01e-124">如果您 Azure 加入的 Windows 裝置先前已加入網域或在工作組中，請考慮下列限制：</span><span class="sxs-lookup"><span data-stu-id="1a01e-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="1a01e-125">當裝置 Azure AD 加入時，它會建立新的使用者，而不會參照現有的設定檔。</span><span class="sxs-lookup"><span data-stu-id="1a01e-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="1a01e-126">設定檔必須手動遷移。</span><span class="sxs-lookup"><span data-stu-id="1a01e-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="1a01e-127">使用者設定檔包含我的最愛、本機檔案、瀏覽器設定及「開始」功能表設定等資訊。</span><span class="sxs-lookup"><span data-stu-id="1a01e-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="1a01e-128">最佳方法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="1a01e-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="1a01e-129">如果裝置使用群組原則物件（GPO），則某些 Gpo 在 Intune 中可能沒有比較的設定[服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)（CSP）。</span><span class="sxs-lookup"><span data-stu-id="1a01e-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="1a01e-130">執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)，尋找現有 gpo 的類似 csp。</span><span class="sxs-lookup"><span data-stu-id="1a01e-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="1a01e-131">使用者將無法對依存于 Active Directory 驗證的應用程式進行驗證。</span><span class="sxs-lookup"><span data-stu-id="1a01e-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="1a01e-132">評估繼承應用程式，並考慮更新至使用新式驗證的應用程式（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="1a01e-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="1a01e-133">Active Directory 印表機探索無法運作。</span><span class="sxs-lookup"><span data-stu-id="1a01e-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="1a01e-134">您可以為所有使用者提供直接印表機路徑，或使用[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="1a01e-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
