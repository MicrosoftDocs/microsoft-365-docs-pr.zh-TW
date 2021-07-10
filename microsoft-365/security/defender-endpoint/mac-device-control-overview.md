---
title: macOS 的裝置控制項
description: 瞭解如何針對 Mac 設定 Microsoft Defender for Endpoint，以減少可移動儲存區（如 USB 裝置）的威脅。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，device，control，usb，可移動，媒體
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363976"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="8fce1-104">macOS 的裝置控制項</span><span class="sxs-lookup"><span data-stu-id="8fce1-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8fce1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8fce1-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fce1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8fce1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8fce1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fce1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8fce1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="8fce1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8fce1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8fce1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="8fce1-110">需求</span><span class="sxs-lookup"><span data-stu-id="8fce1-110">Requirements</span></span>

<span data-ttu-id="8fce1-111">MacOS 的裝置控制具有下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="8fce1-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="8fce1-112">Microsoft Defender for Endpoint 的授權 (可以是試驗) </span><span class="sxs-lookup"><span data-stu-id="8fce1-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="8fce1-113">作業系統最低版本： macOS 11 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8fce1-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="8fce1-114">產品版本下限：101.34.20</span><span class="sxs-lookup"><span data-stu-id="8fce1-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="8fce1-115">裝置控制項原則</span><span class="sxs-lookup"><span data-stu-id="8fce1-115">Device control policy</span></span>

