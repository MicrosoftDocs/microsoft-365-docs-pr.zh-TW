---
title: 傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果使用者持續從 Office 365 傳送被歸類為垃圾郵件的電子郵件，使用者將遭到限制而無法再傳送任何郵件。
ms.openlocfilehash: c817add2581ffdbe709023dc3b348631defec169
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823815"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者

如果使用者持續從 Office 365 傳送被歸類為垃圾郵件的電子郵件，使用者將遭到限制而無法傳送任何電子郵件，但仍可以收到電子郵件。 使用者會列在服務中，做為錯誤的外寄寄件者，並將會收到未傳遞回報 (NDR)，指出：

> 「因為您不是認可的有效寄件者，所以無法傳遞您的郵件。 最有可能發生此狀況的原因是您的電子郵件地址有傳送垃圾郵件的嫌疑，因此系統已不允許此電子郵件地址傳送電子郵件。  請連絡您的電子郵件系統管理員以取得協助。 遠端伺服器傳回「550 5.1.8 存取被拒，錯誤的外寄寄件者。」

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

預估完成時間：5 分鐘

您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主題中的＜反垃圾郵件＞項目。

下列程序也可以透過遠端 PowerShell 執行。 使用 Get-BlockedSenderAddress Cmdlet 來取得受限制使用者的清單，以及使用 Remove-BlockedSenderAddress 來移除限制。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>移除封鎖的 Office 365 電子郵件帳戶的限制

您可以在安全性與合規性中心 (SCC) 完成此工作。 如需 SCC 的詳細資訊，請[移至安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。 您必須在**組織管理**或**安全性系統管理員**角色群組，才能執行這些功能。 如需 SCC 角色群組的詳細資訊，請[移至安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。

1. 使用具備 Office 365 全域系統管理員權限的公司或學校帳戶登入 Office 365 安全性與合規性中心，並在左側清單中，展開 [威脅管理]****，選擇 [檢閱]****，然後選擇 [限制的使用者]****。

    > [!TIP]
    > 若要直接前往安全性 &amp; 合規性中心中的 [限制的使用者]**** 頁面 (先前稱為重要訊息中心)，請使用此 URL：[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此頁面會包含已遭封鎖而無法傳送電子郵件的使用者清單。  尋找您想要移除限制的使用者，並選取 [解除封鎖]****。

3. 隨即會出現飛出視窗，內含帳戶的傳送受到限制的詳細資料。 您必須逐一查看建議，以確保帳戶實際上遭到入侵時，您會採取適當的動作。 完成時，按 [下一步]****。

4. 下一個畫面提供建議來協助避免未來的入侵。 啟用多重要素驗證 (MFA)，並變更密碼，是很好的防禦方式。 完成時按一下 [解除封鎖使用者]****。

5. 按一下 [是]**** 以確認變更。

    > [!NOTE]
    > 可能需要 30 分鐘以上的時間，才能移除限制。

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>確認發生此情況時系統管理員會收到警示

「無法傳送電子郵件的受限制使用者」警示以原則的形式於 [Office 365 安全性與合規性警示] 原則頁面下提供。 這原先是輸出垃圾郵件原則，但現在是 Office 365 警示平台的原生部分。 如需警示的詳細資訊，請移至[安全性與合規性中心的警示原則](../../compliance/alert-policies.md)。

> [!IMPORTANT]
> 若要讓警示運作，必須開啟稽核記錄搜尋。 如需詳細資訊，請參閱[開啟或關閉 Office 365 稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

此警示的原則是預設值，都每個 Office 365 租用戶都會隨附，因此不需要進行設定。 它會被視為高嚴重性警示，並且會每次使用者遭限制無法傳送郵件而引發警示時，寄送電子郵件給所設定的 TenantAdmins 群組。 系統管理員可以更新發生此警示所通知的群組，方法是移至警示，其位於 SCC 入口網站 > [警示] > [警示原則] > [使用者受限制無法傳送電子郵件]。

您可以編輯警示，以便：
- 開啟/關閉電子郵件通知
- 傳送電子郵件給需要的收件者
- 限制您每天收到的通知

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>使用 PowerShell 檢查並移除限制
用於限制的使用者的 PowerShell 命令為：
- `Get-BlockedSenderAddress`：執行可擷取受限制而無法傳送電子郵件的使用者清單
- `Remove-BlockedSenderAddress`：執行可從限制中移除使用者

## <a name="for-more-information"></a>相關資訊

[回應遭入侵的電子郵件帳戶](responding-to-a-compromised-email-account.md)

[了解「無法傳送電子郵件的受限制使用者」警示](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[輸出郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

[安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)

[安全性與合規性中心的警示原則](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
