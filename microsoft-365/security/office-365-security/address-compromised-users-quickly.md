---
title: 利用自動調查和回應來處理已遭破壞的使用者帳戶
keywords: AIR，autoIR，ATP，自動化，調查，回應，修正，威脅，高級，威脅，保護，已遭破壞
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: 瞭解如何使用 Microsoft Defender for Office 365 方案2中的自動調查和回應功能，以加速偵測和解決已遭破壞之使用者帳戶的處理常式。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176060"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>利用自動調查和回應來處理已遭破壞的使用者帳戶

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[Microsoft Defender For Office 365 方案 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 包含強大的 [自動化調查和回應](office-365-air.md) (AIR) 功能。 這類功能可讓您的安全性運作小組儲存大量的時間和精力處理威脅。 Microsoft 繼續加強安全性功能。 最近，AIR 功能已增強，可在目前預覽) 中包含已遭破壞的使用者安全性行動手冊 (。 請閱讀本文以深入瞭解已遭破壞的使用者安全性行動手冊。 [使用 Microsoft Defender For Office 365，查看並回應使用者洩密和限制損等範圍](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)的博客文章，以取得其他詳細資料。

![針對已遭破壞的使用者進行自動調查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

「已遭破壞的使用者安全性行動手冊」可讓貴組織的安全性小組進行下列作業：

- 加速偵測到的使用者帳戶的偵測;

- 在帳戶被攻破時限制遭到破壞的範圍;和

- 更有效率地回應遭到破壞的使用者。

## <a name="compromised-user-alerts"></a>遭到破壞的使用者警示

當使用者帳戶受損時，會發生反常或反常的行為。 例如，網路釣魚和垃圾郵件可能會從受信任的使用者帳戶內部傳送。 適用于 office 365 的 Defender （適用于 office 365 中的電子郵件模式和共同作業活動中）可以偵測到。 發生這種情況時，就會觸發警示，威脅緩解程式會開始進行。

例如，以下是由於可疑電子郵件傳送而觸發的警示：

![因可疑電子郵件傳送而觸發的警示](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

以下是當使用者達到傳送限制時所觸發的警示的範例：

![因傳送限制已達到所觸發的警示](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>調查和回應已遭破壞的使用者

當使用者帳戶遭到攻破時，會觸發警示。 在某些情況下，此使用者帳戶會遭到封鎖，並避免傳送任何後續的電子郵件訊息，直到您組織的安全作業小組解決問題為止。 在其他情況下，自動調查會開始，這可能會導致您的安全小組應採取建議的動作。

- [查看和調查限制的使用者](#view-and-investigate-restricted-users)

- [查看有關自動化調查的詳細資料](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 您必須具有適當的許可權，才能執行下列工作。 請參閱 [使用 AIR 功能所需的許可權](office-365-air.md#required-permissions-to-use-air-capabilities)。

### <a name="view-and-investigate-restricted-users"></a>查看和調查限制的使用者

您有幾個選項可供您流覽至限制的使用者清單。 例如，在安全性 & 規範中心，您可以前往「 **威脅管理**」 \> **查看** \> **限制的使用者**。 下列程式說明如何使用「 **警示** 」儀表板進行流覽，這是查看可能已觸發的各種警示的好方法。

1. 移至 <https://protection.office.com> 並登入。

2. 在功能窗格中，選擇 [ **警示** \> **儀表板**]。

3. 在 [ **其他警示** ] 小工具中，選擇 [ **受限制的使用者**]。

   ![其他提醒小工具](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   這會開啟受限制的使用者清單。

   ![Office 365 中的受限使用者](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. 選取清單中的使用者帳戶，以查看詳細資料並採取動作，例如 [發行受限制的使用者](removing-user-from-restricted-users-portal-after-spam.md)。

### <a name="view-details-about-automated-investigations"></a>查看有關自動化調查的詳細資料

當自動調查開始時，您可以在安全性 & 規範中心中查看其詳細資料和結果。 移至 **威脅管理** \> **調查**，然後選取調查以查看其詳細資料。

若要深入瞭解，請參閱 [查看調查的詳細資料](air-view-investigation-results.md)。

## <a name="keep-the-following-points-in-mind"></a>請記住下列幾點

- **停留在提醒** 上。 如您所知，入侵的可能性越長，您的組織、客戶及協力廠商的潛在影響程度越大，成本也越大。 及早偵測和及時回應對於緩解威脅很重要，尤其是在使用者的帳戶遭到破壞時。

- 「**自動化」協助（但不取代）您的安全性運作小組**。 自動化調查和回應功能可在初期偵測到遭到損害的使用者，但是您的安全性作業小組可能需要接洽並進行一些調查和修復。 需要一些協助嗎？ 請參閱 [複查和核准動作](air-review-approve-pending-completed-actions.md)。

- 請 **不要依賴可疑的登入警示做為您唯一的指示器**。 當使用者帳戶遭到攻破時，可能會或不會觸發可疑的登入警示。 有時候，它是一系列的活動，會在帳戶遭到洩漏後觸發警示。 想要瞭解更多關於提醒的資訊嗎？ 請參閱 [警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。

## <a name="next-steps"></a>後續步驟

- [回顧使用 AIR 功能所需的許可權](office-365-air.md#required-permissions-to-use-air-capabilities)

- [在 Office 365 中尋找並調查惡意電子郵件](investigate-malicious-email-that-was-delivered.md)

- [深入瞭解 Microsoft Defender for Endpoint 中的 AIR](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [造訪 Microsoft 365 藍圖，查看即將推出的功能](https://www.microsoft.com/microsoft-365/roadmap?filters=)
