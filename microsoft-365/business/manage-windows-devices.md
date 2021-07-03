---
title: 啟用已加入網域的 Windows 10 裝置以供商務 Microsoft 365 管理
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 瞭解如何啟用 Microsoft 365，以在少數幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: eb95c437030ae13a44f5e8043b3544d5846001c2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287688"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="ad69e-103">啟用已加入網域的 Windows 10 裝置以供 Microsoft 365 商務進階版管理</span><span class="sxs-lookup"><span data-stu-id="ad69e-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="ad69e-104">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務進階版來保護 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。</span><span class="sxs-lookup"><span data-stu-id="ad69e-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="ad69e-105">若要設定此保護，您可以執行 **混合式 AZURE AD 聯結裝置**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="ad69e-106">這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ad69e-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="ad69e-107">觀賞：設定混合式 Azure Active Directory 聯結</span><span class="sxs-lookup"><span data-stu-id="ad69e-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="ad69e-108">這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。</span><span class="sxs-lookup"><span data-stu-id="ad69e-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="ad69e-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="ad69e-109">Before you begin</span></span>

- <span data-ttu-id="ad69e-110">使用 Azure AD 連線將使用者同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ad69e-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="ad69e-111"> (OU) 同步處理完成 Azure AD 連線組織單位。</span><span class="sxs-lookup"><span data-stu-id="ad69e-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="ad69e-112">請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務進階版的授權。</span><span class="sxs-lookup"><span data-stu-id="ad69e-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="ad69e-113">如需步驟，請參閱 [同步處理網域使用者至 Microsoft](manage-domain-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="ad69e-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="ad69e-114">1. 驗證 Intune 中的 MDM 授權</span><span class="sxs-lookup"><span data-stu-id="ad69e-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="ad69e-115">移至 [端點管理員](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，然後在 [Microsoft Intune] 頁面上，選取 [**裝置註冊**]，然後在 [概覽] 頁面上，確定 **[** **MDM 授權** 為 **Intune**]。</span><span class="sxs-lookup"><span data-stu-id="ad69e-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="ad69e-116">如果 **mdm 授權** 單位為 **None**，請按一下 **MDM 授權** 單位將其設定為 **Intune**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="ad69e-117">如果已 **Microsoft Office 365** **mdm 授權**，請移至 [**裝置**] [  >  **註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以加入 **Intune MDM** 機關 (只有當 **MDM 授權** 設定為 Microsoft Office 365) 時，才可使用 [**新增 mdm 授權**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ad69e-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="ad69e-118">2. 確認已針對加入的電腦啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="ad69e-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="ad69e-119">移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [ **Azure Active Directory** (在 [系統 **管理中心**] 清單) 沒有看見 Azure Active Directory 時，請選取 [全部顯示]。</span><span class="sxs-lookup"><span data-stu-id="ad69e-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="ad69e-120">在 **Azure Active Directory 系統管理中心**，移至 [ **Azure Active Directory** ]，選擇 [**裝置**]，然後選擇 [**裝置設定**]。</span><span class="sxs-lookup"><span data-stu-id="ad69e-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="ad69e-121">確認 **使用者可以將裝置加入至 AZURE AD** 已啟用</span><span class="sxs-lookup"><span data-stu-id="ad69e-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="ad69e-122">若要啟用所有使用者，請將設定為 [ **全部**]。</span><span class="sxs-lookup"><span data-stu-id="ad69e-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="ad69e-123">若要啟用特定使用者，請將設定為 [已 **選擇** ]，以啟用特定的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="ad69e-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="ad69e-124">將 Azure AD 中已同步處理的所需網域使用者新增至 [安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="ad69e-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="ad69e-125">選擇 [ **選取群組** ]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="ad69e-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="ad69e-126">3. 確認已為 MDM 啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="ad69e-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="ad69e-127">移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [select **Endpoint Managemen** t (] [如果不顯示 **端點管理員**，請選取 **全部顯示**]) </span><span class="sxs-lookup"><span data-stu-id="ad69e-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="ad69e-128">在 **Microsoft 端點管理員系統管理中心**，移至 [**裝置**]  >  **Windows**  >  **Windows 註冊**  >  **自動註冊**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="ad69e-129">確認已啟用 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="ad69e-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="ad69e-130">若要註冊所有電腦，設定為 [**全部**] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 和新電腦的使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="ad69e-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="ad69e-131">設定為 [ **部分** ]，以註冊特定使用者群組的電腦。</span><span class="sxs-lookup"><span data-stu-id="ad69e-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="ad69e-132">將 Azure AD 中已同步處理的所需網域使用者新增至 [安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="ad69e-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="ad69e-133">選擇 [ **選取群組** ]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="ad69e-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="ad69e-134">4. 建立必要的資源</span><span class="sxs-lookup"><span data-stu-id="ad69e-134">4. Create the required resources</span></span> 

<span data-ttu-id="ad69e-135">使用[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模組中的[Initialize-SecMgmtHybirdDeviceEnrollment 指令程式](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)，執行[設定混合式 Azure AD 聯結](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)所需的工作已得到簡化。</span><span class="sxs-lookup"><span data-stu-id="ad69e-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="ad69e-136">當您呼叫此 Cmdlet 時，它會建立並設定所需的服務連線點和群組原則。</span><span class="sxs-lookup"><span data-stu-id="ad69e-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="ad69e-137">您可以從 PowerShell: 實例中喚醒呼叫下列各項，以安裝此模組。</span><span class="sxs-lookup"><span data-stu-id="ad69e-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="ad69e-138">建議您在執行 Azure AD 連線的 Windows 伺服器上安裝此模組。</span><span class="sxs-lookup"><span data-stu-id="ad69e-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="ad69e-139">若要建立所需的服務連線點和群組原則，您將會呼叫  [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad69e-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="ad69e-140">當您執行此工作時，您將需要 Microsoft 365 商務進階版全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="ad69e-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="ad69e-141">當您準備好建立資源時，請呼叫下列專案：</span><span class="sxs-lookup"><span data-stu-id="ad69e-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="ad69e-142">第一個命令會建立與 Microsoft 雲端的連線，當出現提示時，請指定您的 Microsoft 365 商務進階版全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="ad69e-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="ad69e-143">5. 連結群組原則</span><span class="sxs-lookup"><span data-stu-id="ad69e-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="ad69e-144">在 [群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要連結原則的位置，然後從快顯功能表中選取 [ *連結現有的 GPO ...* ]。</span><span class="sxs-lookup"><span data-stu-id="ad69e-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="ad69e-145">選取上一個步驟中建立的原則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="ad69e-146">取得最新的系統管理範本</span><span class="sxs-lookup"><span data-stu-id="ad69e-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="ad69e-147">如果您看不到原則 **使用預設 Azure AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803或更新版本安裝 ADMX。</span><span class="sxs-lookup"><span data-stu-id="ad69e-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="ad69e-148">若要修正此問題，請遵循下列步驟 (附注：最新的 MDM 會向後相容) ：</span><span class="sxs-lookup"><span data-stu-id="ad69e-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1. <span data-ttu-id="ad69e-149">下載： [Windows 10 10 月2020更新 (20H2) 的系統管理範本 ( admx) ](https://www.microsoft.com/download/102157)。</span><span class="sxs-lookup"><span data-stu-id="ad69e-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2. <span data-ttu-id="ad69e-150">在網域控制站上安裝套件。</span><span class="sxs-lookup"><span data-stu-id="ad69e-150">Install the package on a Domain Controller.</span></span>
3. <span data-ttu-id="ad69e-151">根據系統管理範本的版本，流覽至資料夾： **C:\Program 檔案 (x86) \microsoft 群組原則 \ Windows 10 10 月2020更新 (20H2)**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4. <span data-ttu-id="ad69e-152">將上述路徑中的 **原則定義** 資料夾重新命名為 **PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5. <span data-ttu-id="ad69e-153">將 **PolicyDefinitions** 資料夾複製到 SYSVOL 共用，預設位置為 **C：\ Windows \SYSVOL\domain\Policies**。</span><span class="sxs-lookup"><span data-stu-id="ad69e-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span>
   - <span data-ttu-id="ad69e-154">如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。</span><span class="sxs-lookup"><span data-stu-id="ad69e-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6. <span data-ttu-id="ad69e-155">如果您有多個網域控制站，請等候 SYSVOL 進行複製，以供使用原則。</span><span class="sxs-lookup"><span data-stu-id="ad69e-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="ad69e-156">此程式適用于任何未來版本的系統管理範本。</span><span class="sxs-lookup"><span data-stu-id="ad69e-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="ad69e-157">此時，您應該可以查看原則 **使用預設 AZURE AD 認證啟用自動 MDM 註冊** 。</span><span class="sxs-lookup"><span data-stu-id="ad69e-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="ad69e-158">相關內容</span><span class="sxs-lookup"><span data-stu-id="ad69e-158">Related content</span></span>

<span data-ttu-id="ad69e-159">[同步處理網域使用者 Microsoft 365](manage-domain-users.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ad69e-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="ad69e-160">[在系統管理中心中建立群組](../admin/create-groups/create-groups.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ad69e-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="ad69e-161">[教程：設定受管理網域的混合式 Azure Active Directory 加入](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ad69e-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>