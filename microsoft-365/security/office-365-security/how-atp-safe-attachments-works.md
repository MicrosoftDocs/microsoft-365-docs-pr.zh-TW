---
title: ATP 安全附件的運作方式
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用 Office 365 的 ATP 安全附件，讓組織安全地抵禦惡意檔。
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201469"
---
# <a name="how-atp-safe-attachments-works"></a>ATP 安全附件的運作方式

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


ATP 安全附件功能會檢查電子郵件附件中組織的人員。 當 ATP 安全附件原則已到位，且該原則所涵蓋的人員會在 Office 365 中查看其電子郵件時，會根據您的 ATP 安全附件原則，檢查其電子郵件附件並採取適當的動作。 根據您的原則定義方式，使用者可以繼續運作，而不會知道他們已傳送惡意檔案。
  
以下是工作中 ATP 安全附件的兩個範例。
  
- **範例1：電子郵件附件** 假設您收到一封具有附件的電子郵件。 不管附件是安全還是實際包含惡意程式碼，以竊取使用者的認證，並不容易。 在「公司管理員」中，安全性管理員會在幾天前定義 ATP 安全附件原則。 透過 ATP 安全附件功能，電子郵件附件會在虛擬環境中開啟並測試，然後才會收到該附件。 如果附件決定為惡意的，將會自動移除它。 如果附件是安全的，當您按一下該附件時，它會如預期的方式開啟。

- **範例2：線上 SharePoint 中的** 檔案假設 Jean-francois 收到檔案，並將其上傳至 SharePoint Online 中的文件庫。 Jean-francois 與小組的其餘部分共用檔案的連結，而不知道該檔案實際上是惡意的。 幸運的是， [SharePoint、OneDrive 和 Microsoft 團隊的 ATP](atp-for-spo-odb-and-teams.md) 會偵測惡意檔，並加以封鎖。 幾天後，Chris 會開啟檔。 雖然 Chris 可以看見該檔案，Chris 卻無法開啟或分享它，可保護 Chris 的電腦和其他惡意檔案。

ATP 安全附件原則可以套用到組織中的特定人員或群組，或套用至整個網域。 此外，ATP 安全附件原則可以設定為在掃描實際附件時使用預留位置附件。 若要深入瞭解，請參閱 **[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)**。

> [!NOTE]
> ATP 安全附件掃描會在您的資料所在的相同區域中進行。 如需資料中心地理位置的詳細資訊，請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All) 

