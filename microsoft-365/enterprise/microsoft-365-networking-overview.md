---
title: Microsoft 365 網路連線概況
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 討論為何網路優化對 SaaS 服務、Microsoft 365 網路的目標，以及 SaaS 需要不同的網路與其他工作負載的意義。
ms.openlocfilehash: 4fea7364dc79717583ebca8ce0dbe333ee818f1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688434"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 網路連線能力一覽

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 是一種分散式軟體即服務 (SaaS) 雲端，可透過一組不同的微服務和應用程式來提供生產力與共同作業案例。 Microsoft 365 （如 Outlook、Word 及 PowerPoint）的用戶端元件會在使用者電腦上執行，並連接至 microsoft 資料中心執行的 Microsoft 365 的其他元件。 最重要的因素是判斷 Microsoft 365 使用者體驗的品質為網路可靠性和 Microsoft 365 用戶端與 Microsoft 365 服務前端之間的低延遲。

在本文中，您將瞭解 Microsoft 365 網路的目標，以及為何 Microsoft 365 網路需要不同于一般網際網路流量的優化方法。

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 網路目標

Microsoft 365 網路的最終目標是在用戶端和最接近的 Microsoft 365 端點之間啟用限制性最低的存取，以優化使用者的經驗。 使用者經驗的品質與使用者所使用之應用程式的效能和回應能力直接相關。 例如，Microsoft 小組視低延遲而定，讓使用者電話通話、會議和共用畫面共同作業不會有任何中斷，而 Outlook 則依賴強大的網路連線功能，以進行即時搜尋功能，以利用伺服器端的索引及 AI 功能。

