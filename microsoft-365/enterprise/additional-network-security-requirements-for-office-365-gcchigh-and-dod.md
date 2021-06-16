---
title: Office 365 GCC 高 DoD 和的額外網路安全性需求
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要： Office 365 GCC 高及 DoD 具有其他網路安全性需求
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926556"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Office 365 GCC High 和 DOD 的額外網路安全性需求

*本文適用于 Office 365 GCC 高、Office 365 DOD、Microsoft 365 GCC 高及 Microsoft 365 DOD。*

Office 365 GCC 高和 DOD 為安全的雲端環境，可滿足美國政府和其供應商和承包商的需求。  這些雲端環境對允許服務存取的外部端點有額外的網路限制。

GCC使用同盟身分識別或混合共存的高和 DOD 客戶可能需要 Microsoft 允許對您現有內部部署的輸入和/或輸出存取權。  這些活動的範例包括：

* 使用 Active Directory Federation Services 或類似支援的 STS) 的同盟識別碼 (
* 使用內部部署 Exchange Server 或商務用 Skype 部署的混合共存
* 從內部部署系統移轉現有的使用者內容

若要允許服務與您的內部部署端點通訊，您 **必須** 傳送電子郵件給 Office 365 工程進行網路變更。

> [!WARNING]
> 所有要求都有 **三周** 的 SLA，所以由於必要的安全性和合規性控制和部署管線，所以無法加速。  這包括初始上架網路要求，以及遷移至服務之後的任何變更。  確定您的網路小組意識到此時程表，並將其包含在規劃週期中。

使用下列資訊，傳送電子郵件給[Office 365 政府版 Allow-List 要求](mailto:o365gwlt@microsoft.com)：

* **若要**： [Office 365 政府版 Allow-List 要求](mailto:o365gwlt@microsoft.com)
* **來源**：租使用者管理員-傳送電子郵件 **必須** 符合您租使用者中的全域系統管理員連絡人
* **電子郵件主題**： Office 365 GCC 高網路要求-contoso.onmicrosoft.us (以租使用者名稱取代) 

您的郵件本文應包含下列資料：

* 您的 Microsoft Online Services 租使用者名稱 (例如，contoso.onmicrosoft.com、fabrikam.onmicrosoft.us) 
* 一個電子郵件通訊群組清單，Microsoft 會與其通訊，以進行與網路變更和/或追蹤無效子網有關的即時通訊
* 指出您是否計畫使用 Microsoft Teams 與內部部署的混合共存
* 同盟身分識別系統外部可存取的 URL (例如，sts.contoso.com) 和 CIDR 標記法中的 IP 位址範圍 (例如，。 10.1.1.0/28) 
* On-Premises PKI 憑證吊銷清單 URL 與 CIDR 標記法中的 IP 位址範圍
* 以 CIDR 標記法 Exchange Server 內部部署的外部可存取 URL 與 IP 位址範圍
* 以 CIDR 標記法商務用 Skype 內部部署的外部可存取 URL 與 IP 位址範圍

根據安全性和合規性原因，請記住您要求的下列限制：

* 每個租使用者有四個子網限制
* 子網必須是 CIDR 標記法 (例如 10.1.1.0/28) 
* 子網範圍不能大於/24
* 我們 **無法** 容納允許存取商業性雲端服務 (商業 Office 365、Google G 套件、Amazon Web 服務等的要求 ) 

當 Microsoft 收到並核准您的要求之後，會有為期三周的 SLA 可供實施，而且無法加速。  當我們收到您的要求時，您將會收到初始認可，並在完成後確認最後的確認。
