---
title: 詐騙情報深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中的欺騙智慧洞察力。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94dc1e438f913c1103154afb8803ef4cf89f64af
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028808"
---
# <a name="spoof-intelligence-insight-in-eop"></a>EOP 中的欺騙智慧洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。 如果您的組織不具備本文所述的功能，請參閱 [使用哄騙智慧原則管理冒牌寄件者的舊版欺騙管理經驗和 EOP 中的欺騙情報洞察力](walkthrough-spoof-intelligence-insight.md)。

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，輸入的電子郵件會自動受到保護以防遭到欺騙。 EOP 會使用 **哄騙情報** 做為組織對網路釣魚的整體防護的一部分。 如需詳細資訊，請參閱 [EOP 中的反欺詐防護](anti-spoofing-protection.md)。

當寄件者欺騙電子郵件地址時，他們似乎是組織網域之一中的使用者，或是將電子郵件傳送至您組織的外部網域中的使用者。 欺騙寄件者以傳送垃圾郵件或網路釣魚電子郵件的攻擊者必須封鎖。 但在某些情況下，合法寄件者是哄騙。 例如：

- 欺騙內部網域的合法案例：
  - 協力廠商寄件者使用您的網域將大宗郵件傳送給您自己的員工，以進行公司投票。
  - 外部公司代表您產生及傳送廣告或產品更新。
  - 助理定期需要在組織內傳送其他人員的電子郵件。
  - 內部應用程式會傳送電子郵件通知。

- 欺騙外部網域的合法案例：
  - 寄件者位於郵寄清單中 (又稱為討論清單) ，而且郵寄清單會將來自原始寄件者的電子郵件轉送至郵寄清單上的所有參與者。
  - 外部公司代表其他公司傳送電子郵件 (例如，自動化報表或軟體即服務公司) 。


您可以使用 Microsoft 365 Defender 入口網站中的 **欺騙智慧洞察力**，快速找出可合法傳送您未驗證的電子郵件的欺騙寄件者，以 (未通過 SPF、DKIM 或 DMARC) 檢查的網域郵件，以及手動允許這些寄件者。


透過允許已知寄件者從已知位置傳送哄騙郵件，您可以減少誤報 (已標示為錯誤) 的良好電子郵件。 透過監視允許的欺騙寄件者，您可以提供額外的安全性層級，以防止不安全的郵件到達您的組織中。

同樣地，您也可以查看哄騙情報所允許的欺騙寄件者，並手動封鎖欺騙性智慧洞察力中的寄件者。

