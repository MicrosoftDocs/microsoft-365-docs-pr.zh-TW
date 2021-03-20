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
description: 使用 Windows PowerShell 以取得組織中基本行動與安全性裝置的詳細資料。
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904249"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="7bd51-103">取得基本行動裝置及安全性受管理裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="7bd51-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="7bd51-104">本文將告訴您如何使用 Windows PowerShell，取得您組織中您設定為基本行動性和安全性之裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7bd51-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="7bd51-105">以下是您可以使用的裝置詳細資料明細。</span><span class="sxs-lookup"><span data-stu-id="7bd51-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="7bd51-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="7bd51-106">**Detail**</span></span>|<span data-ttu-id="7bd51-107">**在 PowerShell 中要尋找的專案**</span><span class="sxs-lookup"><span data-stu-id="7bd51-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="7bd51-108">裝置已註冊基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="7bd51-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="7bd51-109">如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="7bd51-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="7bd51-110">IsManaged 參數的值 \*\*   為：</span><span class="sxs-lookup"><span data-stu-id="7bd51-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="7bd51-111">**True**= 裝置已註冊。</span><span class="sxs-lookup"><span data-stu-id="7bd51-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="7bd51-112">**False**= 裝置未註冊。</span><span class="sxs-lookup"><span data-stu-id="7bd51-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="7bd51-113">裝置符合您的裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="7bd51-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="7bd51-114">如需詳細資訊，請參閱 [建立裝置安全性原則](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7bd51-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="7bd51-115">IsCompliant 參數的值 \*\*   為：</span><span class="sxs-lookup"><span data-stu-id="7bd51-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="7bd51-116">**True**  = 裝置符合原則。</span><span class="sxs-lookup"><span data-stu-id="7bd51-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="7bd51-117">**False**  = device 與原則不符。</span><span class="sxs-lookup"><span data-stu-id="7bd51-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本行動性及安全性 PowerShell 參數":::

>[!NOTE]
><span data-ttu-id="7bd51-119">本文中的命令和腳本也會傳回 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)所管理之任何裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7bd51-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7bd51-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="7bd51-120">Before you begin</span></span>

