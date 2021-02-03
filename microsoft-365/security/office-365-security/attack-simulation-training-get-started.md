---
title: 開始使用攻擊模擬訓練
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用攻擊模擬訓練，在 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 組織中執行模擬網路釣魚和密碼攻擊。
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877161"
---
# <a name="get-started-using-attack-simulation-training"></a>開始使用攻擊模擬訓練

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

如果您的組織有 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 （包括 [威脅調查和回應功能](office-365-ti.md)），您可以使用 Microsoft Security Center 中的「攻擊模擬訓練」，在您的組織中執行現實的攻擊案例。 這些模擬的攻擊可協助您找出並找出有漏洞的使用者，而真實的攻擊會影響您的下一行。 若要深入瞭解，請閱讀本文。

> [!NOTE]
> 攻擊模擬訓練會取代 [Microsoft Defender For Office 365 中](attack-simulator.md)所述的舊攻擊模擬器 v1 體驗。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Microsoft 安全中心，請移至 <https://security.microsoft.com/> 。 攻擊模擬訓練可在 **電子郵件和協同** 作業的 \> **攻擊模擬訓練** 中取得。 若要直接進入攻擊模擬訓練，請開啟 <https://security.microsoft.com/attacksimulator> 。

- 如需不同 Microsoft 365 訂閱中的攻擊模擬訓練可用性的相關資訊，請參閱 [Microsoft Defender For Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您必須在安全性 & 合規性中心或 Azure Active Directory 中指派許可權，才能執行本文中的程式。 具體說來，您必須是 **組織管理**、 **安全性管理員** 或下列其中一個角色的成員：
  - **攻擊模擬器管理員**：建立及管理攻擊類比活動的所有層面。
  - **攻擊模擬器的「負載作者**」：建立系統管理員可以稍後再啟動的攻擊負載。

  如需詳細資訊，請參閱 [安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md) 或 [有關系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

- 攻擊模擬訓練沒有對應的 PowerShell Cmdlet。

- 攻擊類比和訓練相關的資料會與其他 Microsoft 365 服務的客戶資料一起儲存。 如需詳細資訊，請參閱 [Microsoft 365 資料位置](/microsoft-365/enterprise/o365-data-locations)。 目前無法使用下列地區的攻擊模擬： SGP、UAE、ZAF、GER、BRA 及 CHE。

## <a name="simulations"></a>類比

*網路釣魚* 是一種常見的電子郵件攻擊術語，可嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊。 *網路釣魚* 是指我們歸類為 _社交工程_ 的技術子集的一部分。

在攻擊模擬訓練中，有多種類型的社交工程技術可供使用：

- **認證收集**：攻擊者會傳送包含 URL 的郵件給收件者。 當收件者按一下 URL 時，會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。 通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。

- **惡意程式碼附件**：攻擊者會傳送包含附件的郵件給收件者。 當收件者開啟附件時，會 (任何程式碼，例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進一步 entrench 自己。

- **附件中的連結**：這是認證搜集的混合。 攻擊者會傳送包含附件內之 URL 的郵件給收件者。 當收件者開啟附件並按一下 URL 時，他們會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。 通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。

- **惡意程式碼連結**：攻擊者會傳送收件者一封郵件，其中包含已知檔案共用 (網站上附件的連結（例如，SharePoint 線上或 Dropbox) ）。 當收件者按一下 URL 時，附件隨即開啟，並隨意執行程式碼 (例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進行進一步的 entrench。

- **磁片磁碟機-依 url**：攻擊者會傳送包含 url 的郵件給收件者。 當收件者按一下 URL 時，會進入嘗試執行背景代碼的網站。 此背景程式碼會嘗試收集收件者的相關資訊，或在其裝置上部署任意程式碼。 通常，目的地網站是眾所周知的網站，已遭到損害或眾所周知的網站複本。 熟悉此網站可協助說服使用者可安全地按一下連結。 此技術也稱為「 _watering 洞」攻擊_。

> [!NOTE]
> 在網路釣魚活動中使用 URL 之前，請先檢查支援的網頁瀏覽器中模擬之網路釣魚 URL 的可用性。 雖然我們與許多 URL 信譽廠商合作，以無條件允許這些類比 URLs，但我們並不一定會有完整的覆蓋範圍 (例如，Google Safe 流覽) 。 大部分廠商都會提供指引，讓您無條件允許特定 URLs (例如， <https://support.google.com/chrome/a/answer/7532419>) 。

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