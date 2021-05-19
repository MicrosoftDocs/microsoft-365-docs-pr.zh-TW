---
title: Linux 上的 Microsoft Defender for Endpoint 中的新功能
description: Linux 上 Microsoft Defender for Endpoint 的主要變更清單。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，whatsnew，release
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
ms.openlocfilehash: 21eaf1c0e0d3f61bb5798c8a4de6fe8f97ce4a0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538792"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b8c09-104">Linux 上的 Microsoft Defender for Endpoint 中的新功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="b8c09-105">101.29.64 (30.121042.12964.0) </span><span class="sxs-lookup"><span data-stu-id="b8c09-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="b8c09-106">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-106">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="b8c09-107">101.25.72 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="b8c09-107">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="b8c09-108">在 Linux 上的 Microsoft Defender for Endpoint 現在可供美國政府客戶預覽。</span><span class="sxs-lookup"><span data-stu-id="b8c09-108">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="b8c09-109">如需詳細資訊，請參閱 [適用于美國政府客戶的 Microsoft Defender For Endpoint](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="b8c09-109">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="b8c09-110">已修正此問題：在具有保險絲檔案系統的系統上，使用 Linux 上的端點的使用方式會導致作業系統掛起</span><span class="sxs-lookup"><span data-stu-id="b8c09-110">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="b8c09-111">其他錯誤修正 & 的效能增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-111">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="b8c09-112">101.25.63 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="b8c09-112">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="b8c09-113">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-113">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="b8c09-114">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="b8c09-114">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="b8c09-115">將整個掛接點新增至防病毒排除清單的情況，提高效能。</span><span class="sxs-lookup"><span data-stu-id="b8c09-115">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="b8c09-116">在此版本之前，來自裝載點的檔案活動仍由產品處理。</span><span class="sxs-lookup"><span data-stu-id="b8c09-116">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="b8c09-117">從這個版本開始，已排除的裝載點的檔案活動會遭到抑制，進而提升產品效能。</span><span class="sxs-lookup"><span data-stu-id="b8c09-117">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="b8c09-118">將新的選項新增至命令列工具，以查看上次隨選掃描的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b8c09-118">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="b8c09-119">若要查看上次隨選掃描的相關資訊，請執行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="b8c09-119">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="b8c09-120">& 錯誤修正的其他效能增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-120">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="b8c09-121">101.18.53</span><span class="sxs-lookup"><span data-stu-id="b8c09-121">101.18.53</span></span>

- <span data-ttu-id="b8c09-122">EDR 的 Linux 現在[一般可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="b8c09-122">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="b8c09-123">在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) </span><span class="sxs-lookup"><span data-stu-id="b8c09-123">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="b8c09-124">`mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄</span><span class="sxs-lookup"><span data-stu-id="b8c09-124">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="b8c09-125">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-125">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="b8c09-126">101.12.99</span><span class="sxs-lookup"><span data-stu-id="b8c09-126">101.12.99</span></span>

- <span data-ttu-id="b8c09-127">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-127">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="b8c09-128">101.04.76</span><span class="sxs-lookup"><span data-stu-id="b8c09-128">101.04.76</span></span>

- <span data-ttu-id="b8c09-129">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="b8c09-129">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="b8c09-130">101.03.48</span><span class="sxs-lookup"><span data-stu-id="b8c09-130">101.03.48</span></span>

- <span data-ttu-id="b8c09-131">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="b8c09-131">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="b8c09-132">101.02.55</span><span class="sxs-lookup"><span data-stu-id="b8c09-132">101.02.55</span></span>

- <span data-ttu-id="b8c09-133">已修正此問題：重新開機/升級後，產品有時候不會開始進行</span><span class="sxs-lookup"><span data-stu-id="b8c09-133">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="b8c09-134">已修正此問題：不會在產品升級期間保留 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="b8c09-134">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="b8c09-135">101.00.75</span><span class="sxs-lookup"><span data-stu-id="b8c09-135">101.00.75</span></span>

- <span data-ttu-id="b8c09-136">新增支援下列檔案系統類型：、、、、、、、 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="b8c09-136">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="b8c09-137">[命令列工具](linux-resources.md#configure-from-the-command-line)的新語法。</span><span class="sxs-lookup"><span data-stu-id="b8c09-137">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="b8c09-138">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-138">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="b8c09-139">100.90.70</span><span class="sxs-lookup"><span data-stu-id="b8c09-139">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="b8c09-140">從100.90.70 之前的產品版本升級已安裝的套件時，更新可能會在紅色 Hat 和 SLES 分配上失敗。</span><span class="sxs-lookup"><span data-stu-id="b8c09-140">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="b8c09-141">這是因為檔案路徑中的主要變更。</span><span class="sxs-lookup"><span data-stu-id="b8c09-141">This is because of a major change in a file path.</span></span> <span data-ttu-id="b8c09-142">臨時性的解決方案是移除較舊的套件，然後再安裝較新的套件。</span><span class="sxs-lookup"><span data-stu-id="b8c09-142">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="b8c09-143">此問題不存在於較新的版本中。</span><span class="sxs-lookup"><span data-stu-id="b8c09-143">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="b8c09-144">防病毒 [排除現在支援萬用字元](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="b8c09-144">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="b8c09-145">新增使用命令列[工具疑難排解效能問題](linux-support-perf.md)的能力 `mdatp`</span><span class="sxs-lookup"><span data-stu-id="b8c09-145">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="b8c09-146">增強套件安裝的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-146">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="b8c09-147">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="b8c09-147">Performance improvements & bug fixes</span></span>
