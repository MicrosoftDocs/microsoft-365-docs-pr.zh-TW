---
title: 調查異常偵測警示
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 調查異常偵測警示。
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420118"
---
# <a name="investigate-anomaly-detection-alerts"></a>調查異常偵測警示

 Microsoft 應用程式控管提供惡意活動的安全性偵測和警示。 本指南的目的是提供您每個警示的一般和實用資訊，協助您進行調查和補救工作。 本指南包含觸發警示的一般條件資訊。 由於異常偵測本質上是不確定的，因此只有在有偏離標準的行為時，才會觸發異常偵測。 最後，某些警示可能處於預覽階段，因此請定期查看正式文件，以取得更新的警示狀態。

## <a name="mitre-attck"></a>MITRE ATT&CK

為了更容易對應 Microsoft 應用程式控管警示與熟悉的 MITRE ATT&CK 矩陣之間的關係，我們已根據對應的 MITRE ATT&CK 策略將警示分類。 這個額外的參考資料可讓您容易了解當觸發 Microsoft 應用程式安全性與控管警示時，可能使用的可疑攻擊技術。

本指南提供調查和補救 Microsoft 應用程式控管警示的資訊，分為以下各類。

- 初次存取
- 執行
- 持續性
- 權限提升
- 防禦規避
- 認證存取
- 集合
- 外流
- 影響

## <a name="security-alert-classifications"></a>安全性警示分類

在適當的調查之後，所有 Microsoft 應用程式控管警示都可以分類為下列其中一種活動類型：

- 確判為真 (TP)：已確認是惡意活動的警報。
- 良性確判為真 (B-TP)：對可疑但非惡意活動的警報，例如滲透測試或其他授權的可疑操作。
- 誤誤 (FP)：非惡意活動的警示。

## <a name="general-investigation-steps"></a>一般調查步驟

在調查任何類型的警示時，請使用下列一般指導方針，以在應用建議動作之前更清楚地了解潛在威脅。

- 檢閱應用程式嚴重性層級，並與租用戶中其餘的應用程式比較。 檢閱此資訊有助於發現您租用戶中的哪些應用程式會帶來更大的風險。
- 如果您發現 TP，請檢閱所有應用程式活動，了解影響。 例如，請檢閱下列應用程式資訊：

  - 授予存取權的範圍
  - 異常行為  
  - IP 位址和位置

## <a name="initial-access-alerts"></a>初次存取警示

本節描述的警示可指出可能試圖在您的組織中保持立足點的惡意應用程式。  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>帶有可疑同意範圍的編碼應用程式名稱

**嚴重性：** 中

**描述**：此偵測可發現帶有字元 (例如 Unicode 或編碼字元) 的 OAuth 應用程式，收到可疑的同意範圍要求並透過 Graph API 存取使用者郵件資料夾。 此警示可能表示有人企圖將惡意應用程式偽裝成已知且受信任的應用程式，以便攻擊者可以誤導使用者同意使用惡意應用程式。

**TP 或 FP？**

- **TP**：如果您可以確認 OAuth 應用程式已使用從未知來源提供的可疑範圍對顯示名稱進行編碼，則表示其確判為真。  

  **建議動作**：檢閱此應用程式要求的權限層級，以及哪些使用者已授予存取權。 根據您的調查，您可以選擇禁止存取此應用程式。

  若要禁止存取應用程式，請在 OAuth 應用程式頁面中，在您要禁止的應用程式出現的列上，選取禁止圖示。 您可以選擇是否要告知使用者他們安裝和授權的應用程式已被禁止。 通知可讓使用者知道應用程將遭到停用，且他們將無法存取連線的應用程式。 如果您不希望使用者知道，請在對話方塊中取消選取 [通知先前授與此遭禁應用程式存取權的使用者]。 建議您讓應用程式使用者知道他們的應用程式即將遭到禁用。

- **FP**：如果您要確認應用程式具有編碼名稱，但在組織中具有合法的商業用途。

  **建議動作**：關閉警示。

#### <a name="understand-the-scope-of-the-breach"></a>了解入侵範圍

請遵循教學課程，了解如何[調查有風險的 OAuth 應用程式](/cloud-app-security/investigate-risky-oauth)。

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>具有讀取範圍的 OAuth 應用程式具有可疑的回覆 URL

**嚴重性：** 中

**描述**：此偵測會發現僅具有讀取範圍的 OAuth 應用程式，例如 User.Read、People.Read、Contacts.Read、Mail.Read、Contacts.Read.Shared 會透過 Graph API 重新導向至可疑的回覆 URL。 此活動會嘗試指出，具有較低權限的惡意應用程式 (例如讀取範圍) 可能會受到利用，以執行使用者帳戶偵察。

