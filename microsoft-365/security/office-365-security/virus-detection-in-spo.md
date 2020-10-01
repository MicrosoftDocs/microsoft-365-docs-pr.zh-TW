---
title: SharePoint Online、OneDrive 和 Microsoft 團隊中內建的病毒防護
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
description: 深入瞭解 SharePoint 線上如何在使用者上傳的檔案中偵測病毒，並防止使用者下載或同步處理檔案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327984"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive 和 Microsoft 團隊中內建的病毒防護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 使用常見的病毒偵測引擎，掃描使用者上傳至 SharePoint 線上、OneDrive 和 Microsoft 小組的檔案。 這種保護包含在 SharePoint 線上、OneDrive 和 Microsoft 小組的所有訂閱中。

> [!IMPORTANT]
> 內建的防病毒功能是一種協助包含病毒的方式。 它們不是用來防禦您環境中惡意程式碼的單一防禦點。 我們鼓勵所有客戶調查和執行各層的反惡意程式碼保護，並套用最佳作法，以保護其企業基礎結構。 如需策略及最佳作法的詳細資訊，請參閱 [安全性藍圖](security-roadmap.md)。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？

Microsoft 365 病毒偵測引擎會在線上 SharePoint 內非同步執行。 **上載時不會自動掃描所有**檔案。 啟發式決定要掃描的檔案。 當發現檔案包含病毒時，會對該檔案進行標記，使其無法再次下載。 在4月2018，我們已移除已掃描檔案的 25 MB 限制。

會發生下列情況：

1. 使用者將檔案上傳到線上 SharePoint。
2. SharePoint 線上決定檔是否符合掃描的準則。
3. 病毒偵測引擎會掃描檔案。
4. 如果找到病毒，病毒引擎便會將檔案上的屬性設定為指出其受到感染。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？

如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。

會發生下列情況：

1. 使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。
2. 使用者會得到偵測到病毒的警告。 根據預設，使用者可以選擇下載檔案，並嘗試使用自身裝置上的反病毒軟體來清除該檔。

> [!NOTE]
>
> 系統管理員可以在 SharePoint 線上 PowerShell 的[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用*DisallowInfectedFileDownload*參數，以防止使用者在未感染的檔案中下載感染的檔案，即使在反病毒警告視窗中也是一樣。 如需相關指示，請參閱 [使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。
>
> 一旦您啟用 *DisallowInfectedFileDownload* 參數，就會完全封鎖使用者和系統管理員對偵測到的/封鎖檔案的存取。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？

OneDrive 同步處理用戶端將不會下載含有病毒的檔案。 同步處理用戶端會顯示無法同步處理檔案的通知。

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a>使用 Office 365 高級威脅防護的延伸功能

具有 [Office 365 高級威脅防護 ](office-365-atp.md) 的 Microsoft 365 組織 (包含在其訂閱中的 atp) 或以附加元件形式購買，可為 SharePoint、OneDrive 和 Microsoft 團隊啟用 atp，以增強報表和保護。 如需詳細資訊，請參閱 [SharePoint、OneDrive 和 Microsoft 小組的 ATP](atp-for-spo-odb-and-teams.md)。

## <a name="more-information"></a>詳細資訊

如需 SharePoint 線上、OneDrive 和 Microsoft 小組的防病毒相關資訊，請參閱 [防範威脅](protect-against-threats.md) 及 [開啟 SharePoint、OneDrive 及 MICROSOFT 小組的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。
