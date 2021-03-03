---
title: 回應遭入侵的電子郵件帳戶
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用可用工具辨識及回應 Microsoft 365 中遭入侵的電子郵件帳戶。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5dfb40c195cb9df9c8f2ac5d1cfbacdda022d416
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406721"
---
# <a name="responding-to-a-compromised-email-account"></a>回應遭入侵的電子郵件帳戶

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**摘要** 了解如何辨識及回應 Microsoft 365 中遭入侵的電子郵件帳戶。

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>什麼是 Microsoft 365 中遭入侵的電子郵件帳戶？

對 Microsoft 365 信箱、資料和其他服務的存取，是透過使用使用者名稱和密碼或 PIN 之類的認證來控制。 當預期使用者以外的其他人竊取這些認證時，遭竊的認證會被視為遭入侵。 攻擊者可以使用這些認證以原始使用者身分登入，並執行非法動作。
攻擊者可以使用遭竊的認證來存取使用者的 Microsoft 365 信箱、SharePoint 資料夾或使用者 OneDrive 中的檔案。 一個常見的動作是攻擊者以原始使用者的身分傳送電子郵件給組織內外的收件者。 當攻擊者以電子郵件寄送資料給外部收件者時，這稱為資料外流。

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>遭入侵的 Microsoft 電子郵件帳戶症狀

使用者可能會注意到並報告其 Microsoft 365 信箱中的異常活動。 以下是一些常見的症狀：

- 可疑的活動，例如遺失或刪除的電子郵件。

- 其他使用者可能會收到來自遭入侵帳戶的電子郵件，該帳戶寄件者的 [寄件備份] 資料夾中不存在對應的電子郵件。

- 出現不是由預期使用者或系統管理員所建立的收件匣規則。 這些規則可能會自動將電子郵件轉寄到未知的地址，或將電子郵件移到 [記事]、[垃圾郵件] 或 [RSS 訂閱] 資料夾。

- 全域通訊清單中使用者的顯示名稱可能會變更。

- 使用者的信箱遭封鎖而無法傳送電子郵件。

- 在 Microsoft Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 中的 [寄件備份] 或 [刪除的郵件] 資料夾包含常見遭入侵帳戶的郵件，例如「我卡在倫敦了，給我錢」。

- 異常的個人資料變更，例如名稱、電話號碼或郵遞區號已更新。

- 異常的認證變更，例如要求變更密碼多次。

- 最近新增郵件轉寄。

- 最近新增異常的簽章，例如假銀行簽章或處方藥簽章。

如果使用者報告上述的任何症狀，則應該執行進一步調查。 Microsoft 365 安全性與合規性中心和 Azure 入口網站會提供工具，以協助您調查您懷疑可能遭入侵之使用者帳戶的活動。

- **安全性與合規性中心的 整合稽核記錄**：檢閱可疑帳戶的所有活動，方法是篩選日期範圍自發生可疑活動之前到目前日期的結果。 請勿在搜尋期間篩選活動。

- **EAC 中的系統管理員稽核記錄**：在 Exchange Online 中，您可以使用 Exchange 系統管理中心 (EAC) 來搜尋及檢閱系統管理員稽核記錄中的項目。 系統管理員稽核記錄會根據 Exchange Online PowerShell Cmdlet 記錄由系統管理員以及已被指派系統管理權限的使用者所執行的特定動作。 系統管理員稽核記錄中的項目會提供執行的 Cmdlet、使用的參數、Cmdlet 的執行者，以及受影響的物件的相關資訊。

- **Azure AD 入口網站中的 Azure AD 登入記錄檔和其他風險報告**：檢查這些欄中的值：

  - 檢閱 IP 位址
  - 登入位置
  - 登入時間
  - 登入成功或失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>如何保護並將電子郵件功能還原到可疑的遭入侵 Microsoft 365 帳戶和信箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使是在您重新取得帳戶的存取權之後，攻擊者可能已新增後門程式項目，使得攻擊者得以繼續控制該帳戶。

