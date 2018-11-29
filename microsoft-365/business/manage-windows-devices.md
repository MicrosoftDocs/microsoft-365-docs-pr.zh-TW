---
title: 啟用 Microsoft 365 商務一併管理已加入網域的 Windows 10 裝置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何啟用來保護 Microsoft 365 本機 AD 加入 Windows 10 裝置。
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866268"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="6c5d9-103">啟用 Microsoft 365 商務一併管理已加入網域的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="6c5d9-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="6c5d9-p101">如果貴組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務來保護您的 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。您可以設定此由第一張使用同步處理您的 Active Directory Azure Active Directory，後面接著 Azure AD 登錄 Windows 10 裝置和其註冊由 Microsoft 365 商務行動裝置管理的。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="6c5d9-106">設為變成由 Microsoft 365 Business 已加入網域的裝置</span><span class="sxs-lookup"><span data-stu-id="6c5d9-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="6c5d9-p102">若要設定您的組織已加入網域的裝置到好處除了內部部署 Active Directory 的 Azure Active Directory 所提供的功能，您可以實作**混合 Azure AD 加入裝置**。這些是加入同時在內部部署 Active Directory 及 Azure Active Directory 的裝置。混合式 Azure AD 加入裝置可受保護及管理 Microsoft 365 商務.</span><span class="sxs-lookup"><span data-stu-id="6c5d9-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="6c5d9-110">完成下列步驟來讓您的 Windows 10 裝置混合加入，並且由 Microsoft 365 商務管理 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="6c5d9-111">若要進行使用者、 群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory、 執行目錄同步作業精靈和 Azure Active Directory 連線[設定 Office 365 的目錄同步作業](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)所述。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c5d9-112">步驟都完全相同的 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="6c5d9-113">完成步驟 3 啟用設為的混合 Azure AD 加入 Windows 10 裝置之前，您必須確定您符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="6c5d9-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="6c5d9-114">您正在執行 Azure AD 的最新版本連線。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="6c5d9-p103">Azure AD 連線已同步處理所有要加入 Azure AD 的混合式的裝置的電腦物件。如果電腦物件屬於特定組織單位 (OU)，請確定這些 Ou 已經設定為 Azure AD 的同步處理連線，以及。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="6c5d9-117">登錄現有已加入網域的 Windows 10 裝置混合 Azure AD Joined 及註冊他們的行動裝置管理由 Intune (Microsoft 365 Business)：</span><span class="sxs-lookup"><span data-stu-id="6c5d9-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="6c5d9-p104">遵循如何[設定混合式 Azure Active Directory 加入裝置](https://go.microsoft.com/fwlink/p/?linkid=872870)的逐步指示。這可讓您在內部部署 Active Directory 同步處理已加入 Windows 10 電腦，並使其雲端準備就緒。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="6c5d9-p105">若要註冊行動裝置管理的 Windows 10 裝置，請參閱[註冊使用群組原則 intune Windows 10 裝置](https://go.microsoft.com/fwlink/p/?linkid=872871)指示。您可以設定群組原則在本機電腦層級或大量作業，您可以建立此群組原則設定網域控制站伺服器上。</span><span class="sxs-lookup"><span data-stu-id="6c5d9-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

