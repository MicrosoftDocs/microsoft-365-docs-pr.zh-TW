---
title: 回應 Office 365 中遭入侵的電子郵件帳戶
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何辨識及回應 Office 365 中遭入侵的電子郵件帳戶
ms.openlocfilehash: 3aa8be9b53f2aa8f3fc6bf64744b36de5d912645
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598600"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>回應 Office 365 中遭入侵的電子郵件帳戶

**摘要** 了解如何辨識及回應 Office 365 中遭入侵的電子郵件帳戶。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什麼是 Office 365 中遭入侵的電子郵件帳戶？

對 Office 365 信箱、資料和其他服務的存取，是透過使用使用者名稱和密碼或 PIN 之類的認證來控制。 當預期使用者以外的其他人竊取這些認證時，遭竊的認證會被視為遭入侵。 攻擊者可以使用這些認證以原始使用者身分登入，並執行非法動作。
攻擊者可以使用遭竊的認證來存取使用者的 Office 365 信箱、SharePoint 資料夾或使用者 OneDrive 中的檔案。 一個常見的動作是攻擊者以原始使用者的身分傳送電子郵件給組織內外的收件者。 當攻擊者以電子郵件寄送資料給外部收件者時，這稱為資料外流。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>遭入侵的 Office 365 電子郵件帳戶症狀

使用者可能會注意到並報告其 Office 365 信箱中的異常活動。 以下是一些常見的症狀：

- 可疑的活動，例如遺失或刪除的電子郵件。

- 其他使用者可能會收到來自遭入侵帳戶的電子郵件，該帳戶寄件者的 [寄件備份]**** 資料夾中不存在對應的電子郵件。

- 出現不是由預期使用者或系統管理員所建立的收件匣規則。 這些規則可能會自動將電子郵件轉寄到未知的地址，或將電子郵件移到 [記事]****、[垃圾郵件]**** 或 [RSS 訂閱]**** 資料夾。

- 全域通訊清單中使用者的顯示名稱可能會變更。

- 使用者的信箱遭封鎖而無法傳送電子郵件。

- 在 Microsoft Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 中的 [寄件備份] 或 [刪除的郵件] 資料夾包含常見遭入侵帳戶的郵件，例如「我卡在倫敦了，給我錢」。

- 異常的個人資料變更，例如名稱、電話號碼或郵遞區號已更新。

- 異常的認證變更，例如要求變更密碼多次。

- 最近新增郵件轉寄。

- 最近新增異常的簽章，例如假銀行簽章或處方藥簽章。

如果使用者報告上述的任何症狀，則應該執行進一步調查。 Microsoft 365 安全性與合規性中心和 Azure 入口網站會提供工具，以協助您調查您懷疑可能遭入侵之使用者帳戶的活動。

- **安全性與合規性中心的 Office 365 整合稽核記錄**：檢閱可疑帳戶的所有活動，方法是篩選日期範圍自發生可疑活動之前到目前日期的結果。 請勿在搜尋期間篩選活動。

- **EAC 中的 Office 365 系統管理員稽核記錄**：在 Exchange Online 中，您可以使用 Exchange 系統管理中心 (EAC) 來搜尋及檢閱系統管理員稽核記錄中的項目。 系統管理員稽核記錄會根據 Exchange Online PowerShell Cmdlet 記錄由系統管理員以及已被指派系統管理權限的使用者所執行的特定動作。 系統管理員稽核記錄中的項目會提供執行的 Cmdlet、使用的參數、Cmdlet 的執行者，以及受影響的物件的相關資訊。

- **Azure AD 入口網站中的 Azure AD 登入記錄檔和其他風險報告**：檢查這些欄中的值：

  - 檢閱 IP 位址

  - 登入位置

  - 登入時間

  - 登入成功或失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保護並將電子郵件功能還原到可疑的遭入侵 Office 365 帳戶和信箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使是在您重新取得帳戶的存取權之後，攻擊者可能已新增後門程式項目，使得攻擊者得以繼續控制該帳戶。

您必須執行下列所有步驟來重新取得帳戶的存取權，愈快愈好，以確保劫持者不會繼續控制您的帳戶。 這些步驟可協助您移除劫持者可能已新增至您的帳戶的任何後門程式項目。 在您執行這些步驟之後，建議您執行病毒掃描，以確認您的電腦未遭入侵。

### <a name="step-1-reset-the-users-password"></a>步驟 1 重設使用者的密碼

> [!WARNING]
> 請勿透過電子郵件傳送新密碼給預期的使用者，因為攻擊者此時仍可能對信箱具有存取權。

1. 遵循[重設 Office 365 商務版密碼](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)中為其他人重設 Office 365 商務版密碼的程序

**附註**：

- 請確定密碼為強式密碼，且包含大寫和小寫字母、至少一個數字，以及至少一個特殊字元。

- 請勿重複使用最後五個密碼。 即使密碼歷程記錄需求可讓您重複使用較新的密碼，您也應該選取攻擊者無法猜測的項目。

