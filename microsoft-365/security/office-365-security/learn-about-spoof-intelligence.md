---
title: 設定詐騙情報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用和管理欺騙性情報，以防範電子郵件欺騙。
ms.openlocfilehash: 32a7668edced5c9dbca2f7b16ff00253b56a5988
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034241"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a>在 Microsoft 365 中設定假冒情報

如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶（沒有 Exchange Online 信箱）的 Microsoft 365 客戶，輸入的電子郵件會在10月2018時自動受到 EOP 的欺騙。 EOP 會使用哄騙情報做為組織對網路釣魚的整體防護的一部分。 如需詳細資訊，請參閱[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)。

當寄件者欺騙電子郵件地址時，他們似乎是組織網域之一中的使用者，或是將電子郵件傳送至您組織的外部網域中的使用者。 欺騙寄件者以傳送垃圾郵件或網路釣魚電子郵件的攻擊者必須封鎖。 但在某些情況下，合法寄件者是哄騙。 例如：

- 欺騙內部網域的合法案例：

  - 協力廠商寄件者使用您的網域將大宗郵件傳送給您自己的員工，以進行公司投票。

  - 外部公司代表您產生及傳送廣告或產品更新。

  - 助理定期需要在組織內傳送其他人員的電子郵件。

  - 內部應用程式會傳送電子郵件通知。

- 欺騙外部網域的合法案例：

  - 寄件者位於郵寄清單（也稱為討論清單），而郵寄清單會將來自原始寄件者的電子郵件轉送至郵寄清單上的所有參與者。

  - 外部公司代表另一家公司傳送電子郵件（例如，自動化的報告或軟體即服務公司）。

哄騙情報，特別是預設（而且只是）哄騙智慧原則，可協助確保合法寄件者所傳送的欺騙電子郵件不會陷入 Microsoft 365 或外部電子郵件系統的垃圾郵件篩選器中，同時也會保護您的使用者免受垃圾郵件或網路釣魚攻擊。

您可以在 Microsoft 365 Security & 合規性中心或 PowerShell （Microsoft 365 客戶的 Exchange Online PowerShell 中）管理欺騙情報;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [反垃圾郵件設定]**** 頁面，請使用 <https://protection.office.com/antispam>。 若要直接移至 [**反網路釣魚**] 頁面<https://protection.office.com/antiphishing>，請使用。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要修改欺騙性智慧原則或啟用或停用欺騙智慧，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 若要取得欺騙智慧原則的唯讀存取權，您必須是「**安全性讀者**」角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 如需適用于哄騙情報的建議設定，請[EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>使用安全性 & 規範中心管理欺騙寄件者

