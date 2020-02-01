---
title: 讓合作夥伴註冊裝置的步驟
description: 如何合作夥伴可以註冊裝置，可由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596550"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="f0e0a-103">讓合作夥伴註冊裝置的步驟</span><span class="sxs-lookup"><span data-stu-id="f0e0a-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="f0e0a-104">本主題說明適用於要遵循註冊裝置的合作夥伴的步驟。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="f0e0a-105">自行註冊裝置的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="f0e0a-106">準備註冊</span><span class="sxs-lookup"><span data-stu-id="f0e0a-106">Prepare for registration</span></span> 
<span data-ttu-id="f0e0a-107">完成之前註冊為客戶，您必須先建立與其[合作夥伴中心](https://partner.microsoft.com/dashboard)的關係。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="f0e0a-108">請務必選取 [**包含委派管理 Azure Active Directory 和 Office 365 的權限**。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="f0e0a-109">深入瞭解[合作夥伴中心的說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="f0e0a-110">若要完成註冊您的客戶，請先建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="f0e0a-111">以方便您使用，您可以下載[範例 CSV 檔](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)此*協力廠商版本*。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) for this *Partner version*.</span></span>

<span data-ttu-id="f0e0a-112">您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="f0e0a-113">如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="f0e0a-114">這種格式是僅供合作夥伴程序。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-114">This format is only for the Partner process.</span></span> <span data-ttu-id="f0e0a-115">自助註冊的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="f0e0a-116">這些值必須 SMBIOS 的製造商值完全相符，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="f0e0a-117">裝置製造商 (範例： SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="f0e0a-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="f0e0a-118">裝置型號 (範例： ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="f0e0a-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="f0e0a-119">裝置序號</span><span class="sxs-lookup"><span data-stu-id="f0e0a-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="f0e0a-120">使用 Azure 入口網站來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="f0e0a-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="f0e0a-121">除了在入口網站存取不同註冊使用 Azure 入口網站是與自助，相同。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="f0e0a-122">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f0e0a-122">Follow these steps:</span></span>

1. <span data-ttu-id="f0e0a-123">瀏覽至[合作夥伴中心](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="f0e0a-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="f0e0a-124">選取 [**客戶**]。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-124">Select **Customers**.</span></span>
3. <span data-ttu-id="f0e0a-125">選取您想要管理的客戶。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="f0e0a-126">選取 [**服務管理**]。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="f0e0a-127">選取 [ **Intune**]。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-127">Select **Intune**.</span></span>
6. <span data-ttu-id="f0e0a-128">搜尋 「 mmd 」 在上方的搜尋方塊中的 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="f0e0a-129">選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-129">Select **Devices**.</span></span>
8. <span data-ttu-id="f0e0a-130">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="f0e0a-131">或者，您可以新增 [訂單識別碼]\*\*\*\* 或 [購買識別碼]\*\*\*\*，以便自行追蹤。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="f0e0a-132">這些值沒有格式需求。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="f0e0a-133">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-133">Select **Register devices**.</span></span> <span data-ttu-id="f0e0a-134">系統會將裝置新增至 [裝置] 刀鋒視窗\*\*\*\* 上標示為 [註冊擱置]\*\*\*\* 的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="f0e0a-135">註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]\*\*\*\*，標示其已準備就緒並等待終端使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="f0e0a-136">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="f0e0a-137">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="f0e0a-137">Possible states reported there include:</span></span>

| <span data-ttu-id="f0e0a-138">狀態</span><span class="sxs-lookup"><span data-stu-id="f0e0a-138">State</span></span> | <span data-ttu-id="f0e0a-139">描述</span><span class="sxs-lookup"><span data-stu-id="f0e0a-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="f0e0a-140">註冊擱置</span><span class="sxs-lookup"><span data-stu-id="f0e0a-140">Registration pending</span></span> | <span data-ttu-id="f0e0a-141">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-141">Registration is not done yet.</span></span> <span data-ttu-id="f0e0a-142">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-142">Check back later.</span></span> |
| <span data-ttu-id="f0e0a-143">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="f0e0a-143">Registration failed</span></span> | <span data-ttu-id="f0e0a-144">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-144">Registration could not be completed.</span></span> <span data-ttu-id="f0e0a-145">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](register-devices-self.md#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="f0e0a-146">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="f0e0a-146">Ready for user</span></span> | <span data-ttu-id="f0e0a-147">註冊成功，且裝置現在已準備好交付給使用者。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="f0e0a-148">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="f0e0a-149">作用中</span><span class="sxs-lookup"><span data-stu-id="f0e0a-149">Active</span></span> | <span data-ttu-id="f0e0a-150">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f0e0a-151">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="f0e0a-152">非作用中</span><span class="sxs-lookup"><span data-stu-id="f0e0a-152">Inactive</span></span> | <span data-ttu-id="f0e0a-153">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f0e0a-154">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="f0e0a-155">疑難排解</span><span class="sxs-lookup"><span data-stu-id="f0e0a-155">Troubleshooting</span></span>

| <span data-ttu-id="f0e0a-156">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="f0e0a-156">Error message</span></span> | <span data-ttu-id="f0e0a-157">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f0e0a-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="f0e0a-158">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="f0e0a-158">Device not found</span></span> | <span data-ttu-id="f0e0a-159">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="f0e0a-160">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="f0e0a-161">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="f0e0a-161">Hardware hash not valid</span></span> | <span data-ttu-id="f0e0a-162">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="f0e0a-163">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="f0e0a-164">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="f0e0a-164">Device already registered</span></span> | <span data-ttu-id="f0e0a-165">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-165">This device is already registered to your organization.</span></span> <span data-ttu-id="f0e0a-166">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-166">No further action required.</span></span> |
| <span data-ttu-id="f0e0a-167">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="f0e0a-167">Device claimed by another organization</span></span> | <span data-ttu-id="f0e0a-168">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="f0e0a-169">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="f0e0a-170">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="f0e0a-170">Unexpected error</span></span> | <span data-ttu-id="f0e0a-171">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="f0e0a-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="f0e0a-172">連絡客戶支援 (<support link>)，並提供 「 要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="f0e0a-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
