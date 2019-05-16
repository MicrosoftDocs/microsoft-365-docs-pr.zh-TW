---
title: 啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何啟用 Microsoft 365，以保護本機 AD 加入的 Windows 10 裝置。
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071543"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="9ab0f-103">啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="9ab0f-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="9ab0f-104">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版來保護 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="9ab0f-105">您可以設定此第一個同步您的 Active Directory 與 Azure Active Directory，後面加上註冊的 Windows 10 裝置與 Azure AD 和註冊其適用於透過 Microsoft 365 商務版的行動裝置管理。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="9ab0f-106">已加入網域的裝置上設定為受 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9ab0f-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="9ab0f-107">若要設定您的組織已加入網域的裝置可受益於內部部署 Active Directory 除了 Azure Active Directory 所提供的功能，您可以實作**混合式 Azure AD 加入裝置**。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="9ab0f-108">這些是加入同時您在內部部署 Active Directory 和 Azure Active Directory 的裝置。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="9ab0f-109">混合式已加入 Azure AD 裝置可保護及由 Microsoft 365 商務版管理。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="9ab0f-110">完成下列步驟來進行 Windows 10 裝置混合式 Azure AD 加入，並且由 Microsoft 365 商務版管理。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="9ab0f-111">若要將您的使用者、 群組及連絡人從本機 Active Directory 同步處理到 Azure Active Directory，執行目錄同步處理精靈和 Azure Active Directory Connect 中[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)所述。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ab0f-112">步驟是完全相同的 Microsoft 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="9ab0f-113">完成步驟 3 以啟用設為混合式 Azure AD 加入的 Windows 10 裝置之前，您需要確定您符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="9ab0f-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="9ab0f-114">您正在執行最新版的 Azure AD connect。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="9ab0f-115">Azure AD connect 已同步處理使用者想要加入 Azure AD 的混合式的裝置的所有電腦物件。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="9ab0f-116">如果電腦物件屬於特定組織單位 (OU)，請確定這些 Ou 設定 Azure AD 中的同步處理連線以及。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="9ab0f-117">登錄現有已加入網域的 Windows 10 裝置是混合式 Azure AD Joined 和註冊其行動裝置管理由 Intune （Microsoft 365 商務版）：</span><span class="sxs-lookup"><span data-stu-id="9ab0f-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="9ab0f-118">請遵循[如何設定混合式 Azure Active Directory 加入裝置](https://go.microsoft.com/fwlink/p/?linkid=872870)中的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="9ab0f-119">這可讓您在內部部署 Active Directory 同步處理加入 Windows 10 電腦，並且使其雲端準備就緒。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="9ab0f-120">若要註冊的行動裝置管理的 Windows 10 裝置，請參閱如需相關指示[註冊 Intune 使用群組原則與 Windows 10 裝置](https://go.microsoft.com/fwlink/p/?linkid=872871)。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="9ab0f-121">您可以設定群組原則在本機電腦層級或針對大量作業，您可以建立這個群組原則設定網域控制站伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9ab0f-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>