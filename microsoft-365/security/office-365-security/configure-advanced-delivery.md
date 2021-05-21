---
title: 設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 系統管理員可以瞭解如何使用 Exchange Online Protection (EOP) 中的高級傳遞原則，以識別不應該在特定支援案例中篩選的郵件 (協力廠商網路釣魚模擬及傳送至安全性作業的郵件 (SecOps) 信箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bebc094b56a20a43f92d1acf8d374110de43d71
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594118"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文所述的功能都是在預覽中，並非每個人都可以使用，而且可能會變更。

若要讓組織保持[預設安全性](secure-by-default.md)，Exchange Online Protection (EOP) 不允許對導致惡意程式碼或高可信度網路釣魚 verdicts 的郵件進行安全清單或篩選旁路。 不過，有些特定案例需要傳遞未篩選的郵件。 例如：

- **協力廠商網路釣魚模擬**：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。
- **(SecOps 的安全性作業) 信箱**：安全小組用來收集及分析未篩選郵件 (良好和不良) 的專用信箱。

您可以使用 Microsoft 365 中的 _高級傳遞原則_，以避免篩選這些 _特定案例中_ 的郵件 <sup>\*</sup> 。 高級傳遞原則可確保不會篩選這些案例中的郵件：

- EOP 中的篩選器和 Microsoft Defender for Office 365 不會對這些郵件採取任何動作。<sup>\*</sup>
- [零小時清除 (](zero-hour-auto-purge.md) 用於垃圾郵件和網路釣魚的 ZAP) 不會對這些郵件採取任何動作。<sup>\*</sup>
- 在這些情況下，不會觸發[預設系統警示](alerts.md)。
- [Office 365 中的 AIR 和](office-365-air.md)叢集會忽略這些郵件。
- 特別是協力廠商網路釣魚模擬：
  - 系統[管理報送](admin-submission.md)會產生自動回應，表示郵件屬於網路釣魚模擬活動的一部分，而且不是實際威脅。 不會觸發警示和空氣。
  - [Office 365 的 Defender 中的安全連結](safe-links.md)不會封鎖或引爆這些郵件中特別識別的 URLs。
  - [Office 365 的 Defender 中的安全附件](safe-attachments.md)不會引爆這些郵件中的附件。

<sup>\*</sup> 您無法略過惡意程式碼篩選或 ZAP 惡意程式碼。

由高級傳遞原則識別的郵件不會受到安全性威脅，所以郵件會標示為系統覆寫。 系統管理員可以在下列體驗中篩選和分析這些系統覆寫：

- [Office 365 方案2之 Defender 中的威脅瀏覽器/即時偵測](threat-explorer.md)
- [威脅瀏覽器/即時偵測中的電子郵件實體頁面](mdo-email-entity-page.md)
- [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Defender for Endpoint 中的高級搜尋](../defender-endpoint/advanced-hunting-overview.md)
- [行銷活動檢視](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **高級傳遞** ] 頁面，請開啟] <https://protection.office.com/advanceddelivery> 。

- 您必須已獲指派許可權，才能執行本文中的程式：
  - 若要在高級傳遞原則中建立、修改或移除已設定的設定，您必須是 **security & 合規性中心** 內的 **安全性系統管理員** 角色群組成員，以及 **Exchange Online** 中 **組織管理** 角色群組的成員。  
  - 若要以唯讀方式存取高級傳遞原則，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)和[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用安全性 & 合規性中心設定高級傳遞原則中的協力廠商網路釣魚模擬

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **高級傳遞**。

2. 在 [ **高級傳遞** ] 頁面上，選取 [ **網路釣魚類比** ] 索引標籤，然後按一下 [ **編輯**]。

3. 在開啟的 **協力廠商網路釣魚類比** 浮出控制項上，設定下列設定：

   - **送出網域**：必須至少有一個電子郵件地址網域 (例如，contoso.com) 。 您最多可以新增10個專案。
   - 傳送 **IP**：必須至少有一個有效的 IPv4 位址。 您最多可以新增10個專案。 有效值為：
     - 單一 IP：例如，192.168.1.1。
     - IP 範圍：例如，192.168.0.1-192.168.0.254。
     - CIDR IP：例如 192.168.0.1/25。
   - **類比 URLs 若要允許**：請輸入您的網路釣魚類比活動中不應該封鎖或引爆的特定 URLs。 您最多可以新增10個專案。

4. 完成後，按一下 [ **儲存]。**

您設定的協力廠商網路釣魚模擬專案會顯示在 [ **網路釣魚類比** ] 索引標籤上。若要進行變更，請按一下索引標籤上的 [ **編輯** ]。

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用安全性 & 合規性中心設定高級傳遞原則中的 SecOps 信箱

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **高級傳遞**。

2. 在 [ **高級傳遞** ] 頁面上，選取 [ **SecOps 信箱** ] 索引標籤，然後按一下 [ **編輯**]。

3. 在開啟的 **SecOps 信箱** 浮出控制項上，輸入您要指定為 SecOps 信箱的現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。

4. 完成後，按一下 **[儲存]**。

您設定的 SecOps 信箱專案會顯示在 [ **SecOps 信箱** ] 索引標籤上。若要進行變更，請按一下索引標籤上的 [ **編輯** ]。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要篩選略過的其他案例

除了高級傳遞原則可以協助您使用的兩種情形之外，還有其他情況可能需要您略過篩選：

- **協力廠商篩選**：如果您的網域的 MX 記錄 *沒有* 指向 Office 365 (郵件會先在其他地方傳送) ，否則 *無法使用* [secure](secure-by-default.md) 。

  若要繞過協力廠商篩選所評估之郵件的 Microsoft 篩選功能，請使用郵件流程規則 (也稱為傳輸規則) ，請參閱 [使用郵件流程規則來設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

- **審核** 中的誤報：您可能想要暫時允許 Microsoft 透過系統 [管理員提交](admin-submission.md) 進行的某些郵件仍要進行分析，以報告未正確標記為壞于 microsoft (誤報) 的已知良好郵件。 就像所有覆寫一樣， **_強烈建議您_** 暫時進行這些折中。
