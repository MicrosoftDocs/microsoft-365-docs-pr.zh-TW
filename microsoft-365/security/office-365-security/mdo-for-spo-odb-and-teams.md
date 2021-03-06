---
title: 適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 瞭解適用于 SharePoint Online、商務用 OneDrive 及 Microsoft Teams 中檔案的 Microsoft Defender Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a0c9721c4d8fc2087e0dbbce19305060344430c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096741"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

保管庫適用于[Office 365 的 Microsoft Defender](whats-new-in-defender-for-office-365.md)中 SharePoint、OneDrive 和 Microsoft Teams 的附件，為[Microsoft 365 中常見的病毒偵測引擎](virus-detection-in-spo.md)已非同步掃描的檔案，提供額外的保護層。 保管庫SharePoint、OneDrive 及 Microsoft Teams 的附件可協助偵測和封鎖在小組網站和文件庫中識別為惡意的現有檔案。

保管庫預設不會啟用 SharePoint、OneDrive 及 Microsoft Teams 的附件。 若要開啟它，請參閱[開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件](turn-on-mdo-for-spo-odb-and-teams.md)。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>保管庫 SharePoint、OneDrive 及 Microsoft Teams 的附件的運作方式

當 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件已啟用並將檔案識別為惡意時，會使用與檔案存放區的直接整合，鎖定檔案。 下列影像顯示文件庫中偵測到的惡意檔案範例。

![商務用 OneDrive 中的檔案，偵測到其中一個是惡意檔案](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

雖然封鎖的檔案仍然會列在文件庫和 web、行動裝置或桌面應用程式中，但無法開啟、複製、移動或共用檔案。 但可刪除封鎖的檔案。

以下是在行動裝置上封鎖的檔案外觀的範例：

![透過 OneDrive 行動應用程式從商務用 OneDrive 中刪除封鎖的檔案](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

根據預設，使用者可以下載封鎖的檔案。 以下是在行動裝置上下載封鎖的檔案的外觀：

![在商務用 OneDrive 中下載封鎖的檔案](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint線上系統管理員可以防止使用者下載惡意檔案。 如需相關指示，請參閱[使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。

若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>針對 SharePoint、OneDrive 及 Microsoft Teams，查看保管庫附件所偵測到之惡意檔案的相關資訊。

保管庫 SharePoint、OneDrive 及 Microsoft Teams 的附件識別為惡意的檔案，會顯示[Office 365 的 Microsoft Defender 報告](view-reports-for-mdo.md)，以及[Explorer (和即時偵測) ](threat-explorer.md)。

從5月2018，當您保管庫 SharePoint、OneDrive 和 Microsoft Teams 的附件，將檔案識別為惡意檔案時，也會在隔離區中使用該檔案。 如需詳細資訊，請參閱[在 Office 365 的 Defender 中管理隔離的](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)檔案。

## <a name="keep-these-points-in-mind"></a>請記住下列重點

- Office 365 的 Defender 不會掃描 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的每一個檔案。 這是原本設計的做法。 檔會以非同步方式掃描。 此程式會使用共用和來賓活動事件，以及智慧試探法和威脅信號，識別惡意檔案。

- 請確認您的 SharePoint 網站已設定為使用[新式體驗](/sharepoint/guide-to-sharepoint-modern-experience)。 Office 365 防護的 Defender 會套用是否使用新式經驗或傳統模式;不過，只有在新式的體驗中，才可使用已封鎖檔案的視覺指示器。

- 保管庫SharePoint、OneDrive 和 Microsoft Teams 的附件是組織整體威脅防護策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾郵件和反惡意程式碼保護，以及保管庫保管庫的 Microsoft Defender 連結和 Office 365 附件。 若要深入了解，請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。
