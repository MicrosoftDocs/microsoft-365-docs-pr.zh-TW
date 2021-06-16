---
title: Office 365 的外部網域名稱系統記錄
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: 規劃 Office 365 部署時使用的外部網域名稱系統記錄參考清單。
ms.openlocfilehash: 2cbbbcb6105feccdaed1f7b6ce05a84b374024c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926260"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Office 365 的外部網域名稱系統記錄

![網域](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)

**要查看您 Office 365 組織的自訂 DNS 記錄清單嗎？** 您可以 [找出建立 Office 365 DNS 記錄所需的資訊](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) 以用於 Office 365 中的網域。

**需要在網域 DNS 主機 (例如 GoDaddy 或 eNom) 新增這些記錄的逐步說明嗎？** [找出許多常用 DNS 主機的逐步指示連結](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 

**堅持使用自訂部署的參照清單嗎？** 以下清單應用來作為自訂 Office 365 部署的參考。您必須選取套用至組織的記錄，並且填入適當的值。 

**回到** [Office 365 的網路規劃和效能調整](./network-planning-and-performance.md)。

通常，SPF 和 MX 是最難找出的記錄。我們已更新在本文結尾的 SPF 記錄指引。請務必記住，_您的網域只能擁有單一的 SPF 記錄_。您可以有多個 MX 記錄；不過，這是導致郵件傳遞問題的原因。擁有可將電子郵件導向一個郵件系統的單一 MX 記錄可解決許多的潛在問題。
  
以下各節會依 Office 365 中的服務組織。若要查看您網域的 Office 365 DNS 記錄自訂清單，請登入 Office 365 和[收集建立 Office 365 DNS 記錄所需的資訊](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67)。
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Office 365 (核心服務) 所需的外部 DNS 記錄
<a name="BKMK_ReqdCore"> </a>

每個 Office 365 客戶必須將兩筆記錄新增至其外部 DNS。第一個 CNAME 筆記錄可確保 Office 365 可以將工作站新增至適當的身份識別平台。第二個所需的記錄可證明您擁有網域名稱。
  
|**DNS 記錄** <br/> |**用途** <br/> |**要使用的值** <br/> |
|----------|-----------|------------|
|**CNAME** <br/> **(套裝軟體)** <br/> |Office 365 會使用它來將驗證導向正確的身分識別平台。[詳細資訊](../admin/services-in-china/purpose-of-cname.md?viewFallbackFrom=o365-worldwide) <br/> **注意：** 此 CNAME 僅適用於 21Vianet 運作的 Office 365。 [詳細資訊](/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**別名：** msoid  <br/> **目標：** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(網域驗證)** <br/> |Office 365 只會使用它來驗證網域是否歸您所有。不會影響其他任何項目。  <br/> |**主機：**@ (或者對某些 DNS 主機服務提供者來說是您的網域名稱)  <br/> **TXT 值：** _下者提供的文字字串：_ Office 365  <br/> Office 365 [網域設定] 精靈提供用來建立此項記錄的值。  <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Office 365 中電子郵件所需的外部 DNS 記錄 (Exchange Online)
<a name="BKMK_ReqdCore"> </a>

Office 365 中電子郵件需要數個不同的記錄，所有的客戶應使用的三個主要記錄是自動探索、MX 和 SPF 記錄。
  
- **自動探索記錄** 允許用戶端電腦自動尋找 Exchange 並正確地設定用戶端。

- **MX 記錄** 告訴其他郵件系統要將您網域的電子郵件傳送到哪裡。**注意：** 您將電子郵件變更至 Office 365 時，藉由更新您網域的 MX 記錄，所有傳送至該網域的電子郵件都會開始送往 Office 365。  
您只想將一小部分的電子郵件地址切換至 Office 365？ 您可以[使用自訂網域的多個電子郵件地址來試驗 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7)。

- **SPF 的 TXT 記錄**：供收件者電子郵件系統用來驗證傳送您電子郵件的伺服器是否經過您的核准。 這有助於防範電子郵件詐騙和網路釣魚這類問題。 請參閱本文中的 [SPF 所需的外部 DNS 記錄](external-domain-name-system-records.md#BKMK_SPFrecords)，協助您了解記錄中要包括的內容。

使用 Exchange 同盟的電子郵件客戶也必須擁有列在表格底部的額外 CNAME 和 TXT 記錄。
  
|**DNS 記錄** <br/> |**用途** <br/> |**要使用的值** <br/> |
|----------|-----------|------------|
|**CNAME** <br/> **(Exchange Online)** <br/> |使用自動探索服務協助 Outlook 用戶端輕易地與 Exchange Online 服務連接。自動探索會自動為使用者尋找正確的 Exchange Server 主機並設定 Outlook。  <br/> |**別名：** 自動探索  <br/> **目標：** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |將網域的內送郵件傳送到 Office 365 中的 Exchange Online 服務。  <br/> [!NOTE] 一旦電子郵件流向 Exchange Online，您應該移除指向舊系統的 MX 記錄。   |**網域：** 例如，contoso.com  <br/> **目標電子郵件伺服器：**\<MX token\>.mail.protection.outlook.com  <br/> **喜好設定/優先順序：** 低於其他任何 MX 記錄 (這可確保已傳遞郵件至 Exchange Online) - 如 1 或「低」  <br/>  遵循下列步驟來尋找您的 \<MX token\>：  <br/>  登入 Office 365，前往 Office 365 系統管理員\>網域。  <br/>  在您網域的 [動作] 欄中選擇「修正問題」。  <br/>  在 [MX 記錄] 區段中，選擇「我要修正什麼？」  <br/>  遵循此頁面上的指示更新您的 MX 記錄。  <br/> [什麼是 MX 優先順序？](../admin/setup/domains-faq.yml) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |有助於防止他人使用您的網域來傳送垃圾郵件或其他惡意電子郵件。寄件者原則架構 (SPF) 記錄的運作方式是識別取得從網域傳送電子郵件之授權的伺服器。  <br/> |[SPF 所需的外部 DNS 記錄](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(Exchange 同盟)** <br/> |用於混合部署的 Exchange 同盟。  <br/> |**TXT 記錄 1：** 例如，contoso.com 和自訂產生的相關網域證明雜湊文字 (如 Y96nu89138789315669824)  <br/> **TXT 記錄 2：** 例如，exchangedelegation.contoso.com 和自訂產生的相關網域證明雜湊文字 (如 Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(Exchange 同盟)** <br/> |當公司使用 Exchange 同盟時，可藉由使用自動探索服務協助 Outlook 用戶端輕易地與 Exchange Online 服務連接。自動探索會自動為使用者尋找正確的 Exchange Server 主機並設定 Outlook。  <br/> |**別名：** 例如， Autodiscover.service.contoso.com  <br/> **目標：** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>商務用 Skype Online 所需的外部 DNS 記錄
<a name="BKMK_ReqdCore"> </a>

當您使用 [Office 365 URL 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) 時，需採取特定的步驟以確認您的網路已正確設定。

> [!NOTE]
> 這些 DNS 記錄也適用於 Teams，特別是在混合式 Teams 和商務用 Skype 案例中，其中可能會發生某些同盟問題。
  
|**DNS 記錄** <br/> |**用途** <br/> |**要使用的值** <br/> |
|----------|-----------|------------|
|**SRV** <br/> **(商務用 Skype Online)** <br/> |讓您的 Office 365 網域可啟用 SIP 同盟與外部用戶端共用立即訊息 (IM) 功能。了解更多 [Office 365 URL 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)。<br/> |**服務：** sipfederationtls  <br/> **通訊協定：** TCP  <br/> **優先順序：** 100  <br/> **加權：** 1  <br/> **連接埠：** 5061  <br/> **目標：** sipfed.online.lync.com  <br/> **注意：** 如果防火牆或 Proxy 伺服器封鎖外部 DNS 的 SRV 查閱，您應將此記錄新增至內部 DNS 記錄。   |
|**SRV** <br/> **(商務用 Skype Online)** <br/> |商務用 Skype 會使用它來協調 Lync 用戶端之間的資訊流程。  <br/> |**服務：** sip  <br/> **通訊協定：** TLS  <br/> **優先順序：** 100  <br/> **加權：** 1  <br/> **連接埠：** 443  <br/> **目標：** sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **(商務用 Skype Online)** <br/> |Lync 用戶端會使用它來協助尋找商務用 Skype Online 服務並登入。  <br/> |**別名：** sip  <br/> **目標：** sipdir.online.lync.com  <br/> 如需詳細資訊，請參閱 [Office 365 URL 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)。  <br/> |
|**CNAME** <br/> **(商務用 Skype Online)** <br/> |Lync 行動用戶端會使用它來協助尋找商務用 Skype Online 服務並登入。  <br/> |**別名：** lyncdiscover  <br/> **目標：** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Office 365 單一登入所需的外部 DNS 記錄
<a name="BKMK_ReqdCore"> </a>

|**DNS 記錄** <br/> |**用途** <br/> |**要使用的值** <br/> |
|----------|-----------|------------|
|**主機 (A)** <br/> |用於單一登入 (SSO)。它能提供端點給外部部署使用者 (和內部部署使用者，如果您需要)，使其得以連接 Active Directory Federation Services (AD FS) 同盟伺服器 Proxy 或經過負載平衡的虛擬 IP (VIP)。  <br/> |**目標：** 例如，sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>SPF 所需的外部 DNS 記錄
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
> SPF 是設計來協助防止詐騙，但是有 SPF 無法防護的詐騙技術。為了防止這些項目，設定 SPF 之後，您也應該為 Office 365 設定 DKIM 和 DMARC。若要開始使用，請參閱[使用 DKIM 驗證從 Office 365 中的網域傳送的輸出電子郵件](../security/office-365-security/use-dkim-to-validate-outbound-email.md)。接下來，請參閱[使用 DMARC 來驗證 Office 365 中的電子郵件](../security/office-365-security/use-dmarc-to-validate-email.md)。
  
SPF 記錄是 TXT 記錄，有助於防止他人使用您的網域來傳送垃圾郵件或其他惡意電子郵件。寄件者原則架構 (SPF) 記錄的運作方式是識別取得從網域傳送電子郵件之授權的伺服器。
  
您的網域只能有一筆 SPF 記錄 (也就是定義 SPF 的 TXT 記錄)。該單一記錄可以有幾個不同的包含項目，但 DNS 總查詢結果不得超過 10 個 (這有助於防範阻斷服務攻擊)。若要協助您建立或更新環境的正確 SPF 記錄值，請參閱下列表格和其他範例。
  
### <a name="structure-of-an-spf-record"></a>SPF 記錄的結構

所有的 SPF 記錄都包含三個部分，其為 SPF 記錄的宣告、應該傳送電子郵件的網域和 IP 位址，以及強制執行規則。您在有效的 SPF 記錄中需要這三個部分。以下是當您僅使用 Exchange Online 電子郵件時，Office 365 最常見的 SPF 記錄範例：
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

接收來自您網域電子郵件的電子郵件系統會查看 SPF 記錄，如果傳送郵件的電子郵件伺服器是 Office 365 伺服器，則接受郵件。例如，如果傳送郵件的伺服器是您的舊電子郵件系統或網際網路上的惡意系統，SPF 檢查可能會失敗，且無法傳遞郵件。這樣的檢查有助於防止詐騙和網路釣魚郵件。
  
### <a name="choose-the-spf-record-structure-you-need"></a>選擇您所需要的 SPF 記錄結構

在您不只使用 Office 365 的 Exchange Online 電子郵件的情況下，(例如，當您也使用來自 SharePoint Online 的電子郵件時)，使用下表來決定要包含在記錄值中的內容。
  
> [!NOTE]
> 如果您有複雜的案例，包含例如在您的防火牆管理電子郵件流量的 Edge 電子郵件伺服器，您將需要設定更詳細的 SPF 記錄。了解如何：[在 Office 365 中設定 SPF 記錄以協助防範詐騙](../security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md)。您也可以了解更多有關 SPF 使用 Office 365 的方式，請閱讀 [Office 365 如何使用寄件者原則架構 (SPF) 協助防範詐騙](../security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing.md)。
  
| 數字|如果您正在使用...  <br/> |用途  <br/> |新增這些包含項目  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |所有的電子郵件系統 (必要)  <br/> |以此值開頭的所有 SPF 記錄  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (普遍)  <br/> |僅搭配使用 Exchange Online  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |協力廠商電子郵件系統 (較不普遍)  <br/> ||包含：\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |內部部署郵件系統 (較不普遍)  <br/> |如果您正在使用 Exchange Online Protection 或 Exchange Online 加上另一個郵件系統，則請使用  <br/> |ip4：\<0.0.0.0\>  <br/> ip6：\< : : \>  <br/> 包含：\<mail.contoso.com\>  <br/> 括號中的值 (\<\>) 應該是將為您的網域傳送電子郵件的其他郵件系統。  <br/> |
|5  <br/> |所有的電子郵件系統 (必要)  <br/> ||-all  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>範例：新增至現有的 SPF 記錄
<a name="bkmk_addtospf"> </a>

如果您已經有 SPF 記錄，必須新增或更新 Office 365 的值。例如，假設 contoso.com 的現有 SPF 記錄是：
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

現在您要更新 Office 365 的 SPF 記錄。您將編輯目前的記錄，讓 SPF 記錄包含您需要的值。對於 Office 365 為「spf.protection.outlook.com」。
  
正確：
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

不正確：
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>常見 SPF 值的更多範例
<a name="bkmk_addtospf"> </a>

如果您使用完整的 Office 365 套件，並使用 MailChimp 代您傳送行銷電子郵件，您在 contoso.com 的 SPF 記錄會如下所示，其中使用了上表第 1、3 與 5 列的值。請記住，第 1 和第 5 列為必填項。
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

或者，如果您擁有 Exchange 混合式組態，其中電子郵件的傳送來源為 Office 365 及您的內部部署郵件系統，您在 contoso.com 的 SPF 記錄看起來可能如下：
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

以下是一些常見的範例，當您將網域新增至電子郵件的 Office 365 時，可協助您調整現有的 SPF 記錄。如果您有複雜的案例，包含例如在您的防火牆管理電子郵件流量的 Edge 電子郵件伺服器，您將需要設定更詳細的 SPF 記錄。了解如何：[在 Office 365 中設定 SPF 記錄以協助防範詐騙](../security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md)。
  
您可以使用下列短連結返回這裡：[https://aka.ms/o365edns]()
