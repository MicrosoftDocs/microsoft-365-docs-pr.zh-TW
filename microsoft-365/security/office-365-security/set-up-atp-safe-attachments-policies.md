---
title: 設定 Office 365 ATP 安全附件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 瞭解如何定義安全附件原則，以利用電子郵件中的惡意檔來保護組織。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d826cb6e0dd4370a1e02722901d083d4f021e2b4
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588117"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>設定 Office 365 ATP 安全附件原則

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您是家用版使用者且正在尋找 Outlook 中安全附件的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。 只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。 最糟糕的就是打開惡意附件，讓您的組織遭受重大災害。 幸好，[Office 365 進階威脅防護](office-365-atp.md) (ATP) 幫得上忙。 您可以設定 [ATP 安全附件](atp-safe-attachments.md)原則，協助確保您組織不會因為不安全的電子郵件附件而遭到攻擊。

## <a name="what-to-do"></a>處理方式

1. 檢閱必要條件

2. 設定 ATP 安全附件原則

3. 了解 ATP 安全附件原則選項

## <a name="step-1-review-the-prerequisites"></a>步驟 1：檢閱必要條件

- 請確認您組織有 [Office 365 進階威脅防護](office-365-atp.md)。

- 請確定您具有必要權限。 若要定義（或編輯） ATP 原則，您必須被指派 Exchange Online 組織管理角色（預設為全域管理員指派此角色）或 Exchange Online 衛生管理與安全性管理員角色。 如需詳細資訊，請參閱下表：

  |角色|指派位置/條件|
  |---------|---------|
  |全域管理員 |簽署購買 Microsoft 365 的人員預設為全域系統管理員。 （請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)以深入瞭解。）|
  |安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
  |Exchange Online 組織管理，Exchange Online 的清理管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|
  |

  若要深入瞭解角色和許可權，請參閱[安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

- [了解 ATP 安全附件原則選項](#step-3-learn-about-atp-safe-attachments-policy-options) (在本文中)。 某些選項 (例如監視或取代選項) 可能會造成電子郵件延遲，因為要掃描附件。 若要避免郵件延遲，請考慮使用[動態傳遞和預覽](dynamic-delivery-and-previewing.md)。

- 最多可允許30分鐘，以將新的或更新的原則散佈至所有 Microsoft 365 資料中心。

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>步驟 2：設定 (或編輯) ATP 安全附件原則

1. 移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。

2. 在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [**威脅管理**] 底下的 [**原則** \> **安全附件**]。

3. 如果您看到 [開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP]****，我們建議您選取此選項。 這將為您的 Microsoft 365 環境啟用[SharePoint、OneDrive 和 Microsoft 小組的 Office 365 高級威脅防護](atp-for-spo-odb-and-teams.md)。

4. 選擇 [新增]**** \([新增] 按鈕類似加號 (**+**))，以開始建立您的原則。

5. 指定原則的名稱、描述及設定。<br/><br/>**範例：** 若要設定名為「無延遲」的原則，以便立即傳送所有人的郵件，然後在其經過掃描之後重新附加附件，您可以指定下列設定：

   - 在 [名稱]**** 方塊中輸入「無延遲」。

   - 在 [描述]**** 方塊中輸入您的描述，例如 [立即傳送郵件並在掃描後重新附加附件]。

   - 在 [回復] 區段中，選擇 [動態傳遞]**** 選項。 ([深入了解 ATP 安全附件的動態傳遞和預覽](dynamic-delivery-and-previewing.md)。)

   - 在 [重新**導向附件**] 區段中，選取 [啟用重新導向] 選項，然後輸入您的全域系統管理員、安全性管理員或將調查惡意附件的安全性分析員的電子郵件地址。

   - 在 [套用至]**** 區段中，選擇 [收件者網域]****，然後選取您的網域。 選擇 [新增]****，然後選擇 [確認]****。

6. 選擇 [儲存]****。

考慮為您的組織設定多個 ATP 安全附件原則。 這些原則會按照其在 **ATP 安全附件**頁面中的順序套用。 在定義或編輯原則之後，至少需 30 分鐘的時間，原則才能在整個 Microsoft 資料中心內生效。

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>步驟 3：了解 ATP 安全附件原則選項

當您設定 ATP 安全附件原則時，您可以從許多選項中選擇，包括監視、封鎖、取代和動態傳遞等等。 如果您想知道這些選項的功能，下表中有每個選項及其效用的摘要。

||||
|---|---|---|
|**選項**|****|**使用時機：**|
|**關閉**|不掃描附件的惡意程式碼  <br/> 不會延遲郵件傳遞|針對只傳送已知的良好附件的掃描器、傳真或智慧主機，關閉掃描功能  <br/> 避免路由內部郵件的非必要延遲。  <br/> **我們不建議大多數使用者採用此選項。您應只使用此選項，關閉一小小群組的信任寄件者的 ATP 安全附件掃描。**|
|**監視**|傳送含有附件的郵件，然後追蹤偵測到的惡意程式碼會發生什麼情況|查看偵測到的惡意程式碼會在組織中哪個位置|
|**封鎖**|防止偵測到惡意程式碼附件的郵件繼續進行  <br/> 將偵測到惡意程式碼的郵件傳送到 [Office 365 中的隔離區](manage-quarantined-messages-and-files.md)，安全性系統管理員或分析者可以在此檢視並釋放 (或刪除) 這些郵件  <br/> 自動封鎖未來的郵件和附件|避免組織遭受相同惡意程式碼附件的重複攻擊|
|**取代**|移除偵測到的惡意程式碼附件  <br/> 通知收件者附件已移除  <br/> 將偵測到惡意程式碼的郵件傳送到 [Office 365 中的隔離區](manage-quarantined-messages-and-files.md)，安全性系統管理員或分析者可以在此檢視並釋放 (或刪除) 這些郵件|提高收件者看到附件因為偵測到惡意程式碼而遭移除的可能性|
|**動態傳遞**|立即傳送郵件  <br/> 將附件取代為預留檔案，直到掃描完成，然後在未偵測到惡意程式碼的情況下重新附加附件  <br/> 掃描期間會保留大部分 PDF 和 Office 檔案的預覽功能  <br/> 將偵測到惡意程式碼的郵件傳送到隔離區，安全性系統管理員或分析者可以在此檢視並釋放 (或刪除) 這些郵件  <br/> [了解 ATP 安全附件的動態傳遞和預覽](dynamic-delivery-and-previewing.md) <br/> |避免郵件延遲，同時為收件者抵禦惡意檔案  <br/> 執行掃描時，讓收件者以安全模式預覽附件|
|**啟用重新導向**|當選取 [監視]、[封鎖] 或 [取代] 選項時套用  <br/> 將附件傳送到安全性系統管理員或分析者可以查看的特定電子郵件地址|讓安全性系統管理員和分析者調查可疑附件|
|**如果惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。**|將不安全附件所設定的動作套用至無法掃描的附件（由於超時或錯誤）|
|

## <a name="next-steps"></a>後續步驟

當您的 ATP 安全附件原則就緒之後，您就可以藉由檢視報告，了解 ATP 如何為您的組織運作。 請參閱下列資源，以深入了解詳細資訊：

- [檢視 Office 365 進階威脅防護的報告](view-reports-for-atp.md)

- [使用安全性與合規性中心中的 Explorer](threat-explorer.md)

隨時掌握最新的 ATP 功能。 瀏覽 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)，並了解[即將新增至 ATP 的新功能](office-365-atp.md#new-features-in-office-365-atp)。
