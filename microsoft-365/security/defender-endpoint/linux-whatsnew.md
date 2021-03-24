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
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Linux 中的新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a>101.18.53

- 現在[可以使用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)LINUX 的 EDR。
- 在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) 
- `mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄
- 效能 & bug 修正的增強功能

## <a name="1011299"></a>101.12.99

- 效能 & bug 修正的增強功能

## <a name="1010476"></a>101.04.76

- 錯誤修正

## <a name="1010348"></a>101.03.48

- 錯誤修正

## <a name="1010255"></a>101.02.55

- 已修正此問題：重新開機/升級後，產品有時候不會開始進行
- 已修正此問題：不會在產品升級期間保留 proxy 設定

## <a name="1010075"></a>101.00.75

- 新增支援下列檔案系統類型：、、、、、、、 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 和 `vfat`
- [命令列工具](linux-resources.md#configure-from-the-command-line)的新語法。
- 效能 & bug 修正的增強功能

## <a name="1009070"></a>100.90.70

> [!WARNING]
> 從100.90.70 之前的產品版本升級已安裝的套件時，更新可能會在紅色 Hat 和 SLES 分配上失敗。 這是因為檔案路徑中的主要變更。 臨時性的解決方案是移除較舊的套件，然後再安裝較新的套件。 此問題不存在於較新的版本中。

- 防病毒 [排除現在支援萬用字元](linux-exclusions.md#supported-exclusion-types)
- 新增使用命令列[工具疑難排解效能問題](linux-support-perf.md)的能力 `mdatp`
- 增強套件安裝的增強功能
- 效能 & bug 修正的增強功能