> [!NOTE]
> 如果您有 Office 365 企業版 E5 訂閱或是個別購買及高級威脅防護（ATP）附加元件，您也可以管理透過[欺騙智慧洞察力](walkthrough-spoof-intelligence-insight.md)欺騙您網域的寄件者。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開 [**欺騙智慧原則**]。

   ![選取哄騙智慧原則](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 進行下列其中一項選擇：

   - **審閱新寄件者**
   - **顯示已經過審閱的寄件者**

4. 在 [**決定是否允許這些寄件者哄騙您**顯示的使用者] 浮出項目時，選取下列其中一個索引標籤：

   - **您的網域**：寄件者哄騙您內部網域中的使用者。
   - **外部網域**：寄件者哄騙外部網域中的使用者。

5. 按一下![[](../../media/scc-expand-icon.png) **允許欺騙？** ] 欄中的展開圖示。 選擇 **[是]** 允許冒牌寄件者，或選擇 [**否**] 將郵件標示為欺騙。 此動作是由預設的反網路釣魚原則或自訂 ATP 反網路釣魚原則所控制（預設值為 [**將郵件移至垃圾郵件資料夾**]）。 如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。

   ![顯示欺騙寄件者飛出的螢幕擷取畫面，以及是否允許寄件者哄騙](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   下列清單說明您所看到的欄和值：

   - **欺騙使用者**：已欺騙的使用者帳戶。 這是電子郵件客戶程式中所顯示寄件者位址（ `5322.From`也稱為位址）中的郵件寄件者。 SPF 不會檢查此位址的有效性。

     - 在 [**您的網域**] 索引標籤上，此值會包含單一電子郵件地址，或如果來源電子郵件伺服器是哄騙多個使用者帳戶，它會包含**一個以上**的使用者帳戶。

     - 在 [**外部網域**] 索引標籤上，此值包含欺騙使用者的網域，而非完整的電子郵件地址。

   - 傳送**基礎結構**：在來源電子郵件伺服器的 IP 位址的反向 DNS 查找（PTR 記錄）中找到的網域，如果來源沒有 PTR 記錄，則為 IP 位址。

     如需郵件來源和郵件寄件者的詳細資訊，請參閱[電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **郵件**數目：在過去30天內，來自組織的傳送基礎結構中包含指定的欺騙寄件者或寄件者的郵件數目。

   - **使用者抱怨**：過去30天內，使用者對此寄件者所進行的投訴。 抱怨的形式通常為對 Microsoft 的垃圾郵件提交。

   - **驗證結果**：下列其中一個值：

      - **傳遞**：寄件者傳送寄件者電子郵件驗證檢查（SPF 或 DKIM）。
      - **失敗**：寄件者失敗 EOP 寄件者驗證檢查。
      - **未知**：這些檢查的結果是未知的。

   - **決策設定依據**：顯示誰決定了傳送基礎結構是否允許哄騙使用者：

       - **欺騙智慧原則**（自動）
       - 系統**管理員**（手動）

   - **上次看到**：從包含欺騙使用者之傳送基礎結構接收郵件的最後日期。

   - 是否**允許哄騙？**：您在這裡看到的值包括：

     - **Yes**：允許虛假使用者和傳送基礎結構組合的郵件，也不會被視為欺騙電子郵件。

     - **No**：來自欺騙使用者和傳送基礎結構的郵件會標示為欺騙。 此動作是由預設的反網路釣魚原則或自訂 ATP 反網路釣魚原則所控制（預設值為 [**將郵件移至垃圾郵件資料夾**]）。 如需詳細資訊，請參閱下一節。

     - **部分使用者**（僅限**您的網域**索引標籤）：傳送基礎結構是哄騙多個使用者，而某些欺騙使用者則不允許，有些則是。 使用 [詳細]**** 索引標籤來查看特定地址。

6. 在頁面底部，按一下 [**儲存**]。

## <a name="use-powershell-to-manage-spoofed-senders"></a>使用 PowerShell 管理欺騙寄件者

若要在哄騙情報中查看允許和封鎖的寄件者，請使用下列語法：

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

此範例會傳回所有允許哄騙您網域中使用者之寄件者的詳細資訊。

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

如需詳細的語法及參數資訊，請參閱[Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy)。

若要在欺騙智慧中設定允許和封鎖的寄件者，請遵循下列步驟：

1. 將**Get-PhishFilterPolicy** Cmdlet 的輸出寫入 CSV 檔案，以捕獲目前偵測到之寄件者的清單：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. 編輯 CSV 檔案，以新增或修改**SpoofedUser** （電子郵件地址）和**AllowedToSpoof** （是或否）值。 儲存檔案，閱讀檔案，並將內容儲存為名為`$UpdateSpoofedSenders`的變數：

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 使用`$UpdateSpoofedSenders`變數來設定欺騙智慧原則：

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

如需詳細的語法及參數資訊，請參閱[Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>使用安全性 & 規範中心設定假冒情報

欺騙性情報的設定選項會在[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)中說明。

您可以設定預設反網路釣魚原則中的欺騙智慧設定，也可以在 [自訂原則] 中設定。 如需根據您訂閱的指示，請參閱下列其中一個主題：

- [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

- [在 Microsoft 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您已設定欺騙智慧與允許和不允許哄騙的寄件者，以及您已設定欺騙性智慧設定，請使用下列任何一項步驟：

- 在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件** \>展開**欺騙性智慧原則** \>選取 [顯示我\> **已複查的寄件者**] 選取 [**您的網域**] 或 [**外部網域**] 索引標籤，然後確認寄件者的 [**允許欺騙？** ] 值。

- 在 PowerShell 中，執行下列命令，以查看允許和不允許哄騙的寄件者：

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- 在 PowerShell 中，執行下列命令，將所有冒牌寄件者的清單匯出至 CSV 檔案：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- 在包含 Exchange Online 信箱的 Microsoft 365 組織中，執行下列其中一個步驟：

  - 在 [安全性 & 規範中心] 中，移至**威脅管理** \> **原則** \> **反網路釣魚** \>按一下 [**預設原則**]，然後查看快顯視窗中的詳細資料。

  - 在 Exchange Online PowerShell 中，執行下列命令並確認設定：

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- 在 Microsoft 365 ATP 組織中，執行下列其中一個步驟：

  - 在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則** \> **ATP 反網路釣魚**]，並執行下列其中一個步驟：

    - 從清單中選取原則。 在出現的快顯視窗中，確認 [**哄騙**] 區段中的值。
    - 按一下 [**預設原則**]。 在出現的快顯視窗中，確認 [**哄騙**] 區段中的值。

  - 在 Exchange Online PowerShell 中， \<以\> Office365 AntiPhish 預設值取代名稱] 的預設值，或自訂 ATP 反網路釣魚原則的名稱，然後執行下列命令並確認設定：

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>其他管理哄騙和網路釣魚的方式

勤於進行詐騙和網路釣魚防護。 以下是檢查欺騙您網域的寄件者並協助防止他們破壞貴組織的相關方式：

- 檢查**冒名郵件報告**。 您通常可使用此報告來檢視及協助管理偽裝的寄件者。 如需詳細資訊，請參閱[欺騙偵測報告](view-email-security-reports.md#spoof-detections-report)。

- 檢閱寄件者原則架構 (SPF) 設定。 如需 SPF 的快速簡介並快速設定，請參閱[在 Microsoft 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Office 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [Office 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 檢閱您的網域金鑰識別郵件 (DKIM) 設定。 除了 SPF 和 DMARC 之外，您還應該使用 DKIM，以協助防止攻擊者傳送看似來自您網域的郵件。 DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件。 如需相關資訊，請參閱[在 Office 365 中使用 DKIM 驗證從自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。

- 檢閱以網域為基礎的訊息認證、報告與一致性 (DMARC) 設定。 搭配 SPF 和 DKIM 來實作 DMARC 可提供額外保護，防範詐騙和網路釣魚電子郵件。 DMARC 可協助接收方郵件系統決定如何處理未通過 SPF 或 DKIM 檢查的您網域傳送的郵件。 如需相關資訊，請參閱[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。