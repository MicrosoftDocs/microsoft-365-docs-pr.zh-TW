---
title: 註冊裝置 Microsoft 受管理電腦中自行
description: 註冊裝置自行這樣可以由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289128"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="2de73-103">Microsoft 受管理電腦中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="2de73-104">本主題說明您註冊裝置上您自己的步驟。</span><span class="sxs-lookup"><span data-stu-id="2de73-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="2de73-105">中[註冊裝置的合作夥伴的 Microsoft 受管理電腦中](register-devices-partner.md)會說明協力廠商的程序。</span><span class="sxs-lookup"><span data-stu-id="2de73-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="2de73-106">Microsoft 受管理的電腦可搭配全新的裝置，或者您可以重新使用您可能已有的裝置 （這會需要，您重新影像它們）。</span><span class="sxs-lookup"><span data-stu-id="2de73-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="2de73-107">您可以在 Azure 入口網站上使用 Microsoft 受管理電腦中註冊裝置，或使用 API 獲得的彈性。</span><span class="sxs-lookup"><span data-stu-id="2de73-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="2de73-108">準備註冊裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-108">Prepare to register devices</span></span>

<span data-ttu-id="2de73-109">如果您已經尚未取得您想要使用、 檢查[Microsoft 受管理的電腦裝置](../service-description/device-list.md)以及與以採購裝置合作夥伴合作，的裝置支援的裝置。</span><span class="sxs-lookup"><span data-stu-id="2de73-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="2de73-110">不論您正在使用全新的裝置，或者重新使用現有的項目，來註冊 Microsoft 受管理的電腦，您需要準備的**以逗號分隔 (CSV) 檔案**。</span><span class="sxs-lookup"><span data-stu-id="2de73-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="2de73-111">此檔案應包含每個裝置的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2de73-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="2de73-112">這種格式是只自助註冊。</span><span class="sxs-lookup"><span data-stu-id="2de73-112">This format is for self-service registration only.</span></span> <span data-ttu-id="2de73-113">合作夥伴應使用的格式已記錄在[登錄中的協力廠商的 Microsoft 受管理電腦的裝置](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="2de73-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="2de73-114">這些值用於顯示用途，並不需要完全相符之裝置的屬性。</span><span class="sxs-lookup"><span data-stu-id="2de73-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="2de73-115">裝置製造商 (範例： SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="2de73-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="2de73-116">裝置型號 (範例： ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="2de73-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="2de73-117">裝置序號</span><span class="sxs-lookup"><span data-stu-id="2de73-117">Device serial number</span></span>

<span data-ttu-id="2de73-118">硬體雜湊必須完全符合。</span><span class="sxs-lookup"><span data-stu-id="2de73-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="2de73-119">硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="2de73-119">Hardware hash</span></span>

<span data-ttu-id="2de73-120">若要取得硬體雜湊您可以從您的 OEM 或協力廠商尋求協助，或針對每個裝置遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2de73-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="2de73-121">以系統管理權限開啟 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="2de73-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="2de73-122">執行`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="2de73-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="2de73-123">執行`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2de73-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="2de73-124">或者，您可以在全新的裝置上遵循下列步驟 （之前第一次經由 OOBE）：</span><span class="sxs-lookup"><span data-stu-id="2de73-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="2de73-125">在不同裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2de73-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="2de73-126">以系統管理權限開啟 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="2de73-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="2de73-127">執行`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="2de73-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="2de73-128">在目標裝置上，開啟，但不是會啟動安裝程式的經驗。</span><span class="sxs-lookup"><span data-stu-id="2de73-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="2de73-129">如果您不小心開始的安裝體驗，您必須重設或重新裝置。</span><span class="sxs-lookup"><span data-stu-id="2de73-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="2de73-130">插入的 USB 磁碟機，並按下 SHIFT + f10 時會顯示功能表。</span><span class="sxs-lookup"><span data-stu-id="2de73-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="2de73-131">以系統管理權限，開啟 PowerShell 命令提示字元，然後執行`cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="2de73-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="2de73-132">執行`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="2de73-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="2de73-133">執行`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2de73-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="2de73-134">移除的 USB 磁碟機，然後關閉該裝置，藉由執行`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="2de73-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="2de73-135">不 power 目標裝置上一次直到您已經完成註冊為它。</span><span class="sxs-lookup"><span data-stu-id="2de73-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="2de73-136">以方便您使用，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="2de73-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this CSV file.</span></span>

<span data-ttu-id="2de73-137">您的檔案必須包含**完全相同的欄名**為其中一個範例 （製造商、 型號、 等），但您自己的資料列的資料。</span><span class="sxs-lookup"><span data-stu-id="2de73-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="2de73-138">如果您使用的範本，在編輯 [記事本] 之類的文字中開啟，並且考慮離開的所有資料列 1 單獨中的，只輸入資料，資料列 2 中下, 面。</span><span class="sxs-lookup"><span data-stu-id="2de73-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="2de73-139">如果您忘記變更其中一個範例資料，將會失敗註冊。</span><span class="sxs-lookup"><span data-stu-id="2de73-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="2de73-140">使用 Azure 入口網站來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="2de73-141">從 Microsoft 受管理電腦的 [ [Azure 入口網站](https://aka.ms/mmdportal)中，選取 [在左側的導覽窗格中的**裝置**。</span><span class="sxs-lookup"><span data-stu-id="2de73-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="2de73-142">選取 [ **+ 註冊裝置**;飛出視窗中開啟：</span><span class="sxs-lookup"><span data-stu-id="2de73-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="2de73-143">[![飛出視窗中選取註冊裝置之後](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="2de73-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (可惜這不是，則為 true。我們可以移除此附註-但現在離開它，直到我們有機會關於該聊天室。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="2de73-145">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2de73-145">Follow these steps:</span></span>

1. <span data-ttu-id="2de73-146">在 [**檔案上傳**，提供您先前建立的 CSV 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="2de73-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="2de73-147">（選用） 您可以新增**順序識別碼**或**購買識別碼**自己追蹤的目的。</span><span class="sxs-lookup"><span data-stu-id="2de73-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="2de73-148">沒有這些值的格式需求。</span><span class="sxs-lookup"><span data-stu-id="2de73-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="2de73-149">選取 [**註冊的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="2de73-149">Select **Register devices**.</span></span> <span data-ttu-id="2de73-150">系統會將裝置新增至您的**裝置] 刀鋒視窗中**，標示為 [**擱置中註冊**裝置的清單。</span><span class="sxs-lookup"><span data-stu-id="2de73-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="2de73-151">註冊通常採用小於 10 分鐘，並成功時裝置將會顯示為**使用者準備**這很好，等待使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="2de73-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="2de73-152">您可以監視進度的主要**Microsoft 受管理電腦的 [裝置**] 頁面上的裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="2de73-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="2de73-153">報告那里可能的狀態包括：</span><span class="sxs-lookup"><span data-stu-id="2de73-153">Possible states reported there include:</span></span>

| <span data-ttu-id="2de73-154">狀態</span><span class="sxs-lookup"><span data-stu-id="2de73-154">State</span></span> | <span data-ttu-id="2de73-155">說明</span><span class="sxs-lookup"><span data-stu-id="2de73-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="2de73-156">註冊暫止</span><span class="sxs-lookup"><span data-stu-id="2de73-156">Registration pending</span></span> | <span data-ttu-id="2de73-157">註冊未尚未完成。</span><span class="sxs-lookup"><span data-stu-id="2de73-157">Registration is not done yet.</span></span> <span data-ttu-id="2de73-158">請稍後再回來。</span><span class="sxs-lookup"><span data-stu-id="2de73-158">Check back later.</span></span> |
| <span data-ttu-id="2de73-159">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="2de73-159">Registration failed</span></span> | <span data-ttu-id="2de73-160">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="2de73-160">Registration could not be completed.</span></span> <span data-ttu-id="2de73-161">如需詳細資訊，請參閱[疑難排解](register-devices-self.md#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="2de73-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="2de73-162">準備使用者</span><span class="sxs-lookup"><span data-stu-id="2de73-162">Ready for user</span></span> | <span data-ttu-id="2de73-163">註冊成功，而且裝置已準備好要傳遞給使用者。</span><span class="sxs-lookup"><span data-stu-id="2de73-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="2de73-164">Microsoft 受管理的電腦會逐步引導其第一次 」 設定，因此不需要為您進行任何進一步的準備工作。</span><span class="sxs-lookup"><span data-stu-id="2de73-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="2de73-165">Active</span><span class="sxs-lookup"><span data-stu-id="2de73-165">Active</span></span> | <span data-ttu-id="2de73-166">裝置已經傳送給使用者，他們必須註冊您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="2de73-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="2de73-167">這也表示他們定期使用裝置。</span><span class="sxs-lookup"><span data-stu-id="2de73-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="2de73-168">非使用中</span><span class="sxs-lookup"><span data-stu-id="2de73-168">Inactive</span></span> | <span data-ttu-id="2de73-169">裝置已經傳送給使用者，他們必須註冊您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="2de73-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="2de73-170">不過，他們有不適用於裝置最近 （過去 7 天）。</span><span class="sxs-lookup"><span data-stu-id="2de73-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="2de73-171">使用 API 來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-171">Register devices by using an API</span></span>

<span data-ttu-id="2de73-172">REST API 就可讓您更大的彈性和重複性與經常不同的裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="2de73-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="2de73-173">目前，若要使用 API，請尋求協助從您的 Microsoft 連絡人加入這項功能的預覽。</span><span class="sxs-lookup"><span data-stu-id="2de73-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="2de73-174">疑難排解</span><span class="sxs-lookup"><span data-stu-id="2de73-174">Troubleshooting</span></span>

| <span data-ttu-id="2de73-175">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="2de73-175">Error message</span></span> | <span data-ttu-id="2de73-176">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2de73-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="2de73-177">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-177">Device not found</span></span> | <span data-ttu-id="2de73-178">我們無法註冊此裝置，因為我們找不到相符項目提供的製造商、 模型，或序號。</span><span class="sxs-lookup"><span data-stu-id="2de73-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="2de73-179">與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="2de73-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="2de73-180">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-180">Device not found</span></span> | <span data-ttu-id="2de73-181">我們無法取消註冊此裝置，因為不存在於您的組織。</span><span class="sxs-lookup"><span data-stu-id="2de73-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="2de73-182">不再需要的動作。</span><span class="sxs-lookup"><span data-stu-id="2de73-182">No further action required.</span></span> |
| <span data-ttu-id="2de73-183">不正確的硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="2de73-183">Hardware hash not valid</span></span> | <span data-ttu-id="2de73-184">您提供此裝置的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="2de73-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="2de73-185">請仔細檢查硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="2de73-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="2de73-186">已註冊的裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-186">Device already registered</span></span> | <span data-ttu-id="2de73-187">此裝置已登錄至您的組織。</span><span class="sxs-lookup"><span data-stu-id="2de73-187">This device is already registered to your organization.</span></span> <span data-ttu-id="2de73-188">不再需要的動作。</span><span class="sxs-lookup"><span data-stu-id="2de73-188">No further action required.</span></span> |
| <span data-ttu-id="2de73-189">另一個組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="2de73-189">Device claimed by another organization</span></span> | <span data-ttu-id="2de73-190">此裝置已經被另一個組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="2de73-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="2de73-191">請與您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="2de73-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="2de73-192">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="2de73-192">Unexpected error</span></span> | <span data-ttu-id="2de73-193">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="2de73-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="2de73-194">連絡支援人員，並提供 「 要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="2de73-194">Contact Support and provide the Request ID: <requestId></span></span> |




