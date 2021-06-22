---
title: 安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: 系統管理員可以瞭解 Office 365 中 Microsoft Defender 的保管庫附件功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 127d862d235abc4cd81f62679b97077c7a80bd70
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054390"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>保管庫Microsoft Defender 中 Office 365 的附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

保管庫[Microsoft Office 365 中的附件針對](defender-for-office-365.md) [Exchange Online Protection (EOP) 中的反惡意程式碼保護](anti-malware-protection.md)已掃描的電子郵件附件，提供額外的保護層級。 具體而言，保管庫附件會在電子郵件傳送至收件者 (程式（稱為 _引爆_) ）之前，使用虛擬環境檢查電子郵件中的附件。

保管庫電子郵件的附件保護是由保管庫附件原則所控制。 沒有預設的保管庫附件原則，**因此若要取得保管庫附件的保護，您必須建立一或多個保管庫附件原則**。 如需相關指示，請參閱[Set up 保管庫附件原則 in Office 365 中的 Defender](set-up-safe-attachments-policies.md)。

下表說明 Microsoft 365 和 Office 365 組織中保管庫附件的案例，也就是包含 Microsoft Defender for Office 365 的組織，也就是說，缺乏授權不是範例 (的問題。

<br>

****

|案例|結果|
|---|---|
|Pat 的 Microsoft 365 E5 組織未設定任何保管庫附件原則。|Pat 未受到保管庫附件的保護。 <p> 系統管理員必須建立至少一個保管庫附件原則，以供使用中保管庫附件保護使用。 此外，原則的條件必須包括 Pat （如果 Pat 是以保管庫附件保護）。|
|「他的組織」具有僅適用于財務員工的保管庫附件原則。 「銷售部門」是「銷售部門」的成員。|「他的保管庫附件不受保護。 <p> 財務員工會受到保管庫附件保護，但不會 (銷售員工，也不會) 其他員工。|
|昨天，Jean-francois 組織中的系統管理員建立了套用至所有員工的保管庫附件原則。 在今天的早期，Jean-francois 收到包含附件的電子郵件。|Jean-francois 會受到保管庫附件的保護。 <p> 通常，新的原則大約需要30分鐘的時間才會生效。|
|Chris 的組織為組織中的每個人都有長期的保管庫附件原則。 Chris 收到包含附件的電子郵件，然後將郵件轉寄給外部收件者。|Chis 會受到保管庫附件的保護。 <p> 如果外部收件者在其組織中也有保管庫附件原則，則轉寄的郵件會受到這些原則的制約。|
|

保管庫附件掃描會在您的 Microsoft 365 資料所在的相同區域中進行。 如需資料中心地理位置的詳細資訊，請參閱 [您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> 下列功能位於 Microsoft 365 Defender 入口網站中保管庫附件原則的全域設定。 不過，這些設定會以全域方式啟用或停用，不需要保管庫附件原則：
>
> - [保管庫 SharePoint、OneDrive 及 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)。
> - [Microsoft 365 E5 中的安全文件](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>保管庫附件原則設定

本節說明保管庫附件原則中的設定：

- **保管庫附件未知的惡意程式碼回應**：此設定會控制保管庫附件惡意程式碼掃描的電子郵件中的動作。 下表說明可用的選項：

  <br>

  ****

  |選項|Effect|使用時機：|
  |---|---|---|
  |**關閉**|保管庫附件不會掃描附件是否有惡意程式碼。 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)仍然會掃描郵件是否有惡意程式碼。|為選取的收件者關閉掃描。 <p> 避免路由內部郵件的非必要延遲。 <p> **大多數使用者不建議使用此選項。您應只使用此選項，關閉只從受信任的寄件者接收郵件之收件者的保管庫附件掃描。**|
  |**監視**|傳送包含附件的郵件，然後追蹤偵測到的惡意程式碼會發生什麼事。 <p> 傳遞安全郵件可能會因為保管庫附件掃描而延遲。|查看您的組織中偵測到惡意程式碼的位置。|
  |**封鎖**|防止傳遞偵測到惡意軟體附件的郵件。 <p> 僅限系統管理員 (不) 使用者可以查看、發行或刪除郵件的郵件遭到 [隔離](manage-quarantined-messages-and-files.md) 。 <p> 自動封鎖未來的郵件和附件實例。 <p> 傳遞安全郵件可能會因為保管庫附件掃描而延遲。|保護您的組織，避免使用相同惡意程式碼附件的重複攻擊。 <p> 此為預設值，以及標準及嚴格的預設 [安全性原則](preset-security-policies.md)中的建議值。|
  |**Replace**|移除偵測到的惡意程式碼附件。 <p> 通知收件者已移除附件。 <p>  僅限系統管理員 (不) 使用者可以查看、發行或刪除郵件的郵件遭到 [隔離](manage-quarantined-messages-and-files.md) 。 <p> 傳遞安全郵件可能會因為保管庫附件掃描而延遲。|對收件者提高知名度，因為偵測到惡意程式碼已移除附件。|
  |**動態傳遞**|會立即傳遞郵件，但是會以預留位置取代附件，直到保管庫附件掃描完成為止。 <p> 如需詳細資訊，請參閱本文稍後的[保管庫附件原則中的動態傳遞](#dynamic-delivery-in-safe-attachments-policies)一節。|避免郵件延遲，防止寄件者惡意的檔案。 <p> 讓收件者在進行掃描時以安全模式預覽附件。|
  |

- 重新 **導向附件的偵測： Enable 重新導向** 並 **將附件傳送至下列電子郵件地址**：針對 **封鎖**、**監視器** 或 **取代** 動作，將包含惡意程式碼附件的郵件傳送至指定的內部或外部電子郵件地址，以進行分析和調查。

  標準和嚴格原則設定的建議是啟用重新定向。 如需詳細資訊，請參閱[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

- **若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取專案**。保管庫附件所指定的動作會對郵件採取 **未知惡意程式碼回應**，即使保管庫附件掃描無法完成也是一樣。 如果您選取 [ **啟用重新導向**]，則無條件選取此選項。 否則，郵件可能會遺失。

- **收件者篩選器**：您必須指定收件者條件和例外狀況，以決定要套用的原則。 您可以使用這些屬性做為條件和例外狀況：
  - **收件者是**
  - **收件者網域是**
  - **收件者是以下的成員**

  您只可以使用條件或例外狀況，但條件或例外狀況可以包含多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

- **Priority**：如果您建立多個原則，您可以指定要套用的順序。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

  如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>保管庫附件原則中的動態傳遞

> [!NOTE]
> 動態傳遞只適用于 Exchange Online 信箱。

保管庫附件原則中的動態傳遞動作會搜尋，以消除保管庫附件掃描可能造成的任何電子郵件傳遞延遲。 電子郵件的本文會傳送給收件者，並提供每個附件的預留位置。 在附件找到安全後，就會保留預留位置，然後即可開啟或下載附件。

若發現有惡意的附件，就會隔離郵件。 只有系統管理員 (非使用者) 可以查看、發行或刪除保管庫附件掃描隔離的郵件。 如需詳細資訊，請參閱 [以系統管理員身分管理被隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。

大多數的 pdf 和 Office 檔都可以在安全模式中預覽，同時保管庫附件掃描進行中。 如果附件與動態傳遞預覽程式不相容，收件者會在完成保管庫附件掃描時，看到附件的預留位置。

如果您使用行動裝置，但無法在行動裝置上的動態傳遞預覽程式中呈現該郵件，請嘗試使用行動裝置瀏覽器，嘗試以先前稱為 Outlook Web App) 的 Outlook 網頁版 (開啟郵件。

以下是動態傳遞和轉寄郵件的一些考慮：

- 如果轉寄的收件者是以使用動態傳遞選項的保管庫附件原則保護，則收件者會看到該預留位置，且具有預覽相容檔案的功能。
- 如果轉寄的收件者不是由保管庫附件原則所保護，將會傳遞郵件和附件，但不需要任何保管庫附件掃描或附件的預留位置。

在某些情況下，動態傳遞無法取代郵件中的附件。 這些情況包括：

- 公用資料夾中的郵件。
- 使用自訂規則，然後再移至使用者信箱的郵件。
-  (會自動或手動將) 雲端信箱移至其他位置（包括封存資料夾）的郵件。
- 收件匣規則會將郵件移出收件匣，移至其他資料夾。
- 刪除的郵件。
- 使用者的信箱搜尋資料夾處於錯誤狀態。
- Exchange Online 啟用 Exclaimer 的組織。 若要解決此問題，請參閱 [KB4014438](https://support.microsoft.com/help/4014438)。
- [S/MIME) ](/exchange/security-and-compliance/smime-exo/smime-exo) 加密郵件。
- 您已在保管庫附件原則中設定動態傳送動作，但收件者不支援動態傳遞 (例如，收件者是內部部署 Exchange 組織中的信箱) 。 不過，[保管庫 Office 365 的 Microsoft Defender 中的連結](set-up-safe-links-policies.md)可以掃描包含 URLs (的 Office 檔附件，具體取決於[保管庫連結的通用設定](configure-global-settings-for-safe-links.md)如何設定) 。

## <a name="submitting-files-for-malware-analysis"></a>提交檔案以進行惡意程式碼分析

- 如果您收到要傳送給 Microsoft 進行分析的檔案，請參閱將 [惡意程式碼和非惡意程式碼提交給 microsoft](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)進行分析。
- 如果您收到的電子郵件訊息 (包含或沒有要提交給 Microsoft 進行分析的附件) ，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。
