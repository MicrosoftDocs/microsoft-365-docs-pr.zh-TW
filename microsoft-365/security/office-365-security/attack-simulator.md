---
title: Office 365 中的攻擊模擬器
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 身為 Office 365 全域管理員，您可以使用的攻擊模擬器在組織中執行真實的攻擊案例。 這可協助您找出並之前真實的攻擊拜訪人次貴公司，找出受到使用者。
ms.openlocfilehash: bb68850587647f7e96c940de10e3da23cd5e83de
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306177"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻擊模擬器

**摘要**如果您是 Office 365 全域系統管理員或安全性系統管理員，而且您的組織有 Office 365 進階威脅防護計劃 2，其中包含[威脅調查及回應功能](office-365-ti.md)，您可以使用的攻擊模擬器來執行在您的組織中的真實的攻擊案例。 這可協助您找出並尋找容易遭受使用者之前真實的攻擊影響底部線條。 閱讀本篇文章以了解更多。

## <a name="the-attacks"></a>攻擊

目前可用的三種類型的攻擊模擬如下：

- [顯示名稱矛網路釣魚攻擊](#display-name-spear-phishing-attack)

- [密碼噴灑攻擊](#password-spray-attack)

- [暴力密碼攻擊](#brute-force-password-attack)

若要順利啟動攻擊，請確定您用來執行模擬的攻擊的帳戶使用多重要素驗證。 此外，您必須是 Office 365 全域系統管理員或安全性系統管理員。 （若要深入了解角色和權限，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)）。

若要存取安全性的攻擊模擬器&amp;合規性中心，選擇 [**威脅管理** \> **攻擊模擬器**。

## <a name="before-you-begin"></a>開始之前...]

請確定您和您的組織符合的攻擊模擬器需求如下：

- 貴組織的電子郵件會託管於 Exchange Online。 （攻擊模擬器不適用於內部部署電子郵件伺服器。）

- 您是 Office 365 全域系統管理員或安全性系統管理員

- [多重要素驗證/條件式存取](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)已關閉，如在最低之 Office 365 全域系統管理員帳戶和安全性系統管理員將使用的攻擊模擬器。 （理想狀況下，多重要素驗證條件式存取已為您組織中的所有使用者。）

- 您的組織有[Office 365 進階威脅防護計劃 2](office-365-atp.md)，與安全性可見的攻擊模擬器&amp;合規性中心 (前往**威脅管理** \> **攻擊模擬器**)

    ![威脅管理-攻擊模擬器](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a>顯示名稱矛網路釣魚攻擊

網路釣魚是通稱歸類為社交樣式攻擊的攻擊廣泛套件。 此類攻擊著重於矛網路釣魚，針對特定群組的個人或組織在多目標攻擊。 一般而言，自訂的攻擊與某些偵察執行，並使用會產生收件者，例如看起來像來自組織內的高階主管的電子郵件訊息中的信任的顯示名稱。

此類攻擊著重於給您，讓您管理誰會顯示訊息，有來自藉由變更顯示名稱和來源地址。 矛網路釣魚攻擊成功時，cyberattackers 存取使用者的認證。

### <a name="to-simulate-a-spear-phishing-attack"></a>若要模擬矛網路釣魚攻擊

![撰寫電子郵件內文](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

您可以製作豐富的 HTML 編輯器，直接在**電子郵件內文**欄位本身或與 HTML 來源搭配使用。

1. 在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。

2. 指定攻擊的有意義的活動名稱，或者選取範本。

   ![網路釣魚起始頁面](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. 指定目標收件者。 這可以是個人或組織中的群組。 每個目標收件者必須擁有 Exchange Online 信箱攻擊的順序才會成功。

   ![收件者的選取範圍](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. 設定網路釣魚電子郵件的詳細資訊。

   ![設定電子郵件的詳細資訊](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   HTML 格式可以為複雜或基本與您的行銷活動需求。 為電子郵件格式是 HTML，您可以插入影像和以增強 believability 的文字。 您可以在所收到的訊息中接收電子郵件用戶端外觀的控制。

5. 指定文字**從 （名稱）** ] 欄位。 這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。

6. 指定的文字或 [**從**] 欄位。 這是顯示為接收電子郵件用戶端的寄件者的電子郵件地址] 欄位。

   您可以在組織內輸入現有的電子郵件命名空間 （這樣會使實際解決接收用戶端，促進非常高信任模型中的電子郵件地址），或您可以輸入的外部電子郵件地址。 您指定的電子郵件地址並沒有實際存在，但仍必須以下列格式為有效的 SMTP 地址，例如`user@domainname.extension`。

7. 使用下拉式清單選取器，請選取 [反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。 多個已設佈景主題的 Url 被提供給您從中選擇，例如文件傳遞、 技術、 薪資等。這實際上是目標的使用者上當系統要您按一下 [URL。

8. 指定自訂的登陸頁面 URL。 使用這將使用者重新導向至您指定的攻擊成功結尾的 URL。 如果您有內部認知訓練，例如，您可以指定，這裡。

9. 指定文字的 [**主旨**] 欄位。 這是顯示為中接收電子郵件用戶端的**主體名稱**] 欄位。

10. 撰寫目標會收到**電子郵件內文**。

    `${username}`電子郵件本文中插入的目標名稱。

    `${loginserverurl}`會插入我們想要目標使用者按一下的 URL

11. 選擇 [**下一步]** ，然後**完成]** 來啟動攻擊。 矛網路釣魚電子郵件會傳遞至您目標收件者的信箱。

## <a name="password-spray-attack"></a>密碼噴灑攻擊

壞動作項目已成功取得從租用戶的有效使用者的清單之後，通常會使用組織的密碼噴灑攻擊。 壞動作項目所知的人員使用常見密碼。 此為廣泛使用的攻擊，來執行，且更難偵測比暴力方法便宜攻擊。

此類攻擊著重於讓您指定要對使用者的大型目標基底常見的密碼。

### <a name="to-simulate-a-password-spray-attack"></a>若要模擬密碼噴灑攻擊

1. 在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。

2. 指定攻擊的有意義的活動名稱。

3. 指定目標收件者。 這可以是個人或組織中的群組。 目標收件者必須在才能成功攻擊的順序中的 Exchange Online 信箱。

4. 指定要用於攻擊的密碼。 例如，您可以嘗試的一個常見、 相關密碼是`Summer2019`。 另一個可能是`Fall2019`，或`Password1`。

5. 選擇 [**完成**] 以啟動攻擊。

## <a name="brute-force-password-attack"></a>暴力密碼攻擊

壞動作項目已成功取得從租用戶的關鍵使用者的清單之後，通常會使用組織暴力密碼攻擊。 此類攻擊著重在嘗試一組單一使用者的帳戶的密碼。

### <a name="to-simulate-a-brute-force-password-attack"></a>若要模擬暴力密碼攻擊

1. 在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。

2. 指定攻擊的有意義的活動名稱。

3. 指定目標收件者。 目標收件者必須在才能成功攻擊的順序中的 Exchange Online 信箱。

4. 指定一組用於攻擊的密碼。 若要這麼做，您可以使用文字檔 (.txt) 的清單中的密碼。 將文字檔不可超過 10 MB 的檔案大小。 使用一個密碼每一行，並確定要包含在清單中的最後一個密碼之後硬式傳回。

5. 選擇 [**完成**] 以啟動攻擊。

## <a name="new-features-in-attack-simulator"></a>攻擊模擬器中的新功能

新功能最近已新增至攻擊模擬器。 這些包括：

- 進階的報告功能。 查看資料，例如速度最快 （或速度最慢） 時間按一下 [郵件被覆寫且更多的視覺效果中的連結，以開啟攻擊模擬電子郵件訊息，最快 （或速度最慢） 時間的能力。

- 電子郵件範本編輯器]。 若要建立自訂、 可重複使用的電子郵件範本可供未來的攻擊模擬的能力。

- CSV 匯入收件者。 若要匯入您的目標收件者清單，而不是使用 address book 選擇使用.csv 檔案的能力。

更多的新功能即將推出的攻擊模擬器。 這些包括：

- 附件承載網路釣魚模擬。 作為附件承載網路釣魚模擬 URL 取代功能。

請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是在開發中、 什麼推行和功能已啟動。

## <a name="see-also"></a>請參閱

[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 進階威脅防護](office-365-atp.md)
