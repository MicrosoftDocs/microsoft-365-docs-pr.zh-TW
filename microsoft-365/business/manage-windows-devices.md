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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564924"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="1c4e7-103">啟用已加入網域的 Windows 10 裝置以由 Microsoft 365 商務版 Premium 管理</span><span class="sxs-lookup"><span data-stu-id="1c4e7-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1c4e7-104">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="1c4e7-105">若要設定此保護，您可以執行**混合式 AZURE AD 聯結裝置**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="1c4e7-106">這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="1c4e7-107">這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="1c4e7-108">開始之前，請先確定您已完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1c4e7-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="1c4e7-109">使用 Azure AD Connect 將使用者同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="1c4e7-110">完成 Azure AD Connect 組織單位（OU）同步處理。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="1c4e7-111">請確定您同步處理的所有網域使用者都具有 Microsoft 365 商務版的授權。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="1c4e7-112">如需步驟，請參閱[同步處理網域使用者至 Microsoft](manage-domain-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="1c4e7-113">1. 驗證 Intune 中的 MDM 授權</span><span class="sxs-lookup"><span data-stu-id="1c4e7-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="1c4e7-114">移至 [portal.azure.com]，並在 [頁面搜尋] 上方的 [Intune] 搜尋。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="1c4e7-115">在 [Microsoft Intune] 頁面上，選取 [**裝置註冊**]，然後在 [**概覽**] 頁面上，確認**MDM 授權**為**Intune**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="1c4e7-116">如果**mdm 授權**單位為**None**，請按一下**MDM 授權**單位將其設定為**Intune**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="1c4e7-117">如果**mdm 授權**是**Microsoft Office 365**，請移至 [**裝置]**  >  [**註冊裝置**]，並使用右側的 [**新增 mdm 授權機構**] 對話方塊，以新增**Intune MDM**授權（[**新增 mdm 機關**] 對話方塊只有在**MDM 授權**設定為 [Microsoft Office 365] 時才可用）。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="1c4e7-118">2. 確認已針對加入的電腦啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c4e7-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="1c4e7-119">移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，並選取 [ **Azure active directory** ] （如果未顯示 azure active directory，請選取 [全部顯示**Admin centers**所有專案）] 清單中的 [azure active directory]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="1c4e7-120">在**Azure Active directory 系統管理中心**中，移至 [ **azure active directory** ]，選擇 [**裝置**]，然後選擇 [**裝置設定**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="1c4e7-121">確認**使用者可以將裝置加入至 AZURE AD**已啟用</span><span class="sxs-lookup"><span data-stu-id="1c4e7-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="1c4e7-122">若要啟用所有使用者，請將設定為 [**全部**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="1c4e7-123">若要啟用特定使用者，請將設定為 [已**選擇**]，以啟用特定的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="1c4e7-124">將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="1c4e7-125">選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="1c4e7-126">3. 確認已為 MDM 啟用 Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c4e7-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="1c4e7-127">移至系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然後選取 [Select **endpoint Managemen**t （選取所有 if**端點管理員**時不會**顯示所有**的）]</span><span class="sxs-lookup"><span data-stu-id="1c4e7-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="1c4e7-128">在**Microsoft 端點**管理員系統管理中心中，移至 [**裝置**] [windows  >  **Windows**  >  **windows 註冊**]  >  **自動註冊**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="1c4e7-129">確認已啟用 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="1c4e7-130">若要註冊所有電腦，設定為 [**全部**] 可在使用者將工作帳戶新增至 Windows 時，自動註冊所有加入 Azure AD 的使用者電腦和新電腦。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="1c4e7-131">設定為 [**部分**]，以註冊特定使用者群組的電腦。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="1c4e7-132">將 Azure AD 中已同步處理的所需網域使用者新增至[安全性群組](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="1c4e7-133">選擇 [**選取群組**]，以啟用該安全性群組的 MDM 使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="1c4e7-134">4. 設定服務連線點（SCP）</span><span class="sxs-lookup"><span data-stu-id="1c4e7-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="1c4e7-135">您可以從[設定混合式 AZURE AD 聯結](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)簡化這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="1c4e7-136">若要完成使用 Azure AD Connect 和您的 Microsoft 365 商務版全域管理員和 Active Directory 系統管理員密碼所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="1c4e7-137">啟動 Azure AD Connect，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="1c4e7-138">在 [**其他**工作] 頁面上，選取 [**設定裝置選項**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="1c4e7-139">在 [**概覽**] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="1c4e7-140">在 [連線**到 AZURE AD]** 頁面上，輸入 Microsoft 365 商務版 Premium 全域管理員的認證。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="1c4e7-141">在 [**裝置選項**] 頁面上，選取 [**設定混合式 Azure AD 聯結**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="1c4e7-142">在 [ **SCP** ] 頁面上，針對您要 Azure AD Connect 以設定 SCP 的每個樹系，完成下列步驟，然後選取 **[下一步]**：</span><span class="sxs-lookup"><span data-stu-id="1c4e7-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="1c4e7-143">選取樹系名稱旁邊的方塊。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-143">Check the box beside the forest name.</span></span> <span data-ttu-id="1c4e7-144">樹系應該是您的 AD 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="1c4e7-145">在 [**驗證服務**] 欄下，開啟下拉式清單，然後選取 [相符的功能變數名稱] （應該只有一個選項）。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="1c4e7-146">選取 [**新增**]，輸入網域管理員認證。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="1c4e7-147">在 [**裝置作業系統**] 頁面上，只選取 [Windows 10 或更新版本的加入網域的裝置]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="1c4e7-148">在 [**準備設定**] 頁面上，選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="1c4e7-149">在 [設定完成] 頁面上 **，選取 [\*\*\*\*結束**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="1c4e7-150">5. 建立 GPO 以供 Intune 登記– ADMX 方法</span><span class="sxs-lookup"><span data-stu-id="1c4e7-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="1c4e7-151">使用。ADMX 範本檔案。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="1c4e7-152">登入 AD server、搜尋及開啟**伺服器管理員**  >  **工具**  >  **群組原則管理**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="1c4e7-153">選取 [**網域**] 底下的功能變數名稱，然後在 [**群組原則物件**] 上按一下滑鼠右鍵，選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="1c4e7-154">提供新的 GPO 名稱，例如 "*Cloud_Enrollment*"，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="1c4e7-155">在 [**群組原則物件**] 底下的新 GPO 上按一下滑鼠右鍵，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="1c4e7-156">在 [**群組原則管理編輯器**] 中，移至 [電腦設定原則] [**系統**  >  **Policies**  >  **管理範本] 「管理範本**」  >  **Windows 元件**  >  **MDM**</span><span class="sxs-lookup"><span data-stu-id="1c4e7-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="1c4e7-157">以滑鼠右鍵按一下 [**啟用預設 Azure AD 認證的自動 MDM 註冊**]，然後選取 [**啟用**  >  **確定]**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="1c4e7-158">關閉 [編輯器] 視窗。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c4e7-159">如果您未看到原則**使用預設 AZURE AD 認證啟用自動 MDM 註冊**，請參閱[取得最新的系統管理範本](#get-the-latest-administrative-templates)。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="1c4e7-160">6. 部署群組原則</span><span class="sxs-lookup"><span data-stu-id="1c4e7-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="1c4e7-161">在 [伺服器管理員] 的 [**網域**> 群組原則物件] 底下，選取上述步驟3中的 GPO，例如 "Cloud_Enrollment"。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="1c4e7-162">為您的 GPO 選取 [**範圍**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="1c4e7-163">在 GPO 的 [範圍] 索引標籤中，以滑鼠右鍵按一下 [**連結**] 底下的 [網域] 連結。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="1c4e7-164">選取 [**強制**]，以部署 GPO，然後在確認畫面中按一下 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="1c4e7-165">取得最新的系統管理範本</span><span class="sxs-lookup"><span data-stu-id="1c4e7-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="1c4e7-166">如果您看不到原則**使用預設 AZURE AD 認證來啟用自動 MDM 註冊**，可能是因為您沒有為 Windows 10、版本1803、版本1809或版本1903安裝 ADMX。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="1c4e7-167">若要修正此問題，請遵循下列步驟（附注：最新的 MDM 會向後相容）：</span><span class="sxs-lookup"><span data-stu-id="1c4e7-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="1c4e7-168">下載： [Windows 10 的系統管理範本（admx）可能是2019更新（1903）](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="1c4e7-169">在網域主控站（PDC）上安裝套件。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="1c4e7-170">根據資料夾的版本來流覽： **C:\Program 檔案（x86） \Microsoft Group Policy\Windows 10 可能2019更新（1903） v3**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="1c4e7-171">將上述路徑中的**原則定義**資料夾重新命名為**PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="1c4e7-172">將**PolicyDefinitions**資料夾複製到**C:\Windows\SYSVOL\domain\Policies**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="1c4e7-173">如果您打算使用整個網域的中央原則存放區，請在那裡新增 PolicyDefinitions 的內容。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="1c4e7-174">重新開機網域主控站以供原則使用。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="1c4e7-175">此程式也適用于未來的任何版本。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="1c4e7-176">此時，您應該可以查看原則**使用預設 AZURE AD 認證啟用自動 MDM 註冊**。</span><span class="sxs-lookup"><span data-stu-id="1c4e7-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

