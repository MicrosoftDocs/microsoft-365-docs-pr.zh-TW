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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 瞭解 Microsoft 365 商務版 Premium 的設定步驟，從訂閱、新增網域和使用者、設定安全性原則等等。
ms.openlocfilehash: 8b26d423d4f62ee8f9ea4a61eb8f7efa72ee26cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633348"
---
# <a name="overview-of-setup"></a><span data-ttu-id="aa050-103">步驟概觀</span><span class="sxs-lookup"><span data-stu-id="aa050-103">Overview of setup</span></span>

<span data-ttu-id="aa050-104">觀賞有關 Microsoft 365 商務版 Premium 設定的簡短影片。</span><span class="sxs-lookup"><span data-stu-id="aa050-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="aa050-105">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="aa050-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="aa050-106">您可以在安裝精靈中執行大部分的設定步驟，但也會列出其他選項。</span><span class="sxs-lookup"><span data-stu-id="aa050-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="aa050-107">步驟1：新增您的網域和使用者</span><span class="sxs-lookup"><span data-stu-id="aa050-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="aa050-108">**[新增您的網域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果您已在[註冊](sign-up.md)時購買網域，此步驟已經完成。）</span><span class="sxs-lookup"><span data-stu-id="aa050-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="aa050-109">**新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="aa050-109">**Add users**.</span></span> <span data-ttu-id="aa050-110">您可以以三種方式來新增使用者：</span><span class="sxs-lookup"><span data-stu-id="aa050-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="aa050-111">在[嚮導](set-up.md#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="aa050-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="aa050-112">如果您有內部部署 Active directory，請使用目錄同步處理以[使用 AZURE AD Connect 新增使用者](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="aa050-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="aa050-113">您也可以稍後在系統管理中心[新增使用者](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="aa050-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="aa050-114">步驟2：設定安全性原則及設定裝置</span><span class="sxs-lookup"><span data-stu-id="aa050-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="aa050-115">使用[設定向導](set-up.md#protect-your-organization)來設定裝置原則。</span><span class="sxs-lookup"><span data-stu-id="aa050-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="aa050-116">您也可以在系統[管理中心](view-policies-and-devices.md)及[Intune 入口網站](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中新增更多內容或進行編輯。</span><span class="sxs-lookup"><span data-stu-id="aa050-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="aa050-117">安裝精靈也會設定基本威脅防護和資料遺失防護設定。</span><span class="sxs-lookup"><span data-stu-id="aa050-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="aa050-118">除了安裝精靈中的安全性設定之外，您還可以新增下列設定來增加您的安全性：</span><span class="sxs-lookup"><span data-stu-id="aa050-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="aa050-119">**電子郵件惡意程式碼保護**</span><span class="sxs-lookup"><span data-stu-id="aa050-119">**Email malware protection**</span></span>
- <span data-ttu-id="aa050-120">**ATP 反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="aa050-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="aa050-121">**Exchange Online 封存**</span><span class="sxs-lookup"><span data-stu-id="aa050-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="aa050-122">**Azure 資訊保護（Plan1**）</span><span class="sxs-lookup"><span data-stu-id="aa050-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="aa050-123">若要開始，請參閱[增加威脅防護](increase-threat-protection.md)和[設定規范功能](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="aa050-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="aa050-124">請參閱[保護您的 Microsoft 365 商務版的十大方式](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)，以取得最佳安全性作法的藍圖。</span><span class="sxs-lookup"><span data-stu-id="aa050-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="aa050-125">步驟3：設定及管理 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="aa050-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="aa050-126">在您執行設定向導之後，您會想要 proctect 您組織中的所有 Windwos 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="aa050-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="aa050-127">Windows 10 專業版是 Microsoft 365 商務版[Premium 的必要條件](pre-requisites-for-data-protection.md)，但如果您有 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 專業人員，您的訂閱可讓您[升級至 Windows 10 專業](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。</span><span class="sxs-lookup"><span data-stu-id="aa050-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="aa050-128">請遵循[Secure Windows 10 電腦](secure-win-10-pcs.md)中的步驟來設定 windows 10 裝置的原則。</span><span class="sxs-lookup"><span data-stu-id="aa050-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="aa050-129">當您將 Windows 10 裝置加入 Azure AD 時，您為 Windows 10 電腦所設定的原則會套用至該 AD。</span><span class="sxs-lookup"><span data-stu-id="aa050-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="aa050-130">如需詳細資訊，請參閱為[Microsoft 365 使用者設定 Windows 裝置](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="aa050-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="aa050-131">步驟4：安裝 Microsoft 365 商務應用程式</span><span class="sxs-lookup"><span data-stu-id="aa050-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="aa050-132">您可以使用 [[安裝精靈]](set-up.md#deploy-office-365-client-apps)，在 Windows 裝置中自動安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="aa050-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="aa050-133">讓使用者安裝適用于 Windows 和裝置的[Office 應用程式](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="aa050-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="aa050-134">進階</span><span class="sxs-lookup"><span data-stu-id="aa050-134">Advanced</span></span>
- <span data-ttu-id="aa050-135">**使用 Autopilot 來設定新裝置**</span><span class="sxs-lookup"><span data-stu-id="aa050-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="aa050-136">您可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)為使用者自動預先設定**新**的 Windows 10 裝置，但是取得可為您做這項作業的[合作夥伴](https://www.microsoft.com/solution-providers/search)會比較容易。</span><span class="sxs-lookup"><span data-stu-id="aa050-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="aa050-137">您也可以前往[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)，並要求雲端技術專家設定您購買的新裝置。</span><span class="sxs-lookup"><span data-stu-id="aa050-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="aa050-138">**存取內部部署的資料**</span><span class="sxs-lookup"><span data-stu-id="aa050-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="aa050-139">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。</span><span class="sxs-lookup"><span data-stu-id="aa050-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="aa050-140">請遵循下列步驟，將已[加入網域的 Windows 10 裝置設定為由 Microsoft 365 商務版管理](manage-windows-devices.md)，以加以設定。</span><span class="sxs-lookup"><span data-stu-id="aa050-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="aa050-141">這是慣用的方法，而此狀態的裝置稱為混合式 Azure AD join 裝置。</span><span class="sxs-lookup"><span data-stu-id="aa050-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="aa050-142">如果您的公司有包含某些內部部署資源（如檔案共用和印表機）的本機 Active Directory，您可以遵循下列步驟，將您的 Azure 已加入的裝置存取這些資源：[從 Microsoft 365 商務版 Premium 中的 Azure 已加入 Azure 裝置存取內部部署資源](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="aa050-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa050-143">請參閱</span><span class="sxs-lookup"><span data-stu-id="aa050-143">See also</span></span>

[<span data-ttu-id="aa050-144">Microsoft 365 商務用訓練影片</span><span class="sxs-lookup"><span data-stu-id="aa050-144">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
