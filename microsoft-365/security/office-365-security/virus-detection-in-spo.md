---
title: SharePoint Online 中的病毒偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 深入瞭解 SharePoint Online 中的防防毒保護。
ms.openlocfilehash: f04cd18bb4880ab631816c90b4976beada436225
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630938"
---
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online 中的病毒偵測

Microsoft 365 可以偵測使用者上傳至 SharePoint 線上之檔案中的病毒，以協助保護您的環境免受惡意軟體的攻擊。 檔案在上傳後可能會進行病毒掃描。 若發現檔案遭到感染，則會設定屬性，讓使用者無法下載或同步處理檔案。

> [!IMPORTANT]
> SharePoint Online 中的這些防病毒功能是一種包含病毒的方式。 它們不是用來防禦您環境中惡意程式碼的單一防禦點。 我們鼓勵所有客戶在不同的層級評估和執行反惡意軟體防護，並套用最佳作法，以保護您的企業基礎結構。 如需策略及最佳作法的詳細資訊，請參閱[安全性藍圖](security-roadmap.md)。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？

Microsoft 365 使用常見的病毒偵測引擎。 在線上 SharePoint 中，引擎會以非同步方式執行，並在上載檔案之後掃描檔案。 試探法是用來判斷要掃描的檔案。 當找到檔案包含病毒時，會加以標記，使其無法再次下載。 在4月2018，我們已移除已掃描檔案的 25 MB 限制。

會發生下列情況：

1. 使用者將檔案上傳到線上 SharePoint。

2. SharePoint 線上決定檔是否符合掃描的準則。

3. 病毒偵測引擎會掃描檔案。

4. 如果找到病毒，病毒引擎便會將檔案上的屬性設定為指出其受到感染。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？

如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。

會發生下列情況：

1. 使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。

2. 使用者會得到偵測到病毒的警告。 使用者可選擇下載該檔案，並嘗試使用自己的防毒軟體來清除該檔案。

> [!NOTE]
> 您可以在 SharePoint 線上 PowerShell 的[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用*DisallowInfectedFileDownload*參數，以防止使用者下載染毒的檔案，即使是在 [反病毒警告] 視窗中也是一樣。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？

使用者是否要使用新的 OneDrive 同步處理用戶端（OneDrive.exe）或 OneDrive 舊版的 Business sync 用戶端（Groove）同步處理檔案，如果檔案包含病毒，同步處理用戶端將不會下載該檔案。 同步處理用戶端會顯示無法同步處理檔案的通知。
