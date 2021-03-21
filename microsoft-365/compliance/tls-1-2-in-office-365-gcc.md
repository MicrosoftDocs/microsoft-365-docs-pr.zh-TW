---
title: 停用 Microsoft 365 GCC 高和 DoD 中的 TLS 1.0 和1。1
description: 討論 Microsoft 在 Microsoft 365 中如何停用在 GCC 高和 DoD 環境中，對 TLS 1.1 和1.0 的支援。
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919339"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>停用 Microsoft 365 GCC 高和 DoD 中的 TLS 1.0 和1。1

## <a name="summary"></a>摘要

為了遵守聯邦風險和授權管理計畫的最新符合性標準 (FedRAMP) ，我們會停用 Microsoft 365 中的傳輸層安全性 (TLS) 版本1.1 和1.0，以供 GCC 高及 DoD 環境使用。 這項變更先前是透過 Microsoft 支援宣告的，以 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

您的資料安全性很重要，我們承諾對可能影響服務使用的變更進行透明性。

雖然 [MICROSOFT TLS 1.0 的執行](https://support.microsoft.com/help/3117336) 沒有已知的安全性弱點，但仍然會繼續致力於 FedRAMP 規範標準。 因此，我們在1.1 年1月15日在2020和 DoD 環境中停用了 TLS 和 365 1.0。 如需如何移除 TLS 1.1 和1.0 相依性的相關資訊，請參閱下列白皮書：

[解決 TLS 1.0 問題](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>其他資訊

從2020年1月15日開始，在 GCC 高端和 DoD 環境中，Microsoft 365 會停用 TLS 1.1 和1.0。

在2020年1月15日，所有用戶端伺服器與瀏覽器伺服器的組合應該使用 TLS 版本 1.2 (或更新版本) ，以確保所有連線都不會向 Microsoft 365 產生任何問題。 這可能需要更新用戶端伺服器與瀏覽器伺服器的某些組合。

針對 SharePoint 和 OneDrive，您必須更新及設定 .NET 以支援 TLS 1.2。 如需詳細資訊，請參閱 [如何在用戶端上啟用 TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

您必須更新用戶端電腦，以確保您維護 Office 365 GCC 高和 DoD 的不間斷存取。

您必須更新透過 TLS 1.0 或 TLS 1.1 呼叫 Microsoft 365 APIs 的應用程式，才能使用 TLS 1.2。 .NET 4.5 的預設值為 TLS 1.1。 若要更新您的 .NET 設定，請參閱 [如何在用戶端上啟用傳輸層安全性 (TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。 如需詳細資訊，請參閱 [在 Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

我們知道下列用戶端應用程式無法使用 TLS 1.2：

- Android 4.3 和舊版
- Firefox 5.0 和舊版
- Internet Explorer 8 – 10 on Windows 7 及更早版本
- Windows Phone 8.0 上的 Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 及更早版本

[！附注] 目前對 Microsoft Online services 連線的分析顯示，大部分的服務和端點請參閱極少的 TLS 1.1 和1.0 使用量，我們會提供這項變更的通知，讓您在支援 TLS 1.1 和1.0 結束之前，依照需要更新任何受影響的用戶端或伺服器。 如果您使用任何內部部署基礎結構的混合案例或 Active Directory Federation Services (AD FS) ，請確定基礎結構可以支援使用 TLS 1.2 (或更新版本) 的輸入和輸出連線。

除了當您使用無法使用 TLS 1.2 的列出用戶端時，您可能會遇到的停機情形，移除 TLS 1.1 及1.0 將會使您無法使用下列 Microsoft 產品：

- Lync phone

## <a name="references"></a>參考

如需協助及參考以確保用戶端使用的是 TLS 1.2，請參閱在 [Office 365 中準備使用 tls 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。