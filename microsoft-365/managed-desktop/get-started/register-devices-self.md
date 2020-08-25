---
title: 自行註冊新裝置
description: 自行註冊裝置，以便由 Microsoft 受管理的電腦管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 470047da0a1902a6076add27a6e7ac516edd3150
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "46869004"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="12274-103">自行註冊新裝置</span><span class="sxs-lookup"><span data-stu-id="12274-103">Register new devices yourself</span></span>

<span data-ttu-id="12274-104">Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。</span><span class="sxs-lookup"><span data-stu-id="12274-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="12274-105">您可以使用 Microsoft Managed Desktop Admin 入口網站來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="12274-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="12274-106">與合作夥伴合作來取得裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="12274-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="12274-107">若是如此，您就不需要擔心取得硬體雜湊，他們會為您處理。</span><span class="sxs-lookup"><span data-stu-id="12274-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="12274-108">請確定您的夥伴已在 [夥伴中心](https://partner.microsoft.com/dashboard)與您建立關聯。</span><span class="sxs-lookup"><span data-stu-id="12274-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="12274-109">您的合作夥伴可在 [合作夥伴中心說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)深入了解。</span><span class="sxs-lookup"><span data-stu-id="12274-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="12274-110">建立這種關聯性後，您的合作夥伴就會代表您直接註冊裝置，您不須採取任何進一步動作。</span><span class="sxs-lookup"><span data-stu-id="12274-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="12274-111">如果您想要查看詳細資料，或您的合作夥伴有疑問，請參閱[可供合作夥伴註冊裝置的步驟](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="12274-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="12274-112">註冊好裝置後，您可以繼續[檢查映像](#check-the-image)並[將裝置交付](#deliver-the-device)給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="12274-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="12274-113">準備註冊全新的裝置</span><span class="sxs-lookup"><span data-stu-id="12274-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="12274-114">在您擁有新的裝置後，您會依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="12274-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="12274-115">取得每個裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="12274-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="12274-116">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="12274-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="12274-117">[在 Microsoft 受管理的電腦中註冊裝置](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="12274-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="12274-118">再次確認映像是否正確。</span><span class="sxs-lookup"><span data-stu-id="12274-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="12274-119">交付裝置</span><span class="sxs-lookup"><span data-stu-id="12274-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="12274-120">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="12274-120">Obtain the hardware hash</span></span>

<span data-ttu-id="12274-121">Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。</span><span class="sxs-lookup"><span data-stu-id="12274-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="12274-122">您有三種選項可取得此資訊：</span><span class="sxs-lookup"><span data-stu-id="12274-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="12274-123">請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="12274-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="12274-124">在每個裝置上執行 [Windows PowerShell 指令碼](#powershell-script-method)，並收集檔案中的結果。</span><span class="sxs-lookup"><span data-stu-id="12274-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="12274-125">啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="12274-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="12274-126">PowerShell 指令碼方法</span><span class="sxs-lookup"><span data-stu-id="12274-126">PowerShell script method</span></span>

<span data-ttu-id="12274-127">您可以使用 PowerShell 圖庫網站上的 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="12274-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="12274-128">如需裝置識別及硬體雜湊的詳細資訊，請參閱 [將裝置新增至 Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)。</span><span class="sxs-lookup"><span data-stu-id="12274-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="12274-129">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="12274-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="12274-130">執行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="12274-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="12274-131">執行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="12274-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="12274-132">快閃磁碟機方法</span><span class="sxs-lookup"><span data-stu-id="12274-132">Flash drive method</span></span>

1. <span data-ttu-id="12274-133">在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="12274-133">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="12274-134">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="12274-134">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="12274-135">執行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="12274-135">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="12274-136">開啟您要註冊的裝置，但*請勿開始設定體驗*。</span><span class="sxs-lookup"><span data-stu-id="12274-136">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="12274-137">如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。</span><span class="sxs-lookup"><span data-stu-id="12274-137">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="12274-138">插入 USB 磁碟機，然後按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="12274-138">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="12274-139">以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="12274-139">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="12274-140">執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="12274-140">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="12274-141">執行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="12274-141">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="12274-142">移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置</span><span class="sxs-lookup"><span data-stu-id="12274-142">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="12274-143">在您完成註冊前，請勿開啟您所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="12274-143">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="12274-144">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="12274-144">Merge hash data</span></span>

<span data-ttu-id="12274-145">您必須將 CSV 檔案中的資料合併成單一檔案，才能完成註冊。</span><span class="sxs-lookup"><span data-stu-id="12274-145">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="12274-146">以下是讓註冊變輕鬆的範例 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="12274-146">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="12274-147">使用管理入口網站註冊裝置</span><span class="sxs-lookup"><span data-stu-id="12274-147">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="12274-148">從 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)的左側流覽窗格中，選取 [ **裝置** ]。</span><span class="sxs-lookup"><span data-stu-id="12274-148">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="12274-149">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="12274-149">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="12274-150">[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="12274-150">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="12274-151">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="12274-151">Follow these steps:</span></span>

1. <span data-ttu-id="12274-152">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="12274-152">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="12274-153">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12274-153">Select **Register devices**.</span></span> <span data-ttu-id="12274-154">系統會將裝置新增至 **裝置**上的裝置清單，並標示為 **AutopilotRegistrationRequested**。</span><span class="sxs-lookup"><span data-stu-id="12274-154">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="12274-155">登錄所需的時間通常不會超過10分鐘，當成功時，裝置會顯示為已就緒，可供 **使用者** 使用，且等候使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="12274-155">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="12274-156">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="12274-156">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="12274-157">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="12274-157">Possible states reported there include:</span></span>

| <span data-ttu-id="12274-158">狀態</span><span class="sxs-lookup"><span data-stu-id="12274-158">State</span></span> | <span data-ttu-id="12274-159">描述</span><span class="sxs-lookup"><span data-stu-id="12274-159">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="12274-160">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="12274-160">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="12274-161">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="12274-161">Registration is not done yet.</span></span> <span data-ttu-id="12274-162">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="12274-162">Check back later.</span></span> |
| <span data-ttu-id="12274-163">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="12274-163">Registration failed</span></span> | <span data-ttu-id="12274-164">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="12274-164">Registration could not be completed.</span></span> <span data-ttu-id="12274-165">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="12274-165">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="12274-166">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="12274-166">Ready for user</span></span> | <span data-ttu-id="12274-167">註冊成功，且裝置現在已準備好交付給使用者。</span><span class="sxs-lookup"><span data-stu-id="12274-167">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="12274-168">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="12274-168">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="12274-169">作用中</span><span class="sxs-lookup"><span data-stu-id="12274-169">Active</span></span> | <span data-ttu-id="12274-170">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="12274-170">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="12274-171">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="12274-171">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="12274-172">非作用中</span><span class="sxs-lookup"><span data-stu-id="12274-172">Inactive</span></span> | <span data-ttu-id="12274-173">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="12274-173">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="12274-174">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="12274-174">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="12274-175">針對裝置註冊進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="12274-175">Troubleshooting device registration</span></span>

| <span data-ttu-id="12274-176">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="12274-176">Error message</span></span> | <span data-ttu-id="12274-177">詳細資料</span><span class="sxs-lookup"><span data-stu-id="12274-177">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="12274-178">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="12274-178">Device not found</span></span> | <span data-ttu-id="12274-179">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="12274-179">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="12274-180">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="12274-180">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="12274-181">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="12274-181">Hardware hash not valid</span></span> | <span data-ttu-id="12274-182">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="12274-182">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="12274-183">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="12274-183">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="12274-184">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="12274-184">Device already registered</span></span> | <span data-ttu-id="12274-185">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="12274-185">This device is already registered to your organization.</span></span> <span data-ttu-id="12274-186">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="12274-186">No further action required.</span></span> |
| <span data-ttu-id="12274-187">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="12274-187">Device claimed by another organization</span></span> | <span data-ttu-id="12274-188">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="12274-188">This device has already been claimed by another organization.</span></span> <span data-ttu-id="12274-189">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="12274-189">Check with your device supplier.</span></span> |
| <span data-ttu-id="12274-190">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="12274-190">Unexpected error</span></span> | <span data-ttu-id="12274-191">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="12274-191">Your request could not be automatically processed.</span></span> <span data-ttu-id="12274-192">連絡客戶支援並提供要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="12274-192">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="12274-193">檢查映像</span><span class="sxs-lookup"><span data-stu-id="12274-193">Check the image</span></span>

<span data-ttu-id="12274-194">如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。</span><span class="sxs-lookup"><span data-stu-id="12274-194">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="12274-195">如果您想要的話，也歡迎您自行套用映像。</span><span class="sxs-lookup"><span data-stu-id="12274-195">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="12274-196">若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。</span><span class="sxs-lookup"><span data-stu-id="12274-196">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="12274-197">交付裝置</span><span class="sxs-lookup"><span data-stu-id="12274-197">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12274-198">將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="12274-198">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="12274-199">如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。</span><span class="sxs-lookup"><span data-stu-id="12274-199">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






