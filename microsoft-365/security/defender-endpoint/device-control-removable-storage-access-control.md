---
title: Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制
description: 關於 Microsoft Defender for Endpoint 的逐步說明
keywords: 可移動儲存媒體
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 801d94eb769c6b738a1d4c011b67f8a2a7cf81f1
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430801"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="789d9-104">Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制</span><span class="sxs-lookup"><span data-stu-id="789d9-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="789d9-105">Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制可讓您執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="789d9-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="789d9-106">審核，允許或防止讀取、寫入或執行可移動儲存的讀取、寫入或執行存取（含或不含）</span><span class="sxs-lookup"><span data-stu-id="789d9-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="789d9-107">特權</span><span class="sxs-lookup"><span data-stu-id="789d9-107">Privilege</span></span> |<span data-ttu-id="789d9-108">權限</span><span class="sxs-lookup"><span data-stu-id="789d9-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="789d9-109">Access</span><span class="sxs-lookup"><span data-stu-id="789d9-109">Access</span></span>    |  <span data-ttu-id="789d9-110">讀取、寫入、執行</span><span class="sxs-lookup"><span data-stu-id="789d9-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="789d9-111">動作模式</span><span class="sxs-lookup"><span data-stu-id="789d9-111">Action Mode</span></span>    |    <span data-ttu-id="789d9-112">Audit、Allow、防止</span><span class="sxs-lookup"><span data-stu-id="789d9-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="789d9-113">CSP 支援</span><span class="sxs-lookup"><span data-stu-id="789d9-113">CSP Support</span></span>   |   <span data-ttu-id="789d9-114">是</span><span class="sxs-lookup"><span data-stu-id="789d9-114">Yes</span></span>      |
|<span data-ttu-id="789d9-115">GPO 支援</span><span class="sxs-lookup"><span data-stu-id="789d9-115">GPO Support</span></span>    |   <span data-ttu-id="789d9-116">是</span><span class="sxs-lookup"><span data-stu-id="789d9-116">Yes</span></span>      |
|<span data-ttu-id="789d9-117">以使用者為基礎的支援</span><span class="sxs-lookup"><span data-stu-id="789d9-117">User-based Support</span></span>     |   <span data-ttu-id="789d9-118">是</span><span class="sxs-lookup"><span data-stu-id="789d9-118">Yes</span></span>      |
|<span data-ttu-id="789d9-119">以機器為基礎的支援</span><span class="sxs-lookup"><span data-stu-id="789d9-119">Machine-based Support</span></span>    |    <span data-ttu-id="789d9-120">是</span><span class="sxs-lookup"><span data-stu-id="789d9-120">Yes</span></span>     |

## <a name="licensing"></a><span data-ttu-id="789d9-121">授權</span><span class="sxs-lookup"><span data-stu-id="789d9-121">Licensing</span></span>

