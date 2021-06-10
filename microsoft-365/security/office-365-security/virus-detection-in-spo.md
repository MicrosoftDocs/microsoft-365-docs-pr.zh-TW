---
title: SharePoint 線上、OneDrive 和 Microsoft Teams 中內建的病毒防護
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203494"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint 線上、OneDrive 和 Microsoft Teams 中內建的病毒防護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)

Microsoft 365 會使用常見的病毒偵測引擎來掃描使用者上傳至 SharePoint Online、OneDrive 和 Microsoft Teams 的檔案。 這種保護包含 SharePoint 線上、OneDrive 及 Microsoft Teams 的所有訂閱。

> [!IMPORTANT]
> 內建的防病毒功能是一種協助包含病毒的方式。 它們不是用來防禦您環境中惡意程式碼的單一防禦點。 我們鼓勵所有客戶調查和執行各層的反惡意程式碼保護，並套用最佳作法，以保護其企業基礎結構。 如需策略及最佳作法的詳細資訊，請參閱 [安全性藍圖](security-roadmap.md)。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？

Microsoft 365 病毒偵測引擎會以非同步方式執行， (獨立于 SharePoint Online 中的檔案上傳) 。 **不會自動掃描所有** 檔案。 啟發式決定要掃描的檔案。 當找到檔案包含病毒時，就會標示該檔案。 在4月2018，我們已移除已掃描檔案的 25 MB 限制。

會發生下列情況：

1. 使用者將檔案上傳到線上 SharePoint。
2. SharePoint線上，成為病毒掃描程式的一部分，稍後會判斷檔案是否符合掃描的準則。
3. 如果檔案符合掃描的準則，病毒偵測引擎便會掃描檔案。
4. 如果在掃描的檔案內找到病毒，病毒引擎便會將檔案上的屬性設定為表示感染的檔案。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？

如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。

會發生下列情況：

1. 使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。
2. 使用者會得到偵測到病毒的警告。 根據預設，使用者可以選擇下載檔案，並嘗試使用自身裝置上的反病毒軟體來清除該檔。

> [!NOTE]
>
> 系統管理員可以在 SharePoint 線上 PowerShell 的 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用 *DisallowInfectedFileDownload* 參數，以防止使用者在未感染的檔案中下載感染的檔案，即使在反病毒警告視窗中也是一樣。 如需相關指示，請參閱[使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。
>
> 一旦您啟用 *DisallowInfectedFileDownload* 參數，就會完全封鎖使用者和系統管理員對偵測到的/封鎖檔案的存取。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？

OneDrive 同步處理用戶端將不會下載含有病毒的檔案。 同步處理用戶端會顯示無法同步處理檔案的通知。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>適用于 Office 365 的 Microsoft Defender 擴充功能

在訂閱中或以附加元件形式購買的[Microsoft Defender Office 365](defender-for-office-365.md) Microsoft 365 組織，都可以針對增強的報表和保護，啟用安全附件，以 SharePoint、OneDrive 及 Microsoft Teams。 如需詳細資訊，請參閱[SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)。

## <a name="related-articles"></a>相關文章

[Microsoft 365 中的惡意程式碼和勒索軟體防護](/compliance/assurance/assurance-malware-and-ransomware-protection)

如需 SharePoint Online、OneDrive 及 Microsoft Teams 的防病毒相關資訊，請參閱[防範威脅](protect-against-threats.md)及[開啟 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](turn-on-mdo-for-spo-odb-and-teams.md)。
