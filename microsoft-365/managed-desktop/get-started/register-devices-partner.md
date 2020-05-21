---
title: 讓合作夥伴註冊裝置的步驟
description: 合作夥伴如何註冊裝置，以便由 Microsoft 受管理的電腦來管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327043"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="81ecd-103">讓合作夥伴註冊裝置的步驟</span><span class="sxs-lookup"><span data-stu-id="81ecd-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="81ecd-104">本主題說明可讓合作夥伴遵循的步驟來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="81ecd-105">您自行註冊裝置的程式會記錄在[Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="81ecd-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="81ecd-106">準備註冊</span><span class="sxs-lookup"><span data-stu-id="81ecd-106">Prepare for registration</span></span> 
<span data-ttu-id="81ecd-107">在完成客戶的註冊之前，您必須先在[夥伴中心](https://partner.microsoft.com/dashboard)建立與他們的關聯。</span><span class="sxs-lookup"><span data-stu-id="81ecd-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="81ecd-108">如需該程式的詳細資訊，請參閱[同意檔](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization)。</span><span class="sxs-lookup"><span data-stu-id="81ecd-108">See the [consent documentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="81ecd-109">任何 CSP 合作夥伴只要客戶 consents，即可代表任何客戶新增裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="81ecd-110">您也可以在[夥伴中心協助](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)深入瞭解合作夥伴關係和 Autopilot 許可權。</span><span class="sxs-lookup"><span data-stu-id="81ecd-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="81ecd-111">本檔僅供合作夥伴和 Oem 用。</span><span class="sxs-lookup"><span data-stu-id="81ecd-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="81ecd-112">自行註冊的程式會記錄在[Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="81ecd-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="81ecd-113">使用夥伴中心註冊裝置</span><span class="sxs-lookup"><span data-stu-id="81ecd-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="81ecd-114">當您建立與客戶的關聯之後，您可以遵循下列步驟，利用合作夥伴中心新增裝置，針對您具有關聯性的任何客戶 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="81ecd-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="81ecd-115">流覽至 [[合作夥伴中心](https://partner.microsoft.com/dashboard)]</span><span class="sxs-lookup"><span data-stu-id="81ecd-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="81ecd-116">從 [合作夥伴中心] 功能表選取 [**客戶**]，然後選取您想要管理其裝置的客戶。</span><span class="sxs-lookup"><span data-stu-id="81ecd-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="81ecd-117">在客戶的詳細資料頁面上，選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="81ecd-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="81ecd-118">在 [**將設定檔**套用至裝置] 底下，選取 [**新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="81ecd-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="81ecd-119">輸入組名的**Microsoft365Managed_Autopilot** ，然後選取 **[流覽]** ，將客戶的清單（csv 檔案格式）上傳至夥伴中心。</span><span class="sxs-lookup"><span data-stu-id="81ecd-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="81ecd-120">群組名稱必須完全符合**Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="81ecd-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="81ecd-121">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="81ecd-122">您應該會收到此 .csv 檔案與您的裝置購買。</span><span class="sxs-lookup"><span data-stu-id="81ecd-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="81ecd-123">如果您未收到 .csv 檔案，您可以遵循[新增裝置至 Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步驟，自行建立。</span><span class="sxs-lookup"><span data-stu-id="81ecd-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="81ecd-124">Windows PowerShell 腳本與[Microsoft Managed Desktop Admin 入口網站](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)所使用的腳本不同。</span><span class="sxs-lookup"><span data-stu-id="81ecd-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="81ecd-125">協力廠商應該使用[Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)在夥伴中心中為 Microsoft 受管理的桌面裝置註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="81ecd-126">如果您在嘗試上傳 .csv 檔案時收到錯誤訊息，請檢查檔案的格式。</span><span class="sxs-lookup"><span data-stu-id="81ecd-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="81ecd-127">您可以只使用硬體雜湊，或 OEM 名稱、序號碼和模型（按該欄順序）或 Windows 產品識別碼。</span><span class="sxs-lookup"><span data-stu-id="81ecd-127">You can use the hardware hash only, or the OEM name, serial number, and model (in that column order), or the Windows Product ID.</span></span> <span data-ttu-id="81ecd-128">您也可以使用 [**新增裝置**] 旁邊的連結所提供的範例 .csv 檔案，以建立裝置清單。</span><span class="sxs-lookup"><span data-stu-id="81ecd-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="81ecd-129">如需 Autopilot 在合作夥伴案例中的詳細資訊，請參閱[將裝置新增至客戶的帳戶](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="81ecd-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="81ecd-130">使用 OEM API 註冊裝置</span><span class="sxs-lookup"><span data-stu-id="81ecd-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="81ecd-131">在完成客戶的註冊之前，您必須先與其建立關聯。</span><span class="sxs-lookup"><span data-stu-id="81ecd-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="81ecd-132">您應該有一個唯一的連結，可提供給您的各個客戶。</span><span class="sxs-lookup"><span data-stu-id="81ecd-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="81ecd-133">請參閱[如何建立 OEM 關聯](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="81ecd-133">See [How to establish OEM relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="81ecd-134">建立關聯之後，您可以開始使用群組標籤**Microsoft365Managed_Autopilot**為客戶註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81ecd-135">群組名稱必須完全符合**Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="81ecd-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="81ecd-136">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="81ecd-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>
