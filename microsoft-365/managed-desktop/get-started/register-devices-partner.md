---
title: 讓合作夥伴註冊裝置的步驟
description: 合作夥伴如何註冊裝置，以便由 Microsoft 受管理的電腦來管理
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689230"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="e3a5a-103">讓合作夥伴註冊裝置的步驟</span><span class="sxs-lookup"><span data-stu-id="e3a5a-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="e3a5a-104">本文說明在註冊裝置時，可讓合作夥伴遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="e3a5a-105">您自行註冊裝置的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="e3a5a-106">準備註冊</span><span class="sxs-lookup"><span data-stu-id="e3a5a-106">Prepare for registration</span></span> 
<span data-ttu-id="e3a5a-107">在完成客戶的註冊之前，您必須先在 [夥伴中心](https://partner.microsoft.com/dashboard)建立與他們的關聯。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="e3a5a-108">如需該程式的詳細資訊，請參閱 [同意檔](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="e3a5a-109">任何 CSP 合作夥伴只要客戶 consents，即可代表任何客戶新增裝置。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="e3a5a-110">您也可以在 [夥伴中心協助](/partner-center/customers_revoke_admin_privileges#windows-autopilot)深入瞭解合作夥伴關係和 Autopilot 許可權。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="e3a5a-111">本檔僅供合作夥伴和 Oem 用。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="e3a5a-112">自行註冊的程式會記錄在 [Microsoft 受管理的桌面的註冊裝置](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="e3a5a-113">使用夥伴中心註冊裝置</span><span class="sxs-lookup"><span data-stu-id="e3a5a-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="e3a5a-114">建立與客戶的關聯之後，您可以遵循下列步驟，使用 Partner Center 新增裝置，針對您具有關聯性的任何客戶 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="e3a5a-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="e3a5a-115">流覽至 [[合作夥伴中心](https://partner.microsoft.com/dashboard)]</span><span class="sxs-lookup"><span data-stu-id="e3a5a-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="e3a5a-116">從 [合作夥伴中心] 功能表選取 [ **客戶** ]，然後選取您想要管理其裝置的客戶。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="e3a5a-117">在客戶的詳細資料頁面上，選取 [ **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="e3a5a-118">在 [ **將設定檔** 套用至裝置] 底下，選取 [ **新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="e3a5a-119">針對您已選取的裝置設定檔輸入適當的群組標籤 (如下表所示) 然後選取 **[流覽]** ，將客戶的清單 (為 .csv 檔案格式) 至 [夥伴中心]。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="e3a5a-120">裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="e3a5a-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="e3a5a-121">Group 標記</span><span class="sxs-lookup"><span data-stu-id="e3a5a-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="e3a5a-122">敏感性資料</span><span class="sxs-lookup"><span data-stu-id="e3a5a-122">Sensitive data</span></span>     |<span data-ttu-id="e3a5a-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="e3a5a-124">Power user</span><span class="sxs-lookup"><span data-stu-id="e3a5a-124">Power user</span></span>     | <span data-ttu-id="e3a5a-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="e3a5a-126">標準版</span><span class="sxs-lookup"><span data-stu-id="e3a5a-126">Standard</span></span>     | <span data-ttu-id="e3a5a-127">**Microsoft365Managed \_ 標準**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="e3a5a-128">組名必須與表格中所列的內容完全相符，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="e3a5a-129">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="e3a5a-130">您應該會收到此 .csv 檔案與您的裝置購買。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="e3a5a-131">如果您未收到 .csv 檔案，您可以遵循 [新增裝置至 Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步驟，自行建立。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="e3a5a-132">Windows PowerShell 腳本與 [Microsoft Managed Desktop Admin 入口網站](./register-devices-self.md#obtain-the-hardware-hash)所使用的腳本不同。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="e3a5a-133">協力廠商應該使用 [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在夥伴中心中為 Microsoft 受管理的桌面裝置註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="e3a5a-134">如果您在嘗試上傳 .csv 檔案時收到錯誤訊息，請檢查檔案的格式。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="e3a5a-135">請確定欄順序符合在 [新裝置上使用 Windows Autopilot 設定檔中所述的資料，以自訂客戶的現成體驗](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="e3a5a-136">您也可以使用 [ **新增裝置** ] 旁邊的連結所提供的範例 .csv 檔案，以建立裝置清單。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="e3a5a-137">如需 Autopilot 在合作夥伴案例中的詳細資訊，請參閱 [將裝置新增至客戶的帳戶](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="e3a5a-138">使用 OEM API 註冊裝置</span><span class="sxs-lookup"><span data-stu-id="e3a5a-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="e3a5a-139">在完成客戶的註冊之前，您必須先與其建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="e3a5a-140">您應該有一個唯一的連結，可提供給您的各個客戶。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="e3a5a-141">請參閱 [如何建立 OEM 關聯](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="e3a5a-142">建立關聯之後，您可以開始使用適當的群組標籤為客戶註冊裝置，以供每個選取的裝置設定檔使用：</span><span class="sxs-lookup"><span data-stu-id="e3a5a-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="e3a5a-143">裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="e3a5a-143">Device profile</span></span>  |<span data-ttu-id="e3a5a-144">Group 標記</span><span class="sxs-lookup"><span data-stu-id="e3a5a-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="e3a5a-145">敏感性資料</span><span class="sxs-lookup"><span data-stu-id="e3a5a-145">Sensitive data</span></span>     | <span data-ttu-id="e3a5a-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="e3a5a-147">Power user</span><span class="sxs-lookup"><span data-stu-id="e3a5a-147">Power user</span></span>     | <span data-ttu-id="e3a5a-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="e3a5a-149">標準版</span><span class="sxs-lookup"><span data-stu-id="e3a5a-149">Standard</span></span>     | <span data-ttu-id="e3a5a-150">**Microsoft365Managed \_ 標準**</span><span class="sxs-lookup"><span data-stu-id="e3a5a-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="e3a5a-151">Group 標記必須與表格中所列的標籤完全相符，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="e3a5a-152">這將允許使用 Microsoft Managed Desktop Autopilot 設定檔來指派新註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="e3a5a-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>