網路設計中的主要目標是將用戶端電腦上的往返時間 (RTT) 減至 Microsoft 全球網路，以減少延遲時間，這是 Microsoft 的公用網路主幹，可將所有的 Microsoft 資料中心互連，以低延遲的方式，高可用性的雲端應用程式進入點遍佈世界各地。 您可以在 [Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 中，深入了解 Microsoft 全域網路。

優化 Microsoft 365 網路效能不需要很複雜。 您可以遵循一些重要的原則，盡可能取得最佳效能：

- 識別 Microsoft 365 網路流量
- 允許從每個使用者連接至 Microsoft 365 的位置，將 Microsoft 365 網路流量的本機分支出口至網際網路
- 允許 Microsoft 365 流量略過 proxy 和封包檢查裝置

如需 Microsoft 365 網路連線原則的詳細資訊，請參閱 [microsoft 365 Network Connectivity 原則](microsoft-365-network-connectivity-principles.md)。

## <a name="traditional-network-architectures-and-saas"></a>傳統的網路架構和 SaaS

傳統的用戶端/伺服器工作負載的網路結構原則，是針對用戶端和端點之間的流量所設計，不會延伸到公司網路周邊外。 此外，在許多商業網路中，所有的輸出網際網路連線都透過公司網路，以及從中心位置出口。

在傳統的網路架構中，一般網際網路流量的較高延遲是為了維護網路周邊安全性所需的權衡性，而 Internet 流量的效能優化通常是在網路出局點升級或擴充設備。 不過，此方法不會解決 SaaS 服務（例如 Microsoft 365）的最佳網路效能需求。

## <a name="identifying-microsoft-365-network-traffic"></a>識別 Microsoft 365 網路流量

我們可讓您更容易識別 Microsoft 365 網路流量，並簡化網路識別碼的管理。

- 新的網路端點類別，讓高緊急的網路流量有別于不受網際網路延遲影響的網路流量。 在最重要的 "Optimize" 類別中，只會有少數 URLs 和支援 IP 位址。
- Web 服務的腳本使用方式或直接裝置設定，以及 Microsoft 365 網路身分識別的變更管理。 您可以從 web 服務或 RSS 格式，或是使用 Microsoft 流程範本的電子郵件，取得變更。
- [Office 365 網路合作夥伴計畫](https://aka.ms/Office365NPP) ，可提供遵循 microsoft 365 網路連線性原則的裝置或服務，並具有簡易的設定。

## <a name="securing-microsoft-365-connections"></a>保護 Microsoft 365 連線

傳統網路安全性的目標是強化公司網路周邊網路，免於入侵和惡意攻擊。 大部分的商業網路會利用類似 proxy 伺服器、防火牆、SSL 中斷及檢查、深度封包檢查和資料遺失防護系統等技術，強制進行網際網路流量的網路安全性。 這些技術為一般網際網路要求提供重要的風險降低，但是當套用至 Microsoft 365 端點時，可能會大幅降低效能、延展性和使用者體驗的品質。

Microsoft 365 可協助滿足您組織的內容安全性和資料使用方式相容性的需求，其採用專為 Microsoft 365 功能和工作負載而設計的內建安全性和控管功能。 如需 Microsoft 365 安全性和合規性的詳細資訊，請參閱 [Office 365 安全性藍圖](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)。 如需 Microsoft 的建議和支援位置的詳細資訊，請參閱在 Microsoft 365 流量上執行高級的處理的高級網路解決方案，請參閱 [使用協力廠商網路裝置或 Office 365 流量的解決方案](https://support.microsoft.com/help/2690045)。

## <a name="why-is-microsoft-365-networking-different"></a>為什麼 Microsoft 365 網路是不同的？

Microsoft 365 的設計是要使用端點安全性和加密網路連線以取得最佳效能，以減少周邊安全性強制執行的需要。 Microsoft 365 資料中心位於世界各地，而且其設計目的是使用各種方法將用戶端連線至最佳可用服務端點。 因為使用者資料與處理是在許多 Microsoft 資料中心之間散佈，所以用戶端電腦不能連接任何單一網路端點。 實際上，microsoft 全球網路的資料和365服務會透過 Microsoft 全球網路進行動態優化，以適應使用者存取使用者的地理位置。

當 Microsoft 365 流量受到封包檢查及集中送出的出入時，就會建立某些常見效能問題：

- 高延遲可能會造成影片和音訊資料流程效能極低，以及資料檢索、搜尋、即時共同作業、行事曆空閒/忙碌資訊、產品內容及其他服務的回應速度很慢
- 從中心位置 Egressing 連線會破壞 Microsoft 365 全域網路的動態路由功能，增加延遲時間和往返時間
- 解密 SSL 安全的 Microsoft 365 網路流量並重新加密可能會造成通訊協定錯誤，並有安全性風險

透過讓用戶端流量盡可能接近其地理位置，縮短 Microsoft 365 進入點的網路路徑，可提高連線效能及 Microsoft 365 中的使用者體驗。 它也有助於減少對 Microsoft 365 效能和可靠性之網路架構的未來變更影響。 最佳連線模型是永遠在使用者的位置提供網路出局，不論這是在公司網路或是家用、旅館、咖啡店和機場等遠端位置。 一般網際網路流量和以 WAN 為基礎的公司網路流量將會分開傳送，不會使用本機直接出局模型。 下圖呈現這個本機直接出口模型。

![本機出口網路架構](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

本機出局架構針對傳統模型上的 Microsoft 365 網路流量，具有下列優點：
  
- 藉由最佳化路由長度，提供最佳的 Microsoft 365 效能。 使用者連線會以 Microsoft 全球網路的 _分散式服務前端_ 基礎結構，動態路由傳送至最接近的 Microsoft 365 進入點，而流量會透過 microsoft 的超低延遲高可用性纖程內部路由傳送至資料和服務端點。
- 透過允許 Microsoft 365 流量的本機出口，以略過代理和流量檢查裝置，減少公司網路基礎結構的負載。
- 利用用戶端端點安全性和雲端安全性功能，以避免應用冗余網路安全性技術，來保護兩端的連線。

> [!NOTE]
> _分散式服務前端_基礎結構是 Microsoft 全球網路的高可用性和可伸縮網路 edge，具有地理位置分散的位置。 它會終止使用者連線，並有效地將其路由傳送至 Microsoft 全球網路中。 您可以在 [Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 中，深入了解 Microsoft 全域網路。

如需瞭解及套用 Microsoft 365 network connectivity 原則的詳細資訊，請參閱 [microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)。

## <a name="conclusion"></a>總結

優化 Microsoft 365 網路效能實際上是為了移除不必要的障礙。 將 Microsoft 365 連線視為信任的流量，可防止資料包檢查和對 proxy 頻寬的競爭帶來延遲。 允許用戶端機器與 Office 365 端點之間的本機連線，可讓流量透過 Microsoft 全球網路動態路由傳送。

## <a name="related-topics"></a>相關主題

[Microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)

[評估 Microsoft 365 網路連線能力](assessing-network-connectivity.md)

[Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)

[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)

[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)

[內容傳遞網路](content-delivery-networks.md)

[Microsoft 365 連線測試](https://aka.ms/netonboard)

[Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 網路部落格](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
