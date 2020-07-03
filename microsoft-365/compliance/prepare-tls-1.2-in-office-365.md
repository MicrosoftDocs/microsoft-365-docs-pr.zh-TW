---
title: 在 Office 365 和 Office 365 GCC 中準備 TLS 1.2
description: 停用 TLS 1.0 和 1.1 支援後，如何準備好以便 Office 365 與 Office 365 GCC 中的所有用戶端-伺服器及瀏覽端伺服器組合可以使用 TLS 1.2。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Office 365 Business
ms.openlocfilehash: d3086c85adf76a322775ce53697504b77e672f9a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024820"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>在 Office 365 和 Office 365 GCC 中準備 TLS 1.2

> [!IMPORTANT]
> 世界正處於疫情大爆發中，Microsoft 公司也意識到了這對客戶與合作夥伴的影響。 為了減輕商業客戶負擔，我們暫時停止了 TLS 1.0和1.1 的取代執法。 當前危機穩定後，將會依照修訂後的時間表發送更新。 （本文已進行修訂以反映變更。）

## <a name="summary"></a>摘要

為了向客戶提供最佳的加密層級，Microsoft 規劃淘汰 Office 365 與 Office 365 GCC 中的傳輸層安全性 (TLS) 1.0 和 1.1 版。 我們明白資料的安全性很重要，也承諾透明公開可能會影響 TLS 服務使用的變更。

[Microsoft TLS 1.0 實作](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)沒有已知的安全性弱點。 但由於未來可能發生通訊協定降級攻擊和其他 TLS 弱點，我們即將終止支援 Microsoft Office 365 與 Office 365 GCC 中的 TLS 1.0 和 1.1。

如需如何刪除 TLS 1.0 和 1.1 相依性的詳細資訊，請參閱下列白皮書：[解決 TLS 1.0 問題](https://www.microsoft.com/download/details.aspx?id=55266)。

## <a name="more-information"></a>其他相關資訊

自 2020 年 1 月起，我們已經開始淘汰 TLS 1.0 和 1.1。 不支援透過 DoD 或 GCC High 執行個體中的 TLS 1.0 或 1.1 連線至 Office 365 的任何用戶端、裝置或服務。 對於 Office 365 商業客戶，我們在 COVID-19 相關疫情穩定下來之前，將會停止強制淘汰 TLS 1.0 和 1.1。

為維持 Office 365 服務連線，我們推薦所有用戶端-伺服器及瀏覽器伺服器組合都使用 TLS 1.2（或更新版本）。 您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。

已知下列用戶端不能使用 TLS 1.2。 請更新用戶端以確保順利存取服務。

- Android 4.3 和舊版
- Firefox 5.0 和舊版
- Windows  7 及舊版中的 Internet Explorer 8-10
- Win Phone 8 中的 Internet Explorer 10
- Safari 6.0.4/OS X10.8.4 和舊版

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>適用於 Microsoft Teams 會議室和 Surface Hub 的 TLS 1.2

自 2018 年 12 月開始，Microsoft Teams 會議室 (先前稱為 Skype Room System V2 SRS V2) 已經支援 TLS 1.2。 建議您在會議室裝置安裝 Microsoft Teams 會議室應用程式 4.0.64.0 版或更新版本。 如需詳細資訊，請參閱[版本資訊](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note)。 變更可與舊版和新版相容。

2019 年 5 月發行的 Surface Hub 支援 TLS 1.2。

Microsoft Teams 會議室和 Surface Hub 產品還需要在伺服器端程式碼進行下列變更，才支援 TLS 1.2：

- 商務用 Skype Online 伺服器變更已於 2019 年 4 月上線。 現在，商務用 Skype Online 支援使用 TLS 1.2 來與 Microsoft Teams 會議室和 Surface Hub 裝置連線。
- 商務用 Skype Server 客戶必須安裝累積更新 (CU)，才能將 TLS 1.2 用於 Teams 會議室系統和 Surface Hub。

  - 若為商務用 Skype Server 2015，CU9 已於 2019 年 5 月發行。
  - 若為商務用 Skype Server 2019，CU1 先前規劃在 2019 年 4 月發行，但已延遲到 2019 年 6 月。

  > [!NOTE]
  > 商務用 Skype 內部部署客戶在為商務用 Skype Server 安裝特定 CU 之前，不應停用 TLS 1.0/1.1。

如果您要在混合情節或動態通訊錄聯合服務 (Active Directory Federation Services) 中使用內部基礎結構，請確定該裝置可以同時支援使用 TLS 1.2 的輸入和輸出連線。

## <a name="references"></a>參考

下列資源提供指引，協助您確定用戶端使用 TLS 1.2 或更新版本及停用 TLS 1.0 和 1.1。

- 對於連線到 Office 365 的 Windows 7 用戶端，請確認 TLS 1.2 是 Windows 中 WinHTTP 的預設安全通訊協定。 如需詳細資訊，請參閱 [KB 3140245 - 更新為 Windows 中的預設安全通訊協定，以啟用 TLS 1.1 和 TLS 1.2 作為預設安全通訊協定](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。
- 若要自移除 TLS 1.0 和 1.1 相依性開始改善 TLS 的使用率，請參閱 [Microsoft 的 TLS](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) 1.2 支援。
- [新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) 可讓您更容易使用薄弱安全性通訊協定，在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上找到連線至服務的用戶端。
- 取得有關如何 [解決 TLS 1.0 問題](https://www.microsoft.com/download/details.aspx?id=55266)的詳細資訊。
- 如需關於安全性的一般資訊，請前往 [Office 365信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。
- [準備 TLS 1.0/1.1 淘汰 – O365 商務用 Skype](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 指南，第 1 部分：為 TLS 1.2 做好準備](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 指南，第 2 部分：正在啟用 TLS 1.2 並辨識不使用 TLS 1.2 的用戶端](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 指南，第 3 部分：關閉 TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [啟用 Office Online Server 中的 TLS 1.1 和 TLS 1.2 支援](https://docs.microsoft.com/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
