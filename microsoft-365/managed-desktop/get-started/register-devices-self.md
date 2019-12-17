---
title: 自行註冊新裝置
description: 自行註冊裝置，以便由 Microsoft 受管理的電腦管理
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a1dbb5708cad32a0e37ddc25c97c70a765580f86
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962520"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="d0e94-103">自行註冊新裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-103">Register new devices yourself</span></span>

<span data-ttu-id="d0e94-104">Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="d0e94-105">您可以使用 Azure 入口網站上的 Microsoft 受管理的電腦來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="d0e94-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="d0e94-106">與合作夥伴合作來取得裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="d0e94-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="d0e94-107">若是如此，您就不需要擔心取得硬體雜湊，他們會為您處理。</span><span class="sxs-lookup"><span data-stu-id="d0e94-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="d0e94-108">確定您的合作夥伴在 [合作夥伴中心](https://partner.microsoft.com/dashboard)建立與您的關係，且具備 Azure Active Directory 和 Office 365 的委派系統管理權限。</span><span class="sxs-lookup"><span data-stu-id="d0e94-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard) and that they include delegated administration privileges for Azure Active Directory and Office 365.</span></span> <span data-ttu-id="d0e94-109">您的合作夥伴可在 [合作夥伴中心說明](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)深入了解。</span><span class="sxs-lookup"><span data-stu-id="d0e94-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="d0e94-110">建立這種關聯性後，您的合作夥伴就會代表您直接註冊裝置，您不須採取任何進一步動作。</span><span class="sxs-lookup"><span data-stu-id="d0e94-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="d0e94-111">如果您想要查看詳細資料，或您的合作夥伴有疑問，請參閱[可供合作夥伴註冊裝置的步驟](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="d0e94-112">註冊好裝置後，您可以繼續[檢查映像](#check-the-image)並[將裝置交付](#deliver-the-device)給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="d0e94-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="d0e94-113">準備註冊全新的裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="d0e94-114">在您擁有新的裝置後，您會依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="d0e94-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="d0e94-115">取得每個裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="d0e94-116">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="d0e94-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="d0e94-117">[在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="d0e94-118">再次確認映像是否正確。</span><span class="sxs-lookup"><span data-stu-id="d0e94-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="d0e94-119">交付裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="d0e94-120">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="d0e94-120">Obtain the hardware hash</span></span>

<span data-ttu-id="d0e94-121">Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。</span><span class="sxs-lookup"><span data-stu-id="d0e94-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="d0e94-122">您有三種選項可取得此資訊：</span><span class="sxs-lookup"><span data-stu-id="d0e94-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="d0e94-123">請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="d0e94-124">在每個裝置上執行 [Windows PowerShell 指令碼](#powershell-script-method)，並收集檔案中的結果。</span><span class="sxs-lookup"><span data-stu-id="d0e94-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="d0e94-125">啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="d0e94-126">PowerShell 指令碼方法</span><span class="sxs-lookup"><span data-stu-id="d0e94-126">PowerShell script method</span></span>

1.  <span data-ttu-id="d0e94-127">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="d0e94-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="d0e94-128">執行 `Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="d0e94-128">Run:  `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="d0e94-129">執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="d0e94-129">Run:  `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="d0e94-130">快閃磁碟機方法</span><span class="sxs-lookup"><span data-stu-id="d0e94-130">Flash drive method</span></span>

1. <span data-ttu-id="d0e94-131">在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d0e94-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="d0e94-132">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="d0e94-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="d0e94-133">執行 `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="d0e94-133">Run:  `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="d0e94-134">開啟您要註冊的裝置，但*請勿開始設定體驗*。</span><span class="sxs-lookup"><span data-stu-id="d0e94-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="d0e94-135">如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。</span><span class="sxs-lookup"><span data-stu-id="d0e94-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="d0e94-136">插入 USB 磁碟機，然後按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="d0e94-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="d0e94-137">以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="d0e94-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="d0e94-138">執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="d0e94-138">Run:  `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="d0e94-139">執行 `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="d0e94-139">Run:  `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="d0e94-140">移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="d0e94-141">在您完成註冊前，請勿開啟您所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="d0e94-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="d0e94-142">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="d0e94-142">Merge hash data</span></span>

<span data-ttu-id="d0e94-143">您必須將 CSV 檔案中的資料合併成單一檔案，才能完成註冊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="d0e94-144">以下是讓註冊變輕鬆的範例 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="d0e94-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices"></a><span data-ttu-id="d0e94-145">註冊裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-145">Register devices</span></span>

<span data-ttu-id="d0e94-146">CSV 檔案必須採用可供註冊的特定格式。</span><span class="sxs-lookup"><span data-stu-id="d0e94-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="d0e94-147">如果您在先前步驟中自行收集了資料，檔案應該已經是正確的格式。如果您是向供應商取得檔案，則可能需要調整格式。</span><span class="sxs-lookup"><span data-stu-id="d0e94-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="d0e94-148">為了方便起見，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-148">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="d0e94-149">您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。</span><span class="sxs-lookup"><span data-stu-id="d0e94-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="d0e94-150">如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。</span><span class="sxs-lookup"><span data-stu-id="d0e94-150">Your spreadsheet needs to include the exact same column headings as the sample one (User Name, First Name, etc...). If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="d0e94-151">如果您忘記變更任何範例資料，註冊將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d0e94-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="d0e94-152">使用 Azure 入口網站來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="d0e94-153">從 Microsoft 受管理的電腦的 [Azure 入口網站](https://aka.ms/mmdportal)，選取左側導覽窗格中的 [裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0e94-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="d0e94-154">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="d0e94-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="d0e94-155">[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="d0e94-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (事實並非如此。我們可以移除此注意事項 - 但現在暫且擱置，留待我們有機會討論。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="d0e94-157">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d0e94-157">Follow these steps:</span></span>

1. <span data-ttu-id="d0e94-158">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="d0e94-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="d0e94-159">或者，您可以新增 [訂單識別碼]\*\*\*\* 或 [購買識別碼]\*\*\*\*，以便自行追蹤。</span><span class="sxs-lookup"><span data-stu-id="d0e94-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="d0e94-160">這些值沒有格式需求。</span><span class="sxs-lookup"><span data-stu-id="d0e94-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="d0e94-161">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0e94-161">Select **Register devices**.</span></span> <span data-ttu-id="d0e94-162">系統會將裝置新增至 [裝置] 刀鋒視窗\*\*\*\* 上標示為 [註冊擱置]\*\*\*\* 的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="d0e94-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="d0e94-163">註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]\*\*\*\*，標示其已準備就緒並等待終端使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="d0e94-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="d0e94-164">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="d0e94-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="d0e94-165">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="d0e94-165">Possible states reported there include:</span></span>

| <span data-ttu-id="d0e94-166">狀態</span><span class="sxs-lookup"><span data-stu-id="d0e94-166">State</span></span> | <span data-ttu-id="d0e94-167">描述</span><span class="sxs-lookup"><span data-stu-id="d0e94-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="d0e94-168">註冊擱置</span><span class="sxs-lookup"><span data-stu-id="d0e94-168">Registration pending</span></span> | <span data-ttu-id="d0e94-169">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-169">Registration is not done yet.</span></span> <span data-ttu-id="d0e94-170">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="d0e94-170">Check back later.</span></span> |
| <span data-ttu-id="d0e94-171">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="d0e94-171">Registration failed</span></span> | <span data-ttu-id="d0e94-172">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-172">Registration could not be completed.</span></span> <span data-ttu-id="d0e94-173">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="d0e94-174">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="d0e94-174">Ready for user</span></span> | <span data-ttu-id="d0e94-175">註冊成功，且裝置現在已準備好交付給使用者。</span><span class="sxs-lookup"><span data-stu-id="d0e94-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="d0e94-176">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="d0e94-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="d0e94-177">作用中</span><span class="sxs-lookup"><span data-stu-id="d0e94-177">Active</span></span> | <span data-ttu-id="d0e94-178">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="d0e94-179">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="d0e94-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="d0e94-180">非作用中</span><span class="sxs-lookup"><span data-stu-id="d0e94-180">Inactive mailboxes</span></span> | <span data-ttu-id="d0e94-181">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="d0e94-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="d0e94-182">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="d0e94-183">針對裝置註冊進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="d0e94-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="d0e94-184">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="d0e94-184">Error message</span></span> | <span data-ttu-id="d0e94-185">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d0e94-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="d0e94-186">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-186">Device not found</span></span> | <span data-ttu-id="d0e94-187">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="d0e94-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="d0e94-188">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="d0e94-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="d0e94-189">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="d0e94-189">Hardware hash not valid</span></span> | <span data-ttu-id="d0e94-190">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="d0e94-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="d0e94-191">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="d0e94-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="d0e94-192">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="d0e94-192">Device already registered</span></span> | <span data-ttu-id="d0e94-193">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="d0e94-193">This device is already registered to your organization.</span></span> <span data-ttu-id="d0e94-194">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="d0e94-194">No action required</span></span> |
| <span data-ttu-id="d0e94-195">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-195">Device claimed by another organization</span></span> | <span data-ttu-id="d0e94-196">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="d0e94-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="d0e94-197">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="d0e94-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="d0e94-198">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="d0e94-198">Unexpected error</span></span> | <span data-ttu-id="d0e94-199">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="d0e94-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="d0e94-200">連絡客戶支援並提供要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="d0e94-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="d0e94-201">檢查映像</span><span class="sxs-lookup"><span data-stu-id="d0e94-201">Check the image</span></span>

<span data-ttu-id="d0e94-202">如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。</span><span class="sxs-lookup"><span data-stu-id="d0e94-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="d0e94-203">如果您想要的話，也歡迎您自行套用映像。</span><span class="sxs-lookup"><span data-stu-id="d0e94-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="d0e94-204">若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。</span><span class="sxs-lookup"><span data-stu-id="d0e94-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="d0e94-205">交付裝置</span><span class="sxs-lookup"><span data-stu-id="d0e94-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0e94-206">將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e94-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="d0e94-207">如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。</span><span class="sxs-lookup"><span data-stu-id="d0e94-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






