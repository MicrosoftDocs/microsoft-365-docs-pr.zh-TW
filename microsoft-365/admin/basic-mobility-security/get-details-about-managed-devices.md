---
title: 取得基本行動裝置及安全性受管理裝置的詳細資料
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用 Windows PowerShell 以取得組織中基本行動及安全性裝置的詳細資料。
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228168"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="ec921-103">取得基本行動裝置及安全性受管理裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="ec921-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="ec921-104">本文說明如何使用 Windows PowerShell，以取得您為基本行動性和安全性設定之組織中裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ec921-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="ec921-105">以下是您可以使用的裝置詳細資料明細。</span><span class="sxs-lookup"><span data-stu-id="ec921-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="ec921-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="ec921-106">**Detail**</span></span>|<span data-ttu-id="ec921-107">**在 PowerShell 中要尋找的專案**</span><span class="sxs-lookup"><span data-stu-id="ec921-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="ec921-108">裝置已註冊基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="ec921-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="ec921-109">如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="ec921-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="ec921-110">IsManaged 參數的值 \*\*   為：</span><span class="sxs-lookup"><span data-stu-id="ec921-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="ec921-111">**True**= 裝置已註冊。</span><span class="sxs-lookup"><span data-stu-id="ec921-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="ec921-112">**False**= 裝置未註冊。</span><span class="sxs-lookup"><span data-stu-id="ec921-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="ec921-113">裝置符合您的裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="ec921-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="ec921-114">如需詳細資訊，請參閱 [建立裝置安全性原則](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ec921-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="ec921-115">IsCompliant 參數的值 \*\*   為：</span><span class="sxs-lookup"><span data-stu-id="ec921-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="ec921-116">**True**  = 裝置符合原則。</span><span class="sxs-lookup"><span data-stu-id="ec921-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="ec921-117">**False**  = device 與原則不符。</span><span class="sxs-lookup"><span data-stu-id="ec921-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本行動性及安全性 PowerShell 參數":::

> [!NOTE]
> <span data-ttu-id="ec921-119">本文中的命令和腳本也會傳回 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)所管理之任何裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ec921-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ec921-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="ec921-120">Before you begin</span></span>

<span data-ttu-id="ec921-121">您必須設定一些事項，才能執行本文所述的命令和腳本。</span><span class="sxs-lookup"><span data-stu-id="ec921-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ec921-122">步驟1：下載並安裝 Windows PowerShell 的 Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="ec921-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ec921-123">如需這些步驟的詳細資訊，請參閱 [連線 to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ec921-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="ec921-124">移至 [IT 專業人員的 Microsoft Online services Sign-In Assistant] RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)   ，然後選取 [ **下載 microsoft online services**] 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="ec921-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="ec921-125">以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="ec921-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="ec921-126">開啟管理員層級的 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="ec921-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="ec921-127">執行 `Install-Module MSOnline` 命令。</span><span class="sxs-lookup"><span data-stu-id="ec921-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="ec921-128">如果系統提示您安裝 NuGet 提供者，請輸入 Y，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="ec921-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="ec921-129">如果系統提示您從 PSGallery 安裝模組，請輸入 Y，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="ec921-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="ec921-130">安裝完成後，請關閉 PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="ec921-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="ec921-131">步驟2：連線 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="ec921-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="ec921-132">在 Windows PowerShell 的 Windows Azure Active Directory 模組中，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ec921-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="ec921-133">在 [Windows PowerShell 認證要求] 對話方塊中，輸入 Microsoft 365 全域管理員帳戶的使用者名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ec921-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="ec921-134">執行下列指令：</span><span class="sxs-lookup"><span data-stu-id="ec921-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="ec921-135">步驟3：請確定您可以執行 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="ec921-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="ec921-136">如果您已設定為執行 PowerShell 腳本，可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="ec921-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="ec921-137">若要執行 Get-MsolUserDeviceComplianceStatus.ps1 腳本，您必須啟用執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="ec921-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="ec921-138">從您的 Windows 桌面，選取 [ **開始**]，然後輸入 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ec921-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="ec921-139">以滑鼠右鍵按一下 [Windows PowerShell]，然後選取 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="ec921-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="ec921-140">執行下列指令：</span><span class="sxs-lookup"><span data-stu-id="ec921-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="ec921-141">出現提示時，請輸入 Y，然後按 Enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="ec921-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="ec921-142">執行 Get-MsolDevice Cmdlet 以顯示組織中所有裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="ec921-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="ec921-143">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="ec921-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ec921-144">執行下列指令：</span><span class="sxs-lookup"><span data-stu-id="ec921-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="ec921-145">如需更多範例，請參閱  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。</span><span class="sxs-lookup"><span data-stu-id="ec921-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="ec921-146">執行腳本以取得裝置詳細資料</span><span class="sxs-lookup"><span data-stu-id="ec921-146">Run a script to get device details</span></span>

<span data-ttu-id="ec921-147">首先，將腳本儲存至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="ec921-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="ec921-148">在記事本中複製並貼上下列文字。</span><span class="sxs-lookup"><span data-stu-id="ec921-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="ec921-149">使用副檔名 .ps1 將其儲存為 Windows PowerShell 腳本檔案;例如，Get-MsolUserDeviceComplianceStatus.ps1。</span><span class="sxs-lookup"><span data-stu-id="ec921-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="ec921-150">執行腳本以取得單一使用者帳戶的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="ec921-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="ec921-151">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="ec921-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ec921-152">移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ec921-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="ec921-153">例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ec921-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="ec921-154">執行下列命令，識別您想要取得設備詳細資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec921-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="ec921-155">此範例會取得 bar@example.com 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ec921-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="ec921-156">執行下列命令以啟動腳本。</span><span class="sxs-lookup"><span data-stu-id="ec921-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="ec921-157">此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。</span><span class="sxs-lookup"><span data-stu-id="ec921-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="ec921-158">您可以使用其他參數來指定 CSV 的檔案名和路徑。</span><span class="sxs-lookup"><span data-stu-id="ec921-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="ec921-159">執行腳本以取得使用者群組的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="ec921-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="ec921-160">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="ec921-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ec921-161">移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ec921-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="ec921-162">例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ec921-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="ec921-163">執行下列命令，識別您要取得設備詳細資料的群組。</span><span class="sxs-lookup"><span data-stu-id="ec921-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="ec921-164">此範例會取得 FinanceStaff 群組中使用者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ec921-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="ec921-165">執行下列命令以啟動腳本。</span><span class="sxs-lookup"><span data-stu-id="ec921-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="ec921-166">此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。</span><span class="sxs-lookup"><span data-stu-id="ec921-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="ec921-167">您可以使用其他參數來指定 CSV 的檔案名和路徑。</span><span class="sxs-lookup"><span data-stu-id="ec921-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec921-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec921-168">Related topics</span></span>

[<span data-ttu-id="ec921-169">已停用 Microsoft 連線</span><span class="sxs-lookup"><span data-stu-id="ec921-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="ec921-170">基本行動與安全性概觀</span><span class="sxs-lookup"><span data-stu-id="ec921-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="ec921-171">MsolDevice</span><span class="sxs-lookup"><span data-stu-id="ec921-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
