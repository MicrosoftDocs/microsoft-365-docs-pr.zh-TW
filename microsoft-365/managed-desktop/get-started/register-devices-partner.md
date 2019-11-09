---
title: 讓合作夥伴註冊裝置的步驟
description: 如何合作夥伴可以註冊裝置，可由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: ceda5765ca6450959c99222daf457cf7584401ba
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074725"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="b65f1-103">讓合作夥伴註冊裝置的步驟</span><span class="sxs-lookup"><span data-stu-id="b65f1-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="b65f1-104">本主題說明適用於要遵循註冊裝置的合作夥伴的步驟。</span><span class="sxs-lookup"><span data-stu-id="b65f1-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="b65f1-105">自行註冊裝置的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="b65f1-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="b65f1-106">準備註冊</span><span class="sxs-lookup"><span data-stu-id="b65f1-106">Prepare for registration</span></span> 
<span data-ttu-id="b65f1-107">完成之前註冊為客戶，您必須先建立與其[合作夥伴中心](https://partner.microsoft.com/dashboard)的關係。</span><span class="sxs-lookup"><span data-stu-id="b65f1-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="b65f1-108">請務必選取 [**包含委派管理 Azure Active Directory 和 Office 365 的權限**。</span><span class="sxs-lookup"><span data-stu-id="b65f1-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="b65f1-109">深入瞭解[合作夥伴中心的說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="b65f1-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="b65f1-110">若要完成註冊您的客戶，請先建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b65f1-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="b65f1-111">以方便您使用，您可以下載[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)此*協力廠商版本*的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b65f1-111">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this *Partner version* of the CSV file.</span></span>

<span data-ttu-id="b65f1-112">您的檔案必須包含**完全相同的欄名**為其中一個範例 （製造商、 型號、 等），但您自己的資料列的資料。</span><span class="sxs-lookup"><span data-stu-id="b65f1-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="b65f1-113">如果您使用的範本，在編輯 [記事本] 之類的文字中開啟，並且考慮離開的所有資料列 1 單獨中的，只輸入資料，資料列 2 中下, 面。</span><span class="sxs-lookup"><span data-stu-id="b65f1-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="b65f1-114">這種格式是僅供合作夥伴程序。</span><span class="sxs-lookup"><span data-stu-id="b65f1-114">This format is only for the Partner process.</span></span> <span data-ttu-id="b65f1-115">自助註冊的程序會詳細說明[自行註冊 Microsoft 受管理電腦中的裝置](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="b65f1-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b65f1-116">這些值必須 SMBIOS 的製造商值完全相符，包括大小寫和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="b65f1-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="b65f1-117">裝置製造商 (範例： SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="b65f1-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="b65f1-118">裝置型號 (範例： ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="b65f1-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="b65f1-119">裝置序號</span><span class="sxs-lookup"><span data-stu-id="b65f1-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="b65f1-120">使用 Azure 入口網站來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="b65f1-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="b65f1-121">除了在入口網站存取不同註冊使用 Azure 入口網站是與自助，相同。</span><span class="sxs-lookup"><span data-stu-id="b65f1-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="b65f1-122">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b65f1-122">Follow these steps:</span></span>

1. <span data-ttu-id="b65f1-123">瀏覽至[合作夥伴中心](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="b65f1-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="b65f1-124">選取 [**客戶**]。</span><span class="sxs-lookup"><span data-stu-id="b65f1-124">Select **Customers**.</span></span>
3. <span data-ttu-id="b65f1-125">選取您想要管理的客戶。</span><span class="sxs-lookup"><span data-stu-id="b65f1-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="b65f1-126">選取 [**服務管理**]。</span><span class="sxs-lookup"><span data-stu-id="b65f1-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="b65f1-127">選取 [ **Intune**]。</span><span class="sxs-lookup"><span data-stu-id="b65f1-127">Select **Intune**.</span></span>
6. <span data-ttu-id="b65f1-128">搜尋 「 mmd 」 在上方的搜尋方塊中的 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b65f1-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="b65f1-129">選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="b65f1-129">Select **Devices**.</span></span>
8. <span data-ttu-id="b65f1-130">在 [**檔案上傳**，提供您先前建立的 CSV 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="b65f1-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="b65f1-131">（選用） 您可以新增**順序識別碼**或**購買識別碼**自己追蹤的目的。</span><span class="sxs-lookup"><span data-stu-id="b65f1-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="b65f1-132">沒有這些值的格式需求。</span><span class="sxs-lookup"><span data-stu-id="b65f1-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="b65f1-133">選取 [**註冊的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="b65f1-133">Select **Register devices**.</span></span> <span data-ttu-id="b65f1-134">系統會將裝置新增至您的**裝置] 刀鋒視窗中**，標示為 [**擱置中註冊**裝置的清單。</span><span class="sxs-lookup"><span data-stu-id="b65f1-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="b65f1-135">註冊通常採用小於 10 分鐘，並成功時裝置將會顯示為**使用者準備**這很好，等待使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="b65f1-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="b65f1-136">您可以監視進度的主要**Microsoft 受管理電腦的 [裝置**] 頁面上的裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="b65f1-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="b65f1-137">報告那里可能的狀態包括：</span><span class="sxs-lookup"><span data-stu-id="b65f1-137">Possible states reported there include:</span></span>

| <span data-ttu-id="b65f1-138">狀態</span><span class="sxs-lookup"><span data-stu-id="b65f1-138">State</span></span> | <span data-ttu-id="b65f1-139">描述</span><span class="sxs-lookup"><span data-stu-id="b65f1-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="b65f1-140">註冊暫止</span><span class="sxs-lookup"><span data-stu-id="b65f1-140">Registration pending</span></span> | <span data-ttu-id="b65f1-141">註冊未尚未完成。</span><span class="sxs-lookup"><span data-stu-id="b65f1-141">Registration is not done yet.</span></span> <span data-ttu-id="b65f1-142">請稍後再回來。</span><span class="sxs-lookup"><span data-stu-id="b65f1-142">Check back later.</span></span> |
| <span data-ttu-id="b65f1-143">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="b65f1-143">Registration failed</span></span> | <span data-ttu-id="b65f1-144">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="b65f1-144">Registration could not be completed.</span></span> <span data-ttu-id="b65f1-145">如需詳細資訊，請參閱[疑難排解裝置註冊](register-devices-self.md#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="b65f1-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="b65f1-146">準備使用者</span><span class="sxs-lookup"><span data-stu-id="b65f1-146">Ready for user</span></span> | <span data-ttu-id="b65f1-147">註冊成功，而且裝置已準備好要傳遞給使用者。</span><span class="sxs-lookup"><span data-stu-id="b65f1-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="b65f1-148">Microsoft 受管理的電腦會逐步引導其第一次 」 設定，因此不需要為您進行任何進一步的準備工作。</span><span class="sxs-lookup"><span data-stu-id="b65f1-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="b65f1-149">作用中</span><span class="sxs-lookup"><span data-stu-id="b65f1-149">Active</span></span> | <span data-ttu-id="b65f1-150">裝置已經傳送給使用者，他們必須註冊您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="b65f1-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="b65f1-151">這也表示他們定期使用裝置。</span><span class="sxs-lookup"><span data-stu-id="b65f1-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="b65f1-152">非使用中</span><span class="sxs-lookup"><span data-stu-id="b65f1-152">Inactive</span></span> | <span data-ttu-id="b65f1-153">裝置已經傳送給使用者，他們必須註冊您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="b65f1-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="b65f1-154">不過，他們有不適用於裝置最近 （過去 7 天）。</span><span class="sxs-lookup"><span data-stu-id="b65f1-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="b65f1-155">疑難排解</span><span class="sxs-lookup"><span data-stu-id="b65f1-155">Troubleshooting</span></span>

| <span data-ttu-id="b65f1-156">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="b65f1-156">Error message</span></span> | <span data-ttu-id="b65f1-157">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b65f1-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="b65f1-158">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="b65f1-158">Device not found</span></span> | <span data-ttu-id="b65f1-159">我們無法註冊此裝置，因為我們找不到相符項目提供的製造商、 模型，或序號。</span><span class="sxs-lookup"><span data-stu-id="b65f1-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="b65f1-160">與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="b65f1-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="b65f1-161">不正確的硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="b65f1-161">Hardware hash not valid</span></span> | <span data-ttu-id="b65f1-162">您提供此裝置的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="b65f1-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="b65f1-163">請仔細檢查硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="b65f1-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="b65f1-164">已註冊的裝置</span><span class="sxs-lookup"><span data-stu-id="b65f1-164">Device already registered</span></span> | <span data-ttu-id="b65f1-165">此裝置已登錄至您的組織。</span><span class="sxs-lookup"><span data-stu-id="b65f1-165">This device is already registered to your organization.</span></span> <span data-ttu-id="b65f1-166">不再需要的動作。</span><span class="sxs-lookup"><span data-stu-id="b65f1-166">No further action required.</span></span> |
| <span data-ttu-id="b65f1-167">另一個組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="b65f1-167">Device claimed by another organization</span></span> | <span data-ttu-id="b65f1-168">此裝置已經被另一個組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="b65f1-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="b65f1-169">請與您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="b65f1-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="b65f1-170">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="b65f1-170">Unexpected error</span></span> | <span data-ttu-id="b65f1-171">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="b65f1-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="b65f1-172">連絡客戶支援 (<support link>)，並提供 「 要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="b65f1-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
