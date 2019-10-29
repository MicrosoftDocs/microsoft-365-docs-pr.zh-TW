---
title: Office 365 如何驗證寄地址以防止網路釣魚
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 若要協助防止詐騙，Office 365 和 Outlook.com 現在需要 RFC 規範從： 地址。
ms.openlocfilehash: da1728b59ce100d988538d572a24ca1a44fa9a7b
ms.sourcegitcommit: 96cbcfe8b02a5efc2d5a4fc070753ea96f298fda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749155"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 如何驗證寄地址以防止網路釣魚

Office 365 和 Outlook.com 電子郵件帳戶會收到越來越多大量的網路釣魚攻擊。 網路釣客使用的其中一種技術是要傳送郵件，值的 [從： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。 [從： 地址也稱為 5322.From 地址。 若要協助避免這種類型的網路釣魚，Office 365 和 Outlook.com 需要加入 RFC 不相容服務接收到的郵件從： 解決這篇文章所述。
  
> [!NOTE]
> 本文中的資訊必須要有基本了解一般的電子郵件地址格式。 如需詳細資訊，請參閱[RFC 5322](https://tools.ietf.org/html/rfc5322) （尤其是各節 3.2.3、 3.4、 和 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。 這篇文章是有關針對 5322.From 地址原則強制執行。 本文不需 5321.MailFrom 地址。 
  
不幸的是，仍有一些舊版的電子郵件伺服器在網際網路上繼續傳送 「 合法 」 的電子郵件有遺失的郵件或從格式錯誤： 地址。 如果您定期從組織而言，使用這些舊版的系統接收電子郵件，鼓勵這些組織更新以符合新式的安全性標準其郵件伺服器。
  
Microsoft 將會啟動推出於 2017 年 11 月 9 日本文中所述的原則強制執行。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 如何強制從有效使用： 地址以防止網路釣魚攻擊

Office 365 的方式，它會強制使用的 [寄件者變更： 該函數會收到以更有效率的郵件中的地址會將您防止網路釣魚攻擊。 本文內容：
  
- [所有郵件必須都包含有效的從： 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [[從的格式： 地址如果您未包含的顯示名稱](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [[從的格式： 地址如果加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [其他的有效及無效的範例： 地址](how-office-365-validates-the-from-address.md#Examples)
    
- [隱藏的自動回覆給您的自訂網域，而不中斷 From： 原則](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Office 365 從覆寫： 地址強制執行原則](how-office-365-validates-the-from-address.md#Override)
    
- [防止，並防止 cybercrimes Office 365 中的其他方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
傳送代理另一個使用者不會影響這項變更，如需詳細資訊，請閱讀 Terry Zink 部落格 「[意味著什麼當我們將 「 寄件者 」 的電子郵件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>所有郵件必須都包含有效的從： 地址
<a name="MustIncludeFromAddress"> </a>

某些自動化的郵件未包含 From： 地址時便會被傳送。 在過去，當 Office 365 或 Outlook.com 接收到郵件，但 From 不： 地址，該服務新增從下列預設值： 為了將可傳送作業訊息的地址：
  
```
From: <>
```

啟動 2017 年 11 月 9 日，Office 365 將會推行變更其資料中心及郵件伺服器會強制執行新的規則可其中沒有 From 郵件： 地址不再可接受的 Office 365 或 Outlook.com。 相反地，Office 365 所接收的所有郵件必須已經都包含有效的從： 地址。 否則，郵件會傳送到 Outlook.com 和 Office 365 中的垃圾電子郵件] 或 [刪除的項目資料夾。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>語法概觀： 有效的格式為 [從： Office 365 的地址
<a name="SyntaxOverviewFromAddress"> </a>

從值的格式： 地址在詳細資料中定義跨多個 Rfc。 有許多變化定址和功能可能會視為有效或無效。 若要讓它保持簡單的 Microsoft 建議您使用下列格式和定義：
  
```
From: "displayname " <emailaddress >
```

其中：
  
- （選用） *displayname*是說明擁有者的電子郵件地址的片語。 例如，這可能會更易記的名稱來描述名稱以外，信箱的寄件者。 使用的顯示名稱是選擇性的。 不過，如果您選擇要使用的顯示名稱，Microsoft 建議您，您一律將其括住引號內所示。 
    
- （必要） *emailaddress*組成： 
    
  ```
  local-part @domain
  ```

    其中：
    
  - （必要） *本機組件*是 string，識別會與位址相關聯的信箱。 這是唯一的網域內。 通常，信箱擁有者的使用者名稱或 GUID 用於值為本機組件。 
    
  - （必要） *網域*是主控信箱的電子郵件地址本機部分所識別郵件伺服器的完整網域名稱 (FQDN)。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>[從的格式： 地址如果您未包含的顯示名稱
<a name="FormatNoDisplayName"> </a>

從正確格式化 A： 不會納入的顯示名稱的地址包含只有單一電子郵件地址包含或不含角括弧。 Microsoft 建議您不要以空格分開角括弧。 此外，不包含任何項目後的電子郵件地址。
  
下列範例是有效的：
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

下列範例是有效但不是建議這麼做，因為它包含角括弧和電子郵件地址之間的空格：
  
```
From: < sender@contoso.com >
```

下列範例會無效，因為它會包含文字後的電子郵件地址：
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>[從的格式： 地址如果加上的顯示名稱
<a name="FormatDisplayName"> </a>

針對從： 地址包含顯示名稱的值，適用下列規則：
  
- 如果寄件者地址包含顯示名稱，並顯示名稱包含逗點，顯示名稱必須在引號括住。 例如：
    
    下列範例是有效的：
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    下列範例不是有效的：
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    不圍繞引號括住的顯示名稱，如果該顯示名稱中包含逗點是根據 RFC 5322 無效的。
    
    最佳作法是，不論的顯示名稱前後的放入的引號是否是逗號內的顯示名稱。
    
- 如果寄件者地址中包含的顯示名稱、 電子郵件地址必須內角括弧括住。
    
    最佳作法是，Microsoft 強烈建議您插入的顯示名稱和電子郵件地址之間的空間。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>其他的有效及無效的範例： 地址
<a name="Examples"> </a>

- 有效：
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 無效。 電子郵件地址不是以角括弧括住：
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有效的但不是建議使用。 顯示名稱不是引號括住。 最佳作法是一律用引號括住顯示名稱：
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 無效。 每個項目括有引號，而不只顯示名稱：
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 無效。 有任何電子郵件地址上角括號：
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 無效。 沒有之間的顯示名稱和左的角括弧空間：
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 無效。 沒有顯示名稱前後關閉 quotation mark 和左的角括弧之間的空間。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>隱藏的自動回覆給您的自訂網域，而不中斷 From： 原則
<a name="SuppressAutoReply"> </a>

以新從： 原則強制執行 >，您不能再使用從： \< \>抑制自動回覆。 相反地，您必須設定為 null 的 MX 記錄的自訂網域。
  
郵件交換程式 (MX) 記錄會以識別接收網域的郵件的郵件伺服器的 DNS 記錄的資源。 因為沒有回應的伺服器可以將郵件傳送未發佈的位址，所以，將自然地被抑制自動回覆 （與所有回覆）。
  
當您設定為 null 的 MX 記錄的自訂網域：
  
- 選擇從網域來傳送郵件，不會接受 （接收） 電子郵件。 例如，如果您主要的網域是 contoso.com，您可能會選擇 noreply.contoso.com。
    
- 設定您的網域的 null MX 記錄。 Null 的 MX 記錄所組成單一點，例如：
    
  ```
  noreply.contoso.com IN MX .
  ```

如需發佈 null MX 的詳細資訊，請參閱[RFC 7505](https://tools.ietf.org/html/rfc7505)。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 從覆寫： 地址強制執行原則
<a name="Override"> </a>

推出新原則完成後，您可以只略過此原則的內送郵件，您收到來自 Office 365 使用下列方法之一： 
  
- IP 允許清單
    
- Exchange Online 的郵件流程規則
    
Microsoft 強烈建議您針對覆寫強制使用 [從： 原則。 覆寫此原則可以增加的曝光度垃圾郵件、 網路釣魚及其他 cybercrimes 貴組織的風險。
  
您不能覆寫此原則，針對您在 Office 365 中傳送的外寄郵件。 此外，Outlook.com 不允許覆寫任何種類，甚至是透過支援。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>防止，並防止 cybercrimes Office 365 中的其他方法
<a name="OtherProtection"> </a>

如需有關如何在您可增強您的組織抵禦網路釣魚像 cybercrimes 的詳細資訊，濫發垃圾郵件、 資料外洩，以及其他威脅，請參閱[Office 365 的安全性最佳做法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)。
  
## <a name="related-topics"></a>相關主題

[非法回應郵件與 EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

