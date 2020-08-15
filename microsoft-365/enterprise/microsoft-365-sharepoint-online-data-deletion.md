---
title: Microsoft 365 SharePoint 線上資料刪除
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 瞭解資料刪除在 SharePoint Online 中的運作方式，例如儲存已刪除內容的位置和時間。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688687"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>在 Microsoft 365 中 SharePoint 線上資料刪除

SharePoint 線上將物件儲存為應用程式資料庫中的抽象程式碼。 當使用者將檔案上傳至 SharePoint 線上時，該檔案會被反彙編並轉譯成應用程式代碼，並儲存在多個資料庫的多個資料表中。 在線上 SharePoint 中，客戶上傳的所有內容都會分割成區塊、加密 (可能會有多個 AES 256 位金鑰) ，以及跨資料中心散佈。 如需有關區塊和加密程式的特定詳細資料，請參閱 [Microsoft Cloud 中的加密](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)。 

在線上 SharePoint 中，專案會從您從原始位置刪除時起的93天內保留。 除非某人從該回收站刪除或清除該回收站，否則它們會一直保留在網站回收站中。 在此情況下，這些專案會移至網站集合的回收站，而這些專案會在剩餘的93天內保留。 如需還原已刪除專案的詳細資訊，請參閱 [還原 SharePoint 網站回收站中的專案](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) ，以及 [從網站集合回收站還原已刪除的專案](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。 在 SharePoint Online 中無法設定回收站保留時間。

當您刪除網站集合時，也會刪除集合中的網站階層，並在其中的所有內容：

- 文件及文件庫
- 清單和清單資料
- 網站設定
- 網站或其子網站相關的角色與安全性資訊
- 頂層網站的子網站、其內容和使用者資訊

如果您不小心刪除網站集合，可以使用 SharePoint 系統管理中心，由全域或 SharePoint 系統管理員還原。

已刪除的網站集合會保留93天。 在 93 天之後，將會永久刪除網站及其所有內容和設定，包括清單、文件庫、頁面及所有子網站。

當使用者從網站集合回收站清除已刪除的專案、保留和備份期間到期時，或系統管理員使用 [Remove-SPODeletedSite Cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)永久刪除網站集合時，就會發生實刪除。 當使用者硬性刪除 (會永久刪除或清除 SharePoint Online 中的) 內容，所有已刪除區塊的加密金鑰也會同時刪除。 先前儲存已刪除之區塊的磁片區塊會標示為未使用，且可重複使用。
