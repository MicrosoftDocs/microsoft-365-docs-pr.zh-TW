---
title: 存取內部部署中 Microsoft 365 商務 Azure AD 加入裝置的資源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何取得像是企業營運系統應用程式、 檔案共用，以及 Azure Active Directory 中的印表機加入 Windows 10 裝置的內部部署資源的存取權。
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866146"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="7fd5b-103">存取內部部署中 Microsoft 365 商務 Azure AD 加入裝置的資源</span><span class="sxs-lookup"><span data-stu-id="7fd5b-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="7fd5b-p101">為 Azure Active Directory 加入任何 Windows 10 裝置必須如您的 Office 365 應用程式的所有雲端資源的存取權，並且可以受到 Microsoft 365 Business。也允許類似的商務列 (LOB) 應用程式、 檔案共用及印表機的內部部署資源的存取權，您必須使用同步處理您的內部部署 Active Directory Azure Active Directory [Azure AD 連線](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)。請參閱 ＜ [Introduction to 裝置管理 Azure Active Directory 中](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)若要深入了解。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="7fd5b-107">執行 Azure AD 連線</span><span class="sxs-lookup"><span data-stu-id="7fd5b-107">Run Azure AD Connect</span></span>

<span data-ttu-id="7fd5b-108">完成下列步驟，讓您的組織已加入的 Azure AD 裝置能夠存取內部部署的資源。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="7fd5b-109">若要進行使用者、 群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory、 執行目錄同步作業精靈並做為 Azure AD 連線所述[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="7fd5b-p102">完成目錄同步作業之後，請確定您的組織 Windows 10 裝置已加入的 Azure AD。每個 Windows 10 裝置上個別完成這個步驟。如需詳細資訊，請參閱[設定 Microsoft 365 商務使用者的 Windows 裝置](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="7fd5b-p103">一旦 Windows 10 裝置 Azure AD 加入，每位使用者應該重新啟動其裝置和其 Microsoft 365 商務認證登入。所有裝置現在都必須也內部資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="7fd5b-p104">沒有額外的步驟所需存取內部部署 Azure AD 的資源加入裝置。這是內建 Windows 10 中的可用的功能。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="7fd5b-117">如果您的組織尚未備妥要部署在 Azure AD 已加入裝置設定前文所述，請考慮設定[混合式 Azure AD Joined 裝置設定](manage-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="7fd5b-118">加入至 Azure AD 的 Windows 裝置時的考量</span><span class="sxs-lookup"><span data-stu-id="7fd5b-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="7fd5b-119">如果您是要加入先前已加入網域的 Windows 裝置的 Azure AD 或工作群組中，您需要考慮下列限制：</span><span class="sxs-lookup"><span data-stu-id="7fd5b-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="7fd5b-p105">當裝置 Azure AD 聯結時，它會建立新的使用者沒有參照現有的設定檔。若要修正此問題，需要以手動方式移轉設定檔。使用者設定檔包含類似我的最愛、 本機檔案、 瀏覽器設定、 開始] 功能表中設定等資訊。最好的作法是尋找協力廠商工具，以將現有的檔案及設定對應至新的設定檔</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="7fd5b-p106">如果裝置使用群組原則物件 (GPO)，有些 Gpo 可能沒有相較下[設定服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) Intune 中。執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)相較下的 Csp 尋找現有的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="7fd5b-p107">使用者無法驗證應用程式的 Active Directory 驗證而定。若要如何處理這評估使用舊版的應用程式並考慮更新，請儘可能使用經過驗證的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="7fd5b-p108">Active Directory 印表機探索將無法運作。若要修正此問題，對所有使用者提供直接印表機路徑或利用[混合雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="7fd5b-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

