---
title: JAMF 裝置控制原則的範例
description: 瞭解如何使用可搭配 JAMF 使用之範例的裝置控制項原則。
keywords: microsoft，defender，端點，Microsoft Defender for Endpoint，mac，device，control，usb，可移動，媒體，jamf
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
ms.openlocfilehash: 21e44090cf21ac8bba29885a2f97242faf3e2164
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363964"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="60fbf-104">JAMF 裝置控制原則的範例</span><span class="sxs-lookup"><span data-stu-id="60fbf-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60fbf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="60fbf-105">**Applies to:**</span></span>
- [<span data-ttu-id="60fbf-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="60fbf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60fbf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60fbf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="60fbf-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="60fbf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="60fbf-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="60fbf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="60fbf-110">本檔包含您可以為自己的組織自訂之裝置控制項原則的範例。</span><span class="sxs-lookup"><span data-stu-id="60fbf-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="60fbf-111">如果您使用 JAMF 來管理企業中的裝置，這些範例就會適用。</span><span class="sxs-lookup"><span data-stu-id="60fbf-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="60fbf-112">限制存取所有卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="60fbf-112">Restrict access to all removable media</span></span>

<span data-ttu-id="60fbf-113">下列範例會限制存取所有的卸除式媒體。</span><span class="sxs-lookup"><span data-stu-id="60fbf-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="60fbf-114">請注意 `none` 原則的最上層所套用的許可權，這表示將禁止所有的檔案作業。</span><span class="sxs-lookup"><span data-stu-id="60fbf-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="60fbf-115">將所有卸除式媒體設定為唯讀</span><span class="sxs-lookup"><span data-stu-id="60fbf-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="60fbf-116">下列範例會將所有卸除式媒體設定為唯讀。</span><span class="sxs-lookup"><span data-stu-id="60fbf-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="60fbf-117">請注意 `read` 原則的最上層所套用的許可權，這表示將不會允許所有的寫入和執行作業。</span><span class="sxs-lookup"><span data-stu-id="60fbf-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="60fbf-118">禁止從卸除式媒體執行程式</span><span class="sxs-lookup"><span data-stu-id="60fbf-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="60fbf-119">下列範例會顯示如何禁止從卸除式媒體執行程式。</span><span class="sxs-lookup"><span data-stu-id="60fbf-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="60fbf-120">請注意 `read` 原則的最上層所套用的和 `write` 許可權。</span><span class="sxs-lookup"><span data-stu-id="60fbf-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="60fbf-121">限制特定供應商的所有裝置</span><span class="sxs-lookup"><span data-stu-id="60fbf-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="60fbf-122">下列範例會限制特定廠商 (中的所有裝置，在此案例中會以 `fff0` 和) 加以識別 `4525` 。</span><span class="sxs-lookup"><span data-stu-id="60fbf-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="60fbf-123">所有其他裝置都不受限制，因為在原則的最上層所定義的許可權會列出所有可能的許可權 (讀取、寫入和執行) 。</span><span class="sxs-lookup"><span data-stu-id="60fbf-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="60fbf-124">限制由廠商識別碼、產品識別碼及序列碼所識別的特定裝置</span><span class="sxs-lookup"><span data-stu-id="60fbf-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="60fbf-125">下列範例會限制兩個特定裝置，依廠商識別碼 `fff0` 、產品識別碼及 `1000` 序號及所 `04ZSSMHI2O7WBVOA` 識別 `04ZSSMHI2O7WBVOB` 。</span><span class="sxs-lookup"><span data-stu-id="60fbf-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="60fbf-126">在所有其他原則層級，許可權包括所有可能的值 (讀取、寫入和執行) ，這表示所有其他裝置都不受限制。</span><span class="sxs-lookup"><span data-stu-id="60fbf-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="60fbf-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="60fbf-127">Related topics</span></span>

- [<span data-ttu-id="60fbf-128">macOS 的裝置控制概覽</span><span class="sxs-lookup"><span data-stu-id="60fbf-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
