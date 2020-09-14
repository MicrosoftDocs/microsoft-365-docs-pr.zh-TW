---
title: 適用於 Exchange Server 的 GDPR
description: 了解如何滿足內部部署 Exchange Server 的 GDPR 要求，例如刪除項目保留和自動資料收集。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7d2f482ad06f9ed44467795f310aecb2c44eea0d
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547319"
---
# <a name="gdpr-for-exchange-server"></a>適用於 Exchange Server 的 GDPR

在保護個人資訊時，我們建議下列事項：

-   在 Exchange Server 中使用[保留標記和原則](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx)，以實作電子郵件生命週期原則。

-   部署[資訊版權管理](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx)，以限制誰可以存取儲存在 Exchange Server 中的資訊。

-   在您的伺服器上啟用 [BitLocker 加密](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/)。

## <a name="identifying-in-scope-content"></a>識別範圍內的內容

Exchange 針對使用者產生的內容使用兩個主要儲存存放庫：信箱和公用資料夾。儲存在個別使用者信箱中的內容是唯一關聯至該使用者，並且代表他們在 Exchange 內的預設存放庫。儲存在使用者信箱的資料包括使用下列應用程式建立的內容：Outlook、網頁版 Outlook (先前稱為 Outlook Web App)、Exchange ActiveSync、商務用 Skype 用戶端及使用 POP、IMAP 或 Exchange Web 服務 (EWS) 連線到 Exchange Server 的其他第三方工具。這些項目的範例包括：郵件、行事曆項目 (會議和約會)、連絡人、備忘稿及工作。刪除個別使用者的信箱會移除使用者所產生的內容或直接傳送到使用者信箱中的內容。您可以藉由使用 Exchange 系統管理中心 (EAC) 或者在 Exchange 管理命令介面中使用 [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/remove-mailbox) Cmdlet，來刪除使用者信箱。
附註：使用 Remove-Mailbox Cmdlet 上的 Permanent 參數時應該小心謹慎，因為如果使用此選項，資料就無法復原。

Exchange 也提供共用信箱，可以讓一或多個使用者存取以傳送及接收儲存在共用信箱中的內容。共用信箱是唯一的實體，未與單一帳戶相關聯。而是將權限授與多個使用者，以傳送、接收及檢閱共用信箱中的電子郵件內容。共用信箱是透過 Exchange 系統管理中心和用於管理一般使用者信箱的相同 Cmdlet 來進行管理。如果您需要從信箱移除個別訊息，依據 Exchange 版本而定，還有不同的選項可用。在 Exchange Server 2010 和 2013 中，您可以使用 [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) Cmdlet 與 DeleteContent 參數來識別信箱中的訊息並且將其移除。在 Exchange Server 2016 及更新版本中，您必須使用 [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx) 功能。

公用資料夾是未與特定使用者相關聯的共用儲存實作。而是將公用資料夾的存取權授與使用者以產生內容。公用資料夾的實際實作會因 Exchange 版本而有所不同 (Exchange Server 2010 使用與 Exchange Server 2013 及更新版本不同的實作)。用來管理公用資料夾中內容的工具有限制。用戶端工具 (例如 Outlook) 是管理公用資料夾中內容的主要機制。有 Cmdlet 可以管理公用資料夾物件，但是無法管理公用資料夾內的個別內容項目。可能需要利用 Exchange Web 服務 (EWS) 的自訂指令碼或其他第三方工具，才能管理個別公用資料夾項目。

主要需求是管理個別使用者信箱內容。這個需求可以透過您一般用來管理信箱的圖形化或 Cmdlet 式工具輕易地解決。如果您需要處理多個信箱或資源類型之間的內容，[eDiscovery](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) 是在 Exchange 內用來識別範圍中內容的偏好機制。

## <a name="deleted-item-retention"></a>刪除項目保留

當您從信箱刪除個別訊息或項目時 (不是整個信箱或公用資料夾資源本身)，內容會根據信箱資料庫或公用資料夾資料庫的 DeletedItemRetention 參數值，以可復原的形式保留。預設值是 14 天，但是這個值可以由 Exchange 系統管理員設定。

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>移除虛刪除和中斷連線的信箱

當 Exchange 信箱停用、刪除或在資料庫之間移動時 (例如，負載平衡的其中一個操作)，信箱會根據作業處於停用、虛刪除或中斷連線狀態。當信箱處於上述任何一種狀態時，Exchange 會根據目前在信箱資料庫上指定的 MailboxRetention 參數值，維護信箱 (包括其內容)。預設值是 30 天，但是這個值可以由 Exchange 系統管理員設定。您可以使用 [Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/remove-storemailbox) Cmdlet，在保留期間自然到期之前，強制 Exchange 永久移除 (清除) 與信箱相關聯的所有資料。

> [!IMPORTANT]
> 使用 Remove-StoreMailbox Cmdlet 時請小心謹慎，因為它會導致目標信箱的無法復原資料遺失。 

## <a name="on-prem-to-cloud-migrations"></a>內部部署到雲端的移轉

從 Exchange Server 將資料移轉至 Exchange Online 時，移轉的資料會繼續以 Exchange 系統管理員可以復原的形式，存在於來源內部部署 Exchange Server。根據預設，此資料在 30 天內會自動從資料庫中移除 (請參閱上述的「虛刪除和中斷連線的信箱」)。

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Exchange Server 向 Microsoft 報告的自動資料收集

在內部部署環境中部署的 Exchange Server，不會向 Microsoft 提供任何類型的自動化報告或使用者資料擷取。在 Windows 作業系統中啟用 Watson 損毀傾印報告的 Exchange Server，可能會在產生損毀報告時收到有限的記憶體內容。
