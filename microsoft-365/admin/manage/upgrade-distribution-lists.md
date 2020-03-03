---
title: 在 Outlook 中將通訊群組清單升級至 Office 365 群組
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何將一或多個通訊群組清單升級至 Office 365 群組，在 Outlook 中，及如何使用 PowerShell 來升級多個通訊群組清單同時。
ms.openlocfilehash: 7337d450cf1e9b249b2b9dc2ab66f32f5b1577e0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361708"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a>在 Outlook 中將通訊群組清單升級至 Office 365 群組

您可以使用 Outlook 的 Office 365 群組升級通訊群組清單。 這是很好的方法讓貴組織的通訊群組清單，所有的功能和 Office 365 群組的功能。 [為什麼您應該將 Outlook 中的通訊群組清單升級成群組](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

您可以在一次，或數個同時升級 Dl 一個。

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a>一或多個通訊群組清單升級至在 Outlook 中的 Office 365 群組

您必須是 Office 365 全域系統管理員或 Exchange 系統管理員，才能升級通訊群組清單。 若要升級至 Office 365 群組，通訊群組必須具有信箱擁有者。 

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。

2. 在 Exchange 系統管理中心中，前往 [**收件者** \> **群組**。<br/>您會看到指出您有 （也稱為**通訊群組**） 合格升級至 Office 365 群組的通訊群組清單的通知。<br/> ![選取要開始使用] 按鈕](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. 選取一或多個通訊群組清單 （也稱為**通訊群組**） 從 [**群組**] 頁面。<br/>![選取一個通訊群組](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. 選取 [升級] 圖示。<br/>![升級至 Office 365 群組圖示](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 在 [資訊] 對話方塊中，選取 **[是]** 以確認升級。 會立即開始處理程序。 根據大小和數目您正在升級的通訊群組清單中，則過程會需要分鐘或數小時。<br/>如果通訊群組清單無法升級，對話方塊會隨即出現說這樣。 請參閱[無法升級通訊群組清單？](#which-distribution-lists-cannot-be-upgraded)。

6. 如果您要升級多個通訊群組清單，請使用哪些通訊群組清單均已升級的篩選下拉式清單。 如果清單不完整，等待長一段時間，然後選取 [以查看哪些已成功升級的 [**重新整理**。<br/>沒有任何通知，告知您升級程序完成時的所有通訊群組清單您所選取。 您可以查出這來查看項目會列在**適用於升級**或**升級 Dl**下方。

7. 如果您選取了 DL 升級，但它有仍會顯示在頁面上為適用於升級，然後它無法升級。 請參閱[What to 時，升級作業不會運作](#what-to-do-if-the-upgrade-doesnt-work)。

> [!NOTE]
> 如果您要取得群組摘要電子郵件，您可能會發現在有時會提供可讓您升級任何合格的通訊群組的底部會列出您的擁有者。 如需 digest 電子郵件的詳細資訊，請參閱[已在 Outlook 中的群組交談](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx)。


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>如果升級無法解決問題，該怎麼辦

若要升級失敗的通訊群組清單維持不變。

如果一或多個**合格**的通訊群組清單無法升級，開啟[支援票證](../contact-support-for-business-products.md)。 此問題： 將需要擴大至群組工程小組他們找出問題。

它是可行的通訊群組清單並未取得升級因服務中斷，但 pretty 互不。 如果您想，等候一段時間，然後再試一次升級 DL。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>如何使用 PowerShell 來升級多個通訊群組清單在同一時間

如果您曾經在使用 PowerShell，您可能想要前往此路由，而不是使用 UI。 我們有一組 cmdlet，可協助您升級通訊群組清單。 請參閱以下。

### <a name="upgrade-a-single-dl"></a>升級單一 DL

若要升級單一 DL 執行下列命令：

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

例如，如果您想要升級的 SMTP 地址 dl1@contoso.com Dl，執行下列命令：

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> 您也可以使用[新增 UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 與 Office 365 群組升級單一通訊群組清單

### <a name="upgrade-multiple-dls-in-a-batch"></a>升級批次中的多個通訊群組清單

您也可以傳遞為批次的多個通訊群組清單，並在一起升級：

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

例如，如果您想要升級使用 SMTP 位址的五個 Dl`dl1@contoso.com`和`dl2@contoso.com`， `dl3@contoso.com`、`dl4@contoso.com`和`dl5@contoso.com`，執行下列命令：

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>升級所有合格的通訊群組清單

有兩種方式在其中您可以升級所有合格的 Dl。

> [!NOTE]
> 升級 DistributionGroup 指令程式不會接收資料管線，因此它所需使用 「 foreach 物件{}"運算子能夠順利執行。

1. 取得租用戶中的合格的通訊群組清單並進行升級使用升級的命令：

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. 取得所有通訊群組清單的清單，並升級僅符合資格的通訊群組清單：

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a>將通訊群組清單升級至在 Outlook 中的 Office 365 群組相關的常見問題集

### <a name="which-distribution-lists-cannot-be-upgraded"></a>無法升級通訊群組清單？

您只可以升級雲端管理、 簡單、 非巢狀通訊群組清單。 下表列出可升級**CANNOT**的通訊群組清單。

|**屬性**|**合格嗎？**|
|:-----|:-----|
|內部部署受管理的通訊群組清單。  <br/> |否  <br/> |
|巢狀通訊群組清單。 通訊群組清單具有子群組或另一個群組的成員。  <br/> |否  <br/> |
|通訊群組清單成員以外的**UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、 **MailUser** **RecipientTypeDetails**  <br/> |否  <br/> |
|有 100 個以上的擁有者的通訊群組清單  <br/> |否  <br/> |
|通訊群組清單，只有成員，但沒有擁有者  <br/> |否  <br/> |
|通訊群組清單具有別名包含特殊字元  <br/> |否  <br/> |
|如果通訊群組清單設定為共用信箱轉寄地址  <br/> |否  <br/> |
|如果 DL 是另一個 DL 中的**寄件者限制**的一部分。  <br/> |否  <br/> |
|安全性群組  <br/> |否  <br/> |
|動態通訊群組清單  <br/> |否  <br/> |
|已轉換成**RoomLists**通訊群組清單  <br/> |否  <br/> |
|**MemberJoinRestriction**及/或**MemberDepartRestriction**是**已關閉**的通訊群組清單  <br/> |否  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>如何檢查通訊群組清單是適合升級？

如果您想要檢查是否 DL 是否合格，您可以執行下列命令：

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

如果您想要檢查通訊群組清單是適合進行升級，請直接執行下列命令：

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>誰可以執行升級的指令碼？

含 Office 365 全域系統管理員或 Exchange 系統管理員權限的人員。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>連絡人卡片仍然顯示通訊群組清單的為何？ 我該怎麼辦可防止已升級的通訊群組清單中我自動顯示建議] 清單？

- Outlook： 當有人嘗試在 Outlook 中傳送一封電子郵件移轉後輸入 Office 365 群組名稱時，收件者會解析為通訊群組清單，而不是群組。 收件者的連絡人卡片會是通訊群組清單連絡人卡片。 這是因為收件者的快取或 nick 名稱快取在 Outlook 中。 電子郵件會傳送至群組時，成功，但寄件者可能會造成混淆。<br/>您可以執行本主題中， [Outlook 自動完成清單的相關資訊](https://go.microsoft.com/fwlink/?LinkID=798736)來重設會修正此問題的快取中的步驟。

- 在 web 上的 outlook： 時網頁型 Outlook，通訊群組清單的收件者仍會保留在快取。 您可以遵循[建議的名稱或電子郵件地址從自動完成清單中移除](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx)重新整理快取，查看 [連絡人卡片] 群組中的步驟。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新的群組成員可以取得的歡迎使用電子郵件收件匣？

否。 根據預設啟用的歡迎訊息] 設定設為 false。 此設定會影響移轉完成後可能會加入的現有和新群組成員。 如果群組擁有者稍後允許來賓使用者，來賓使用者不會在其收件匣中收到的歡迎使用電子郵件。 來賓成員可以繼續使用該群組。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>如果一或 Dl 部分不會升級？

雖然 DL 符合資格，但無法升級，有某些情況下，在其中。 DL 不會取得升級，但仍會保留為 DL。

- 系統管理員已套用**群組電子郵件地址原則**的組織中的群組，以及它們嘗試升級不會滿足準則的 Dl DL 無法升級

- Dl **MemberJoinRestriction**或**MemberDepartRestriction**設為**已關閉**，無法升級

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>會發生什麼情況 DL 從 EAC 升級失敗時？

只有當通話送至伺服器時，會發生升級。 如果升級失敗時，將 Dl 會保持不變。 它們 like 他們用來運作。


