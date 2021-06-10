---
title: Advanced eDiscovery 中的 AzCopy 疑難排解
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在 Advanced eDiscovery 中為錯誤修正載入非 Office 365 資料時，排查 Azure AzCopy 的錯誤。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919289"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Advanced eDiscovery 中的 AzCopy 疑難排解

當您在 Advanced eDiscovery 中載入非 Microsoft 365 資料或檔以進行錯誤修正時，使用者介面會提供 Azure AzCopy 命令，其中包含了您要上傳的檔案所在位置的參數，以及將檔案上傳至 Azure 的儲存位置。 若要上傳檔，請複製此命令，然後在本機電腦上的命令提示字元中執行它。  下列螢幕擷取畫面顯示 AzCopy 命令的範例：

![Upload 非 Microsoft 365 檔案](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常，當您執行它時，提供的命令會正常運作。 不過，在某些情況下，顯示的命令不會順利執行。 可能的原因有幾個。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>本機電腦上未安裝支援的 AzCopy 版本

此時，您必須使用 AzCopy app-v 8.1，以 Advanced eDiscovery 中載入非 Microsoft 365 的資料。 如果您不是使用 AzCopy 的第板，則在先前的螢幕擷取畫面所顯示的 [ **Upload** 檔案] 頁面上顯示的 AzCopy 命令，會傳回錯誤。 若要安裝此版本，請參閱[使用 AzCopy 的 Windows 傳送資料](/previous-versions/azure/storage/storage-use-azcopy)。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>本機電腦上未安裝 AzCopy，或其未安裝在預設位置

如果 AzCopy 並未安裝或安裝在預設安裝位置（) 的預設安裝 (位置 `%ProgramFiles(x86)%` ）上，當您執行 AzCopy 命令時，可能會收到下列錯誤：

> 系統找不到指定的路徑。

如果本機電腦上未安裝 AzCopy，您可以在[Windows 上找到傳輸資料中的「AzCopy 中](/previous-versions/azure/storage/storage-use-azcopy)的安裝資訊」。 請務必將其安裝在預設位置。

如果安裝了 AzCopy，但是安裝的位置與預設位置不同，您可以複製命令、將其貼到文字檔，然後將路徑變更至已安裝 AzCopy 的位置。 例如，如果 Azcopy 位於 `%ProgramFiles%` ，您可以將命令的第一個部分變更 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 為 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。 進行此變更後，請從文本檔案複製並執行命令提示字元。

> [!TIP]
> 如果 AzCopy 安裝在預設安裝位置的另一個位置，請考慮將其卸載，然後在預設位置重新安裝。 這可協助您避免未來發生此問題。