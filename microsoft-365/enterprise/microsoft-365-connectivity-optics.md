---
title: Microsoft 365連接器件
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 本文包含 Microsoft 365 連線性光學器件的相關資訊。
ms.openlocfilehash: 952990a63d4ad064b2027c6f2364e8082342fa34
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53455974"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365連接器件

本檔說明 Microsoft 通常會從客戶裝置收集的部分連線功能，並說明 Microsoft 使用這類資料分析和優化服務傳遞的一些方式，以及評估並確保最佳的使用者體驗。

連線器件一般會從 Microsoft 應用程式收集，該應用程式可能會安裝在使用者的裝置上，或從瀏覽器存取。 與在 Microsoft 365 服務內選用的資料收集不同的是，此處所述的許多互連器件，都是確保 Microsoft 符合我們對客戶可用性和效能承諾的整數。 這些光學器件可讓 Microsoft 快速偵測和回應使用者與 Microsoft 服務端點之間的連線路徑中的任何問題。 其中一些光學器件也用來啟用[Microsoft 365 系統管理 Center 中的網路](office-365-network-mac-perf-overview.md)連線功能。

## <a name="optics-collected-from-microsoft-365-applications"></a>從 Microsoft 365 應用程式收集的光學器件

目前已透過所有裝置使用不常用的採樣來收集光學器件。 一般來講，根據服務需求及隨機進行抽樣的情況而定，特定的小事情 (服務端點) 所設定的一組特定的光學和目的地。
在每個光學收集間隔中，可能會使用使用者裝置作為度量來源，並使用 Microsoft 365 服務端點收集下列一或多項度量，作為度量目的地：

| 測量 | 描述 |
| --- | --- |
| 延遲 | 透過 HTTP 取得小型檔案所需的時間 |
| 輸送量 | 透過 HTTP 取得較大檔案所花費的時間，極少測量以避免過度的頻寬消耗 |
|  (RTT) 的來回行程時間 | ICMP ping |
| Traceroute | ICMP traceroute |

每個度量通常會與其他資訊相關聯，其中可能包含下列專案：

| 項目 | 描述 |
| --- | --- |
| 租使用者識別碼 | 與使用者裝置相關聯之客戶 Azure Active Directory 租使用者的唯一識別碼。 |
| 監視器識別碼 | 產生要求的應用程式識別碼 (例如 Outlook、OneDrive 等 ) ，由執行度量的用戶端應用程式提供。 |
| 要求識別碼 | 度量要求的識別碼，是由 Microsoft 提供的度量設定所指定。 |
| 遠端 IP | 與用戶端至服務端點之要求相關聯的遮罩來源 IP，由接收計量要求的伺服器提供，並根據 Microsoft 所看到的用戶端來源 IP 位址進行計算。 IP 位址會遮罩為 a/24 子網的 IPv4 位址或 a/48 子網 IPv6 位址，以確保 Microsoft 無法識別個別的裝置或使用者。 |
| 前端 | Microsoft 365 的服務前端識別碼，由接收計量要求的伺服器所提供。 |
| 端點 | Microsoft 365 服務端點位置，由接收計量要求的伺服器所提供。 |
| 憑證發行者 | 連線至服務端點時所呈現之 SSL 憑證的「憑證發行者」屬性，表示向服務端點簽發憑證的憑證授權單位者。 |
| 憑證指紋 | 連線至服務端點時所呈現之 SSL 憑證的「憑證指紋」屬性，它是可公開存取的憑證的唯一識別碼。 |
| 緯度/經度 | 最終使用者裝置的已提取緯度和經度。 這只是針對已在使用者裝置上啟用 Windows 位置服務，且已[在 Microsoft 365 系統管理入口網站中集合此資訊](office-365-network-mac-perf-overview.md#1-enable-windows-location-services)的承租人收集。 |

## <a name="measurement-process"></a>度量過程

每個使用者裝置通常會以排程的方式 (針對已安裝的應用程式來執行度量，或根據載入網頁型應用) 程式 (的瀏覽器頁面的動作來執行) 。 度量活動的執行方式是後臺作業，而不會影響使用者的應用程式經驗。 若要用於此程式特定小小小的測量類型和目的地為隨機性，客戶可能會注意到其地區中的 Microsoft 服務端點要求，與一般應用程式連線的一般使用者裝置的一般要求類似。 此外，客戶可能會注意到在其本地地區以外的 Microsoft 服務端點的要求。 這些度量通常是用來確保客戶要求與最佳服務端點的最佳路由，因為對客戶及 ISP 基礎結構的變更可能需要 Microsoft 不斷變更我們的要求路由原則。 深入瞭解 Microsoft 如何將流量路由傳送至最佳服務端點，以及如何在[Microsoft 365 網路連線概述](microsoft-365-networking-overview.md)中最優化 Microsoft 365 服務的連線能力。

## <a name="service-endpoints"></a>服務端點

在發佈的[Office 365 URLs 和 IP 位址範圍](urls-and-ip-address-ranges.md)內，用作這些測量目標的 Microsoft 服務端點會包含在發佈的中。 您不需要存取其他服務端點，就能提供這些連接器件的集合。