- 如果您的內部部署身分識別與 Office 365 同盟，則必須變更您的內部部署密碼，然後必須通知您的系統管理員相關入侵。

> [!TIP]
> 我們強烈建議您啟用多重要素驗證 (MFA)，以防止入侵，特別是具有系統管理權限的帳戶。  您可以在[這裡](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)深入了解 MFA。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步驟 2 移除可疑的電子郵件轉寄地址

1. 開啟 [Microsoft 365 系統管理中心] > [作用中的使用者]****。

2. 找出有問題的使用者帳戶，並展開 [郵件設定]****。

3. 針對 [電子郵件轉寄]****，按一下 [編輯]****。

4. 移除任何可疑的轉寄地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步驟 3 停用任何可疑的收件匣規則

1. 使用 Outlook 網頁版登入使用者的信箱。

2. 按一下齒輪圖示並按一下 [郵件]****。

3. 按一下 [收件匣和整理規則]**** 並檢閱規則。

4. 停用或刪除可疑的規則。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步驟 4 解除封鎖使用者，使其可以傳送郵件

如果懷疑遭入侵的信箱被非法用來傳送垃圾郵件，則可能是該信箱已被封鎖無法傳送郵件。

若要解除封鎖信箱，使其可以傳送郵件，請遵循[傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者](removing-user-from-restricted-users-portal-after-spam.md)中的程序。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步驟 5 選用：封鎖使用者帳戶，使其無法登入

> [!IMPORTANT]
> 您可以封鎖懷疑遭入侵的帳戶，使該帳戶無法登入，直到您認為可以安全地重新啟用存取權為止。

1. 移至 Microsoft 365 系統管理中心。

2. 在 Microsoft 365 系統管理中心，選取 [使用者]****。

3. 選取要封鎖的員工，然後在使用者窗格中選擇 [登入狀態]**** 旁邊的 [編輯]****。

4. 在 [登入狀態]**** 窗格上，選擇 [封鎖登入]****，然後選擇 [儲存]****。

5. 在系統管理中心的左下方瀏覽窗格中，展開 [系統管理中心]****，然後選取 [Exchange]****。

6. 在 Exchange 系統管理中心中，瀏覽到 [收件者] > [信箱]****。

7. 選取使用者，然後在使用者屬性頁面的 [行動裝置]**** 底下，按一下 [停用 Exchange ActiveSync]**** 和 [停用裝置用 OWA]****，並且對這兩個選項都回答 [是]****。

8. 在 [電子郵件連線]**** 底下，按一下 [停用]****，然後回答 [是]****。

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步驟 6 選用：從所有系統管理角色群組移除懷疑遭入侵的帳戶

> [!NOTE]
> 保護的帳戶之後，就可以還原系統管理角色群組的成員資格。

1. 使用全域系統管理員帳戶登入 Microsoft 365 系統管理中心，然後開啟 [作用中使用者]****。

2. 找出懷疑遭入侵的帳戶，並手動檢查以查看是否有對給該帳戶指派任何系統管理角色。

3. 開啟 [安全性與合規性中心]****。

4. 按一下 [權限]****。

5. 手動檢查角色群組，以查看懷疑遭入侵的帳戶是否為任何群組的成員。  如果是：

   a. 按一下角色群組，然後按一下 [編輯角色群組]****。

   b. 按一下 [選擇成員]**** 和 [編輯]****，從角色群組移除使用者。

6. 開啟 [Exchange 系統管理中心]****。

7. 按一下 [權限]****。

8. 手動檢查角色群組，以查看懷疑遭入侵的帳戶是否為任何群組的成員。 如果是：

   a. 按一下角色群組，然後按一下 [編輯]****。

   b. 使用 [成員]**** 區段，從角色群組移除該使用者。

### <a name="step-7-optional-additional-precautionary-steps"></a>步驟 7 選用：額外的預防步驟

1. 務必確認您所傳送的項目。 您可能需要通知您的連絡人清單上的人員，您的帳戶已遭入侵。 攻擊者可能會要求他們給予金錢，比方說騙他們說您滯留在不同國家/地區因而缺錢，或是攻擊者也可能傳送病毒給他們來劫持電腦。

2. 使用此 Exchange 帳戶作為其備用電子郵件帳戶的任何其他服務可能已遭入侵。 先為您的 Office 365 訂閱執行下列步驟，然後再為您的其他帳戶執行這些步驟。

3. 確認您的連絡資訊，例如電話號碼及地址，是正確的。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Office 365

您的 Office 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。  使用 [Office 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Office 365 租用戶的最佳做法。

- 要在前 30 天內完成的工作。  這些工作會有立即的影響，而且對您的使用者影響較低。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>另請參閱

- [偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)

- [網際網路犯罪客訴中心](https://www.ic3.gov/preventiontips.aspx)

- [美國證券交易委員會 -「網路釣魚」詐騙](https://www.sec.gov/investor/pubs/phishing.htm)

- 若要直接向 Microsoft 和您的系統管理員檢舉垃圾郵件，[請使用檢舉訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
