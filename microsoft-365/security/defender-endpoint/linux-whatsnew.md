---
title: Microsoft Defender for Linux 中的新功能
description: Microsoft Defender ATP for Linux 的主要變更清單。
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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057487"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="86c8f-104">Microsoft Defender for Linux 中的新功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="86c8f-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="86c8f-105">101.18.53</span></span>

- <span data-ttu-id="86c8f-106">現在[可以使用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)LINUX 的 EDR。</span><span class="sxs-lookup"><span data-stu-id="86c8f-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="86c8f-107">在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) </span><span class="sxs-lookup"><span data-stu-id="86c8f-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="86c8f-108">`mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄</span><span class="sxs-lookup"><span data-stu-id="86c8f-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="86c8f-109">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="86c8f-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="86c8f-110">101.12.99</span></span>

- <span data-ttu-id="86c8f-111">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="86c8f-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="86c8f-112">101.04.76</span></span>

- <span data-ttu-id="86c8f-113">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="86c8f-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="86c8f-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="86c8f-114">101.03.48</span></span>

- <span data-ttu-id="86c8f-115">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="86c8f-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="86c8f-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="86c8f-116">101.02.55</span></span>

- <span data-ttu-id="86c8f-117">已修正此問題：重新開機/升級後，產品有時候不會開始進行</span><span class="sxs-lookup"><span data-stu-id="86c8f-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="86c8f-118">已修正此問題：不會在產品升級期間保留 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="86c8f-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="86c8f-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="86c8f-119">101.00.75</span></span>

- <span data-ttu-id="86c8f-120">新增支援下列檔案系統類型：、、、、、、、 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="86c8f-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="86c8f-121">[命令列工具](linux-resources.md#configure-from-the-command-line)的新語法。</span><span class="sxs-lookup"><span data-stu-id="86c8f-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="86c8f-122">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="86c8f-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="86c8f-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="86c8f-124">從100.90.70 之前的產品版本升級已安裝的套件時，更新可能會在紅色 Hat 和 SLES 分配上失敗。</span><span class="sxs-lookup"><span data-stu-id="86c8f-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="86c8f-125">這是因為檔案路徑中的主要變更。</span><span class="sxs-lookup"><span data-stu-id="86c8f-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="86c8f-126">臨時性的解決方案是移除較舊的套件，然後再安裝較新的套件。</span><span class="sxs-lookup"><span data-stu-id="86c8f-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="86c8f-127">此問題不存在於較新的版本中。</span><span class="sxs-lookup"><span data-stu-id="86c8f-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="86c8f-128">防病毒 [排除現在支援萬用字元](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="86c8f-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="86c8f-129">新增使用命令列[工具疑難排解效能問題](linux-support-perf.md)的能力 `mdatp`</span><span class="sxs-lookup"><span data-stu-id="86c8f-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="86c8f-130">增強套件安裝的增強功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="86c8f-131">效能 & bug 修正的增強功能</span><span class="sxs-lookup"><span data-stu-id="86c8f-131">Performance improvements & bug fixes</span></span>
