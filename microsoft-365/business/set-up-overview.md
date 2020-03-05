---
title: 步驟概觀
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解 Microsoft 365 商務版，從訂閱，來新增網域與使用者、 設定安全性原則和其他的設定步驟。
ms.openlocfilehash: 75ef784a886de754e7550d9e86af1242209346dd
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417219"
---
# <a name="overview-of-setup"></a><span data-ttu-id="c592c-103">步驟概觀</span><span class="sxs-lookup"><span data-stu-id="c592c-103">Overview of setup</span></span>

<span data-ttu-id="c592c-104">觀看有關 Microsoft 365 商務版安裝程式。</span><span class="sxs-lookup"><span data-stu-id="c592c-104">Watch a short video about Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="c592c-105">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="c592c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="c592c-106">可以在安裝程式精靈] 完成大部分的設定步驟，但也會列出其他選項。</span><span class="sxs-lookup"><span data-stu-id="c592c-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="c592c-107">步驟 1： 加入您的網域和使用者</span><span class="sxs-lookup"><span data-stu-id="c592c-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="c592c-108">**[新增您的網域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果您在[註冊](sign-up.md)購買您的網域，為已完成這個步驟。）</span><span class="sxs-lookup"><span data-stu-id="c592c-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="c592c-109">**新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="c592c-109">**Add users**.</span></span> <span data-ttu-id="c592c-110">您可以在任何的三種方式新增使用者：</span><span class="sxs-lookup"><span data-stu-id="c592c-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="c592c-111">在[精靈](set-up.md#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="c592c-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="c592c-112">如果您有內部部署 Active directory，請使用新增[的使用者使用 Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="c592c-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="c592c-113">您也可以在系統管理中心的 [[新增使用者更新版本](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="c592c-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="c592c-114">步驟 2： 設定安全性原則和設定裝置</span><span class="sxs-lookup"><span data-stu-id="c592c-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="c592c-115">使用[安裝精靈](set-up.md#protect-your-organization)來設定裝置原則。</span><span class="sxs-lookup"><span data-stu-id="c592c-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="c592c-116">您也可以新增更多，或稍後在[系統管理中心](view-policies-and-devices.md)和[Intune 入口網站](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中加以編輯。</span><span class="sxs-lookup"><span data-stu-id="c592c-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="c592c-117">安裝精靈 」 也會設定基本威脅保護和資料遺失防護設定。</span><span class="sxs-lookup"><span data-stu-id="c592c-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="c592c-118">除了在安裝精靈中的安全性設定，您可以藉由新增下列設定值增加您的安全性：</span><span class="sxs-lookup"><span data-stu-id="c592c-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="c592c-119">**電子郵件的惡意程式碼保護**</span><span class="sxs-lookup"><span data-stu-id="c592c-119">**Email malware protection**</span></span>
- <span data-ttu-id="c592c-120">**ATP 防網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c592c-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="c592c-121">**Exchange Online 封存**</span><span class="sxs-lookup"><span data-stu-id="c592c-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="c592c-122">**Azure 資訊保護 (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="c592c-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="c592c-123">若要開始，請參閱[增加威脅防護](increase-threat-protection.md)，並[設定符合性功能](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c592c-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="c592c-124">另請參閱[上方的 10 種方法來保護您的 Microsoft 365 商務版](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的最佳安全性作法藍圖。</span><span class="sxs-lookup"><span data-stu-id="c592c-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="c592c-125">步驟 3： 設定及管理 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="c592c-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="c592c-126">執行設定精靈之後，您會想要 proctect Windwos 10 的所有電腦貴組織中。</span><span class="sxs-lookup"><span data-stu-id="c592c-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="c592c-127">Windows 10 專業版是 Microsoft 365 商務版的[必要條件](pre-requisites-for-data-protection.md)，但如果您有 Windows 7 專業版、 Windows 8 專業版或 Windows 8.1 專業版，您的訂閱賦與您[升級至 Windows 10 專業版](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)。</span><span class="sxs-lookup"><span data-stu-id="c592c-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="c592c-128">遵循設定 Windows 10 裝置原則[保護 Windows 10 電腦](secure-win-10-pcs.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c592c-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="c592c-129">當您在 Windows 10 裝置加入 Azure AD 時，取得套用所設定的 Windows 10 電腦的原則。</span><span class="sxs-lookup"><span data-stu-id="c592c-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="c592c-130">如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="c592c-130">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="c592c-131">步驟 4： 安裝 Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="c592c-131">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="c592c-132">您可以使用[安裝精靈](set-up.md#deploy-office-365-client-apps)，在 Windows 裝置上自動安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="c592c-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="c592c-133">Windows 和裝置，可讓使用者[安裝 Office 應用程式](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="c592c-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="c592c-134">進階</span><span class="sxs-lookup"><span data-stu-id="c592c-134">Advanced</span></span>
- <span data-ttu-id="c592c-135">**使用 Autopilot 來設定新裝置**</span><span class="sxs-lookup"><span data-stu-id="c592c-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="c592c-136">您可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)來自動預先設定**新**的 Windows 10 裝置的使用者，但它可能會比較容易取得[合作夥伴](https://www.microsoft.com/solution-providers/search)可以執行這項操作您。</span><span class="sxs-lookup"><span data-stu-id="c592c-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="c592c-137">您也可以移至[Microsoft 網上商店](https://go.microsoft.com/fwlink/?linkid=874598)，並要求 cloud 技術專家您購買的新裝置上設定。</span><span class="sxs-lookup"><span data-stu-id="c592c-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="c592c-138">**存取內部部署的資料**</span><span class="sxs-lookup"><span data-stu-id="c592c-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="c592c-139">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版來保護 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="c592c-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="c592c-140">請遵循[啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)設定此案例中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c592c-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="c592c-141">這是慣用的方法，並在此狀態的裝置稱為混合式 Azure AD 加入的裝置。</span><span class="sxs-lookup"><span data-stu-id="c592c-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="c592c-142">如果貴公司有本機 Active Directory，其中包含一些內部資源 （例如檔案共用和印表機），您可以授與您的 Azure AD 加入的裝置存取這些資源遵循以下步驟：[存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="c592c-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c592c-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c592c-143">See also</span></span>

[<span data-ttu-id="c592c-144">Microsoft 365 商務版訓練影片</span><span class="sxs-lookup"><span data-stu-id="c592c-144">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
