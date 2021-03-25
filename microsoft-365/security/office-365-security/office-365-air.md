---
title: Microsoft Defender for Office 365 中的自動調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1460deef11a87044530c54c8b10637284829a0cd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204760"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自動調查和回應 (AIR) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender For Office 365](defender-for-office-365.md) 包含強大的自動化調查和回應 (空氣) 功能，可節約您的安全性運作小組時間和工作。 當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。 保持傳入提醒的數量非常驚人。 自動化某些工作可以協助。

AIR 可讓您的安全性運作小組更有效率地運作。 AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。 適當的修正動作等待核准，讓安全性作業小組能夠有效地回應偵測到的威脅。 透過 AIR，您的安全性運作小組可以著重于優先順序較高的工作，而不會失去所觸發之重要警示的視線。

本文說明：

- [空氣的整體流向](#the-overall-flow-of-air);
- [如何取得空氣](#how-to-get-air);和
- 設定或使用 AIR 功能 [所需的許可權](#required-permissions-to-use-air-capabilities) 。
- 您的安全性中心即將推出的變更

本文也包含 [後續步驟](#next-steps)，以及深入瞭解的資源。

## <a name="the-overall-flow-of-air"></a>空氣的整體流動

會觸發警示，安全性行動手冊會開始進行自動調查，進而會產生結果和建議的動作。 以下是空氣的整體流動流程，逐步執行：

1. 自動調查是以下列其中一種方式啟動：
   - [警示是](#which-alert-policies-trigger-automated-investigations)由電子郵件 (中的可疑專案所觸發，例如郵件、附件、URL 或遭到破壞的使用者帳戶) 。 會建立事件，並開始進行自動調查。或
   - 安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。
2. 當自動調查執行時，它會收集有關電子郵件的相關資訊，以及與該電子郵件相關的實體。 這類實體可以包含檔案、URLs 及收件者。 調查的範圍會隨著新的和相關的提醒觸發而增加。
3. 在自動調查的期間和之後，都可以查看 [詳細資料和結果](air-view-investigation-results.md) 。 結果包括可以採取的 [建議動作](air-remediation-actions.md) ，以回應及修正找到的任何威脅。
4. 您的安全性運作小組會檢查 [調查結果和建議](air-view-investigation-results.md)，並 [批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。
5. 當擱置的修復動作獲批准 (或拒絕) 時，自動調查即完成。

在適用于 Office 365 的 Microsoft Defender 中，不會自動採取任何修正動作。 在組織的安全性小組核准後才能採取補救動作。 AIR 功能可透過識別修正動作來儲存您的安全性運作小組時間，並提供做出明智決定所需的詳細資料。

在每次自動調查期間和之後，您的安全性作業小組可以：

- [檢視與調查相關警示的詳細資料](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [查看調查的結果詳細資料](air-view-investigation-results.md#view-details-of-an-investigation)
- [根據調查的結果檢閱和核准動作](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 如需詳細資訊，請參閱 [AIR 的運作方式](automated-investigation-response-office.md)。

## <a name="how-to-get-air"></a>如何取得空中

AIR 功能包含在 [適用于 Office 365 的 Microsoft Defender](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中，但前提是已設定您的原則及警示。 需要協助嗎？ 遵循 [防範威脅](protect-against-threats.md) 以設定或設定下列保護設定的指導方針：

- 應開啟[審核記錄](../../compliance/turn-audit-log-search-on-or-off.md) () 
- [反惡意程式碼原則](protect-against-threats.md#part-1---anti-malware-protection)
- [Antiphishing 保護](protect-against-threats.md#part-2---anti-phishing-protection)
- [反垃圾郵件保護](protect-against-threats.md#part-3---anti-spam-protection)
- [Antiphishing 保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
- [反垃圾郵件保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)
- [安全連結和安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [電子郵件自動清除零小時](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop)

此外，請務必 [檢查您組織的警示原則](../../compliance/alert-policies.md)，尤其是「 [威脅管理」類別中的預設原則](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>哪些警示原則會觸發自動調查？

Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些預設的 [報警原則](../../compliance/alert-policies.md#default-alert-policies) 可以觸發自動調查。 下表說明觸發自動調查的警示、在 Microsoft 365 安全性中心的嚴重性，以及產生的方式：

|警報|嚴重性|警示的產生方式|
|:---|:---|:---|
|偵測到可能的惡意 URL 按一下|**High**|發生下列任何情況時，就會產生此警示： <ul><li>由組織中 [安全連結](safe-links.md) 所保護的使用者按一下惡意連結</li><li>URLs 的判定變更是由 Microsoft Defender for Office 365 所識別</li><li>根據組織的 [安全連結原則](set-up-safe-links-policies.md)) ，使用者會覆寫安全連結警告頁面 (。</li></ul> <p> 如需觸發此警示之事件的詳細資訊，請參閱 [設定安全連結原則](set-up-safe-links-policies.md)。|
|使用者報告電子郵件訊息為惡意程式碼或網路釣魚網路|**資訊**|當您組織中的使用者使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)，將郵件報告為網路釣魚電子郵件時，就會產生此警示。|
|傳遞後移除包含惡意程式碼的電子郵件|**資訊**|當包含惡意程式碼的電子郵件訊息傳送至組織中的信箱時，就會產生此警示。 如果發生此事件，Microsoft 會使用 [零小時自動清除](zero-hour-auto-purge.md)，從 Exchange Online 信箱移除染毒郵件。|
|傳遞後移除包含網路釣魚 URLs 的電子郵件|**資訊**|當包含網路釣魚的任何郵件傳送至您組織中的信箱時，就會產生此警示。 如果發生此事件，Microsoft 會使用 [零小時自動清除](zero-hour-auto-purge.md)，從 Exchange Online 信箱移除染毒郵件。|
|偵測到可疑的電子郵件寄送模式|**Medium**|當貴組織中的某人傳送了可疑的電子郵件，並有限制傳送電子郵件的風險時，就會產生此警示。 警示是針對可能表示帳戶已受損，但不足以限制使用者之行為的早期警告。 <p> 雖然這種情況很少見，但由此原則產生的警示可能是反常的。 不過，最好 [檢查使用者帳戶是否受損](responding-to-a-compromised-email-account.md)。|
|限制使用者傳送電子郵件|**High**|當您組織中的人員限制傳送輸出郵件時，就會產生此警示。 此提醒通常 [會在電子郵件帳戶遭到破壞](responding-to-a-compromised-email-account.md)時產生結果。 <p> 如需有關限制使用者的詳細資訊，請參閱 [從 Microsoft 365 中的受限使用者入口網站移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)。|
|

> [!TIP]
> 若要深入瞭解報警原則或編輯預設設定，請參閱 [Microsoft 365 規範中心的警示原則](../../compliance/alert-policies.md)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用 AIR 功能所需的許可權

許可權是透過特定角色授與的，如下表所述：

|工作|需要) 角色 (|
|---|---|
|設定 AIR 功能|下列其中一個角色： <ul><li>全域系統管理員</li><li>安全性系統管理員</li></ul> <p> 您可以在 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](permissions-in-the-security-and-compliance-center.md)指派這些角色。|
|開始自動調查 <p> --- 或 --- <p> 核准或拒絕建議的動作|在 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](permissions-in-the-security-and-compliance-center.md)內指派的下列其中一個角色： <ul><li>全域系統管理員</li><li>安全性系統管理員</li><li>安全性操作員</li><li>安全性讀取者 <br> --- 且 --- </li><li>搜尋和清除 (此角色只會指派在 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md)。 您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。</li></ul>|

## <a name="required-licenses"></a>必要的授權

[Microsoft Defender For Office 365 方案 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 授權應指派給：

- 安全性管理員 (包括全域管理員) 
- 組織的安全性運作小組 (包括安全性讀者和具有 **搜尋和清除** 角色的使用者) 
- 使用者


## <a name="changes-are-coming-soon-in-your-security-center"></a>您的安全性中心即將推出變更

如果您已在 Microsoft Defender for Office 365 中使用 AIR 功能，您就會看到 [改進的 Microsoft 365 安全性中心](../defender/overview-security-center.md)的一些變更。 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="整合的動作中心":::

新的和改善的安全性中心會在 [Microsoft defender For Office 365](defender-for-office-365.md) 和 [Microsoft defender for Endpoint](../defender-endpoint/automated-investigations.md)中共同提供 AIR 功能。 有了這些更新與改善功能，您的安全性作業小組就能在單一位置檢視電子郵件、共同作業內容、使用者帳戶和裝置上的自動化調查和補救動作的詳細資訊。

> [!TIP]
> 新的 Microsoft 365 安全性中心 (<https://security.microsoft.com>) 會取代下列的中心：
>
> - Office 365 的安全性 & 規範中心 (<https://protection.office.com>) 
> - Microsoft Defender Security Center (<https://securitycenter.windows.com>) 
>
> 除了 URL 變更之外，還有一個全新的外觀與風格，其設計目的是讓您的安全性小組獲得更簡化的體驗，並在一個位置看到更多威脅偵測。

### <a name="what-to-expect"></a>預期的專案

下表列出 Microsoft Defender for Office 365 中的空氣變更與改進功能。

|項目|變更的內容為何？|
|---|---|
|**調查** 頁面|「更新 **調查** 」頁面與您在 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中所看到的一致。 您將會看到一些與新的整合 **調查** 視圖相符的一般格式和樣式變更。 例如，調查圖表會有更統一的格式。|
|**使用者** ] 索引標籤|[ **使用者** ] 索引標籤現在是 [ **信箱** ] 索引標籤。[ **信箱** ] 索引標籤上會列出使用者的詳細資料。|
|**電子郵件** ] 索引標籤|已移除 [ **電子郵件** ] 索引標籤;請造訪 [ **實體** ] 索引標籤，以查看電子郵件和電子郵件叢集專案的清單。|
|**實體** ] 索引標籤|[ **實體** ] 索引標籤具有 tab 鍵] 索引標籤的樣式，其中包含所有摘要視圖，以及按實體類型篩選的功能。 除了 [**在瀏覽器中開啟**] 選項之外，[**實體**] 索引標籤現在還包括「**移搜尋**」選項。 您現在可以使用 [威脅瀏覽器](threat-explorer.md) 或 [高級搜尋](../defender-endpoint/advanced-hunting-overview.md) 來尋找實體和威脅，並篩選結果。|
|**動作** ] 索引標籤|[更新的 **動作** ] 索引標籤現在包含 [ **暫止動作** ] 索引標籤和 [ **動作記錄** ] 索引卷您可以在選取暫止動作時開啟的側邊窗格中，核准 (或拒絕動作) 。|
|**證據** ] 索引標籤|新的 [ **證據** ] 索引標籤會顯示與動作相關的主要實體調查結果。 您可以在選取暫止動作時所開啟的側邊窗格中，核准 (或拒絕相關的每個證據的動作) 。|
|**控制中心**|更新的 **操作中心** ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 會在電子郵件、裝置和身分識別間，將擱置和完成的動作組合在一起。 若要深入瞭解，請參閱動作中心。  (若要深入瞭解，請參閱 [操作中心](https://docs.microsoft.com/microsoft-365/security/defender/mtp-action-center)。 ) 
|**事件** 頁面|[ **事件** ] 頁面現在可將多項調查與多項調查進行關聯，以提供更佳的調查觀點。  ([深入瞭解事件](https://docs.microsoft.com/microsoft-365/security/defender/incidents-overview)。 ) 


## <a name="next-steps"></a>後續步驟

- [查看自動調查的詳細資料和結果](air-view-investigation-results.md#view-details-of-an-investigation)
- [審閱及核准擱置的動作](air-remediation-actions.md)