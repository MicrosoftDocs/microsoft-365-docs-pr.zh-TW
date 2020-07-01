---
title: TLS 1.0 和1.1 已過時的 Office 365
description: 說明 Office 365 的 TLS 1.0 和1.1 棄用。
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
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937328"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>TLS 1.0 和1.1 已過時的 Office 365

從2018年10月31日到，Office 365 服務的傳輸層安全性（TLS）1.0 和1.1 通訊協定已被取代。 對使用者的影響預計會降至最低。 這項變更會在兩年中公佈，第一次公開宣告于12月2017。 本文僅適用于與 Office 365 服務相關的 Office 365 本地用戶端，但是也可以套用至 Office 和 Office Online Server/Office Web Apps 的內部部署 TLS 問題。

## <a name="office-and-tls-overview"></a>Office 和 TLS 概述

Office 用戶端依靠 Windows web 服務（WINHTTP）來傳送和接收透過 TLS 通訊協定的流量。 如果本機電腦的 web 服務可以使用 TLS 1.2，則 Office 用戶端可以使用 TLS 1.2。 所有 Office 用戶端都可以使用 TLS 通訊協定，因為 TLS 和 SSL 通訊協定都是作業系統的一部分，而不是 Office 用戶端特有的。

### <a name="on-windows-8-and-later-versions"></a>在 Windows 8 和更新版本上

根據預設，如果沒有網路裝置設定為拒絕 TLS 1.2 流量，則可以使用 TLS 1.2 和1.1 通訊協定。

### <a name="on-windows-7"></a>在 Windows 7

沒有[KB 3140245](https://support.microsoft.com/help/3140245)更新，TLS 1.1 和1.2 通訊協定無法使用。 此更新會解決此問題，並新增下列登錄子機碼：

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 未安裝此更新的 Windows 7 使用者會受到2018年10月31日的影響。 [KB 3140245](https://support.microsoft.com/help/3140245)具有如何變更 WINHTTP 設定以啟用 TLS 通訊協定的詳細資料。

#### <a name="more-information"></a>其他相關資訊

知識庫文章描述的**DefaultSecureProtocols**登錄機碼值，會決定可以使用的網路通訊協定：

|DefaultSecureProtocols 值|已啟用通訊協定|
|-|-|
|0x00000008|預設啟用 SSL 2.0|
|0x00000020|預設啟用 SSL 3.0|
|0x00000080|預設啟用 TLS 1.0|
|0x00000200|預設啟用 TLS 1.1|
|0x00000800|預設啟用 TLS 1.2|

## <a name="office-clients-and-tls-registry-keys"></a>Office 用戶端和 TLS 登錄機碼

您可以參考[KB 4057306，準備在 Office 365 中對 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306)。 這是 IT 系統管理員的一般文章，也是有關 TLS 1.2 變更的官方檔。

下表顯示在 2018 10 月31日後，Office 365 用戶端中的適當登錄機碼值。

|在2018年10月31日之後啟用 Office 365 服務的通訊協定|十六進位值|
|-|-|
|TLS 1.0 + 1.1 + 1。2|0x00000A80|
|TLS 1.1 + 1。2|0x00000A00|
|TLS 1.0 + 1。2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> 建議您不要使用 SSL 2.0 和3.0 通訊協定，也可以使用**DefaultSecureProtocols**機碼加以設定。 SSL 2.0 和3.0 被視為已被取代的通訊協定。 最佳作法是使用 SSL 2.0 和 SSL 3.0，但決定這項決策最後取決於最符合您產品需求的決策。 如需有關 SSL 3.0 弱點的詳細資訊，請參閱[KB 3009008](https://support.microsoft.com/help/3009008)。

您可以使用 [程式師模式] 中的預設 Windows 計算機設定相同的參照登錄機碼值。 如需詳細資訊，請參閱[KB 3140245 更新，以啟用 tls 1.1 和 tls 1.2 做為 Windows WinHTTP 中的預設安全通訊協定](https://support.microsoft.com/help/3140245)。

不論是否安裝 Windows 7 更新（[KB 3140245](https://support.microsoft.com/help/3140245)），DefaultSecureProtocols 登錄子系統都不存在，必須手動新增或透過群組原則物件（GPO）新增。 也就是說，除非您必須自訂已啟用或限制的安全通訊協定，否則不需要此機碼。 您只需要 Windows 7 SP1 （[KB 3140245](https://support.microsoft.com/help/3140245)）更新。