<span data-ttu-id="8fce1-116">若要設定 macOS 的裝置控制，您必須建立原則來描述您要放在組織內的限制。</span><span class="sxs-lookup"><span data-stu-id="8fce1-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="8fce1-117">裝置控制原則會包含在用來設定所有其他產品設定的設定檔中。</span><span class="sxs-lookup"><span data-stu-id="8fce1-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="8fce1-118">如需詳細資訊，請參閱 [設定檔結構](mac-preferences.md#configuration-profile-structure)。</span><span class="sxs-lookup"><span data-stu-id="8fce1-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="8fce1-119">在設定設定檔中，裝置控制項原則是在下列區段中定義：</span><span class="sxs-lookup"><span data-stu-id="8fce1-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="8fce1-120">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-120">Section</span></span>|<span data-ttu-id="8fce1-121">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-122">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-123">**Key**</span></span> | <span data-ttu-id="8fce1-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="8fce1-124">deviceControl</span></span> |
| <span data-ttu-id="8fce1-125">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-125">**Data type**</span></span> | <span data-ttu-id="8fce1-126">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="8fce1-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8fce1-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8fce1-127">**Comments**</span></span> | <span data-ttu-id="8fce1-128">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="8fce1-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="8fce1-129">裝置控制項原則可以用來：</span><span class="sxs-lookup"><span data-stu-id="8fce1-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="8fce1-130">自訂裝置控制項所引發之通知的 URL 目標</span><span class="sxs-lookup"><span data-stu-id="8fce1-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="8fce1-131">允許或封鎖可移動裝置</span><span class="sxs-lookup"><span data-stu-id="8fce1-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="8fce1-132">自訂由裝置控制所引發之通知的 URL 目標</span><span class="sxs-lookup"><span data-stu-id="8fce1-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="8fce1-133">在裝置上強制執行已就地安裝的裝置控制項原則時 (例如，對卸除式媒體裝置的存取限制在) ，向使用者顯示通知。</span><span class="sxs-lookup"><span data-stu-id="8fce1-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![裝置控制通知](images/mac-device-control-notification.png)

<span data-ttu-id="8fce1-135">當使用者按一下此通知時，網頁會在預設瀏覽器中開啟。</span><span class="sxs-lookup"><span data-stu-id="8fce1-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="8fce1-136">您可以設定使用者按一下通知時所開啟的 URL。</span><span class="sxs-lookup"><span data-stu-id="8fce1-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="8fce1-137">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-137">Section</span></span>|<span data-ttu-id="8fce1-138">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-139">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-140">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-140">**Key**</span></span> | <span data-ttu-id="8fce1-141">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="8fce1-141">navigationTarget</span></span> |
| <span data-ttu-id="8fce1-142">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-142">**Data type**</span></span> | <span data-ttu-id="8fce1-143">字串</span><span class="sxs-lookup"><span data-stu-id="8fce1-143">String</span></span> |
| <span data-ttu-id="8fce1-144">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8fce1-144">**Comments**</span></span> | <span data-ttu-id="8fce1-145">若未定義，產品會使用指向一般頁面的預設 URL，以說明產品所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8fce1-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="8fce1-146">允許或封鎖可移動裝置</span><span class="sxs-lookup"><span data-stu-id="8fce1-146">Allow or block removable devices</span></span>

<span data-ttu-id="8fce1-147">裝置控制項原則的「卸除式媒體」區段可用來限制對卸除式媒體的存取。</span><span class="sxs-lookup"><span data-stu-id="8fce1-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="8fce1-148">目前支援下列類型的卸除式媒體，而且可以包含在 [原則： USB 儲存裝置] 中。</span><span class="sxs-lookup"><span data-stu-id="8fce1-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="8fce1-149">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-149">Section</span></span>|<span data-ttu-id="8fce1-150">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-151">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-152">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-152">**Key**</span></span> | <span data-ttu-id="8fce1-153">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fce1-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="8fce1-154">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-154">**Data type**</span></span> | <span data-ttu-id="8fce1-155">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="8fce1-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8fce1-156">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8fce1-156">**Comments**</span></span> | <span data-ttu-id="8fce1-157">請參閱下列各節以取得字典內容的描述。</span><span class="sxs-lookup"><span data-stu-id="8fce1-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="8fce1-158">原則的此區段是階層式的，可讓您獲得最大的彈性，並涵蓋大量的使用案例。</span><span class="sxs-lookup"><span data-stu-id="8fce1-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="8fce1-159">在最上層是由廠商識別碼識別的廠商。</span><span class="sxs-lookup"><span data-stu-id="8fce1-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="8fce1-160">針對每個廠商，都有產品識別碼所識別的產品。</span><span class="sxs-lookup"><span data-stu-id="8fce1-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="8fce1-161">最後，每個產品都有用於表示特定裝置的系列號碼。</span><span class="sxs-lookup"><span data-stu-id="8fce1-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="8fce1-162">如需如何尋找設備識別碼的詳細資訊，請參閱 [查詢裝置識別碼](#look-up-device-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="8fce1-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="8fce1-163">原則會從最特殊的專案評估為最一般的專案。</span><span class="sxs-lookup"><span data-stu-id="8fce1-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="8fce1-164">也就是說，裝置電源開啟時，產品會嘗試在每個可移除媒體裝置的原則中尋找最明確的相符，並在該等級套用許可權。</span><span class="sxs-lookup"><span data-stu-id="8fce1-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="8fce1-165">如果沒有任何相符專案，則會套用下一個符合最相符原則的最佳方式，當裝置與原則中的任何其他專案都不符合時，此為預設值。</span><span class="sxs-lookup"><span data-stu-id="8fce1-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="8fce1-166">原則強制執行層級</span><span class="sxs-lookup"><span data-stu-id="8fce1-166">Policy enforcement level</span></span>

<span data-ttu-id="8fce1-167">在 [卸除式媒體] 區段中，有一個選項可以設定強制執行層級，其可採用下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="8fce1-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="8fce1-168">`audit` -如果限制存取裝置，則會向使用者顯示通知，但仍然可以使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="8fce1-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="8fce1-169">此強制等級可用於評估原則的效能。</span><span class="sxs-lookup"><span data-stu-id="8fce1-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="8fce1-170">`block` -在此強制性層級下，使用者可以在裝置上執行的作業，會限制在原則中定義的專案。</span><span class="sxs-lookup"><span data-stu-id="8fce1-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="8fce1-171">此外，會對使用者提出通知。</span><span class="sxs-lookup"><span data-stu-id="8fce1-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8fce1-172">根據預設，強制性層級設為 `audit` 。</span><span class="sxs-lookup"><span data-stu-id="8fce1-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="8fce1-173">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-173">Section</span></span>|<span data-ttu-id="8fce1-174">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-175">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-176">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-176">**Key**</span></span> | <span data-ttu-id="8fce1-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="8fce1-177">enforcementLevel</span></span> |
| <span data-ttu-id="8fce1-178">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-178">**Data type**</span></span> | <span data-ttu-id="8fce1-179">字串</span><span class="sxs-lookup"><span data-stu-id="8fce1-179">String</span></span> |
| <span data-ttu-id="8fce1-180">**可能值**</span><span class="sxs-lookup"><span data-stu-id="8fce1-180">**Possible values**</span></span> | <span data-ttu-id="8fce1-181">審核 (預設) </span><span class="sxs-lookup"><span data-stu-id="8fce1-181">audit (default)</span></span> <br/> <span data-ttu-id="8fce1-182">塊</span><span class="sxs-lookup"><span data-stu-id="8fce1-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="8fce1-183">預設權限等級</span><span class="sxs-lookup"><span data-stu-id="8fce1-183">Default permission level</span></span>

<span data-ttu-id="8fce1-184">在 [卸除式媒體] 區段的最上層，您可以設定不符合原則中任何其他專案之裝置的預設許可權等級。</span><span class="sxs-lookup"><span data-stu-id="8fce1-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="8fce1-185">此設定可以設定為：</span><span class="sxs-lookup"><span data-stu-id="8fce1-185">This setting can be set to:</span></span>

- <span data-ttu-id="8fce1-186">`none` -無法在裝置上執行作業</span><span class="sxs-lookup"><span data-stu-id="8fce1-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="8fce1-187">下列值的組合：</span><span class="sxs-lookup"><span data-stu-id="8fce1-187">A combination of the following values:</span></span>
    - <span data-ttu-id="8fce1-188">`read` -允許在裝置上進行讀取作業</span><span class="sxs-lookup"><span data-stu-id="8fce1-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="8fce1-189">`write` -允許在裝置上寫入作業</span><span class="sxs-lookup"><span data-stu-id="8fce1-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="8fce1-190">`execute` -允許在裝置上執行作業</span><span class="sxs-lookup"><span data-stu-id="8fce1-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="8fce1-191">如果 `none` 許可權層級中有，則 `read` `write` 會忽略 (、或) 中的任何其他許可權 `execute` 。</span><span class="sxs-lookup"><span data-stu-id="8fce1-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="8fce1-192">`execute`許可權只是指 Mach-O 二進位檔案的執行。</span><span class="sxs-lookup"><span data-stu-id="8fce1-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="8fce1-193">不包含執行腳本或其他類型的負載。</span><span class="sxs-lookup"><span data-stu-id="8fce1-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="8fce1-194">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-194">Section</span></span>|<span data-ttu-id="8fce1-195">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-196">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-197">**Key**</span></span> | <span data-ttu-id="8fce1-198">許可</span><span class="sxs-lookup"><span data-stu-id="8fce1-198">permission</span></span> |
| <span data-ttu-id="8fce1-199">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-199">**Data type**</span></span> | <span data-ttu-id="8fce1-200">字串陣列</span><span class="sxs-lookup"><span data-stu-id="8fce1-200">Array of strings</span></span> |
| <span data-ttu-id="8fce1-201">**可能值**</span><span class="sxs-lookup"><span data-stu-id="8fce1-201">**Possible values**</span></span> | <span data-ttu-id="8fce1-202">無</span><span class="sxs-lookup"><span data-stu-id="8fce1-202">none</span></span> <br/> <span data-ttu-id="8fce1-203">讀</span><span class="sxs-lookup"><span data-stu-id="8fce1-203">read</span></span> <br/> <span data-ttu-id="8fce1-204">寫</span><span class="sxs-lookup"><span data-stu-id="8fce1-204">write</span></span> <br/> <span data-ttu-id="8fce1-205">執行</span><span class="sxs-lookup"><span data-stu-id="8fce1-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="8fce1-206">依廠商、產品及序號限制可移除媒體</span><span class="sxs-lookup"><span data-stu-id="8fce1-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="8fce1-207">如 [允許或封鎖可移除裝置](#allow-or-block-removable-devices)中所述，可透過廠商識別碼、產品識別碼及序號來識別卸除式媒體（例如 USB 裝置）。</span><span class="sxs-lookup"><span data-stu-id="8fce1-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="8fce1-208">在 [卸除式媒體] 原則的最上層，您可以選擇在廠商層級定義更細微的限制。</span><span class="sxs-lookup"><span data-stu-id="8fce1-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="8fce1-209">`vendors`字典包含一或多個專案，每個專案都是由廠商識別碼識別。</span><span class="sxs-lookup"><span data-stu-id="8fce1-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="8fce1-210">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-210">Section</span></span>|<span data-ttu-id="8fce1-211">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-212">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-213">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-213">**Key**</span></span> | <span data-ttu-id="8fce1-214">供應商</span><span class="sxs-lookup"><span data-stu-id="8fce1-214">vendors</span></span> |
| <span data-ttu-id="8fce1-215">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-215">**Data type**</span></span> | <span data-ttu-id="8fce1-216">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="8fce1-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8fce1-217">針對每個廠商，您可以為該廠商的裝置指定所需的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="8fce1-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="8fce1-218">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-218">Section</span></span>|<span data-ttu-id="8fce1-219">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-220">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-221">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-221">**Key**</span></span> | <span data-ttu-id="8fce1-222">許可</span><span class="sxs-lookup"><span data-stu-id="8fce1-222">permission</span></span> |
| <span data-ttu-id="8fce1-223">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-223">**Data type**</span></span> | <span data-ttu-id="8fce1-224">字串陣列</span><span class="sxs-lookup"><span data-stu-id="8fce1-224">Array of strings</span></span> |
| <span data-ttu-id="8fce1-225">**可能值**</span><span class="sxs-lookup"><span data-stu-id="8fce1-225">**Possible values**</span></span> | <span data-ttu-id="8fce1-226">與[預設許可權等級](#default-permission-level)相同</span><span class="sxs-lookup"><span data-stu-id="8fce1-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="8fce1-227">此外，您可以選擇性地指定屬於該廠商的產品集合，其定義更為細微的許可權。</span><span class="sxs-lookup"><span data-stu-id="8fce1-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="8fce1-228">`products`字典包含一或多個專案，每個專案都是由產品識別碼所識別。</span><span class="sxs-lookup"><span data-stu-id="8fce1-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="8fce1-229">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-229">Section</span></span>|<span data-ttu-id="8fce1-230">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-231">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-232">**Key**</span></span> | <span data-ttu-id="8fce1-233">產品</span><span class="sxs-lookup"><span data-stu-id="8fce1-233">products</span></span> |
| <span data-ttu-id="8fce1-234">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-234">**Data type**</span></span> | <span data-ttu-id="8fce1-235">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="8fce1-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8fce1-236">針對每個產品，您可以指定該產品所需的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="8fce1-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="8fce1-237">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-237">Section</span></span>|<span data-ttu-id="8fce1-238">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-239">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-240">**Key**</span></span> | <span data-ttu-id="8fce1-241">許可</span><span class="sxs-lookup"><span data-stu-id="8fce1-241">permission</span></span> |
| <span data-ttu-id="8fce1-242">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-242">**Data type**</span></span> | <span data-ttu-id="8fce1-243">字串陣列</span><span class="sxs-lookup"><span data-stu-id="8fce1-243">Array of strings</span></span> |
| <span data-ttu-id="8fce1-244">**可能值**</span><span class="sxs-lookup"><span data-stu-id="8fce1-244">**Possible values**</span></span> | <span data-ttu-id="8fce1-245">與[預設許可權等級](#default-permission-level)相同</span><span class="sxs-lookup"><span data-stu-id="8fce1-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="8fce1-246">此外，您可以指定一組選擇性的系列號碼，以定義更細微的許可權。</span><span class="sxs-lookup"><span data-stu-id="8fce1-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="8fce1-247">`serialNumbers`字典包含一或多個專案，每個專案都是由序號來識別。</span><span class="sxs-lookup"><span data-stu-id="8fce1-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="8fce1-248">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-248">Section</span></span>|<span data-ttu-id="8fce1-249">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-250">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-251">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-251">**Key**</span></span> | <span data-ttu-id="8fce1-252">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="8fce1-252">serialNumbers</span></span> |
| <span data-ttu-id="8fce1-253">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-253">**Data type**</span></span> | <span data-ttu-id="8fce1-254">字典 (嵌套偏好) </span><span class="sxs-lookup"><span data-stu-id="8fce1-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8fce1-255">針對每個序數，您可以指定所需的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="8fce1-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="8fce1-256">區段</span><span class="sxs-lookup"><span data-stu-id="8fce1-256">Section</span></span>|<span data-ttu-id="8fce1-257">值</span><span class="sxs-lookup"><span data-stu-id="8fce1-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8fce1-258">**網域**</span><span class="sxs-lookup"><span data-stu-id="8fce1-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8fce1-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="8fce1-259">**Key**</span></span> | <span data-ttu-id="8fce1-260">許可</span><span class="sxs-lookup"><span data-stu-id="8fce1-260">permission</span></span> |
| <span data-ttu-id="8fce1-261">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fce1-261">**Data type**</span></span> | <span data-ttu-id="8fce1-262">字串陣列</span><span class="sxs-lookup"><span data-stu-id="8fce1-262">Array of strings</span></span> |
| <span data-ttu-id="8fce1-263">**可能值**</span><span class="sxs-lookup"><span data-stu-id="8fce1-263">**Possible values**</span></span> | <span data-ttu-id="8fce1-264">與[預設許可權等級](#default-permission-level)相同</span><span class="sxs-lookup"><span data-stu-id="8fce1-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="8fce1-265">範例裝置控制項原則</span><span class="sxs-lookup"><span data-stu-id="8fce1-265">Example device control policy</span></span>

<span data-ttu-id="8fce1-266">下列範例會示範上述所有概念如何結合到裝置控制項原則中。</span><span class="sxs-lookup"><span data-stu-id="8fce1-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="8fce1-267">在下列範例中，請記下可移除媒體原則的階層性質。</span><span class="sxs-lookup"><span data-stu-id="8fce1-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="8fce1-268">我們已在下列檔中包含裝置控制原則的更多範例：</span><span class="sxs-lookup"><span data-stu-id="8fce1-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="8fce1-269">Intune 裝置控制原則的範例</span><span class="sxs-lookup"><span data-stu-id="8fce1-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="8fce1-270">JAMF 裝置控制原則的範例</span><span class="sxs-lookup"><span data-stu-id="8fce1-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="8fce1-271">查詢裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="8fce1-271">Look up device identifiers</span></span>

<span data-ttu-id="8fce1-272">若要尋找 USB 裝置的廠商識別碼、產品識別碼及序列碼，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8fce1-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="8fce1-273">登入 Mac 裝置。</span><span class="sxs-lookup"><span data-stu-id="8fce1-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="8fce1-274">插入您要查閱識別碼的 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="8fce1-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="8fce1-275">在 macOS 的最上層功能表中，選取 [ **關於此 Mac**]。</span><span class="sxs-lookup"><span data-stu-id="8fce1-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![關於此 Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="8fce1-277">選取 [ **系統報告**]。</span><span class="sxs-lookup"><span data-stu-id="8fce1-277">Select **System Report**.</span></span>

    ![系統報告](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="8fce1-279">從左欄中，選取 [ **USB**]。</span><span class="sxs-lookup"><span data-stu-id="8fce1-279">From the left column, select **USB**.</span></span>

    ![所有 USB 裝置的視圖](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="8fce1-281">在 [ **USB 裝置樹狀目錄**] 底下，流覽至您插入的 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="8fce1-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![USB 裝置的詳細資料](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="8fce1-283">會顯示廠商識別碼、產品識別碼及序號碼。</span><span class="sxs-lookup"><span data-stu-id="8fce1-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="8fce1-284">將廠商識別碼及產品識別碼新增至可移除媒體原則時，您必須只在後新增此元件 `0x` 。</span><span class="sxs-lookup"><span data-stu-id="8fce1-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="8fce1-285">例如，在下圖中，[廠商識別碼] `1000` 和 [產品識別碼] `090c` 。</span><span class="sxs-lookup"><span data-stu-id="8fce1-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="8fce1-286">探索組織中的 USB 裝置</span><span class="sxs-lookup"><span data-stu-id="8fce1-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="8fce1-287">您可以從 Microsoft Defender for Endpoint advanced 搜尋中的 USB 裝置，查看裝載、卸載及大量變更事件。</span><span class="sxs-lookup"><span data-stu-id="8fce1-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="8fce1-288">這些事件有助於識別可疑的使用活動，或執行內部調查。</span><span class="sxs-lookup"><span data-stu-id="8fce1-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="8fce1-289">裝置控制項原則部署</span><span class="sxs-lookup"><span data-stu-id="8fce1-289">Device control policy deployment</span></span>

<span data-ttu-id="8fce1-290">裝置控制項原則必須包含在其他產品設定旁，如在 macOS 的 [ [設定 Microsoft Defender For Endpoint](mac-preferences.md)] 的 [喜好設定] 中所述。</span><span class="sxs-lookup"><span data-stu-id="8fce1-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="8fce1-291">您可以使用 [Configuration profile 部署](mac-preferences.md#configuration-profile-deployment)中所列的指示來部署此設定檔。</span><span class="sxs-lookup"><span data-stu-id="8fce1-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="8fce1-292">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="8fce1-292">Troubleshooting tips</span></span>

<span data-ttu-id="8fce1-293">透過 Intune 或 JAMF 推入設定設定檔之後，您可以從終端執行下列命令，檢查它是否已成功由產品挑選：</span><span class="sxs-lookup"><span data-stu-id="8fce1-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="8fce1-294">此命令會列印至標準輸出產品所使用的裝置控制項原則。</span><span class="sxs-lookup"><span data-stu-id="8fce1-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="8fce1-295">在這種情況下 `Policy is empty` ，請確定) 設定設定檔的 (已從管理主控台推入您的裝置， (b) 它是有效的裝置控制項原則，如本檔所述。</span><span class="sxs-lookup"><span data-stu-id="8fce1-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="8fce1-296">在已成功傳遞原則，且已將一或多個裝置插入其中的裝置上，您可以執行下列命令來列出所有裝置及已套用的有效許可權。</span><span class="sxs-lookup"><span data-stu-id="8fce1-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="8fce1-297">輸出範例：</span><span class="sxs-lookup"><span data-stu-id="8fce1-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="8fce1-298">在上述範例中，只有一部卸除式媒體裝置會 `read` `execute` 根據傳送至裝置的裝置控制項原則，自行插入並具有許可權。</span><span class="sxs-lookup"><span data-stu-id="8fce1-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fce1-299">相關主題</span><span class="sxs-lookup"><span data-stu-id="8fce1-299">Related topics</span></span>

- [<span data-ttu-id="8fce1-300">Intune 裝置控制原則的範例</span><span class="sxs-lookup"><span data-stu-id="8fce1-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="8fce1-301">JAMF 裝置控制原則的範例</span><span class="sxs-lookup"><span data-stu-id="8fce1-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
