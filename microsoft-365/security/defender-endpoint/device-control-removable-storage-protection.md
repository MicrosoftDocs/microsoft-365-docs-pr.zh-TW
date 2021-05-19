---
title: Microsoft Defender for Endpoint 裝置控制可移除的儲存體保護
description: 瞭解可協助防止使用者或機器或兩者（或兩者）使用未經授權的可移動儲存媒體的功能
keywords: 可移動儲存媒體
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538384"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="53acd-104">Microsoft Defender for Endpoint 裝置控制可移除的儲存體保護</span><span class="sxs-lookup"><span data-stu-id="53acd-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="53acd-105">Microsoft Defender for Endpoint Device Control Control 儲存體 Protection 可防止使用者或機器或兩者使用未經授權的可移動儲存媒體。</span><span class="sxs-lookup"><span data-stu-id="53acd-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="53acd-106">保護原則</span><span class="sxs-lookup"><span data-stu-id="53acd-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="53acd-107">裝置安裝</span><span class="sxs-lookup"><span data-stu-id="53acd-107">Device installation</span></span>

<span data-ttu-id="53acd-108">**功能** -根據各種裝置內容，避免安裝或未排除。</span><span class="sxs-lookup"><span data-stu-id="53acd-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="53acd-109">**描述**</span><span class="sxs-lookup"><span data-stu-id="53acd-109">**Description**</span></span>
- <span data-ttu-id="53acd-110">在電腦層級套用：對任何已登入的使用者套用相同的原則。</span><span class="sxs-lookup"><span data-stu-id="53acd-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="53acd-111">支援 MEM 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="53acd-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="53acd-112">所列支援的「[裝置屬性](#device-properties)」。</span><span class="sxs-lookup"><span data-stu-id="53acd-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="53acd-113">如需 Windows 的詳細資訊，請參閱 how [to control 使用 Microsoft Defender for Endpoint 的 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="53acd-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="53acd-114">**支援的平臺** Windows 10</span><span class="sxs-lookup"><span data-stu-id="53acd-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="53acd-115">**描述**</span><span class="sxs-lookup"><span data-stu-id="53acd-115">**Description**</span></span>
- <span data-ttu-id="53acd-116">在電腦層級套用：對任何已登入的使用者套用相同的原則</span><span class="sxs-lookup"><span data-stu-id="53acd-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="53acd-117">如需 macOS 特定資訊，請參閱 [Device control for macOS](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="53acd-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="53acd-118">已啟用系統擴充的 **支援平臺** macOS Catalina 10.15.4 + () </span><span class="sxs-lookup"><span data-stu-id="53acd-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="53acd-119">可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-119">Removable storage Access Control</span></span>

<span data-ttu-id="53acd-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="53acd-120">**Capabilities**</span></span>
- <span data-ttu-id="53acd-121">*審核* 根據不同裝置內容讀取或寫入或執行「可移動儲存」的存取權，具有或不含排除。</span><span class="sxs-lookup"><span data-stu-id="53acd-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="53acd-122">*避免* 以不同裝置屬性為基礎，以或不含排除允許特定裝置的方式讀取或寫入或執行存取。</span><span class="sxs-lookup"><span data-stu-id="53acd-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="53acd-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="53acd-123">**Description**</span></span>
- <span data-ttu-id="53acd-124">在任何機器或使用者或兩者上套用–只允許特定人員對特定電腦上的特定可移動儲存體執行讀取/寫入/執行存取。</span><span class="sxs-lookup"><span data-stu-id="53acd-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="53acd-125">支援 MEM OMA-URI 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="53acd-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="53acd-126">所列支援的「[裝置屬性](#device-properties)」。</span><span class="sxs-lookup"><span data-stu-id="53acd-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="53acd-127">如需 Windows 中的功能，請參閱可[拆卸儲存體存取控制](device-control-removable-storage-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="53acd-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="53acd-128">**支援的平臺** Windows 10</span><span class="sxs-lookup"><span data-stu-id="53acd-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="53acd-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="53acd-129">**Description**</span></span>
- <span data-ttu-id="53acd-130">在電腦層級套用：對任何已登入的使用者套用相同的原則。</span><span class="sxs-lookup"><span data-stu-id="53acd-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="53acd-131">如需 macOS 特定資訊，請參閱 [Device control for macOS](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="53acd-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="53acd-132">已啟用系統擴充的 **支援平臺** macOS Catalina 10.15.4 + () </span><span class="sxs-lookup"><span data-stu-id="53acd-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="53acd-133">Windows可擕式裝置存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="53acd-134">**功能**-拒絕任何 [Windows 便攜裝置](/windows-hardware/drivers/portable/)的讀取或寫入權限，例如：平板電腦、iPhone。</span><span class="sxs-lookup"><span data-stu-id="53acd-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="53acd-135">**描述**</span><span class="sxs-lookup"><span data-stu-id="53acd-135">**Description**</span></span>
- <span data-ttu-id="53acd-136">在任何一部機器或使用者或兩者上套用。</span><span class="sxs-lookup"><span data-stu-id="53acd-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="53acd-137">支援 MEM OMA-URI 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="53acd-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="53acd-138">**支援的平臺** Windows 10</span><span class="sxs-lookup"><span data-stu-id="53acd-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="53acd-139">Endpoint DLP 可拆卸儲存體</span><span class="sxs-lookup"><span data-stu-id="53acd-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="53acd-140">**功能** -審計或警告或防止使用者將專案或資訊複製到卸除式媒體或 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="53acd-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="53acd-141">**Description** -如需 Windows 的詳細資訊，請參閱 [瞭解 Microsoft 365 端點資料遺失防護](../../compliance/endpoint-dlp-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="53acd-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="53acd-142">**支援的平臺** Windows 10</span><span class="sxs-lookup"><span data-stu-id="53acd-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="53acd-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="53acd-143">BitLocker</span></span> 

<span data-ttu-id="53acd-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="53acd-144">**Capabilities**</span></span>
- <span data-ttu-id="53acd-145">封鎖資料以寫入不 BitLocker 受保護的抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="53acd-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="53acd-146">封鎖對卸除式磁碟機的存取，除非在組織所擁有的電腦上加密。</span><span class="sxs-lookup"><span data-stu-id="53acd-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="53acd-147">**Description** -如需 Windows 的詳細資訊，請參閱 [BitLocker –抽取式磁碟磁碟機設定](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)。</span><span class="sxs-lookup"><span data-stu-id="53acd-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="53acd-148">**支援的平臺** Windows 10</span><span class="sxs-lookup"><span data-stu-id="53acd-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="53acd-149">裝置內容</span><span class="sxs-lookup"><span data-stu-id="53acd-149">Device properties</span></span>

<span data-ttu-id="53acd-150">Microsoft Defender for Endpoint Device Control Control 儲存體 Protection 可讓您根據下表中所述的屬性限制「可拆卸儲存體存取」：</span><span class="sxs-lookup"><span data-stu-id="53acd-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="53acd-151">內容名稱</span><span class="sxs-lookup"><span data-stu-id="53acd-151">Property Name</span></span>  |<span data-ttu-id="53acd-152">適用原則</span><span class="sxs-lookup"><span data-stu-id="53acd-152">Applicable Policies</span></span>  |<span data-ttu-id="53acd-153">適用于作業系統</span><span class="sxs-lookup"><span data-stu-id="53acd-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="53acd-154">描述</span><span class="sxs-lookup"><span data-stu-id="53acd-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="53acd-155">裝置類別</span><span class="sxs-lookup"><span data-stu-id="53acd-155">Device Class</span></span>    |     [<span data-ttu-id="53acd-156">如何使用 Microsoft Defender for Endpoint 控制 USB 裝置和其他卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="53acd-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="53acd-157">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-157">Windows</span></span>      |  <span data-ttu-id="53acd-158">如需裝置識別碼格式的相關資訊，請參閱 [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。</span><span class="sxs-lookup"><span data-stu-id="53acd-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="53acd-159">**附注**：裝置安裝可以套用至任何裝置，而不只是可移動儲存裝置。</span><span class="sxs-lookup"><span data-stu-id="53acd-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="53acd-160">主要識別碼</span><span class="sxs-lookup"><span data-stu-id="53acd-160">Primary ID</span></span>   |     <span data-ttu-id="53acd-161">可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="53acd-162">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-162">Windows</span></span>      |      <span data-ttu-id="53acd-163">主要識別碼包括「可移動儲存」和「CD/DVD」。</span><span class="sxs-lookup"><span data-stu-id="53acd-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="53acd-164">裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="53acd-164">Device ID</span></span>     |  <span data-ttu-id="53acd-165">[如何使用 Microsoft Defender For Endpoint 來控制 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md);可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="53acd-166">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-166">Windows</span></span>   |    <span data-ttu-id="53acd-167">如需裝置識別碼格式的相關資訊，請參閱 [標準的 USB 識別碼](/windows-hardware/drivers/install/standard-usb-identifiers)，例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8。</span><span class="sxs-lookup"><span data-stu-id="53acd-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="53acd-168">硬體識別碼</span><span class="sxs-lookup"><span data-stu-id="53acd-168">Hardware ID</span></span>     |     <span data-ttu-id="53acd-169">[如何使用 Microsoft Defender For Endpoint 來控制 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md);可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="53acd-170">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-170">Windows</span></span>    |    <span data-ttu-id="53acd-171">識別系統中裝置的字串，例如，USBSTOR \ DiskGeneric_Flash_Disk______8 07; **附注**：硬體識別碼不是唯一的;不同裝置可能會共用相同的值。</span><span class="sxs-lookup"><span data-stu-id="53acd-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="53acd-172">實例識別碼</span><span class="sxs-lookup"><span data-stu-id="53acd-172">Instance ID</span></span>    | <span data-ttu-id="53acd-173">裝置安裝;可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="53acd-174">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-174">Windows</span></span>    |   <span data-ttu-id="53acd-175">字串可唯一識別系統中的裝置，例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8 07 \ 8735B611&0</span><span class="sxs-lookup"><span data-stu-id="53acd-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="53acd-176">易記名稱</span><span class="sxs-lookup"><span data-stu-id="53acd-176">Friendly Name</span></span>     |     <span data-ttu-id="53acd-177">可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="53acd-178">Windows</span><span class="sxs-lookup"><span data-stu-id="53acd-178">Windows</span></span>      |    <span data-ttu-id="53acd-179">附加至裝置的字串，例如一般快閃磁片 USB 裝置</span><span class="sxs-lookup"><span data-stu-id="53acd-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="53acd-180">廠商識別碼/產品識別碼</span><span class="sxs-lookup"><span data-stu-id="53acd-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="53acd-181">可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="53acd-182">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="53acd-182">Windows Mac</span></span>      |     <span data-ttu-id="53acd-183">[廠商識別碼] 是 USB 委員會指派給廠商的四位數廠商程式碼。</span><span class="sxs-lookup"><span data-stu-id="53acd-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="53acd-184">產品識別碼是廠商指派給裝置的四位數產品碼;支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="53acd-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="53acd-185">串列 NumberId</span><span class="sxs-lookup"><span data-stu-id="53acd-185">Serial NumberId</span></span>     |     <span data-ttu-id="53acd-186">可拆卸儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="53acd-187">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="53acd-187">Windows Mac</span></span>   |     <span data-ttu-id="53acd-188">例如， <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="53acd-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="53acd-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="53acd-189">Related topic</span></span>

- [<span data-ttu-id="53acd-190">Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="53acd-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

