---
title: 適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 瞭解 Office 365 的高級威脅防護，以瞭解 SharePoint Online 中的檔案、商務 OneDrive 商務和 Microsoft 團隊。
ms.openlocfilehash: 194b8e45e573ae4c4cd1f3428a1f80c48e1d80c8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326862"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

在 [Office 365 Advanced 威脅防護 ](office-365-atp.md) 中，SharePoint、OneDrive 和 Microsoft 小組的 ATP， (ATP) 為已在上載時已掃描的檔案，針對 [Microsoft 365 中的常見病毒偵測引擎](virus-detection-in-spo.md)，提供額外的保護層級。 SharePoint、OneDrive 和 Microsoft 團隊的 ATP 可協助偵測和封鎖在小組網站和文件庫中識別為惡意的現有檔案。

預設不會啟用 SharePoint、OneDrive 和 Microsoft 團隊的 ATP。 若要將其開啟，請參閱 [開啟 ATP 的 SharePoint、OneDrive 和 Microsoft 團隊](turn-on-atp-for-spo-odb-and-teams.md)。

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive 和 Microsoft 小組的 ATP 的運作方式

當 SharePoint、OneDrive 和 Microsoft 團隊的 ATP 已啟用並將檔案識別為惡意時，會使用與檔案存放區的直接整合，鎖定檔案。 下列影像顯示文件庫中偵測到的惡意檔案範例。

![商務用 OneDrive 中的檔案，偵測到其中一個是惡意檔案](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

雖然封鎖的檔案仍然會列在文件庫和 web、行動裝置或桌面應用程式中，但無法開啟、複製、移動或共用檔案。 但可刪除封鎖的檔案。

以下是在行動裝置上封鎖的檔案外觀的範例：

![透過 OneDrive 行動應用程式從商務用 OneDrive 中刪除封鎖的檔案](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

根據預設，使用者可以下載封鎖的檔案。 以下是在行動裝置上下載封鎖的檔案的外觀：

![在商務用 OneDrive 中下載封鎖的檔案](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online admins 可防止使用者下載惡意檔案。 如需相關指示，請參閱 [使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。

若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>針對 SharePoint、OneDrive 和 Microsoft 小組，查看 ATP 所偵測到之惡意檔案的相關資訊。

由 ATP 識別為惡意的檔案，會顯示在 [Office 365 Advanced 威脅防護](view-reports-for-atp.md) 和 [Explorer (和即時偵測) ](threat-explorer.md)中的報告。

從5月2018日到5月，當檔案是由 ATP 識別為惡意時，檔案也會存在於隔離區中。 如需詳細資訊，請參閱 [使用安全性 & 合規性中心管理隔離](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)的檔案。

## <a name="keep-these-points-in-mind"></a>請記住下列重點

- ATP 不會掃描 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的每個單一檔案。 原先的設計就是如此。 檔會以非同步方式掃描。 此程式會使用共用和來賓活動事件，以及智慧試探法和威脅信號，識別惡意檔案。

- 請確認您的 SharePoint 網站已設定為使用[新式體驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。 ATP 保護會套用是否使用新式經驗或傳統模式;不過，只有在新式的體驗中，才可使用已封鎖檔案的視覺指示器。

- SharePoint、OneDrive 和 Microsoft 團隊的 ATP 是組織整體威脅防護策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾郵件和反惡意程式碼保護，以及 Office 365 ATP 中的安全連結和安全附件。 若要深入了解，請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。