**TP 或 FP？**

- **TP**：如果您可以確認具有讀取範圍的 OAuth 應用程式來自未知來源並重新導向至可疑的 URL，則表示其確判為真。

  **建議動作**：檢閱應用程式要求的回覆 URL 和範圍。 根據您的調查，您可以選擇禁止存取此應用程式。 檢閱此應用程式要求的權限層級，以及哪些使用者已授予存取權。

  若要禁止存取應用程式，請在 OAuth 應用程式頁面中，在您要禁止的應用程式出現的列上，選取禁止圖示。 您可以選擇是否要告知使用者他們安裝和授權的應用程式已被禁止。 通知可讓使用者知道應用程將遭到停用，且他們將無法存取連線的應用程式。 如果您不希望使用者知道，請在對話方塊中取消選取 [通知先前授與此遭禁應用程式存取權的使用者]。 建議您讓應用程式使用者知道他們的應用程式即將遭到禁用。

- **B-TP**：調查後，您可以確認應用程式在組織中具有合法的商業用途。

  **建議動作**：關閉警示。

#### <a name="understand-the-scope-of-the-breach"></a>了解入侵範圍 

1. 檢閱應用程式完成的所有活動。
1. 如果您懷疑應用程式可疑，建議您在不同的 App Store 中調查應用程式名稱和回覆 URL。 檢查 App Store 時，請專注於下列類型的應用程式：
   - 最近建立的應用程式。
   - 具有可疑回覆 URL 的應用程式
   - 最近尚未更新的應用程式。 缺少更新可能表示應用程式不再受到支援。
1. 如果您仍然懷疑應用程式可疑，您可以在網路上研究應用程式名稱、發行者名稱和回覆 URL  

## <a name="persistence-alerts"></a>持續性警示

本節描述的警示可指出可能試圖在您的組織中保持立足點的惡意執行者。

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>具有可疑 OAuth 範圍的應用程式會建立收件匣規則  

**嚴重性：** 中

**MITRE 識別碼**：T1137.005、T1114  

此偵測可發現同意可疑範圍的 OAuth 應用程式、建立可疑的收件匣規則，然後透過 Graph API 存取使用者的郵件資料夾和郵件。 收件匣規則，例如將所有或特定電子郵件轉寄到另一個電子郵件帳戶，以及 Graph 呼叫以存取電子郵件並傳送到另一個電子郵件帳戶，可能會試圖從您的組織中竊取資訊。  

**TP 或 FP？**

- **TP**：如果您可以確認收件匣規則是由 OAuth 第三方應用程式建立，並且具有從未知來源提供的可疑範圍，則表示其確判為真。

  **建議動作**：停用並移除應用程式、重設密碼，以及移除收件匣規則。

  請遵循「如何使用 Azure Active Directory 重設密碼」教學課程，以及遵循「如何移除收件匣規則」教學課程。

- **FP**：如果您可以確認該應用程式出於合法理由，為新的或個人的外部電子郵件帳戶建立收件匣規則。

  **建議動作**：關閉警示。

#### <a name="understand-the-scope-of-the-breach"></a>了解入侵範圍

1. 檢閱應用程式完成的所有活動。
1. 檢閱應用程式授與的範圍。
1. 檢閱應用程式建立的收件匣規則動作和條件。

## <a name="collection-alerts"></a>集合警示

本節描述的警報可指出，惡意行為者可能正嘗試從您的組織收集對其目標有益的資料。

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>應用程式進行異常 Graph 呼叫以讀取電子郵件

**嚴重性：** 中

**MITRE 識別碼**：T1114

此偵測可發現企業營運 (LOB) OAuth 應用程式透過 Graph API 存取異常且大量的使用者郵件資料夾和郵件，這表示惡意攻擊者已嘗試入侵您的組織。

**TP 或 FP？**

- **TP**：如果您可以確認異常 Graph 活動是由企業營運 (LOB) OAuth 應用程式執行的，則表示其確判為真。

  **建議**：暫時停用應用程式並重設密碼，然後重新啟用應用程式。

  請遵循「如何使用 Azure Active Directory 重設密碼」教學課程。

- **FP**：如果您可以確認應用程式試圖執行異常大量的 Graph 呼叫。

  **建議動作**：關閉警示。

#### <a name="understand-the-scope-of-the-breach"></a>了解入侵範圍

1. 請查閱此應用程式所執行之事件的活動記錄，以深入了解其他 Graph 活動，以讀取電子郵件並嘗試收集使用者的敏感性電子郵件資訊。
1. 監視新增到應用程式的未預期認證。
