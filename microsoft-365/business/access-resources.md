---
title: 存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何取得內部資源的存取權，例如線條的商務應用程式、 檔案共用及從 Azure Active Directory 的印表機加入 Windows 10 裝置。
ms.openlocfilehash: 2be8eb16b9d17547d3bc4c3e4fe499b4c14117a4
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660262"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="6511b-103">存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源</span><span class="sxs-lookup"><span data-stu-id="6511b-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="6511b-104">任何 Windows 10 裝置加入 Azure Active Directory，將有權存取所有雲端為基礎的資源，例如您的 Office 365 應用程式，並可由 Microsoft 365 商務版保護。</span><span class="sxs-lookup"><span data-stu-id="6511b-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="6511b-105">也允許存取內部資源的企業營運一行 (LOB) 應用程式、 檔案共用及印表機，您必須使用[Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)與 Azure Active Directory 同步您的內部部署 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6511b-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="6511b-106">若要了解更多的[Azure Active Directory 中的裝置管理簡介](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="6511b-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="6511b-107">執行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="6511b-107">Run Azure AD Connect</span></span>

<span data-ttu-id="6511b-108">完成下列步驟，以讓您的組織已加入 Azure AD 裝置能夠存取內部部署的資源。</span><span class="sxs-lookup"><span data-stu-id="6511b-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="6511b-109">若要將您的使用者、 群組及連絡人從本機 Active Directory 同步處理到 Azure Active Directory，請執行目錄同步處理精靈，為 Azure AD Connect 所述[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。</span><span class="sxs-lookup"><span data-stu-id="6511b-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="6511b-110">目錄同步作業完成之後，請確定您組織的 Windows 10 裝置加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6511b-110">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="6511b-111">每個 Windows 10 裝置上分別執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="6511b-111">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="6511b-112">如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="6511b-112">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="6511b-113">一旦 Windows 10 裝置加入 Azure AD，每位使用者應該重新啟動其裝置並使用其 Microsoft 365 商務版認證登入。</span><span class="sxs-lookup"><span data-stu-id="6511b-113">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="6511b-114">所有的裝置現在有以及內部資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="6511b-114">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="6511b-115">沒有額外的步驟，才能存取內部資源的 Azure AD 加入裝置。</span><span class="sxs-lookup"><span data-stu-id="6511b-115">No additional steps are required to get access to on-premise resources for Azure AD joined devices.</span></span> <span data-ttu-id="6511b-116">這是 Windows 10 中可用的內建功能。</span><span class="sxs-lookup"><span data-stu-id="6511b-116">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="6511b-117">如果您的組織尚未備妥要部署在 Azure AD 加入裝置組態前文所述，請考慮[混合式 Azure AD Joined 裝置組態](manage-windows-devices.md)設定。</span><span class="sxs-lookup"><span data-stu-id="6511b-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="6511b-118">您的 Windows 裝置加入 Azure AD 時的考量</span><span class="sxs-lookup"><span data-stu-id="6511b-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="6511b-119">如果您是加入先前已加入網域的 Windows 裝置的 Azure AD 或工作群組中，您需要考慮下列限制：</span><span class="sxs-lookup"><span data-stu-id="6511b-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="6511b-120">當 Azure AD 裝置加入時，它會建立新的使用者，而不參照現有的設定檔。</span><span class="sxs-lookup"><span data-stu-id="6511b-120">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="6511b-121">若要修正此問題，必須手動移轉設定檔。</span><span class="sxs-lookup"><span data-stu-id="6511b-121">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="6511b-122">使用者設定檔包含像是我的最愛、 本機檔案、 瀏覽器設定、 開始功能表中的設定等資訊。最好的作法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔</span><span class="sxs-lookup"><span data-stu-id="6511b-122">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="6511b-123">如果裝置使用群組原則物件 (GPO)，有些 Gpo 可能沒有可以比較[設定服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) 在 Intune 中。</span><span class="sxs-lookup"><span data-stu-id="6511b-123">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="6511b-124">執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)，以尋找現有的 Gpo 相當於今年。</span><span class="sxs-lookup"><span data-stu-id="6511b-124">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="6511b-125">使用者將無法驗證依賴 Active Directory 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="6511b-125">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="6511b-126">若要處理這評估使用舊版的應用程式，並考慮更新以盡可能使用新式驗證的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6511b-126">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="6511b-127">Active Directory 印表機探索將無法運作。</span><span class="sxs-lookup"><span data-stu-id="6511b-127">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="6511b-128">若要修正此問題，提供直接的印表機路徑的所有使用者，或利用[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="6511b-128">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
