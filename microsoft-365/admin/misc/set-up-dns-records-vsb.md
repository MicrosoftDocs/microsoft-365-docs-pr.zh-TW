---
title: 將您的網域連線到 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 上驗證您的網域並建立 DNS 記錄。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658176"
---
# <a name="connect-your-domain-to-microsoft-365"></a>將您的網域連線到 Microsoft 365

> [!NOTE]
> 如果您沒有新增網域，貴組織中的人員將會使用 onmicrosoft.com 網域的電子郵件地址，直到您新增網域為止。 新增使用者之前，請務必先新增您的網域，這樣您就不需要再設定一次。

若您在下方找不到所需內容，請[查看網域常見問題集](../setup/domains-faq.yml)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft

您將會從系統管理中心網域設定向導取得 MX 記錄的資訊。

在您的主機提供者的網站上，新增 MX 記錄。
請確認欄位已設定為下列的值：

- 記錄類型: `MX`
- 優先順序: 設定為可用的最高值，通常為 `0`。
- 主機名稱: `@`
- 指向 [位址]: 從系統管理中心複製值並貼上。
- TTL： `3600‎` （或您的提供者預設值）

儲存記錄，然後移除任何其他的 MX 記錄。

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>新增 CNAME 記錄以將使用者與他們的郵箱連結
您將會從系統管理中心網域設定精靈取得 CNAME 記錄的資訊。

在您的寄存供應商的網站上，新增以下 CNAME 記錄。 請確認每個欄位皆已設定為下列的值：

- 記錄類型: `CNAME (Alias)`
- 主機: 從系統管理中心貼上您複製的值。
- 指向 [位址]: 從系統管理中心複製值並貼上。
- TTL： `3600‎` （或您的提供者預設值）

## <a name="add-a-txt-record-to-help-prevent-spam"></a>新增 TXT 記錄以協助防範垃圾郵件
**在您開始之前:** 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 請改為將所需的 Microsoft 365 值新增到您主機服務提供者網站的目前記錄中，這樣您就有了一份包含兩組值的 *單一* SPF 記錄。

在您的主機提供者網站上，編輯現有 SPF 記錄或建立 SPF 記錄。
請確認欄位已設定為下列的值：

- 記錄類型: `TXT (Text)`
- 主機: `@`
- TXT 值: `v=spf1 include:spf.protection.outlook.com -all`
- TTL： `3600‎` （或您的提供者預設值）

儲存記錄。

透過其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 以驗證您的 SPF 記錄

SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。

若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) 和 [使用 DMARC 在 Microsoft 365 中驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

最後，返回系統管理員中心網域設定精靈以完成你的設定。
