---
title: Microsoft Defender for Endpoint 裝置控制印表機保護
description: Microsoft Defender for Endpoint 裝置控制印表機保護會封鎖透過非公司的印表機或未經核准的 USB 印表機列印的人員。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809212"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="1c386-103">裝置控制印表機保護</span><span class="sxs-lookup"><span data-stu-id="1c386-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="1c386-104">Microsoft Defender for Endpoint 裝置控制印表機保護會封鎖透過非公司的印表機或未經核准的 USB 印表機列印的人員。</span><span class="sxs-lookup"><span data-stu-id="1c386-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="1c386-105">授權</span><span class="sxs-lookup"><span data-stu-id="1c386-105">Licensing</span></span> 

<span data-ttu-id="1c386-106">在您開始使用印表機保護之前，您應該先[確認您的 Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="1c386-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="1c386-107">若要存取和使用印表機保護，您必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="1c386-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="1c386-108">功能/原則部署的 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="1c386-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="1c386-109">報表的 Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1c386-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="1c386-110">權限</span><span class="sxs-lookup"><span data-stu-id="1c386-110">Permission</span></span> 

<span data-ttu-id="1c386-111">針對 Intune 中的原則部署，若要透過 OMA-URI 部署原則，帳戶必須具有建立、編輯、更新或刪除裝置設定檔的許可權。</span><span class="sxs-lookup"><span data-stu-id="1c386-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="1c386-112">您可以建立自訂角色，或使用具有下列許可權的任何內建角色：</span><span class="sxs-lookup"><span data-stu-id="1c386-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="1c386-113">原則和設定檔管理員角色。</span><span class="sxs-lookup"><span data-stu-id="1c386-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="1c386-114">或自訂角色已開啟裝置設定設定檔的「建立/編輯/更新/讀取/刪除/查看報告」許可權</span><span class="sxs-lookup"><span data-stu-id="1c386-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="1c386-115">或全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="1c386-115">Or Global admin</span></span>

<span data-ttu-id="1c386-116">若要查看裝置設定報告，該帳戶必須具有「查看報告」許可權。</span><span class="sxs-lookup"><span data-stu-id="1c386-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="1c386-117">您可以建立自訂角色，或使用具有下列許可權的內建角色：</span><span class="sxs-lookup"><span data-stu-id="1c386-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="1c386-118">全域安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="1c386-118">Global security admin</span></span>
- <span data-ttu-id="1c386-119">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="1c386-119">Security admin</span></span>
- <span data-ttu-id="1c386-120">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="1c386-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="1c386-121">準備您的端點</span><span class="sxs-lookup"><span data-stu-id="1c386-121">Prepare your endpoints</span></span>

<span data-ttu-id="1c386-122">請確定您規劃部署印表機保護的 Windows 10 裝置，以符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="1c386-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="1c386-123">加入有問必答計畫。</span><span class="sxs-lookup"><span data-stu-id="1c386-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="1c386-124">已安裝下列 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="1c386-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="1c386-125">Windows 1809：安裝 Windows 更新[KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="1c386-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="1c386-126">Windows 1909：安裝 Windows 更新[KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="1c386-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="1c386-127">若為 Windows 2004 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1c386-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="1c386-128">如果您計畫透過「群組原則」來部署原則，裝置必須 MDATP 加入;如果您計畫透過 MEM 部署原則，裝置必須已加入 Intune。</span><span class="sxs-lookup"><span data-stu-id="1c386-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="1c386-129">部署裝置控制印表機保護原則</span><span class="sxs-lookup"><span data-stu-id="1c386-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="1c386-130">您可以透過群組原則或 Intune 部署原則。</span><span class="sxs-lookup"><span data-stu-id="1c386-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="1c386-131">職稱</span><span class="sxs-lookup"><span data-stu-id="1c386-131">Title</span></span> | <span data-ttu-id="1c386-132">描述</span><span class="sxs-lookup"><span data-stu-id="1c386-132">Description</span></span> | <span data-ttu-id="1c386-133">CSP 支援</span><span class="sxs-lookup"><span data-stu-id="1c386-133">CSP Support</span></span> | <span data-ttu-id="1c386-134">GPO 支援</span><span class="sxs-lookup"><span data-stu-id="1c386-134">GPO Support</span></span> | <span data-ttu-id="1c386-135">以使用者為基礎的支援</span><span class="sxs-lookup"><span data-stu-id="1c386-135">User-based Support</span></span> | <span data-ttu-id="1c386-136">以機器為基礎的支援</span><span class="sxs-lookup"><span data-stu-id="1c386-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="1c386-137">**啟用裝置控制列印限制**</span><span class="sxs-lookup"><span data-stu-id="1c386-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="1c386-138">透過非公司的印表機封鎖人員進行列印</span><span class="sxs-lookup"><span data-stu-id="1c386-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="1c386-139">是</span><span class="sxs-lookup"><span data-stu-id="1c386-139">Yes</span></span>|<span data-ttu-id="1c386-140">是</span><span class="sxs-lookup"><span data-stu-id="1c386-140">Yes</span></span>|<span data-ttu-id="1c386-141">是</span><span class="sxs-lookup"><span data-stu-id="1c386-141">Yes</span></span>|<span data-ttu-id="1c386-142">是</span><span class="sxs-lookup"><span data-stu-id="1c386-142">Yes</span></span>|
|<span data-ttu-id="1c386-143">**已核准的 USB 連線列印裝置清單**\*</span><span class="sxs-lookup"><span data-stu-id="1c386-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="1c386-144">允許特定的 USB 印表機</span><span class="sxs-lookup"><span data-stu-id="1c386-144">Allow specific USB printer</span></span>|<span data-ttu-id="1c386-145">是</span><span class="sxs-lookup"><span data-stu-id="1c386-145">Yes</span></span>|<span data-ttu-id="1c386-146">是</span><span class="sxs-lookup"><span data-stu-id="1c386-146">Yes</span></span>|<span data-ttu-id="1c386-147">是</span><span class="sxs-lookup"><span data-stu-id="1c386-147">Yes</span></span>|<span data-ttu-id="1c386-148">是</span><span class="sxs-lookup"><span data-stu-id="1c386-148">Yes</span></span>|
|||||||

<span data-ttu-id="1c386-149">\*這個原則必須和 **啟用裝置控制列印限制** 一起使用</span><span class="sxs-lookup"><span data-stu-id="1c386-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="1c386-150">透過 Intune 部署原則</span><span class="sxs-lookup"><span data-stu-id="1c386-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="1c386-151">對於 Intune，目前的裝置控制項印表機保護只支援 OMA URI。</span><span class="sxs-lookup"><span data-stu-id="1c386-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="1c386-152">**案例1：透過任何非公司的印表機封鎖人員列印**</span><span class="sxs-lookup"><span data-stu-id="1c386-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="1c386-153">透過機器套用原則：</span><span class="sxs-lookup"><span data-stu-id="1c386-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="1c386-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="1c386-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="1c386-155">套用原則于使用者：</span><span class="sxs-lookup"><span data-stu-id="1c386-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="1c386-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="1c386-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="1c386-157">CSP 支援的字串 `` <enabled/>`` ：</span><span class="sxs-lookup"><span data-stu-id="1c386-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="自訂編輯列":::

<span data-ttu-id="1c386-159">**案例2：允許特定核准的 USB 印表機**</span><span class="sxs-lookup"><span data-stu-id="1c386-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="1c386-160">透過機器套用原則：</span><span class="sxs-lookup"><span data-stu-id="1c386-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="1c386-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="1c386-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="1c386-162">套用原則于使用者：</span><span class="sxs-lookup"><span data-stu-id="1c386-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="1c386-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="1c386-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="1c386-164">具有經核准的 USB 印表機透過 ' ApprovedUsbPrintDevices ' 屬性的 CSP 支援字串範例 `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` ：</span><span class="sxs-lookup"><span data-stu-id="1c386-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="編輯列":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="1c386-166">透過群組原則部署原則</span><span class="sxs-lookup"><span data-stu-id="1c386-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="1c386-167">如果裝置並未加入 Intune，您也可以透過 [群組原則] 來部署原則。</span><span class="sxs-lookup"><span data-stu-id="1c386-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="1c386-168">**案例1：透過任何非公司的印表機封鎖人員列印**</span><span class="sxs-lookup"><span data-stu-id="1c386-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="1c386-169">透過機器套用原則：</span><span class="sxs-lookup"><span data-stu-id="1c386-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="1c386-170">電腦設定 > 系統管理範本 > 印表機：啟用裝置控制列印限制</span><span class="sxs-lookup"><span data-stu-id="1c386-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="1c386-171">套用原則于使用者：</span><span class="sxs-lookup"><span data-stu-id="1c386-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="1c386-172">使用者設定 > 系統管理範本 > 控制台 > 印表機：啟用裝置控制列印限制</span><span class="sxs-lookup"><span data-stu-id="1c386-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="啟用裝置列印限制":::
 

<span data-ttu-id="1c386-174">**案例2：允許特定核准的 USB 印表機**</span><span class="sxs-lookup"><span data-stu-id="1c386-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="1c386-175">透過機器套用原則：</span><span class="sxs-lookup"><span data-stu-id="1c386-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="1c386-176">電腦設定 > 系統管理範本 > 印表機：已核准的 USB 連線列印裝置清單</span><span class="sxs-lookup"><span data-stu-id="1c386-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="1c386-177">套用原則于使用者：</span><span class="sxs-lookup"><span data-stu-id="1c386-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="1c386-178">使用者設定 > 系統管理範本 > 控制台 > 印表機：已核准的 USB 連線列印裝置清單</span><span class="sxs-lookup"><span data-stu-id="1c386-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="已核准的 usb 連線列印裝置清單":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="1c386-180">在 Microsoft Defender for Endpoint portal 中查看裝置控制印表機保護資料</span><span class="sxs-lookup"><span data-stu-id="1c386-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="1c386-181">[Microsoft 365 的安全性中心](https://security.microsoft.com)會顯示以上裝置控制印表機保護原則所封鎖的列印。</span><span class="sxs-lookup"><span data-stu-id="1c386-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高級搜尋":::