<span data-ttu-id="7bd51-121">您必須設定一些事項，才能執行本文所述的命令和腳本。</span><span class="sxs-lookup"><span data-stu-id="7bd51-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7bd51-122">步驟1：下載並安裝適用于 Windows PowerShell 的 Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="7bd51-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7bd51-123">如需這些步驟的詳細資訊，請參閱 [Connect To Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7bd51-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="7bd51-124">移至 [IT 專業人員的 Microsoft Online services Sign-In Assistant] RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   ，然後選取 [ **下載 microsoft online services**] 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="7bd51-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="7bd51-125">以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="7bd51-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="7bd51-126">開啟管理員層級的 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7bd51-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="7bd51-127">執行 Install-Module MSOnline 命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="7bd51-128">如果系統提示您安裝 NuGet 提供者，請輸入 Y，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="7bd51-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="7bd51-129">如果系統提示您從 PSGallery 安裝模組，請輸入 Y，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="7bd51-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="7bd51-130">安裝完成後，請關閉 PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="7bd51-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="7bd51-131">步驟2：連線至您的 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="7bd51-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="7bd51-132">在 windows PowerShell Windows Azure Active Directory 模組中，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="7bd51-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="7bd51-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="7bd51-134">在 [Windows PowerShell 憑證要求] 對話方塊中，輸入 Microsoft 365 全域管理員帳戶的使用者名稱和密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7bd51-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="7bd51-135">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-135">Run the following command.</span></span>

    <span data-ttu-id="7bd51-136">Connect-MsolService-身分 $UserCredential</span><span class="sxs-lookup"><span data-stu-id="7bd51-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="7bd51-137">步驟3：請確定您可以執行 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="7bd51-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="7bd51-138">如果您已設定為執行 PowerShell 腳本，可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="7bd51-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="7bd51-139">若要執行 Get-MsolUserDeviceComplianceStatus.ps1 腳本，您必須啟用執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="7bd51-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="7bd51-140">在您的 Windows 桌面中，選取 [ **開始**]，然後輸入 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7bd51-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="7bd51-141">以滑鼠右鍵按一下 [Windows PowerShell]，然後選取 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="7bd51-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="7bd51-142">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-142">Run the following command.</span></span>

    <span data-ttu-id="7bd51-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="7bd51-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="7bd51-144">出現提示時，請輸入 Y，然後按 Enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="7bd51-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="7bd51-145">**執行 Get-MsolDevice Cmdlet 以顯示組織中所有裝置的詳細資料**</span><span class="sxs-lookup"><span data-stu-id="7bd51-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="7bd51-146">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="7bd51-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="7bd51-147">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-147">Run the following command.</span></span>

    <span data-ttu-id="7bd51-148">Get-MsolDevice-ReturnRegisteredOwners |Where-Object {$ _。RegisteredOwners-gt 0}</span><span class="sxs-lookup"><span data-stu-id="7bd51-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="7bd51-149">如需更多範例，請參閱  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。</span><span class="sxs-lookup"><span data-stu-id="7bd51-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="7bd51-150">執行腳本以取得裝置詳細資料</span><span class="sxs-lookup"><span data-stu-id="7bd51-150">Run a script to get device details</span></span>

<span data-ttu-id="7bd51-151">首先，將腳本儲存至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="7bd51-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="7bd51-152">將下列文字複製並貼到 [記事本] 中。</span><span class="sxs-lookup"><span data-stu-id="7bd51-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="7bd51-153">param (</span><span class="sxs-lookup"><span data-stu-id="7bd51-153">param (</span></span>

3.  <span data-ttu-id="7bd51-154">[PSObject []] $users = @ () ，</span><span class="sxs-lookup"><span data-stu-id="7bd51-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="7bd51-155">[切換] $export，</span><span class="sxs-lookup"><span data-stu-id="7bd51-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="7bd51-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date 格式 "yyMMdd_HHMMss" ) + ".csv"</span><span class="sxs-lookup"><span data-stu-id="7bd51-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="7bd51-157">[字串] $exportPath = [環境]：： GetFolderPath ( "Desktop" ) </span><span class="sxs-lookup"><span data-stu-id="7bd51-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="7bd51-158">)</span><span class="sxs-lookup"><span data-stu-id="7bd51-158">)</span></span>

9.  <span data-ttu-id="7bd51-159">[System.Collections.IDictionary] $script： schema = @ {</span><span class="sxs-lookup"><span data-stu-id="7bd51-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="7bd51-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="7bd51-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="7bd51-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="7bd51-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="7bd51-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="7bd51-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="7bd51-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="7bd51-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="7bd51-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="7bd51-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="7bd51-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="7bd51-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="7bd51-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="7bd51-172">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-172">}</span></span>
    

25.  <span data-ttu-id="7bd51-173">函數 createResultObject</span><span class="sxs-lookup"><span data-stu-id="7bd51-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="7bd51-174">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-174">{</span></span>
    

28.  <span data-ttu-id="7bd51-175">[PSObject] $resultObject = New-Object TypeName PSObject-Property $script：架構</span><span class="sxs-lookup"><span data-stu-id="7bd51-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="7bd51-176">退回 $resultObject</span><span class="sxs-lookup"><span data-stu-id="7bd51-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="7bd51-177">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-177">}</span></span>
    

33.  <span data-ttu-id="7bd51-178">如果 ($users。計數-eq 0) </span><span class="sxs-lookup"><span data-stu-id="7bd51-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="7bd51-179">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-179">{</span></span>
    

35.  <span data-ttu-id="7bd51-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="7bd51-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="7bd51-181">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-181">}</span></span>
    

38.  <span data-ttu-id="7bd51-182">[PSObject []] $result = foreach ($u $users) </span><span class="sxs-lookup"><span data-stu-id="7bd51-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="7bd51-183">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-183">{</span></span>
    

41.  <span data-ttu-id="7bd51-184">[PSObject] $devices = msoldevice-RegisteredOwnerUpn $u。 UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7bd51-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="7bd51-185">$devices) 中的 foreach ($d</span><span class="sxs-lookup"><span data-stu-id="7bd51-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="7bd51-186">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-186">{</span></span>
    

44.  <span data-ttu-id="7bd51-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="7bd51-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="7bd51-188">$deviceResult DeviceId = $d DeviceId</span><span class="sxs-lookup"><span data-stu-id="7bd51-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="7bd51-189">$deviceResult。 DeviceOSType = $d DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="7bd51-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="7bd51-190">$deviceResult。 DeviceOSVersion = $d DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="7bd51-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="7bd51-191">$deviceResult。 DeviceTrustLevel = $d DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="7bd51-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="7bd51-192">$deviceResult。 DisplayName = $d。 DisplayName</span><span class="sxs-lookup"><span data-stu-id="7bd51-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="7bd51-193">$deviceResult。 IsCompliant = $d IsCompliant</span><span class="sxs-lookup"><span data-stu-id="7bd51-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="7bd51-194">$deviceResult。 IsManaged = $d IsManaged</span><span class="sxs-lookup"><span data-stu-id="7bd51-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="7bd51-195">$deviceResult。 DeviceObjectId = $d ObjectId</span><span class="sxs-lookup"><span data-stu-id="7bd51-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="7bd51-196">$deviceResult。 RegisteredOwnerUpn = $u UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7bd51-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="7bd51-197">$deviceResult。 RegisteredOwnerObjectId = $u ObjectId</span><span class="sxs-lookup"><span data-stu-id="7bd51-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="7bd51-198">$deviceResult。 RegisteredOwnerDisplayName = $u DisplayName</span><span class="sxs-lookup"><span data-stu-id="7bd51-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="7bd51-199">$deviceResult。 ApproximateLastLogonTimestamp = $d ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="7bd51-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="7bd51-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="7bd51-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="7bd51-201">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-201">}</span></span>
    

61.  <span data-ttu-id="7bd51-202">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-202">}</span></span>
    

63.  <span data-ttu-id="7bd51-203">如果 ($export) </span><span class="sxs-lookup"><span data-stu-id="7bd51-203">If ($export)</span></span>
    

64.  <span data-ttu-id="7bd51-204">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-204">{</span></span>
    

65.  <span data-ttu-id="7bd51-205">$result |Export-Csv-path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="7bd51-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="7bd51-206">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-206">}</span></span>
    

67.  <span data-ttu-id="7bd51-207">Else</span><span class="sxs-lookup"><span data-stu-id="7bd51-207">Else</span></span>
    

68.  <span data-ttu-id="7bd51-208">{</span><span class="sxs-lookup"><span data-stu-id="7bd51-208">{</span></span>
    

69.  <span data-ttu-id="7bd51-209">$result</span><span class="sxs-lookup"><span data-stu-id="7bd51-209">$result</span></span>
    

70.  <span data-ttu-id="7bd51-210">}</span><span class="sxs-lookup"><span data-stu-id="7bd51-210">}</span></span>
    

71.  <span data-ttu-id="7bd51-211">使用副檔名為 ps1，將其儲存為 Windows PowerShell script 檔案。例如，Get-MsolUserDeviceComplianceStatus.ps1。</span><span class="sxs-lookup"><span data-stu-id="7bd51-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="7bd51-212">執行腳本以取得單一使用者帳戶的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="7bd51-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="7bd51-213">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="7bd51-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="7bd51-214">移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7bd51-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="7bd51-215">例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="7bd51-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="7bd51-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="7bd51-217">執行下列命令，識別您想要取得設備詳細資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="7bd51-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="7bd51-218">此範例會取得 bar@example.com 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7bd51-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="7bd51-219">$u = Get-MsolUser UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="7bd51-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="7bd51-220">執行下列命令以啟動腳本。</span><span class="sxs-lookup"><span data-stu-id="7bd51-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="7bd51-221">.\Get-MsolUserDeviceComplianceStatus.ps1-使用者 $u 匯出</span><span class="sxs-lookup"><span data-stu-id="7bd51-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="7bd51-222">此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。</span><span class="sxs-lookup"><span data-stu-id="7bd51-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="7bd51-223">您可以使用其他參數來指定 CSV 的檔案名和路徑。</span><span class="sxs-lookup"><span data-stu-id="7bd51-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="7bd51-224">執行腳本以取得使用者群組的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="7bd51-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="7bd51-225">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="7bd51-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="7bd51-226">移至您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7bd51-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="7bd51-227">例如，如果您將其儲存至 C:\PS-Scripts，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7bd51-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="7bd51-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="7bd51-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="7bd51-229">執行下列命令，識別您要取得設備詳細資料的群組。</span><span class="sxs-lookup"><span data-stu-id="7bd51-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="7bd51-230">此範例會取得 FinanceStaff 群組中使用者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7bd51-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="7bd51-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" |% {Get-MsolUser-ObjectId $ _。ObjectId}</span><span class="sxs-lookup"><span data-stu-id="7bd51-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="7bd51-232">執行下列命令以啟動腳本。</span><span class="sxs-lookup"><span data-stu-id="7bd51-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="7bd51-233">.\Get-MsolUserDeviceComplianceStatus.ps1-使用者 $u 匯出</span><span class="sxs-lookup"><span data-stu-id="7bd51-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="7bd51-234">此資訊會以 CSV 檔案形式匯出至您的 Windows 桌面。</span><span class="sxs-lookup"><span data-stu-id="7bd51-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="7bd51-235">您可以使用其他參數來指定 CSV 的檔案名和路徑。</span><span class="sxs-lookup"><span data-stu-id="7bd51-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7bd51-236">相關主題</span><span class="sxs-lookup"><span data-stu-id="7bd51-236">Related topics</span></span>

[<span data-ttu-id="7bd51-237">已停用 Microsoft Connect</span><span class="sxs-lookup"><span data-stu-id="7bd51-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="7bd51-238">基本行動與安全性概觀</span><span class="sxs-lookup"><span data-stu-id="7bd51-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="7bd51-239">MsolDevice</span><span class="sxs-lookup"><span data-stu-id="7bd51-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)