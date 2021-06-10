---
title: Microsoft Defender Office 365 中的威脅瀏覽器和即時偵測基本知識
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用 Explorer 或即時偵測，以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300122"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>威脅總管與即時偵測基本概念

本文內容：

- [威脅瀏覽器與即時偵測的差異](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [必要的授權和權限](#required-licenses-and-permissions)

> [!NOTE]
> 這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。 此系列中的其他兩篇文章是威脅流覽 [器中的威脅搜尋](threat-hunting-in-threat-explorer.md) ，以及 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。

本文說明威脅探索與即時偵測報告的差異，以及所需的授權和許可權。

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [許可權](#required-licenses-and-permissions)，則可以使用 **威脅 explorer** (稱為 **Explorer**) 或 **即時** 偵測，以偵測並修正威脅。

在 [ **安全性 & 規範中心**] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。

<br>

****

|使用 Microsoft Defender Office 365 方案2，您會看到：|使用 Microsoft Defender Office 365 方案1，您會看到：|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

使用這些工具，您可以：

- 請參閱 Microsoft 365 安全性功能偵測到惡意程式碼。
- 查看網路釣魚 URL，然後按一下 [已判定資料]。
- 從瀏覽器中的視圖開始自動調查和回應程式。
- 調查惡意電子郵件及其他資訊。

如需詳細資訊，請參閱 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>威脅瀏覽器與即時偵測的差異

- *即時* 偵測是適用于 Office 365 方案1之 Defender 的報表工具。 *威脅瀏覽器* 是適用于 Office 365 方案2之 Defender 的威脅搜尋和修正工具。
- 即時偵測報告可讓您即時查看偵測。 威脅瀏覽器也會這麼做，但是它會提供特定攻擊的其他詳細資料，例如，反白顯示攻擊活動，並讓安全性運作小組能夠修正威脅 (包括觸發 [自動調查和回應調查](automated-investigation-response-office.md)) 。
- *所有的電子郵件* view 都可用於威脅瀏覽器，但不會包含在即時偵測報告中。
- 威脅瀏覽器中包含豐富型篩選功能和修正動作。 如需詳細資訊，請參閱[Microsoft defender for Office 365 Service Description：每個 defender 的功能可用性以取得 Office 365 計畫](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用瀏覽器或即時偵測的其中一項：

- 但是 Explorer 只會包含在 Office 365 方案2的 Defender 中。
- 在 Office 365 方案1的 Defender 中包含即時偵測報告。

安全性作業小組需要為所有應受 Office 365 的 Defender 保護的使用者指派授權，並請注意，瀏覽器和即時偵測會顯示已授權使用者的偵測資料。

若要查看和使用 Explorer *或* 即時偵測，您必須具備下列各項：

- 針對安全性 & 規範中心：

  - 組織管理
  - 安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) 
  - 安全性讀取者

- Exchange Online：

  - 組織管理
  - 僅限檢視組織管理
  - 僅限檢視收件者
  - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能權限](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>其他資訊
- [威脅瀏覽器收集電子郵件實體頁面上的電子郵件詳細資料](mdo-email-entity-page.md)
- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案](mdo-for-spo-odb-and-teams.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威脅防護的自動化調查及回應](automated-investigation-response-office.md)