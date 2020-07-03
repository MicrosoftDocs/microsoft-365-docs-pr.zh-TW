---
title: 取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD
description: 討論 Microsoft 如何將日期向前移動，以停止支援在 Office 365 中的 GCC 高端和 DoD 環境中的 TLS 1.1 和1.0，並準備使用 TLS 1.2。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024817"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>取代 TLS 1.0 和 1.1 in Office 365 GCC 高和 DoD

> [!IMPORTANT]
> 世界正處於疫情大爆發中，Microsoft 公司也意識到了這對客戶與合作夥伴的影響。 為了減輕商業客戶負擔，我們暫時停止了 TLS 1.0和1.1 的取代執法。 當前危機穩定後，將會依照修訂後的時間表發送更新。 （本文已進行修訂以反映變更。）

## <a name="summary"></a>摘要

為了遵守聯邦風險和授權管理計畫（FedRAMP）的最新符合性標準，我們在 Microsoft Office 365 中，移至取代 Transport Layer Security （TLS）版本1.1 和1.0，以供 GCC 高和 DoD 環境使用。 這項變更先前是透過 Microsoft 支援宣告的，以 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

我們知道您的資料安全性很重要，我們承諾對可能影響服務使用的變更進行透明性。

雖然[MICROSOFT TLS 1.0 的執行](https://support.microsoft.com/help/3117336)沒有已知的安全性弱點，但仍然會繼續致力於 FedRAMP 規範標準。 因此，我們會在從1.1 年1月15日開始2020，取代環境 DoD 中的 Office 365 中，TLS 和1.0。 如需如何移除 TLS 1.1 和1.0 相依性的相關資訊，請參閱下列白皮書：

[解決 TLS 1.0 問題](https://www.microsoft.com/download/details.aspx?id=55266)

在準備 TLS 1.1 和1.0 的此變更時，建議您改用 TLS 版本1.2。 如需詳細資訊，請參閱[在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

## <a name="more-information"></a>詳細資訊

從2020年1月15日開始，在 GCC 高端和 DoD 環境中的 Office 365 會取代 TLS 1.1 及1.0。

在2020年1月15日，所有用戶端伺服器與瀏覽器伺服器的組合都應該使用 TLS 版本1.2 （或更新版本），以確保所有連線都不會有任何問題給 Office 365 服務。 這可能需要更新用戶端伺服器與瀏覽器伺服器的某些組合。

如果您未更新至 TLS 版本1.2 （或更新版本）于1月 15 2020 日，當您嘗試連線到 Office 365 時，您會遇到問題。 此外，您還必須更新至 TLS 1.2 （或更新版本），以作為解決方法的一部分。

我們知道下列用戶端無法使用 TLS 1.2：

- Android 4.3 和舊版
- Firefox 5.0 和舊版
- Internet Explorer 8 – 10 on Windows 7 及更早版本
- Windows Phone 8.0 上的 Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 及更早版本

建議您更新用戶端，以確保您維護 Office 365 GCC 高和 DoD 的不間斷存取。

[！附注] 目前對 Microsoft Online services 連線的分析顯示，大部分的服務和端點請參閱極少的 TLS 1.1 和1.0 使用量，我們會提供這項變更的通知，讓您在支援 TLS 1.1 和1.0 結束之前，依照需要更新任何受影響的用戶端或伺服器。 如果您正在使用任何內部部署基礎結構的混合式案例或 Active Directory Federation Services （AD FS），請確定基礎結構可以支援使用 TLS 1.2 （或更新版本）的輸入和輸出連線。

除了當您使用無法使用 TLS 1.2 的列出用戶端時，您可能會遇到的停機情形，移除 TLS 1.1 及1.0 將會使您無法使用下列 Microsoft 產品：

- Lync phone

## <a name="references"></a>參考

下列支援文章說明的指導方針與參考，可協助確保用戶端使用 TLS 1.2：

[在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
