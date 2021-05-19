---
title: 使用哄騙智慧原則及欺詐智慧洞察力來管理冒牌寄件者
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用欺詐智慧原則和欺騙智慧洞察力，以允許或封鎖偵測到的寄件者。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 821488f79186e1b5c306b587764377989346eea5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530883"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>使用哄騙智慧原則和 EOP 中的欺騙智慧洞察力來管理冒牌寄件者

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文說明所取代的老式欺騙寄件者管理體驗。 如需更多有關全新體驗的資訊，請參閱 [EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，輸入的電子郵件會在2018年10月時自動受到 EOP 的欺騙。 EOP 會使用 **哄騙情報** 做為組織對網路釣魚的整體防護的一部分。 如需詳細資訊，請參閱 [EOP 中的反欺詐防護](anti-spoofing-protection.md)。

預設 (且只有) 欺詐 **智慧原則** ，可協助確保合法寄件者所傳送的欺騙電子郵件不會陷入 EOP 垃圾郵件篩選器中，同時也會保護您的使用者免受垃圾郵件或網路釣魚攻擊。 您也可以使用「 **欺騙性智慧洞察力** 」，快速判斷哪些外部寄件者可合法傳送您未驗證的電子郵件 (來自未透過 SPF、DKIM 或 DMARC 檢查) 的網域的郵件。

您可以在安全性 & 合規性中心或 PowerShell (Exchange Online PowerShell 中管理使用 Microsoft 365 信箱的 Exchange Online 組織的欺騙情報;組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。
  - 若要直接移至欺騙智慧原則的 **反垃圾郵件設定** 頁面，請使用 <https://protection.office.com/antispam> 。
  - 若要直接移至 **安全性儀表板** 頁面以取得欺騙性智慧洞察力，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要修改欺騙性智慧原則或啟用或停用欺騙智慧，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀的訪問欺騙性智慧原則，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 欺騙性情報的選項會在 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)中說明。

- 您可以啟用、停用及設定反網路釣魚原則中的欺騙智慧設定。 如需根據您訂閱的指示，請參閱下列其中一個主題：

  - [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。
  - [設定 Microsoft Defender 中 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

- 如需適用于哄騙情報的建議設定，請參閱 [EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)。

## <a name="manage-spoofed-senders"></a>管理欺騙寄件者

有兩種方式可以允許和封鎖欺騙寄件者：

- [使用哄騙智慧原則](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [使用哄騙情報洞察力](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>管理欺騙性智慧原則中的欺騙寄件者

1. 在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。

2. 在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 以展開 [ **欺騙智慧原則**]。

   ![選取哄騙智慧原則](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 進行下列其中一項選擇：

   - **審閱新寄件者**
   - **顯示已經過審閱的寄件者**

4. 在 [ **決定是否允許這些寄件者哄騙您** 顯示的使用者] 浮出項目時，選取下列其中一個索引標籤：

   - **您的網域**：寄件者哄騙您內部網域中的使用者。
   - **外部網域**：寄件者哄騙外部網域中的使用者。

5. 按一下 ![ ](../../media/scc-expand-icon.png) [ **允許欺騙？** ] 欄中的展開圖示。 選擇 **[是]** 允許冒牌寄件者，或選擇 [ **否** ] 將郵件標示為欺騙。 此巨集指令是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。 如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。

   ![顯示欺騙寄件者飛出的螢幕擷取畫面，以及是否允許寄件者哄騙](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   下列清單說明您所看到的欄和值：

   - **欺騙使用者**：已欺騙的使用者帳戶。 這是寄件者位址 (中的郵件寄件者，也稱為 `5322.From` 電子郵件客戶程式中顯示的位址) 。 SPF 不會檢查此位址的有效性。
     - 在 [ **您的網域** ] 索引標籤上，此值會包含單一電子郵件地址，或如果來源電子郵件伺服器是哄騙多個使用者帳戶，它會包含 **一個以上** 的使用者帳戶。
     - 在 [ **外部網域** ] 索引標籤上，此值包含欺騙使用者的網域，而非完整的電子郵件地址。

   - 傳送 **基礎結構**：) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域。 如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。

     如需郵件來源和郵件寄件者的詳細資訊，請參閱 [電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **郵件** 數目：在過去30天內，來自組織的傳送基礎結構中包含指定的欺騙寄件者或寄件者的郵件數目。

   - **使用者抱怨**：過去30天內，使用者對此寄件者所進行的投訴。 抱怨的形式通常為對 Microsoft 的垃圾郵件提交。

   - **驗證結果**：下列其中一個值：
      - **傳遞**：寄件者傳送寄件者電子郵件驗證檢查 (SPF 或 DKIM) 。
      - **失敗**：寄件者失敗 EOP 寄件者驗證檢查。
      - **未知**：這些檢查的結果是未知的。

   - **決策設定依據**：顯示誰決定了傳送基礎結構是否允許哄騙使用者：
       - **欺騙性智慧原則** (自動) 
       - **Admin** (手動) 

   - **上次看到**：從包含欺騙使用者之傳送基礎結構接收郵件的最後日期。

   - 是否 **允許哄騙？**：您在這裡看到的值包括：
     - **Yes**：允許虛假使用者和傳送基礎結構組合的郵件，也不會被視為欺騙電子郵件。
     - **No**：來自欺騙使用者和傳送基礎結構的郵件會標示為欺騙。 此巨集指令是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。 如需詳細資訊，請參閱下一節。

     - **有些使用者** (**您的網域** ] 索引標籤只) ：傳送基礎結構是哄騙多個使用者，而某些欺騙使用者則是允許的，有些則不是。 使用 [詳細] 索引標籤來查看特定地址。

6. 在頁面底部，按一下 [ **儲存**]。

#### <a name="use-powershell-to-manage-spoofed-senders"></a>使用 PowerShell 管理欺騙寄件者

若要在哄騙情報中查看允許和封鎖的寄件者，請使用下列語法：

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

此範例會傳回所有允許哄騙您網域中使用者之寄件者的詳細資訊。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

如需詳細的語法及參數資訊，請參閱 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy)。

若要在欺騙智慧中設定允許和封鎖的寄件者，請遵循下列步驟：

1. 透過執行下列命令，將 **Get-PhishFilterPolicy** Cmdlet 的輸出寫入 CSV 檔案，以捕獲目前偵測到之寄件者的清單：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. 編輯 CSV 檔案，以新增或修改下列值：
   - 來源伺服器的 PTR 記錄或 IP/24 位址) 中的 **寄件者** (網域
   - **SpoofedUser**：下列其中一個值：
     - 內部使用者的電子郵件地址。
     - 外部使用者的電子郵件網域。
     - 空白值，表示您想要封鎖或允許來自指定之 **寄件者** 的任何和所有冒牌郵件，而不論欺騙的電子郵件地址。
   - **AllowedToSpoof** (是或否) 
   - **SpoofType** (內部或外部) 

   透過執行下列命令，儲存檔、讀取檔案，並將內容儲存為名為的變數 `$UpdateSpoofedSenders` ：

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 透過 `$UpdateSpoofedSenders` 執行下列命令，使用變數來設定欺騙智慧原則：

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

如需詳細的語法及參數資訊，請參閱 [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)。

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>在欺騙智慧洞察力中管理欺騙性寄件者

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **儀表板**。

2. 在 [ **洞察力** ] 列中，尋找下列其中一個專案：

   - **過去七天內可能會出現的欺騙網域**：此認知表示已啟用欺騙情報 (預設會啟用該功能) 。
   - **啟用欺騙保護**：此真知灼見表示已停用欺騙智慧，按一下洞察力可讓您啟用欺騙智慧。

3. 儀表板上的洞察力顯示如下資訊：

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   這兩種洞察力分為兩種模式：

   - **深入瞭解模式**：如果已啟用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能會影響的郵件數目。
   - **假設模式**：如果已停用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能 *會* 影響的郵件數目。

   無論是哪種方式，顯示在真知灼見中的欺騙性網域都會分為兩類： **可疑的網域** 和 **非可疑的網域**。

   - **可疑網域**：
     - **高度信賴性哄騙**：根據電子郵件傳送模式和網域的信譽分數，我們強烈相信網域是哄騙的，而來自這些網域的郵件更可能是惡意的。
     - **適中** 的信譽哄騙：根據歷史傳送模式和網域的信譽分數，我們適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。 在此類別中，誤報很可能超出高可信度的欺騙。
   - **非可疑網域**：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。 不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。 因此，不會對郵件採取任何反欺詐動作。

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>查看可疑和 nonsuspicious 網域的詳細資訊

1. 在 [偽造智慧洞察力] 中，按一下 [ **可疑的網域** 或 **非可疑的網域** ]，以移至 [ **偽造智慧洞察力** ] 頁面。 「 **欺騙性智慧洞察力** 」頁面包含下列資訊：

   - **冒牌網域**：電子郵件客戶程式的 [ **寄件者** ] 方塊中顯示的欺騙使用者網域。 此位址也稱為 `5322.From` 位址。
   - **基礎結構**：也稱為傳送 _基礎結構_。 ) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域。 如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。
   - **郵件數目**：傳送基礎結構至您的組織中，在過去7天內包含指定的冒牌網域的郵件數目。
   - **上次看到**：從包含欺騙網域之傳送基礎結構接收郵件的最後日期。
   - **哄騙類型**：此值為 **External**。
   - 是否 **允許哄騙？**：您在這裡看到的值包括：
     - **Yes**：來自欺騙使用者網域和傳送基礎結構的電子郵件會被允許，未被視為欺騙電子郵件。
     - **No**：來自欺騙使用者網域及傳送基礎結構的郵件會標示為欺騙。 此巨集指令是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。

2. 選取清單中的專案，以查看快顯視窗中網域/傳送基礎結構對的詳細資料。 此資訊包含：
   - 我們為何會發現這種情況。
   - 您需要執行的工作。
   - 網域摘要。
   - WhoIs 寄件者的相關資料。
   - 來自相同寄件者的您租使用者中所看到的類似訊息。

   在這裡，您也可以選擇從 **允許欺騙** 寄件者允許清單中，新增或移除網域/傳送基礎結構對。 只會據此設定切換。

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已設定欺騙性智慧與允許和不允許哄騙的寄件者，請使用下列任何一項步驟：

- 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反垃圾郵件** \> 展開 **欺騙性智慧原則** \> 選取 [ **顯示我已複查的寄件者** \> ] 選取 [ **您的網域** ] 或 [ **外部網域** ] 索引標籤，然後確認寄件者的 [ **允許欺騙？** ] 值。

- 在 PowerShell 中，執行下列命令，以查看允許和不允許哄騙的寄件者：

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- 在 PowerShell 中，執行下列命令，將所有冒牌寄件者的清單匯出至 CSV 檔案：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
