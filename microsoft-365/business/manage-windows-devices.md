---
title: 啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理
f1.keywords:
- CSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 瞭解如何啟用 Microsoft 365，以在幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560836"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="d8bc9-103">啟用已加入網域的 Windows 10 裝置以由 Microsoft 365 商務版 Premium 管理</span><span class="sxs-lookup"><span data-stu-id="d8bc9-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="d8bc9-104">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="d8bc9-105">若要設定此保護，您可以執行**混合式 AZURE AD 聯結裝置**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="d8bc9-106">這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="d8bc9-107">這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="d8bc9-108">開始之前，請先確定您已完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d8bc9-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="d8bc9-109">使用 Azure AD Connect 將使用者同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="d8bc9-110">完成 Azure AD Connect 組織單位 (OU) sync。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="d8bc9-111">請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務版的授權。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d8bc9-112">如需步驟，請參閱[同步處理網域使用者至 Microsoft](manage-domain-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="d8bc9-113">1. 驗證 Intune 中的 MDM 授權</span><span class="sxs-lookup"><span data-stu-id="d8bc9-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="d8bc9-114">移至[端點管理員](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，然後在 Microsoft Intune 頁面上，選取 [**裝置註冊**]，然後在 [一覽] 頁面上，確定 **[** **MDM 授權**為**Intune**]。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="d8bc9-115">如果**mdm 授權**單位為**None**，請按一下**MDM 授權**單位將其設定為**Intune**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="d8bc9-116">如果**mdm 授權**是**Microsoft Office 365**，請移至 [**裝置]**  >  [**註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以加入**Intune MDM**授權 (只有當**MDM 機關**設定為 [Microsoft Office 365) 時，才可使用 [**新增 mdm 授權**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="d8bc9-117">2. 確認已針對加入的電腦啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="d8bc9-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="d8bc9-118">移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [ **Azure active directory** (]，在 [系統**管理中心**] 清單中看不到 [azure active directory]) 的 [全部顯示]。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="d8bc9-119">在**Azure Active directory 系統管理中心**中，移至 [ **azure active directory** ]，選擇 [**裝置**]，然後選擇 [**裝置設定**]。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="d8bc9-120">確認**使用者可以將裝置加入至 AZURE AD**已啟用</span><span class="sxs-lookup"><span data-stu-id="d8bc9-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="d8bc9-121">若要啟用所有使用者，請將設定為 [**全部**]。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="d8bc9-122">若要啟用特定使用者，請將設定為 [已**選擇**]，以啟用特定的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="d8bc9-123">將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="d8bc9-124">選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="d8bc9-125">3. 確認已為 MDM 啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="d8bc9-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="d8bc9-126">移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [Select **endpoint Managemen**t (選取 [**顯示所有**if**端點管理員**] 不可見) </span><span class="sxs-lookup"><span data-stu-id="d8bc9-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="d8bc9-127">在**Microsoft 端點**管理員系統管理中心中，移至 [**裝置**] [windows  >  **Windows**  >  **windows 註冊**]  >  **自動註冊**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="d8bc9-128">確認已啟用 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="d8bc9-129">若要註冊所有電腦，設定為 [**全部**] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 的使用者電腦和新電腦。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="d8bc9-130">設定為 [**部分**]，以註冊特定使用者群組的電腦。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="d8bc9-131">將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="d8bc9-132">選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="d8bc9-133">4. 建立必要的資源</span><span class="sxs-lookup"><span data-stu-id="d8bc9-133">4. Create the required resources</span></span> 

<span data-ttu-id="d8bc9-134">使用[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模組中的[Initialize-SecMgmtHybirdDeviceEnrollment 指令程式](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)，執行[設定混合式 Azure AD 聯結](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)所需的工作已得到簡化。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="d8bc9-135">當您呼叫此 Cmdlet 時，它會建立並設定所需的服務連線點和群組原則。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="d8bc9-136">您可以從 PowerShell: 實例中喚醒呼叫下列各項，以安裝此模組。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="d8bc9-137">建議您在執行 Azure AD Connect 的 Windows Server 上安裝此模組。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="d8bc9-138">若要建立所需的服務連線點和群組原則，您將會呼叫[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="d8bc9-139">當您執行此工作時，您將需要 Microsoft 365 商務版通用的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="d8bc9-140">當您準備好建立資源時，請呼叫下列專案：</span><span class="sxs-lookup"><span data-stu-id="d8bc9-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="d8bc9-141">第一個命令會建立與 Microsoft 雲端的連線，當系統提示時，請指定您的 Microsoft 365 商務版通用系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="d8bc9-142">5. 連結群組原則</span><span class="sxs-lookup"><span data-stu-id="d8bc9-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="d8bc9-143">在 [群組原則管理主控台 (GPMC) 中，以滑鼠右鍵按一下您要連結原則的位置，然後從快顯功能表中選取 [*連結現有的 GPO ...* ]。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="d8bc9-144">選取上一個步驟中建立的原則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="d8bc9-145">取得最新的系統管理範本</span><span class="sxs-lookup"><span data-stu-id="d8bc9-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="d8bc9-146">如果您看不到原則**使用預設 AZURE AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803、版本1809或版本1903安裝 ADMX。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="d8bc9-147">若要修正此問題，請遵循下列步驟 (附注：最新的 MDM 會向後相容) ：</span><span class="sxs-lookup"><span data-stu-id="d8bc9-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="d8bc9-148">下載： [Windows 10 的系統管理範本 ( admx) 可能2019更新 (1903) ](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="d8bc9-149">在網域主控站 (PDC) 上安裝套件。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="d8bc9-150">根據資料夾的版本來流覽： **C:\Program 檔案 (x86) \Microsoft Group Policy\Windows 10 可能 2019 Update (1903) v3**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="d8bc9-151">將上述路徑中的**原則定義**資料夾重新命名為**PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="d8bc9-152">將**PolicyDefinitions**資料夾複製到**C:\Windows\SYSVOL\domain\Policies**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="d8bc9-153">如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="d8bc9-154">重新開機網域主控站以供原則使用。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="d8bc9-155">此程式也適用于未來的任何版本。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="d8bc9-156">此時，您應該可以查看原則**使用預設 AZURE AD 認證啟用自動 MDM 註冊**。</span><span class="sxs-lookup"><span data-stu-id="d8bc9-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
