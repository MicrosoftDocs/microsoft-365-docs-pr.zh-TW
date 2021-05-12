---
title: 停用 Microsoft 365 的 TLS 1.0 和1。1
description: 說明 TLS 1.0 和1.1 已過時和 Microsoft 365 的停用。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332675"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>停用 Microsoft 365 的 TLS 1.0 和1。1

> [!IMPORTANT]
> 由於 COVID-19，我們暫時停止停用的 TLS 1.0 和1.1，以供商務客戶用。 隨著供貨鏈的調整和某些國家的開啟，我們會在10月15日（2020）重新開機 TLS 1.2 強制推出。 在下列星期數和數月內，首展會繼續進行。

從2018年10月31日到，針對 Microsoft 365 服務，已棄用傳輸層安全性 (TLS) 1.0 和1.1 通訊協定。 對使用者的影響很小。 這項變更已于兩年內公佈，第一次公開宣告于12月2017。 本文僅適用于與 Office 365 服務相關的 Office 365 本地用戶端，但是也可以套用至 Office 和 Office Online Server/Office Web Apps 的內部部署 TLS 問題。

針對 SharePoint 和 OneDrive，您必須更新及設定 .NET 以支援 TLS 1.2。 如需詳細資訊，請參閱 [如何在用戶端上啟用 TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

## <a name="office-365-and-tls-overview"></a>Office 365 和 TLS 概述

Office 用戶端依賴 Windows web 服務 (WINHTTP) 以透過 TLS 通訊協定傳送及接收流量。 如果本機電腦的 web 服務可以使用 TLS 1.2，則 Office 用戶端可以使用 TLS 1.2。 所有 Office 用戶端都可以使用 TLS 通訊協定，因為 TLS 和 SSL 通訊協定都是作業系統的一部分，而不是 Office 用戶端特有的。

### <a name="on-windows-8-and-later-versions"></a>在 Windows 8 和更新版本上

根據預設，如果沒有網路裝置設定為拒絕 TLS 1.2 流量，則可以使用 TLS 1.2 和1.1 通訊協定。

### <a name="on-windows-7"></a>在 Windows 7

沒有 [KB 3140245](https://support.microsoft.com/help/3140245) 更新，TLS 1.1 和1.2 通訊協定無法使用。 此更新會解決此問題，並新增下列登錄子機碼：

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 未安裝此更新的 Windows 7 使用者會受到2018年10月31日的影響。 [KB 3140245](https://support.microsoft.com/help/3140245) 具有如何變更 WINHTTP 設定以啟用 TLS 通訊協定的詳細資料。

#### <a name="more-information"></a>其他資訊

知識庫文章描述的 **DefaultSecureProtocols** 登錄機碼值，會決定可以使用的網路通訊協定：

|DefaultSecureProtocols 值|已啟用通訊協定|
|-|-|
|0x00000008|預設啟用 SSL 2.0|
|0x00000020|預設啟用 SSL 3.0|
|0x00000080|預設啟用 TLS 1.0|
|0x00000200|預設啟用 TLS 1.1|
|0x00000800|預設啟用 TLS 1.2|

## <a name="office-clients-and-tls-registry-keys"></a>Office 用戶端和 TLS 登錄機碼

您可以參考 [KB 4057306，準備在 Office 365 中對 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306)。 這是 IT 系統管理員的一般文章，也是有關 TLS 1.2 變更的官方檔。

下表顯示在 2018 10 月31日後，Office 365 用戶端中的適當登錄機碼值。

|在2018年10月31日之後啟用 Office 365 服務的通訊協定|十六進位值|
|-|-|
|TLS 1.0 + 1.1 + 1。2|0x00000A80|
|TLS 1.1 + 1。2|0x00000A00|
|TLS 1.0 + 1。2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> 請勿使用 SSL 2.0 和3.0 通訊協定，也可以使用 **DefaultSecureProtocols** 機碼加以設定。 SSL 2.0 和3.0 被視為過時和不安全的通訊協定。 最佳作法是使用 SSL 2.0 和 SSL 3.0，但決定這項決策最後取決於最符合您產品需求的決策。 如需有關 SSL 3.0 弱點的詳細資訊，請參閱 [KB 3009008](https://support.microsoft.com/help/3009008)。

您可以使用 [程式師模式] 中的預設 Windows 計算機設定相同的參照登錄機碼值。 如需詳細資訊，請參閱 [KB 3140245 更新，以啟用 tls 1.1 和 tls 1.2 做為 Windows WinHTTP 中的預設安全通訊協定](https://support.microsoft.com/help/3140245)。

不論 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) 是否已安裝，DefaultSecureProtocols 登錄子機碼都不存在，必須手動新增，或透過群組原則物件 (GPO) 。 也就是說，除非您必須自訂已啟用或限制的安全通訊協定，否則不需要此機碼。 您只需要 Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 更新。

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>更新及設定 .NET Framework 以支援 TLS 1。2

您必須更新透過 TLS 1.0 或 TLS 1.1 呼叫 Microsoft 365 APIs 的應用程式，才能使用 TLS 1.2。 .NET 4.5 的預設值為 TLS 1.1。 若要更新您的 .NET 設定，請參閱 [如何在用戶端上啟用傳輸層安全性 (TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

## <a name="more-information"></a>其他資訊

如需詳細資訊，請參閱 [在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

## <a name="references"></a>參考

下列資源提供的指導可協助確保用戶端使用 TLS 1.2 或更新版本，以及停用 TLS 1.0 和1.1：

- 對於連線到 Office 365 的 Windows 7 用戶端，請確認 TLS 1.2 是 Windows 中 WinHTTP 的預設安全通訊協定。 如需詳細資訊，請參閱 [KB 3140245-更新啟用 TLS 1.1 和 tls 1.2 做為 Windows WinHTTP 中的預設安全通訊協定](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。
- 若要透過移除 TLS 1.0 和1.1 相依性來處理弱 TLS 使用狀況，請參閱 [Microsoft 的 tls 1.2 支援](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。
- [新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) 可讓您更容易使用薄弱安全性通訊協定，在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上找到連線至服務的用戶端。
- 取得如何 [解決 TLS 1.0 問題的](https://www.microsoft.com/download/details.aspx?id=55266)詳細資訊。
- 如需關於安全性的一般資訊，請前往 [Office 365信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。
- [準備 TLS 1.0/1.1 淘汰 – O365 商務用 Skype](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 指南，第 1 部分：為 TLS 1.2 做好準備](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 指南，第 2 部分：正在啟用 TLS 1.2 並辨識不使用 TLS 1.2 的用戶端](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 指南，第 3 部分：關閉 TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [啟用 Office Online Server 中的 TLS 1.1 和 TLS 1.2 支援](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

