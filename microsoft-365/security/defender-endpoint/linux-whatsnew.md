---
title: Linux 上的 Microsoft Defender for Endpoint 中的新功能
description: 在 Linux 上的 Microsoft Defender ATP 主要變更清單。
keywords: microsoft，defender，atp，linux，whatsnew，發行
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
ms.openlocfilehash: 2866cd0c9ee9b40aa9c08c4ff7dce64f745d3d03
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688628"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="13be9-104">Linux 上的 Microsoft Defender for Endpoint 中的新功能</span><span class="sxs-lookup"><span data-stu-id="13be9-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="13be9-105">101.25.72 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="13be9-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="13be9-106">在 Linux 上的 Microsoft Defender for Endpoint 現在可供美國政府客戶預覽。</span><span class="sxs-lookup"><span data-stu-id="13be9-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="13be9-107">如需詳細資訊，請參閱 [適用于美國政府客戶的 Microsoft Defender For Endpoint](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="13be9-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="13be9-108">已修正此問題：在具有保險絲檔案系統的系統上，使用 Linux 上的端點的使用方式會導致作業系統掛起</span><span class="sxs-lookup"><span data-stu-id="13be9-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="13be9-109">其他錯誤修正 & 的效能增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="13be9-110">101.25.63 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="13be9-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="13be9-111">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="13be9-112">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="13be9-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="13be9-113">將整個掛接點新增至防病毒排除清單的情況，提高效能。</span><span class="sxs-lookup"><span data-stu-id="13be9-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="13be9-114">在此版本之前，來自裝載點的檔案活動仍由產品處理。</span><span class="sxs-lookup"><span data-stu-id="13be9-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="13be9-115">從這個版本開始，已排除的裝載點的檔案活動會遭到抑制，進而提升產品效能。</span><span class="sxs-lookup"><span data-stu-id="13be9-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="13be9-116">將新的選項新增至命令列工具，以查看上次隨選掃描的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="13be9-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="13be9-117">若要查看上次隨選掃描的相關資訊，請執行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="13be9-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="13be9-118">& 錯誤修正的其他效能增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="13be9-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="13be9-119">101.18.53</span></span>

- <span data-ttu-id="13be9-120">現在[可以使用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)LINUX 的 EDR。</span><span class="sxs-lookup"><span data-stu-id="13be9-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="13be9-121">在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) </span><span class="sxs-lookup"><span data-stu-id="13be9-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="13be9-122">`mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄</span><span class="sxs-lookup"><span data-stu-id="13be9-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="13be9-123">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="13be9-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="13be9-124">101.12.99</span></span>

- <span data-ttu-id="13be9-125">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="13be9-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="13be9-126">101.04.76</span></span>

- <span data-ttu-id="13be9-127">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="13be9-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="13be9-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="13be9-128">101.03.48</span></span>

- <span data-ttu-id="13be9-129">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="13be9-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="13be9-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="13be9-130">101.02.55</span></span>

- <span data-ttu-id="13be9-131">已修正此問題：重新開機/升級後，產品有時候不會開始進行</span><span class="sxs-lookup"><span data-stu-id="13be9-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="13be9-132">已修正此問題：不會在產品升級期間保留 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="13be9-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="13be9-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="13be9-133">101.00.75</span></span>

- <span data-ttu-id="13be9-134">新增支援下列檔案系統類型：、、、、、、、 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="13be9-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="13be9-135">[命令列工具](linux-resources.md#configure-from-the-command-line)的新語法。</span><span class="sxs-lookup"><span data-stu-id="13be9-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="13be9-136">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="13be9-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="13be9-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="13be9-138">從100.90.70 之前的產品版本升級已安裝的套件時，更新可能會在紅色 Hat 和 SLES 分配上失敗。</span><span class="sxs-lookup"><span data-stu-id="13be9-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="13be9-139">這是因為檔案路徑中的主要變更。</span><span class="sxs-lookup"><span data-stu-id="13be9-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="13be9-140">臨時性的解決方案是移除較舊的套件，然後再安裝較新的套件。</span><span class="sxs-lookup"><span data-stu-id="13be9-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="13be9-141">此問題不存在於較新的版本中。</span><span class="sxs-lookup"><span data-stu-id="13be9-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="13be9-142">防病毒 [排除現在支援萬用字元](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="13be9-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="13be9-143">新增使用命令列[工具疑難排解效能問題](linux-support-perf.md)的能力 `mdatp`</span><span class="sxs-lookup"><span data-stu-id="13be9-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="13be9-144">增強套件安裝的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="13be9-145">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="13be9-145">Performance improvements & bug fixes</span></span>
