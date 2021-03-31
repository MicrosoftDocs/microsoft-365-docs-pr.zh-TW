---
title: 讓合作夥伴註冊裝置的步驟
description: 合作夥伴如何註冊裝置，以便由 Microsoft 受管理的電腦來管理
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445587"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="d2c68-104">讓合作夥伴註冊裝置的步驟</span><span class="sxs-lookup"><span data-stu-id="d2c68-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="d2c68-105">本主題說明可讓合作夥伴遵循的步驟來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="d2c68-106">您自行註冊裝置的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="d2c68-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="d2c68-107">準備註冊</span><span class="sxs-lookup"><span data-stu-id="d2c68-107">Prepare for registration</span></span> 
<span data-ttu-id="d2c68-108">在完成客戶的註冊之前，您必須先在 [夥伴中心](https://partner.microsoft.com/dashboard)建立與他們的關聯。</span><span class="sxs-lookup"><span data-stu-id="d2c68-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="d2c68-109">如需該程式的詳細資訊，請參閱 [同意檔](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。</span><span class="sxs-lookup"><span data-stu-id="d2c68-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="d2c68-110">任何 CSP 合作夥伴只要客戶 consents，即可代表任何客戶新增裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="d2c68-111">您也可以在 [夥伴中心協助](/partner-center/customers_revoke_admin_privileges#windows-autopilot)深入瞭解合作夥伴關係和 Autopilot 許可權。</span><span class="sxs-lookup"><span data-stu-id="d2c68-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="d2c68-112">本檔僅供合作夥伴和 Oem 用。</span><span class="sxs-lookup"><span data-stu-id="d2c68-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="d2c68-113">自行註冊的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="d2c68-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="d2c68-114">使用夥伴中心註冊裝置</span><span class="sxs-lookup"><span data-stu-id="d2c68-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="d2c68-115">當您建立與客戶的關聯之後，您可以遵循下列步驟，利用合作夥伴中心新增裝置，針對您具有關聯性的任何客戶 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="d2c68-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="d2c68-116">流覽至 [[合作夥伴中心](https://partner.microsoft.com/dashboard)]</span><span class="sxs-lookup"><span data-stu-id="d2c68-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="d2c68-117">從 [合作夥伴中心] 功能表選取 [ **客戶** ]，然後選取您想要管理其裝置的客戶。</span><span class="sxs-lookup"><span data-stu-id="d2c68-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="d2c68-118">在客戶的詳細資料頁面上，選取 [ **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="d2c68-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="d2c68-119">在 [ **將設定檔** 套用至裝置] 底下，選取 [ **新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="d2c68-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="d2c68-120">輸入組名的 **Microsoft365Managed_Autopilot** ，然後選取 **[流覽]** ，將客戶的清單 (以 .csv 檔案格式上傳) 至 [夥伴中心]。</span><span class="sxs-lookup"><span data-stu-id="d2c68-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d2c68-121">群組名稱必須完全符合 **Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="d2c68-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="d2c68-122">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="d2c68-123">您應該會收到此 .csv 檔案與您的裝置購買。</span><span class="sxs-lookup"><span data-stu-id="d2c68-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="d2c68-124">如果您未收到 .csv 檔案，您可以遵循 [新增裝置至 Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步驟，自行建立。</span><span class="sxs-lookup"><span data-stu-id="d2c68-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="d2c68-125">Windows PowerShell 腳本與 [Microsoft Managed Desktop Admin 入口網站](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)所使用的腳本不同。</span><span class="sxs-lookup"><span data-stu-id="d2c68-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="d2c68-126">協力廠商應該使用 [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在夥伴中心中為 Microsoft 受管理的桌面裝置註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="d2c68-127">如果您在嘗試上傳 .csv 檔案時收到錯誤訊息，請檢查檔案的格式。</span><span class="sxs-lookup"><span data-stu-id="d2c68-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="d2c68-128">請確定欄順序符合在 [新裝置上使用 Windows Autopilot 設定檔中所述的資料，以自訂客戶的現成體驗](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="d2c68-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="d2c68-129">您也可以使用 [ **新增裝置** ] 旁邊的連結所提供的範例 .csv 檔案，以建立裝置清單。</span><span class="sxs-lookup"><span data-stu-id="d2c68-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="d2c68-130">如需 Autopilot 在合作夥伴案例中的詳細資訊，請參閱 [將裝置新增至客戶的帳戶](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="d2c68-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="d2c68-131">使用 OEM API 註冊裝置</span><span class="sxs-lookup"><span data-stu-id="d2c68-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="d2c68-132">在完成客戶的註冊之前，您必須先與其建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d2c68-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="d2c68-133">您應該有一個唯一的連結，可提供給您的各個客戶。</span><span class="sxs-lookup"><span data-stu-id="d2c68-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="d2c68-134">請參閱 [如何建立 OEM 關聯](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="d2c68-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="d2c68-135">建立關聯之後，您可以開始使用群組標籤 **Microsoft365Managed_Autopilot** 為客戶註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2c68-136">群組名稱必須完全符合 **Microsoft365Managed_Autopilot** ，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="d2c68-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="d2c68-137">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="d2c68-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>