您必須執行下列所有步驟來重新取得帳戶的存取權，愈快愈好，以確保劫持者不會繼續控制您的帳戶。 這些步驟可協助您移除劫持者可能已新增至您的帳戶的任何後門程式項目。 在您執行這些步驟之後，建議您執行病毒掃描，以確認您的電腦未遭入侵。

### <a name="step-1-reset-the-users-password"></a>步驟 1 重設使用者的密碼

遵循[重設某人的商務密碼](../../admin/add-users/reset-passwords.md#reset-my-admin-password)中的程序進行。

> [!IMPORTANT]
>
> - 請勿透過電子郵件傳送新密碼給預期的使用者，因為攻擊者此時仍可能對信箱具有存取權。
>
> - 請確定密碼為強式密碼，且包含大寫和小寫字母、至少一個數字，以及至少一個特殊字元。
>
> - 請勿重複使用最後五個密碼。 即使密碼歷程記錄需求可讓您重複使用較新的密碼，您也應該選取攻擊者無法猜測的項目。
>
> - 如果您的內部部署身分識別與 Microsoft 365 同盟，則必須變更您的內部部署密碼，然後必須通知您的系統管理員相關入侵。
>
> - 務必更新應用程式密碼。 使用者帳戶密碼重設時，應用程式密碼未自動撤銷。 使用者應該刪除現有的應用程式密碼，並建立新密碼。 如需指示，請參閱[從其他安全性驗證頁面建立和刪除應用程式密碼](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)。
>
> - 我們強烈建議您啟用多重要素驗證 (MFA)，以防止入侵，特別是具有系統管理權限的帳戶。 若要深入了解 MFA，請至 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步驟 2 移除可疑的電子郵件轉寄地址

1. 開啟位於 <https://admin.microsoft.com> 的 Microsoft 365 系統管理中心

2. 移至 [使用者 **]** \> [作用中使用者 **]**。 尋找發生問題的使用者帳戶，並選取使用者 (列) 而不選取核取方塊。

3. 在顯示的詳細資料飛出視窗中，選取 [郵件 **]** 索引標籤。

4. 如果 [電子郵件轉寄 **]** 區段中的值為 [己套用 **]**，請按一下 [管理電子郵件轉寄 **]**。 在顯示的 [管理電子郵件轉寄 **]** 飛出視窗中，清除 [轉寄所有傳送到此信箱的電子郵件 **]**，然後按一下 [儲存變更 **]**。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步驟 3 停用任何可疑的收件匣規則

1. 使用 Outlook 網頁版登入使用者的信箱。

2. 按一下齒輪圖示並按一下 [郵件]。

3. 按一下 [收件匣和整理規則] 並檢閱規則。

4. 停用或刪除可疑的規則。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步驟 4 解除封鎖使用者，使其可以傳送郵件

如果懷疑遭入侵的信箱被非法用來傳送垃圾郵件，則可能是該信箱已被封鎖無法傳送郵件。

若要解除封鎖信箱，使其可以傳送郵件，請遵循[傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者](removing-user-from-restricted-users-portal-after-spam.md)中的程序。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步驟 5 選用：封鎖使用者帳戶，使其無法登入

> [!IMPORTANT]
> 您可以封鎖懷疑遭入侵的帳戶，使該帳戶無法登入，直到您認為可以安全地重新啟用存取權為止。

1. 開啟 Microsoft 365 系統管理中心，然後移至 [使用者 **]** \> [作用中使用者 **]**。

2. 尋找並選取使用者帳戶，按一下 [更多圖示![]](../../media/ITPro-EAC-MoreOptionsIcon.png)，然後選取 [編輯登入狀態 **]**。

3. 在顯示的 **[封鎖登入]** 窗格中，選取 **[封鎖此使用者，使其無法登入]**，然後按一下 **[儲存變更]**。

4. 開啟位於 <admin.protection.outlook.com/ecp/> 的 Exchange 系統管理中心 (EAC)，然後移至 [收件者] > [信箱 **]**。

5. 尋找並選取使用者。 在詳細資料窗格中，執行下列步驟：

   - 在 [電話和語音功能 **]** 區段中，執行下列步驟：

     - 選取 [停用 Exchange ActiveSync **]**，然後按一下顯示的警告中的 [是 **]**。
     - 選取 [停用裝置用 OWA **]**，然後按一下顯示的警告中的 [是 **]**。

   - 在 Outlook 網頁版的 [電子郵件連線 **]** 區段中，按一下 [停用 **]**，然後按一下顯示的警告中的 [是 **]**。

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步驟 6 選用：從所有系統管理角色群組移除懷疑遭入侵的帳戶

> [!NOTE]
> 保護的帳戶之後，就可以還原系統管理角色群組的成員資格。

1. 使用全域系統管理員帳戶登入：

2. 在 Microsoft 365 系統管理中心，執行下列步驟：

   1. 移至 [使用者 **]** \> [作用中使用者 **]**。
   2. 尋找並選取使用者帳戶，按一下 [更多圖示![]](../../media/ITPro-EAC-MoreOptionsIcon.png)，然後選取 [管理角色 **]**。
   3. 移除指派給帳戶的任何系統管理角色。 完成後，按一下 [儲存變更 **]**。

3. 在位於 <https://protection.office.com> 的安全性與合規性中心，執行下列步驟：

   選取 [權限 **]**，選取清單中的每個角色群組，並在顯示的詳細資料飛出視窗的 [成員 **]** 區段中尋找該使用者帳戶。 如果角色群組包含該使用者帳戶，請執行下列步驟：

   a. 按一下 [成員 **]** 旁的 [編輯 **]**。
   b. 顯示的飛出視窗上的 [編輯選擇成員 **]**，按一下 [編輯 **]**。
   c. 在顯示的 [選擇成員 **]** 飛出視窗中，選取該使用者帳戶，然後按一下 [移除 **]**。 完成時，依序按一下 [完成 **]** 和 [儲存 **]**，然後按一下 [關閉 **]**。

4. 在位於 <admin.protection.outlook.com/ecp/> 的 EAC 中，執行下列步驟：

   選取 [權限 **]**，手動選取每個角色群組，然後在詳細資料窗格中，在 [成員 **]** 區段中驗證使用者帳戶。  如果角色群組包含該使用者帳戶，請執行下列步驟：

   a. 選取角色群組，按一下 [編輯 **]** ![編輯圖示](../../media/ITPro-EAC-EditIcon.png)。
   b. 在 [成員 **]** 區段中，選取該使用者帳戶，然後按一下 [移除 **]** ![移除圖示](../../media/ITPro-EAC-RemoveIcon.gif)。 完成後，按一下 [儲存 **]**。

### <a name="step-7-optional-additional-precautionary-steps"></a>步驟 7 選用：額外的預防步驟

1. 務必確認您所傳送的項目。 您可能需要通知您的連絡人清單上的人員，您的帳戶已遭入侵。 攻擊者可能會要求他們給予金錢，比方說騙他們說您滯留在不同國家/地區因而缺錢，或是攻擊者也可能傳送病毒給他們來劫持電腦。

2. 使用此 Exchange 帳戶作為其備用電子郵件帳戶的任何其他服務可能已遭入侵。 先為您的 Microsoft 365 訂閱執行下列步驟，然後再為您的其他帳戶執行這些步驟。

3. 確認您的連絡資訊，例如電話號碼及地址，是正確的。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Microsoft 365

您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。  使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。

- 要在前 30 天內完成的工作。  這些工作會有立即的影響，而且對您的使用者影響較低。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>請參閱

- [偵測並修復 Microsoft 365 中 Outlook 規則與自訂表單插入式攻擊](detect-and-remediate-outlook-rules-forms-attack.md)

- [網際網路犯罪客訴中心](https://www.ic3.gov/Home/Ransomware)

- [美國證券交易委員會 -「網路釣魚」詐騙](https://www.sec.gov/investor/pubs/phishing.htm)

- 若要直接向 Microsoft 和您的系統管理員檢舉垃圾郵件，[請使用檢舉訊息增益集](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
