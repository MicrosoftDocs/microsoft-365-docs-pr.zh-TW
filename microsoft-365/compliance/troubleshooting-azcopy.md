---
title: 在高級 eDiscovery 中 AzCopy 疑難排解
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8b72112feea4af0a33ef3a0cc12005c8deea195
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637513"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>在高級 eDiscovery 中 AzCopy 疑難排解

在 [Advanced eDiscovery] 中載入非 Microsoft 365 資料或檔以進行錯誤修正時，使用者介面會提供 Azure AzCopy 命令，其中包含了您要上傳的檔案所在位置的參數，以及檔案將要上傳至的 Azure 儲存位置。 若要上傳檔，請複製此命令，然後在本機電腦上的命令提示字元中執行它。  下列螢幕擷取畫面顯示 AzCopy 命令的範例：

![上傳非 Microsoft 365 檔案](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常，當您執行它時，提供的命令會正常運作。 不過，在某些情況下，顯示的命令不會順利執行。 可能的原因有幾個。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>本機電腦上未安裝支援的 AzCopy 版本

此時，您必須使用 AzCopy app-v 8.1，在 Advanced eDiscovery 中載入非 Microsoft 365 資料。 如果您不是使用 AzCopy 的第板，則顯示在先前的螢幕擷取畫面所顯示之 [上**傳**檔案] 頁面上的 AzCopy 命令會傳回錯誤。 若要安裝此版本，請參閱在[Windows 上使用 AzCopy app-v 8.1 傳輸資料](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>本機電腦上未安裝 AzCopy，或其未安裝在預設位置

如果 AzCopy 未安裝或安裝在預設安裝位置（亦即`%ProgramFiles(x86)%`）以外的位置，當您執行 AzCopy 命令時，可能會收到下列錯誤：

    The system cannot find the path specified.

如果本機電腦上未安裝 AzCopy，您可以從[這裡](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)安裝。 請務必將其安裝在預設位置。

如果安裝了 AzCopy，但是安裝的位置與預設位置不同，您可以複製命令、將其貼到文字檔，然後將路徑變更至已安裝 AzCopy 的位置。 例如，如果 Azcopy 位於`%ProgramFiles%`，您可以將命令的第一個部分變更`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`為。 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 進行此變更後，請從文本檔案複製並執行命令提示字元。

> [!TIP]
> 如果 AzCopy 安裝在預設安裝位置的另一個位置，請考慮將其卸載，然後在預設位置重新安裝。 這可協助您避免未來發生此問題。
