---
title: 從限制的使用者入口網站中移除封鎖的使用者
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何從 Microsoft 365 Defender 入口網站中的 [限制的使用者] 頁面移除使用者。 使用者因為傳送輸出垃圾郵件而被新增至 [限制的使用者] 入口網站，通常是因為帳戶遭入侵。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082849"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>從 Microsoft 365 中限制的使用者入口網站移除封鎖的使用者

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果使用者超過[服務限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[輸出垃圾郵件](configure-the-outbound-spam-policy.md)原則中所指定的輸出傳送限制之一，系統就會限制使用者傳送電子郵件，但他們仍可接收電子郵件。

使用者會被新增至 Microsoft 365 Defender 入口網站中的 [限制的使用者 **]** 頁面。 當他們嘗試傳送電子郵件時，系統會以未傳遞回報 (又稱為 NDR 或退回的郵件) 傳回郵件，並包含錯誤碼 [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和下列文字：

> 「因為您不是認可的有效寄件者，所以無法傳遞您的郵件。 最有可能發生此狀況的原因是您的電子郵件地址有傳送垃圾郵件的嫌疑，因此系統已不允許此電子郵件地址傳送電子郵件。  請連絡您的電子郵件系統管理員以取得協助。 遠端伺服器傳回 ‘550 5.1.8 存取被拒，錯誤的外寄寄件者。’」

系統管理員可以從 Microsoft 365 Defender 中的 [限制的使用者] 頁面或在 Exchange Online PowerShell 中移除使用者。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [限制的使用者 **]** 頁面，請使用 <https://security.microsoft.com/restrictedusers>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要從限制的使用者入口網站移除使用者，您必須是 **組織管理** 或 **安全性系統管理員** 角色群組的成員。
  - 若要以唯讀方式存取限制的使用者入口網站，您必須是 **全域讀取者** 或 **安全性讀取者** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 超過外寄電子郵件限制的寄件者是遭入侵帳戶的指標。 從限制的使用者入口網站移除使用者之前，請務必遵循所需的步驟重新取得該帳戶的控制權。 如需詳細資訊，請參閱[回應 Office 365 中遭入侵的電子郵件帳戶](responding-to-a-compromised-email-account.md)。

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>使用 Microsoft 365 Defender 入口網站從限制的使用者清單中移除使用者

1. 在 Microsoft 365 Defender 入口網站中，移至 [電子郵件與共同作業 **]**  >  [檢閱 **]**  >  [限制的使用者 **]**。

2. 在 [限制的使用者 **]** 頁面上，按一下使用者，以尋找並選取您要解除封鎖的使用者。

3. 按一下出現的 [解除封鎖 **]** 動作。

4. 在出現的 [解除封鎖使用者 **]** 飛出視窗中，閱讀有關該限制帳戶的詳細資料。 您必須逐一查看建議，以確保帳戶遭入侵時，您會採取適當的動作。

   完成後，按 [下一步 **]**。

5. 下一個畫面提供建議來協助避免未來的入侵。 啟用多重要素驗證 (MFA) 並重設密碼，是良好的防禦方式。

   完成後，按一下 [提交 **]**。

6. 按一下 **[是]** 以確認變更。

   > [!NOTE]
   > 從使用者移除所有限制最多可能需要 24 小時的時間。

## <a name="verify-the-alert-settings-for-restricted-users"></a>確認受限使用者的提醒設定

當系統封鎖使用者傳送電子郵件時，預設的警示原則 **無法傳送電子郵件的受限使用者** 會自動通知系統管理員。 您可以確認這些設定，並新增其他要通知的使用者。 如需有關警示原則的詳細資訊，請參閱 [Microsoft 365 中的警示原則](../../compliance/alert-policies.md)。

> [!IMPORTANT]
> 若要讓警示運作，必須開啟稽核記錄搜尋。 如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

1. 在 Microsoft 365 Defender 入口網站中，移至 [電子郵件與共同作業 **]** \> [原則與規則 **]** \> [警示原則 **]**。

2. 在 [警示原則 **]** 頁面上，尋找並選取名為 [無法傳送電子郵件的受限制使用者 **]** 的警示。 您可以依據名稱排序原則，或使用 [搜尋方塊 **]** 來尋找原則。

3. 在出現的 [無法傳送電子郵件的受限制使用者 **]** 飛出視窗中，驗證或設定下列設定：
   - **狀態**：確認已開啟警示 ![打開](../../media/scc-toggle-on.png)。
   - **電子郵件收件者**：按一下 **[編輯]**，在 **[編輯收件者]** 飛出視窗中確認或設定如下列設定：
     - **傳送電子郵件通知**：驗證已選取此選項 (**開啟**)。
     - **電子郵件收件者**：預設值是 **TenantAdmins** (表示 **全域系統管理員** 成員)。 若要新增其他收件者，按一下方塊中的空白處。 收件者清單隨即顯示，您可以輸入名稱開始篩選，然後選取收件者。 若要移除方塊中的現有收件者，只要按一下其名稱旁的移除圖示![](../../media/m365-cc-sc-remove-selection-icon.png)即可。
     - **每日通知限制**：預設值是 **[無限制]**，但您可以選取每天的通知數量上限。

     完成後，按一下 [儲存]。

4. 返回 **[限制使用者傳送電子郵件]** 飛出視窗中，按一下 **[關閉]**。

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>使用 Exchange Online PowerShell 來檢視和移除限制的使用者清單中的使用者

若要檢視限制傳送電子郵件的使用者清單，請執行下列命令：

```powershell
Get-BlockedSenderAddress
```

若要檢視特定使用者的詳細資料，請以其電子郵件地址取代 \<emailaddress\> 並執行下列命令：

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

如需詳細的語法及參數資訊，請參閱 [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)。

若要從限制的使用者清單中移除使用者，請以其電子郵件地址取代 \<emailaddress\> 並執行下列命令：

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

如需詳細的語法及參數資訊，請參閱 [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)。
