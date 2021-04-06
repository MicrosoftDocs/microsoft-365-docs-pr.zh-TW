---
title: 在 Microsoft Defender ATP 中設定條件式存取
description: 深入瞭解在 Intune、Microsoft Defender Security Center 和 Azure 中執行條件式存取所需的步驟
keywords: 條件式存取、條件化、存取、裝置風險、風險層級、整合、intune 整合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165858"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f9124-104">在 Microsoft Defender for Endpoint 中設定條件式存取</span><span class="sxs-lookup"><span data-stu-id="f9124-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9124-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f9124-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9124-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f9124-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f9124-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9124-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f9124-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f9124-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f9124-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f9124-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f9124-110">本節會引導您完成所有必須執行的步驟，才能正確地執行條件式存取。</span><span class="sxs-lookup"><span data-stu-id="f9124-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="f9124-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="f9124-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="f9124-112">請務必注意，此案例中不支援 Azure AD 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="f9124-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="f9124-113">只支援 Intune 註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="f9124-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="f9124-114">您必須確定您的所有裝置都已在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="f9124-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="f9124-115">您可以使用下列任何選項，在 Intune 中註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="f9124-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="f9124-116">IT 系統管理員：如需如何啟用自動註冊的詳細資訊，請參閱 [Windows 註冊](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="f9124-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="f9124-117">使用者：如需如何在 Intune 中註冊 Windows 10 裝置的詳細資訊，請參閱 [在 intune 中註冊您的 windows 10 裝置](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="f9124-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="f9124-118">使用者替代：如需有關加入 Azure AD 網域的詳細資訊，請參閱 how [to： Plan a AZURE ad join 實現](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="f9124-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="f9124-119">在 Microsoft Defender 安全中心、Intune 入口網站和 Azure AD 入口網站中，您必須採取下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f9124-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="f9124-120">請務必注意存取這些入口網站所需的角色，並執行條件式存取：</span><span class="sxs-lookup"><span data-stu-id="f9124-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="f9124-121">**Microsoft Defender 安全中心** -您必須以全域系統管理員角色登入入口網站，才能開啟整合。</span><span class="sxs-lookup"><span data-stu-id="f9124-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="f9124-122">**Intune** -您必須使用具有管理許可權的安全性系統管理員許可權登入入口網站。</span><span class="sxs-lookup"><span data-stu-id="f9124-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="f9124-123">**AZURE AD 入口網站** -您必須以全域系統管理員、安全性管理員或條件式存取管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="f9124-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="f9124-124">您將需要 Microsoft Intune 環境（Intune managed 和 Azure AD 加入的 Windows 10 裝置）。</span><span class="sxs-lookup"><span data-stu-id="f9124-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="f9124-125">請執行下列步驟來啟用條件式存取：</span><span class="sxs-lookup"><span data-stu-id="f9124-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="f9124-126">步驟1：從 Microsoft Defender 安全中心開啟 Microsoft Intune 連線</span><span class="sxs-lookup"><span data-stu-id="f9124-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="f9124-127">步驟2：在 Intune 中開啟用於端點整合的 Defender</span><span class="sxs-lookup"><span data-stu-id="f9124-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="f9124-128">步驟3：在 Intune 中建立相容性原則</span><span class="sxs-lookup"><span data-stu-id="f9124-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="f9124-129">步驟4：指派原則</span><span class="sxs-lookup"><span data-stu-id="f9124-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="f9124-130">步驟5：建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f9124-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="f9124-131">步驟1：開啟 Microsoft Intune 連線</span><span class="sxs-lookup"><span data-stu-id="f9124-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="f9124-132">在功能窗格中，選取 [**設定**  >  **高級功能**] [  >  **Microsoft Intune connection**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="f9124-133">將 Microsoft Intune 設定切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="f9124-134">按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="f9124-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="f9124-135">步驟2：在 Intune 中開啟用於端點整合的 Defender</span><span class="sxs-lookup"><span data-stu-id="f9124-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="f9124-136">登入 [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="f9124-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f9124-137">選取 [**裝置規範**] [  >  **Microsoft Defender ATP**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="f9124-138">將 **[連線 Windows 10.0.15063 + 裝置至 Microsoft Defender 高級威脅防護]** 設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="f9124-139">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f9124-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="f9124-140">步驟3：在 Intune 中建立相容性原則</span><span class="sxs-lookup"><span data-stu-id="f9124-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="f9124-141">在 [Azure 入口網站](https://portal.azure.com)中，選取 [ **所有服務**]、[在 **Intune** 上篩選]，然後選取 [ **Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="f9124-142">選取 [**裝置規範**  >  **原則**] [  >  **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="f9124-143">輸入 **名稱** 和 **描述**。</span><span class="sxs-lookup"><span data-stu-id="f9124-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="f9124-144">在 [ **平臺**] 中，選取 [ **Windows 10 和更新版本**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="f9124-145">在 [ **裝置健康情況** 設定] 中，設定 **[要求裝置位於或低於裝置威脅層級** ] 的首選層級：</span><span class="sxs-lookup"><span data-stu-id="f9124-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="f9124-146">**安全**：這是最安全的層級。</span><span class="sxs-lookup"><span data-stu-id="f9124-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="f9124-147">裝置不能有任何現有威脅，但仍然可以存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="f9124-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="f9124-148">如果找到任何威脅，裝置就會評估為不相容。</span><span class="sxs-lookup"><span data-stu-id="f9124-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="f9124-149">**Low**：只有低層級威脅存在時，裝置才符合。</span><span class="sxs-lookup"><span data-stu-id="f9124-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="f9124-150">具有中低或高威脅層級的裝置不相容。</span><span class="sxs-lookup"><span data-stu-id="f9124-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="f9124-151">**中**：如果裝置上所發現的威脅為低或適中，裝置就符合。</span><span class="sxs-lookup"><span data-stu-id="f9124-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="f9124-152">如果偵測到高層級威脅，裝置會決定為不相容。</span><span class="sxs-lookup"><span data-stu-id="f9124-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="f9124-153">**High**：此層級是最低的安全性，可允許所有威脅層級。</span><span class="sxs-lookup"><span data-stu-id="f9124-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="f9124-154">因此，具有高、中度或低威脅層級的裝置會被視為相容性。</span><span class="sxs-lookup"><span data-stu-id="f9124-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="f9124-155">選取 **[確定]**，並 **建立** 以儲存變更 (並建立) 原則。</span><span class="sxs-lookup"><span data-stu-id="f9124-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="f9124-156">步驟4：指派原則</span><span class="sxs-lookup"><span data-stu-id="f9124-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="f9124-157">在 [Azure 入口網站](https://portal.azure.com)中，選取 [ **所有服務**]、[在 **Intune** 上篩選]，然後選取 [ **Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="f9124-158">選取 **裝置符合性**  >  **原則**> 選取您的 Microsoft Defender ATP 相容性原則。</span><span class="sxs-lookup"><span data-stu-id="f9124-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="f9124-159">選取 [作業 **]**。</span><span class="sxs-lookup"><span data-stu-id="f9124-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="f9124-160">包含或排除 Azure AD 群組，以指派原則。</span><span class="sxs-lookup"><span data-stu-id="f9124-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="f9124-161">若要將原則部署至群組，請選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="f9124-162">原則所針對的使用者裝置會根據規範評估。</span><span class="sxs-lookup"><span data-stu-id="f9124-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="f9124-163">步驟5：建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f9124-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="f9124-164">在 [azure 入口網站](https://portal.azure.com)中，開啟 **Azure Active Directory**  >  **條件式存取**  >  **新原則**。</span><span class="sxs-lookup"><span data-stu-id="f9124-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="f9124-165">輸入原則 **名稱**，然後選取 [ **使用者和群組**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="f9124-166">使用 [包含] 或 [排除] 選項新增原則的群組，然後選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="f9124-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="f9124-167">選取 [ **Cloud app**]，然後選擇要保護的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9124-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="f9124-168">例如，選擇 [ **選取應用程式**]，然後選取 [ **Office 365 SharePoint 線上** 和 **office 365 Exchange Online**。</span><span class="sxs-lookup"><span data-stu-id="f9124-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="f9124-169">選取 **[完成]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f9124-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="f9124-170">選取  >  [**用戶端應用程式**] 以將原則套用至應用程式和瀏覽器的條件。</span><span class="sxs-lookup"><span data-stu-id="f9124-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="f9124-171">例如，選取 **[是]**，然後啟用 **瀏覽器** 和行動 **應用程式及桌面用戶端**。</span><span class="sxs-lookup"><span data-stu-id="f9124-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="f9124-172">選取 **[完成]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f9124-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="f9124-173">根據裝置符合性，選取 **[授** 與套用條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="f9124-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="f9124-174">例如，選取 **[授與存取權**]  >  **需要將裝置標示為相容**。</span><span class="sxs-lookup"><span data-stu-id="f9124-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="f9124-175">選擇 [ **選取** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f9124-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="f9124-176">選取 [ **啟用原則**]，然後 **建立** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f9124-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="f9124-177">如需詳細資訊，請參閱 [在 Intune 中使用條件式存取啟用 Microsoft DEFENDER ATP](https://docs.microsoft.com/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="f9124-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="f9124-178">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f9124-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f9124-179">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f9124-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)