<span data-ttu-id="789d9-122">開始使用 [可移動儲存體] 存取控制之前，您應該先[確認 Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="789d9-122">Before you get started with Removable Storage Access Control, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="789d9-123">若要存取和使用 [可移動儲存體] 存取控制，您必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="789d9-123">To access and use Removable Storage Access Control, you must have the following:</span></span>

- <span data-ttu-id="789d9-124">功能/原則部署的 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="789d9-124">Microsoft 365 E3 for functionality/policy deployment.</span></span>
- <span data-ttu-id="789d9-125">報告 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="789d9-125">Microsoft 365 E5 for reporting.</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="789d9-126">準備您的端點</span><span class="sxs-lookup"><span data-stu-id="789d9-126">Prepare your endpoints</span></span>

<span data-ttu-id="789d9-127">在具有反惡意軟體用戶端版本 **4.18.2103.3 或更新** 版本的 Windows 10 裝置上，部署可移動儲存體存取控制。</span><span class="sxs-lookup"><span data-stu-id="789d9-127">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="789d9-128">**4.18.2104 或更新版本**：新增 SerialNumberId、VID_PID、以 filepath 為基礎的 GPO 支援、ComputerSid</span><span class="sxs-lookup"><span data-stu-id="789d9-128">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="789d9-129">**4.18.2105 或更新版本**：針對 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 新增萬用字元支援、特定電腦上的特定使用者組合、可移動 SSD (SANDISK 至尊 SSD) /USB 連接的 SCSI (UAS) 支援</span><span class="sxs-lookup"><span data-stu-id="789d9-129">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="789d9-130">**4.18.2107 或更新版本**：新增 Windows 可擕式裝置 (WPD) 支援 (以供行動裝置（例如平板電腦) ）</span><span class="sxs-lookup"><span data-stu-id="789d9-130">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 介面":::

> [!NOTE]
> <span data-ttu-id="789d9-132">Windows 安全性元件都不需要使用中，您可以執行可移動儲存體存取控制，而不限 Windows 安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="789d9-132">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="789d9-133">原則屬性</span><span class="sxs-lookup"><span data-stu-id="789d9-133">Policy properties</span></span>

<span data-ttu-id="789d9-134">您可以使用下列屬性建立「可移動儲存」群組：</span><span class="sxs-lookup"><span data-stu-id="789d9-134">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="789d9-135">**屬性名稱：群組識別碼**</span><span class="sxs-lookup"><span data-stu-id="789d9-135">**Property name: Group Id**</span></span>

1. <span data-ttu-id="789d9-136">描述： [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、唯一識別碼、代表群組，並將用於原則中。</span><span class="sxs-lookup"><span data-stu-id="789d9-136">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="789d9-137">**屬性名稱： DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="789d9-137">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="789d9-138">描述：列出您要用來在群組中涵蓋的裝置屬性。</span><span class="sxs-lookup"><span data-stu-id="789d9-138">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="789d9-139">如需每個裝置屬性的詳細資訊，請參閱上述 **裝置** 內容一節。</span><span class="sxs-lookup"><span data-stu-id="789d9-139">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="789d9-140">選項：</span><span class="sxs-lookup"><span data-stu-id="789d9-140">Options:</span></span>
    - <span data-ttu-id="789d9-141">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="789d9-141">PrimaryId</span></span>
        - <span data-ttu-id="789d9-142">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="789d9-142">RemovableMediaDevices</span></span>
        - <span data-ttu-id="789d9-143">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="789d9-143">CdRomDevices</span></span>
        - <span data-ttu-id="789d9-144">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="789d9-144">WpdDevices</span></span>
    - <span data-ttu-id="789d9-145">DeviceId</span><span class="sxs-lookup"><span data-stu-id="789d9-145">DeviceId</span></span>
    - <span data-ttu-id="789d9-146">HardwareId</span><span class="sxs-lookup"><span data-stu-id="789d9-146">HardwareId</span></span>
    - <span data-ttu-id="789d9-147">InstancePathId： InstancePathId 是唯一識別系統中裝置的字串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8 .07 \ 8735B611&0。</span><span class="sxs-lookup"><span data-stu-id="789d9-147">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="789d9-148">例如， (**&0**) 代表可用的槽，而且可能會從裝置變更為裝置。</span><span class="sxs-lookup"><span data-stu-id="789d9-148">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="789d9-149">為了獲得最佳結果，請在結尾使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="789d9-149">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="789d9-150">例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8。 07 \ 8735B611 \*</span><span class="sxs-lookup"><span data-stu-id="789d9-150">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="789d9-151">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="789d9-151">FriendlyNameId</span></span>
    - <span data-ttu-id="789d9-152">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="789d9-152">SerialNumberId</span></span>
    - <span data-ttu-id="789d9-153">Vid</span><span class="sxs-lookup"><span data-stu-id="789d9-153">VID</span></span>
    - <span data-ttu-id="789d9-154">Pid</span><span class="sxs-lookup"><span data-stu-id="789d9-154">PID</span></span>
    - <span data-ttu-id="789d9-155">VID_PID</span><span class="sxs-lookup"><span data-stu-id="789d9-155">VID_PID</span></span>
        - <span data-ttu-id="789d9-156">0751_55E0：符合此確切的 VID/PID 對</span><span class="sxs-lookup"><span data-stu-id="789d9-156">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="789d9-157">_55E0：搭配任何具有 PID = 55E0 的媒體</span><span class="sxs-lookup"><span data-stu-id="789d9-157">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="789d9-158">0751_：搭配任何具有 VID = 0751 的媒體</span><span class="sxs-lookup"><span data-stu-id="789d9-158">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="789d9-159">**屬性名稱： MatchType**</span><span class="sxs-lookup"><span data-stu-id="789d9-159">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="789d9-160">描述：當 DescriptorIDList 中使用多個裝置屬性時，MatchType 會定義關聯性。</span><span class="sxs-lookup"><span data-stu-id="789d9-160">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="789d9-161">選項：</span><span class="sxs-lookup"><span data-stu-id="789d9-161">Options:</span></span>

    - <span data-ttu-id="789d9-162">MatchAll： DescriptorIdList 下的任何屬性都是 **和** 關聯;例如，如果系統管理員將 DeviceID 和 InstancePathID，用於每個連線的 USB，系統會檢查 USB 是否同時滿足這兩個值。</span><span class="sxs-lookup"><span data-stu-id="789d9-162">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="789d9-163">MatchAny： [DescriptorIdList] 底下的屬性將是 **Or** relationship;例如，如果系統管理員為 DeviceID 和 InstancePathID，則對於每個連線的 USB，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系統就會執行強制執行。</span><span class="sxs-lookup"><span data-stu-id="789d9-163">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="789d9-164">以下是存取控制原則屬性：</span><span class="sxs-lookup"><span data-stu-id="789d9-164">Following are the access control policy properties:</span></span>

<span data-ttu-id="789d9-165">**屬性名稱： PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="789d9-165">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="789d9-166">描述： [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、唯一識別碼、代表原則，並將用於報告和疑難排解。</span><span class="sxs-lookup"><span data-stu-id="789d9-166">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="789d9-167">**屬性名稱： IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="789d9-167">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="789d9-168">描述：將套用原則的群組 (s) 。</span><span class="sxs-lookup"><span data-stu-id="789d9-168">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="789d9-169">如果新增多個群組，則會將原則套用至所有群組中的任何介質。</span><span class="sxs-lookup"><span data-stu-id="789d9-169">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="789d9-170">選項：此實例必須使用群組識別碼/GUID。</span><span class="sxs-lookup"><span data-stu-id="789d9-170">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="789d9-171">下列範例顯示 GroupID 的使用方式：</span><span class="sxs-lookup"><span data-stu-id="789d9-171">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="789d9-172">**屬性名稱： ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="789d9-172">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="789d9-173">描述：不會將原則套用至的群組 (s) 。</span><span class="sxs-lookup"><span data-stu-id="789d9-173">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="789d9-174">選項：此實例必須使用群組識別碼/GUID。</span><span class="sxs-lookup"><span data-stu-id="789d9-174">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="789d9-175">**屬性名稱：專案識別碼**</span><span class="sxs-lookup"><span data-stu-id="789d9-175">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="789d9-176">描述：一個 PolicyRule 可以有多個專案;每個具有唯一 GUID 的專案都會告訴裝置控制一種限制。</span><span class="sxs-lookup"><span data-stu-id="789d9-176">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="789d9-177">**屬性名稱： Type**</span><span class="sxs-lookup"><span data-stu-id="789d9-177">**Property name: Type**</span></span>

1. <span data-ttu-id="789d9-178">描述：針對 IncludedIDList 中的可移動儲存群組定義動作。</span><span class="sxs-lookup"><span data-stu-id="789d9-178">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="789d9-179">強制執行：允許或拒絕</span><span class="sxs-lookup"><span data-stu-id="789d9-179">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="789d9-180">Audit： AuditAllowed 或 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="789d9-180">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="789d9-181">選項：</span><span class="sxs-lookup"><span data-stu-id="789d9-181">Options:</span></span>

    - <span data-ttu-id="789d9-182">允許</span><span class="sxs-lookup"><span data-stu-id="789d9-182">Allow</span></span>
    - <span data-ttu-id="789d9-183">拒絕</span><span class="sxs-lookup"><span data-stu-id="789d9-183">Deny</span></span>
    - <span data-ttu-id="789d9-184">AuditAllowed：定義允許存取時的通知和事件</span><span class="sxs-lookup"><span data-stu-id="789d9-184">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="789d9-185">AuditDenied：在存取遭到拒絕時定義通知和事件;必須一起使用 **Deny** 專案。</span><span class="sxs-lookup"><span data-stu-id="789d9-185">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="789d9-186">當同一個媒體有衝突類型時，系統會將原則中的第一個類型。</span><span class="sxs-lookup"><span data-stu-id="789d9-186">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="789d9-187">衝突類型的範例為 **Allow** 和 **Deny**。</span><span class="sxs-lookup"><span data-stu-id="789d9-187">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="789d9-188">**屬性名稱： Sid**</span><span class="sxs-lookup"><span data-stu-id="789d9-188">**Property name: Sid**</span></span>

<span data-ttu-id="789d9-189">描述：本機電腦 Sid 或 AD 物件的 Sid，定義是否要在特定使用者或使用者群組上套用此原則;一個專案最多可以有一個 Sid，而沒有任何 Sid 的專案則表示在機器上套用原則。</span><span class="sxs-lookup"><span data-stu-id="789d9-189">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="789d9-190">**屬性名稱： ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="789d9-190">**Property name: ComputerSid**</span></span>

<span data-ttu-id="789d9-191">描述：本機電腦 Sid 或 AD 物件的 Sid，定義是否要在特定機器或電腦群組上套用此原則;一個專案最多可以有一個 ComputerSid，而沒有任何 ComputerSid 的專案則表示在機器上套用原則。</span><span class="sxs-lookup"><span data-stu-id="789d9-191">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="789d9-192">如果您想要將專案套用至特定使用者和特定的機器，請將 Sid 和 ComputerSid 新增至相同的專案。</span><span class="sxs-lookup"><span data-stu-id="789d9-192">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="789d9-193">**屬性名稱：選項**</span><span class="sxs-lookup"><span data-stu-id="789d9-193">**Property name: Options**</span></span>

<span data-ttu-id="789d9-194">描述：定義是否要顯示通知。</span><span class="sxs-lookup"><span data-stu-id="789d9-194">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="可看到裝置狀態的畫面":::

<span data-ttu-id="789d9-196">選項：0-4。</span><span class="sxs-lookup"><span data-stu-id="789d9-196">Options: 0-4.</span></span> <span data-ttu-id="789d9-197">選取 [類型允許] 或 [拒絕] 時：</span><span class="sxs-lookup"><span data-stu-id="789d9-197">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="789d9-198">0：無</span><span class="sxs-lookup"><span data-stu-id="789d9-198">0: nothing</span></span>
   - <span data-ttu-id="789d9-199">4：停用此專案的 **AuditAllowed** 和 **AuditDenied** 。</span><span class="sxs-lookup"><span data-stu-id="789d9-199">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="789d9-200">即使發生 **封鎖** ，且已設定 **AuditDenied** ，系統就不會顯示通知。</span><span class="sxs-lookup"><span data-stu-id="789d9-200">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="789d9-201">選取 [類型 **AuditAllowed** ] 或 [ **AuditDenied** ] 時：</span><span class="sxs-lookup"><span data-stu-id="789d9-201">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="789d9-202">0：無</span><span class="sxs-lookup"><span data-stu-id="789d9-202">0: nothing</span></span>
   - <span data-ttu-id="789d9-203">1：顯示通知</span><span class="sxs-lookup"><span data-stu-id="789d9-203">1: show notification</span></span>
   - <span data-ttu-id="789d9-204">2： send 事件</span><span class="sxs-lookup"><span data-stu-id="789d9-204">2: send event</span></span>
   - <span data-ttu-id="789d9-205">3：顯示通知及傳送事件</span><span class="sxs-lookup"><span data-stu-id="789d9-205">3: show notification and send event</span></span>

<span data-ttu-id="789d9-206">**屬性名稱： AccessMask**</span><span class="sxs-lookup"><span data-stu-id="789d9-206">**Property name: AccessMask**</span></span>

<span data-ttu-id="789d9-207">描述：定義存取。</span><span class="sxs-lookup"><span data-stu-id="789d9-207">Description: Defines the access.</span></span>

<span data-ttu-id="789d9-208">選項1-7：</span><span class="sxs-lookup"><span data-stu-id="789d9-208">Options 1-7:</span></span>
  - <span data-ttu-id="789d9-209">1：讀取</span><span class="sxs-lookup"><span data-stu-id="789d9-209">1: Read</span></span>
  - <span data-ttu-id="789d9-210">2：寫入</span><span class="sxs-lookup"><span data-stu-id="789d9-210">2: Write</span></span>
  - <span data-ttu-id="789d9-211">3：讀取和寫入</span><span class="sxs-lookup"><span data-stu-id="789d9-211">3: Read and Write</span></span>
  - <span data-ttu-id="789d9-212">4：執行</span><span class="sxs-lookup"><span data-stu-id="789d9-212">4: Execute</span></span>
  - <span data-ttu-id="789d9-213">5：讀取和執行</span><span class="sxs-lookup"><span data-stu-id="789d9-213">5: Read and Execute</span></span>
  - <span data-ttu-id="789d9-214">6：寫入和執行</span><span class="sxs-lookup"><span data-stu-id="789d9-214">6: Write and Execute</span></span>
  - <span data-ttu-id="789d9-215">7：讀取和寫入和執行</span><span class="sxs-lookup"><span data-stu-id="789d9-215">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="789d9-216">常見的可移動儲存體存取控制案例</span><span class="sxs-lookup"><span data-stu-id="789d9-216">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="789d9-217">為了協助您熟悉 Microsoft Defender for Endpoint 可移動儲存體存取控制，我們為您提供下列一些常見案例。</span><span class="sxs-lookup"><span data-stu-id="789d9-217">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="789d9-218">案例1：防止寫入和執行所有但允許特定核准 USBs 的存取</span><span class="sxs-lookup"><span data-stu-id="789d9-218">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="789d9-219">建立群組</span><span class="sxs-lookup"><span data-stu-id="789d9-219">Create groups</span></span>

    1. <span data-ttu-id="789d9-220">群組1：任何「可移動儲存」和「CD/DVD」。</span><span class="sxs-lookup"><span data-stu-id="789d9-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="789d9-221">例如，可移動儲存區和 CD/DVD 的範例是： Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the the Group.xmlFile 的 [任何可移動儲存體和 cd dvd](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。</span><span class="sxs-lookup"><span data-stu-id="789d9-221">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="789d9-222">群組2：根據裝置屬性核准的 USBs。</span><span class="sxs-lookup"><span data-stu-id="789d9-222">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="789d9-223">此使用案例的範例為：範例識別碼– Group **65fa649a-a111-4912-9294-fb6337a25038** In 樣本 [已核准的 USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔。</span><span class="sxs-lookup"><span data-stu-id="789d9-223">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="789d9-224">您必須以 `&` 值取代 `&amp;` 。</span><span class="sxs-lookup"><span data-stu-id="789d9-224">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="789d9-225">建立原則</span><span class="sxs-lookup"><span data-stu-id="789d9-225">Create policy</span></span>

    1. <span data-ttu-id="789d9-226">原則1：封鎖寫入和執行存取，但允許核准的 USBs。</span><span class="sxs-lookup"><span data-stu-id="789d9-226">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="789d9-227">此使用案例的範例是： PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** In 範例 [案例1封鎖寫入和執行存取，但允許核准的 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案。</span><span class="sxs-lookup"><span data-stu-id="789d9-227">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="789d9-228">原則2：對允許的 USBs 的「寫入」和「執行」存取權。</span><span class="sxs-lookup"><span data-stu-id="789d9-228">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="789d9-229">這種使用案例的範例是： PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** In 範例 [案例1的「審核寫入」和「執行核准 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案的存取」。</span><span class="sxs-lookup"><span data-stu-id="789d9-229">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="789d9-230">案例2：審核寫入並執行全部，但封鎖特定的未核准 USBs</span><span class="sxs-lookup"><span data-stu-id="789d9-230">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="789d9-231">建立群組</span><span class="sxs-lookup"><span data-stu-id="789d9-231">Create groups</span></span>

    1. <span data-ttu-id="789d9-232">群組1：任何「可移動儲存」和「CD/DVD」。</span><span class="sxs-lookup"><span data-stu-id="789d9-232">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="789d9-233">此使用案例的範例是： Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample Group.xmlfile 中的 [任何可移動儲存體和 CD DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)檔案。</span><span class="sxs-lookup"><span data-stu-id="789d9-233">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="789d9-234">群組2：根據裝置屬性（例如，在「未 [核准的 USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)檔案中的「廠商識別碼/產品識別碼」、「易記名稱–群組 **65fa649a-a111-4912-9294-fb6337a25038** 」）進行未核准的 USBs。</span><span class="sxs-lookup"><span data-stu-id="789d9-234">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="789d9-235">您必須以 `&` 值取代 `&amp;` 。</span><span class="sxs-lookup"><span data-stu-id="789d9-235">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="789d9-236">建立原則</span><span class="sxs-lookup"><span data-stu-id="789d9-236">Create policy</span></span>

    1. <span data-ttu-id="789d9-237">原則1：封鎖「寫入」和「執行」許可權，但會封鎖特定的未核准 USBs。</span><span class="sxs-lookup"><span data-stu-id="789d9-237">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="789d9-238">這種使用案例的範例是： PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** In 範例 [案例2的「審核寫入」和「執行」許可權，但會封鎖特定的未核准 USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案。</span><span class="sxs-lookup"><span data-stu-id="789d9-238">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="789d9-239">原則2：對其他人進行審核寫入和執行存取。</span><span class="sxs-lookup"><span data-stu-id="789d9-239">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="789d9-240">這種使用案例的範例是： PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** In 範例 [案例2的「審核寫入」和「執行」 others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="789d9-240">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="789d9-241">透過群組原則部署及管理原則</span><span class="sxs-lookup"><span data-stu-id="789d9-241">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="789d9-242">「可移動儲存體存取控制」功能可讓您透過群組原則將原則套用至使用者或裝置，或同時套用兩者。</span><span class="sxs-lookup"><span data-stu-id="789d9-242">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="789d9-243">授權</span><span class="sxs-lookup"><span data-stu-id="789d9-243">Licensing</span></span>

<span data-ttu-id="789d9-244">開始使用 [可移動儲存體] 存取控制之前，必須先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="789d9-244">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="789d9-245">若要存取和使用 [可移動儲存體] 存取控制，您必須具有 Microsoft 365 E3 或 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="789d9-245">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="789d9-246">透過群組原則部署原則</span><span class="sxs-lookup"><span data-stu-id="789d9-246">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="789d9-247">將所有群組合並 `<Groups>` `</Groups>` 成一個 xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="789d9-247">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="789d9-248">下圖說明案例1的範例 [：防止寫入和執行全部，但允許特定核准的 USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。</span><span class="sxs-lookup"><span data-stu-id="789d9-248">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="顯示在裝置上允許特定核准 USBs 之設定設定的畫面":::
    
2. <span data-ttu-id="789d9-250">將所有規則合併 `<PolicyRules>` `</PolicyRules>` 到一個 xml 檔案中。</span><span class="sxs-lookup"><span data-stu-id="789d9-250">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="789d9-251">如果您想要限制特定使用者，請使用 SID 屬性進入專案中。</span><span class="sxs-lookup"><span data-stu-id="789d9-251">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="789d9-252">若原則專案中沒有 SID，該專案將會套用到機器的所有使用者登入實例。</span><span class="sxs-lookup"><span data-stu-id="789d9-252">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="789d9-253">下圖說明 SID 內容的使用方式，以及案例1的範例 [：防止寫入權及執行全部，但允許特定核准的 USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。</span><span class="sxs-lookup"><span data-stu-id="789d9-253">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="顯示程式碼以指出 SID 屬性屬性用法的畫面":::

3. <span data-ttu-id="789d9-255">在網路共用資料夾上儲存規則和群組 XML 檔案，並將網路共用資料夾路徑放入「群組原則」設定中：「**電腦設定-> 系統管理範本-> Windows 元件-> Microsoft Defender 防毒軟體-> 裝置控制項： ' 定義裝置控制項原則群組」和「定義裝置控制項原則規則**」。</span><span class="sxs-lookup"><span data-stu-id="789d9-255">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="789d9-256">目的機器必須能夠存取網路共用以具備該原則。</span><span class="sxs-lookup"><span data-stu-id="789d9-256">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="789d9-257">不過，在閱讀原則之後，就不再需要網路共用連線，即使機器重新開機也是一樣。</span><span class="sxs-lookup"><span data-stu-id="789d9-257">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="裝置控制項畫面":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="789d9-259">透過 Intune OMA-URI 部署及管理原則</span><span class="sxs-lookup"><span data-stu-id="789d9-259">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="789d9-260">「可移動儲存體存取控制」功能可讓您透過 OMA-URI 將原則套用至使用者或裝置，或同時套用兩者。</span><span class="sxs-lookup"><span data-stu-id="789d9-260">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="789d9-261">授權</span><span class="sxs-lookup"><span data-stu-id="789d9-261">Licensing</span></span>

<span data-ttu-id="789d9-262">開始使用 [可移動儲存體] 存取控制之前，必須先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="789d9-262">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="789d9-263">若要存取和使用 [可移動儲存體] 存取控制，您必須具有 Microsoft 365 E3 或 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="789d9-263">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="789d9-264">權限</span><span class="sxs-lookup"><span data-stu-id="789d9-264">Permission</span></span>

<span data-ttu-id="789d9-265">針對 Intune 中的原則部署，帳戶必須具有建立、編輯、更新或刪除裝置設定檔的許可權。</span><span class="sxs-lookup"><span data-stu-id="789d9-265">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="789d9-266">您可以建立自訂角色，或使用具有這些許可權的任何內建角色。</span><span class="sxs-lookup"><span data-stu-id="789d9-266">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="789d9-267">原則與設定檔管理員角色</span><span class="sxs-lookup"><span data-stu-id="789d9-267">Policy and profile Manager role</span></span>
- <span data-ttu-id="789d9-268">已開啟裝置設定檔的「建立/編輯/更新/讀取/刪除/查看報告」許可權的自訂角色</span><span class="sxs-lookup"><span data-stu-id="789d9-268">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="789d9-269">全域管理員</span><span class="sxs-lookup"><span data-stu-id="789d9-269">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="789d9-270">透過 OMA-URI 部署原則</span><span class="sxs-lookup"><span data-stu-id="789d9-270">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="789d9-271">**Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com/) > 裝置-> 設定檔-> 建立設定檔-> 平臺： Windows 10 和更新版本 & 設定檔：自訂**</span><span class="sxs-lookup"><span data-stu-id="789d9-271">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="789d9-272">針對每個群組建立 OMA URI 規則：</span><span class="sxs-lookup"><span data-stu-id="789d9-272">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="789d9-273">OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="789d9-273">OMA-URI:</span></span>

      <span data-ttu-id="789d9-274">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**% 7D/GroupData</span><span class="sxs-lookup"><span data-stu-id="789d9-274">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="789d9-275">例如，對於範例中的 **任何「可移動儲存」和「CD/DVD」** 群組，連結必須是：</span><span class="sxs-lookup"><span data-stu-id="789d9-275">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="789d9-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="789d9-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="789d9-277">資料類型： String (XML 檔案) </span><span class="sxs-lookup"><span data-stu-id="789d9-277">Data Type: String (XML file)</span></span>

2. <span data-ttu-id="789d9-278">針對每個原則，也建立 OMA URI：</span><span class="sxs-lookup"><span data-stu-id="789d9-278">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="789d9-279">OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="789d9-279">OMA-URI:</span></span>

      <span data-ttu-id="789d9-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="789d9-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="789d9-281">例如，針對 **區塊寫入和執行存取，但允許** 範例中的核准 USBs 規則，該連結必須是：</span><span class="sxs-lookup"><span data-stu-id="789d9-281">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="789d9-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="789d9-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="789d9-283">資料類型： String (XML 檔案) </span><span class="sxs-lookup"><span data-stu-id="789d9-283">Data Type: String (XML file)</span></span>


## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="789d9-284">使用 Intune 使用者介面部署及管理原則</span><span class="sxs-lookup"><span data-stu-id="789d9-284">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="789d9-285">這項功能 (在 Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com/) > 裝置 > 設定設定檔 > 建立設定檔 > 平臺： Windows 10 和更新版本 & 設定檔：尚未提供裝置控制項) 。</span><span class="sxs-lookup"><span data-stu-id="789d9-285">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="789d9-286">View Device Control 可移動儲存體 Microsoft Defender for Endpoint 中的存取控制資料</span><span class="sxs-lookup"><span data-stu-id="789d9-286">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="789d9-287">Microsoft 365 安全性入口網站顯示由裝置控制項可移動儲存體存取控制封鎖的可拆卸儲存體。</span><span class="sxs-lookup"><span data-stu-id="789d9-287">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="789d9-288">若要存取 Microsoft 365 的安全性，您必須具備下列訂閱：</span><span class="sxs-lookup"><span data-stu-id="789d9-288">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="789d9-289">E5 報表的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="789d9-289">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="描述「可移動儲存」之瓶頸的畫面":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="789d9-291">常見問題集</span><span class="sxs-lookup"><span data-stu-id="789d9-291">Frequently asked questions</span></span>

<span data-ttu-id="789d9-292">**USBs 最大數目的可拆卸儲存體媒體限制是多少？**</span><span class="sxs-lookup"><span data-stu-id="789d9-292">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="789d9-293">我們已驗證一個具有100000媒體的 USB 群組（大小高達 7 MB）。</span><span class="sxs-lookup"><span data-stu-id="789d9-293">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="789d9-294">原則可在 Intune 和 GPO 中運作，但不會出現效能問題。</span><span class="sxs-lookup"><span data-stu-id="789d9-294">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="789d9-295">**為何原則無法運作？**</span><span class="sxs-lookup"><span data-stu-id="789d9-295">**Why does the policy not work?**</span></span>

<span data-ttu-id="789d9-296">最常見的原因是沒有必要的 [反惡意程式碼用戶端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="789d9-296">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="789d9-297">另一個原因可能是 XML 檔的格式不正確，例如，未使用 XML 檔案中 "&" 字元的正確 markdown 格式，或文字編輯器可能會在導致 XML 分析無法運作的檔案開頭，新增一個位元組順序標記 (BOM) 0xEF 0xBB 0xBF。</span><span class="sxs-lookup"><span data-stu-id="789d9-297">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="789d9-298">一個簡單的解決方案是下載 [範例](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 檔案 (選取 [ **Raw** ]，然後按一下 [ **另存** 新檔]) 然後更新。</span><span class="sxs-lookup"><span data-stu-id="789d9-298">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="789d9-299">如果有值而且原則是透過「群組原則」管理，請檢查用戶端裝置是否可以存取原則 XML 路徑。</span><span class="sxs-lookup"><span data-stu-id="789d9-299">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="789d9-300">**如何知道哪些機器在組織中使用的反惡意軟體用戶端版本已過時？**</span><span class="sxs-lookup"><span data-stu-id="789d9-300">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="789d9-301">您可以使用下列查詢來取得 Microsoft 365 安全性入口網站上的反惡意程式碼用戶端版本：</span><span class="sxs-lookup"><span data-stu-id="789d9-301">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
