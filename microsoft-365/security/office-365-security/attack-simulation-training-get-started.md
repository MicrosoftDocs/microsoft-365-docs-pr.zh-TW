---
title: 開始使用攻擊模擬訓練
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用攻擊模擬訓練，在其 Microsoft 365 E5 或 Microsoft Defender 中對 Office 365 計畫2組織執行模擬網路釣魚和密碼攻擊。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082897"
---
# <a name="get-started-using-attack-simulation-training"></a>開始使用攻擊模擬訓練

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用** 于 [Office 365 方案2的 Microsoft Defender](defender-for-office-365.md)

如果您的組織有 Microsoft 365 E5 或 Microsoft Defender 用於 Office 365 計畫2（包括[威脅調查和回應功能](office-365-ti.md)），您可以使用 Microsoft 365 Defender 入口網站中的攻擊模擬訓練，在您的組織中執行實際的攻擊案例。 這些模擬的攻擊可協助您找出並找出有漏洞的使用者，而真實的攻擊會影響您的下一行。 若要深入瞭解，請閱讀本文。

> [!NOTE]
> 攻擊模擬訓練會取代[Microsoft Defender 中 Office 365 的攻擊模擬器中](attack-simulator.md)所述的舊攻擊模擬器 v1 經驗。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Microsoft 365 Defender 入口網站，請前往 <https://security.microsoft.com>。 攻擊模擬訓練可在 **電子郵件和協同** 作業的 \> **攻擊模擬訓練** 中取得。 若要直接進入攻擊模擬訓練，請開啟 <https://security.microsoft.com/attacksimulator> 。

- 如需不同 Microsoft 365 訂閱中的攻擊模擬訓練可用性的相關資訊，請參閱[Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您必須在 Microsoft 365 Defender 入口網站或 Azure Active Directory 中指派許可權，才能執行本文中的程式。 具體說來，您必須是 **組織管理**、 **安全性管理員** 或下列其中一個角色的成員：
  - **攻擊模擬器管理員**：建立及管理攻擊類比活動的所有層面。
  - **攻擊模擬器的「負載作者**」：建立系統管理員可以稍後再啟動的攻擊負載。

  如需詳細資訊，請參閱 Microsoft 365 Defender 入口網站或系統[管理員角色](../../admin/add-users/about-admin-roles.md)[中的許可權](permissions-microsoft-365-security-center.md)。

- 攻擊模擬訓練沒有對應的 PowerShell Cmdlet。

- 攻擊類比和訓練相關資料會與其他客戶資料一起儲存，以供 Microsoft 365 服務使用。 如需詳細資訊，請參閱[Microsoft 365 資料位置](../../enterprise/o365-data-locations.md)。 可在下列地區取得攻擊模擬： <、APC、EUR、IND、CAN、澳大利亞、FRA、GBR、JPN 和 KOR。

- 在 15 2021 年6月為止，GCC 中提供攻擊模擬訓練。 如果您的組織已 Office 365 G5 GCC 或 Microsoft Defender for Office 365 (Plan 2) ，您可以使用 Microsoft 365 Defender 入口網站中的攻擊模擬訓練訓練，在組織中執行實際的攻擊案例，如本文所述。 GCC 高或 DoD 環境中尚未提供攻擊模擬訓練。

> [!NOTE]
> 攻擊模擬訓練為 E3 客戶提供一項功能的子集，以作為試用版。 試用版產品包含使用認證收集負載的功能，以及可選取「ISA 網路釣魚」或「大量市場網路釣魚」訓練經驗的功能。 其他功能都不是 E3 試用版產品的一部分。

## <a name="simulations"></a>類比

*網路釣魚* 是一種常見的電子郵件攻擊術語，可嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊。 *網路釣魚* 是指我們歸類為 _社交工程_ 的技術子集的一部分。

在攻擊模擬訓練中，有多種類型的社交工程技術可供使用：

- **認證收集**：攻擊者會傳送包含 URL 的郵件給收件者。 當收件者按一下 URL 時，會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。 通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。

- **惡意程式碼附件**：攻擊者會傳送包含附件的郵件給收件者。 當收件者開啟附件時，會 (任何程式碼，例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進一步 entrench 自己。

- **附件中的連結**：這是認證搜集的混合。 攻擊者會傳送包含附件內之 URL 的郵件給收件者。 當收件者開啟附件並按一下 URL 時，他們會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。 通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。

- **惡意程式碼連結**：攻擊者會傳送收件者一封郵件，其中包含已知檔案共用 (網站上附件的連結，例如，SharePoint 線上或 Dropbox) 。 當收件者按一下 URL 時，附件隨即開啟，並隨意執行程式碼 (例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進行進一步的 entrench。

- **磁片磁碟機-依 url**：攻擊者會傳送包含 url 的郵件給收件者。 當收件者按一下 URL 時，會進入嘗試執行背景代碼的網站。 此背景程式碼會嘗試收集收件者的相關資訊，或在其裝置上部署任意程式碼。 通常，目的地網站是眾所周知的網站，已遭到損害或眾所周知的網站複本。 熟悉此網站可協助說服使用者可安全地按一下連結。 此技術也稱為「 _watering 洞」攻擊_。

> [!NOTE]
> 在網路釣魚活動中使用 URL 之前，請先檢查支援的網頁瀏覽器中模擬之網路釣魚 URL 的可用性。 雖然我們與許多 URL 信譽廠商合作，以無條件允許這些類比 URLs，但我們並不一定 (如 Google 保管庫流覽) 等完整覆蓋。 大部分廠商都會提供指引，讓您無條件允許特定 URLs (例如， <https://support.google.com/chrome/a/answer/7532419>) 。

下列清單說明攻擊模擬訓練所用的 URLs：

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>建立模擬

如需如何建立及傳送新模擬的逐步指示，請參閱 [模擬網路釣魚攻擊](attack-simulation-training.md)。

### <a name="create-a-payload"></a>建立有效載荷

如需如何建立用於類比的負載的逐步指示，請參閱 [建立攻擊模擬訓練的自訂負載](attack-simulation-training-payloads.md)。

### <a name="gaining-insights"></a>取得洞察力

如需如何透過報告取得深入瞭解的逐步指示，請參閱 [透過攻擊模擬訓練取得深入](attack-simulation-training-insights.md)瞭解。

> [!NOTE]
> 攻擊模擬程式使用保管庫 Office 365 的 Defender 中的連結，以安全地追蹤傳送至網路釣魚活動收件者的負載郵件中之 URL 的資料，即使保管庫連結原則中的 [**不要追蹤使用者點擊**] 設定也是一樣。