本文的其餘部分將說明如何使用 Microsoft 365 Defender 入口網站和 PowerShell (Exchange Online PowerShell 中的欺騙智慧洞察力，以 Microsoft 365 具有 Exchange Online 信箱的組織;組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。


> [!NOTE]
>
> - 欺詐智慧洞察力只會顯示欺騙性智慧所偵測到的欺騙寄件者。 當您覆寫真知灼見中的 allow 或 block 判定時，哄騙寄件者會變成隻會出現在承租人允許/封鎖清單中 [ **偽造** ] 索引標籤上的 [手動允許] 或 [封鎖] 專案。 您也可以手動為欺騙性寄件者建立允許或封鎖專案，以取得欺騙性的智慧。 如需詳細資訊，請參閱[管理 EOP 中的租用戶允許/封鎖清單](tenant-allow-block-list.md)。
>
> - 承租人「允許/封鎖」清單中的「欺騙性智慧真知灼見」和「 **欺騙** 」索引標籤會取代 [安全性 & 合規性中心的 [反垃圾郵件原則] 頁面上提供的欺騙智慧原則功能。
>
>- 欺騙性智慧洞察力會顯示7天的資料。 **SpoofIntelligenceInsight** Cmdlet 會顯示30天的資料。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://security.microsoft.com/antiphishing> 。 若要直接移至 [ **偽造智慧洞察力** ] 頁面，請使用 <https://security.microsoft.com/spoofintelligence> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要修改欺騙性智慧原則或啟用或停用欺騙智慧，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀的訪問欺騙性智慧原則，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 您可以在 EOP 和 Microsoft Defender for Office 365 中，啟用並停用欺騙性智慧中的反網路釣魚原則。 預設會啟用欺騙智慧。 如需詳細資訊，請參閱[在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)或[設定 Microsoft Defender 中的反網路釣魚原則，以進行 Office 365](configure-atp-anti-phishing-policies.md)。

- 如需適用于哄騙情報的建議設定，請參閱 [EOP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)。

## <a name="open-the-spoof-intelligence-insight-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 入口網站中開啟欺騙智慧洞察力

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。

2. 在 [ **反網路釣魚** ] 頁面上，欺騙性的智慧洞察力看起來像這樣：

   ![反網路釣魚原則頁面上的欺騙智慧洞察力](../../media/m365-sc-spoof-intelligence-insight.png)

   洞察力有兩種模式：

   - **深入瞭解模式**：如果已啟用欺騙智慧，則真知灼見會顯示過去7天內，欺騙情報偵測到的郵件數目。
   - **假設模式**：如果已停用欺騙智慧，則真知灼見會顯示過去七天內，欺騙情報偵測到 *的郵件數目* 。

若要查看有關欺騙智慧偵測的資訊，請按一下 [偽造智慧洞察力] 中的 [ **查看哄騙活動** ]。

### <a name="view-information-about-spoofed-messages"></a>查看有關欺騙性郵件的資訊

> [!NOTE]
> 請記住，此頁面上只會顯示欺騙性智慧所偵測到的欺騙寄件者。 當您覆寫真知灼見中的 allow 或 block 判定時，哄騙寄件者會變成隻會出現在承租人允許/封鎖清單中 [ **偽造** ] 索引標籤上的 [手動允許] 或 [封鎖] 專案。

在您按一下 [偽造智慧資訊] 中的 [**查看哄騙活動**] 後出現的 [**哄騙情報** 資訊] 頁面上，此頁面包含下列資訊：

- **冒牌使用者**：在電子郵件客戶程式的 [**寄件者**] 方塊中顯示的欺騙使用者 **網域**。 「寄件者」位址也稱為 `5322.From` 位址。
- 傳送 **基礎結構**：也稱為 _基礎結構_。 傳送基礎結構會是下列其中一個值：
  - ) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域。
  - 如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。
- **郵件** 數目：在過去7天內，來自欺騙網域 _與_ 傳送基礎結構之結合的郵件數目。
- **上次看到**：從包含欺騙網域之傳送基礎結構接收郵件的最後日期。
- **哄騙類型**：下列其中一個值：
  - **Internal**：哄騙寄件者位於屬於您組織 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 中的網域。
  - **外部**：冒牌寄件者位於外部網域。
- **動作**： **允許** 或 **封鎖** 此值：
  - **允許**：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。 不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。 因此，不會對郵件採取任何反欺詐動作。
  - 已 **封鎖**：來自欺騙性網域 _和_ 傳送基礎結構的郵件會因欺騙性智慧而標示為壞。 對哄騙郵件採取的動作是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。 如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

您可以按一下 [選取的欄標題] 來排序結果。

若要篩選結果，您可以使用下列選項：

- 按一下 [ **篩選** ] 按鈕。 在出現的 [ **篩選** ] 浮出控制項中，您可以透過下列方式篩選結果：
  - **哄騙類型**
  - **Action**
- 使用 [ **搜尋** ] 方塊，輸入以逗號分隔的欺騙網域值清單，或傳送基礎結構值以篩選結果。

### <a name="view-details-about-spoofed-messages"></a>查看有關哄騙郵件的詳細資料

當您從清單中選取專案時，會出現詳細資料彈出列表，其中包含下列資訊和功能：

- **允許****從電子欺騙中** 取得或封鎖：選取其中一個值以覆寫原始的欺騙智慧判定，並將輸入從欺騙智慧洞察力移至承租人允許/封鎖清單以取得欺騙的允許或封鎖專案。
- 我們為何會發現這種情況。
- 您需要執行的工作。
- 包含主要欺騙智慧頁面中大部分相同資訊的域摘要。
- WhoIs 寄件者的相關資料。
- 開啟[威脅瀏覽器](threat-explorer.md)的連結，以查看有關 Office 365) 之寄件者 (Microsoft Defender 的其他詳細資料。
- 來自相同寄件者的您租使用者中所看到的類似訊息。

### <a name="about-allowed-spoofed-senders"></a>關於允許的欺騙寄件者

您手動變更為 **允許哄騙** 的欺騙性智慧或遭到封鎖的寄件者所允許的欺騙寄件者，只允許來自欺騙網域 *和* 傳送基礎結構的組合中的郵件。 不允許來自任何來源的冒牌網域的電子郵件，也不允許來自任何網域之傳送基礎結構的電子郵件。

例如，下列欺騙寄件者可哄騙：

- **網域**： gmail.com
- **基礎結構**： tms.mx.com

只有來自該網域/傳送基礎結構對的電子郵件才會遭到欺騙。 其他企圖哄騙 gmail.com 的寄件者不會自動允許。 來自來自 tms.mx.com 的來自其他網域中寄件者的郵件，仍會透過欺騙智慧加以檢查，而且可能會遭到封鎖。

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>使用 Exchange Online PowerShell 或獨立 EOP 中的欺騙智慧洞察力 PowerShell

在 PowerShell 中，您可以使用 **SpoofIntelligenceInsight 指令程式** 來 **查看** 被欺騙情報偵測到的允許和封鎖的欺騙寄件者。 若要手動允許或封鎖欺騙寄件者，您必須使用 **TenantAllowBlockListSpoofItems** Cmdlet。 如需詳細資訊，請參閱 [Use PowerShell configure The 承租人 Allow/封鎖清單](tenant-allow-block-list.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list)。

若要查看哄騙智慧洞察力中的資訊，請執行下列命令：

```powershell
Get-SpoofIntelligenceInsight
```

如需詳細的語法及參數資訊，請參閱 [SpoofIntelligenceInsight](/powershell/module/exchange/get-spoofintelligenceinsight)。

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>其他管理哄騙和網路釣魚的方式

勤於進行詐騙和網路釣魚防護。 以下是檢查寄件者哄騙您網域的相關方法，並協助防止他們破壞您的組織：

- 檢查 **冒名郵件報告**。 您通常可使用此報告來檢視及協助管理偽裝的寄件者。 如需詳細資訊，請參閱 [欺騙偵測報告](view-email-security-reports.md#spoof-detections-report)。

- 檢閱寄件者原則架構 (SPF) 設定。 如需 SPF 的快速簡介並快速設定，請參閱[在 Microsoft 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Office 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [Office 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 檢閱您的網域金鑰識別郵件 (DKIM) 設定。 除了 SPF 和 DMARC 之外，您還應該使用 DKIM，以協助防止攻擊者傳送看似來自您網域的郵件。 DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件。 如需相關資訊，請參閱[在 Office 365 中使用 DKIM 驗證從自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。

- 檢閱以網域為基礎的訊息認證、報告與一致性 (DMARC) 設定。 搭配 SPF 和 DKIM 來實作 DMARC 可提供額外保護，防範詐騙和網路釣魚電子郵件。 DMARC 可協助接收方郵件系統決定如何處理未通過 SPF 或 DKIM 檢查的您網域傳送的郵件。 如需相關資訊，請參閱[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。
