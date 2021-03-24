---
title: 整合 Microsoft Defender for Endpoint with 其他 Microsoft 解決方案
description: 瞭解 Microsoft Defender for Endpoint 如何與其他 Microsoft 解決方案整合，包括 Microsoft Defender for Identity 和 Azure Security Center。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender，條件式存取，office，高級威脅防護，microsoft defender 身分識別，microsoft defender for office，azure security center，microsoft cloud app security，azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060488"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender for Endpoint 和其他 Microsoft 解決方案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>與其他 Microsoft 解決方案整合

Microsoft Defender for Endpoint 直接與各種 Microsoft 解決方案整合。

### <a name="azure-security-center"></a>Azure 資訊安全中心
Microsoft Defender for Endpoint 提供綜合的伺服器保護解決方案，包括 Windows Server 上的端點偵測和回應 (EDR) 功能。

### <a name="azure-sentinel"></a>Azure Sentinel
Microsoft Defender for Endpoint connector 可讓您將來自 Microsoft Defender for Endpoint 的警示資料流程成 Azure Sentinel。 這可讓您更深入地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。

### <a name="azure-information-protection"></a>Azure 資訊保護
將敏感性資料保持安全，同時透過資料探索和資料保護在工作場所中實現生產力。

### <a name="conditional-access"></a>條件式存取
Microsoft Defender for Endpoint 的動態裝置風險分數已整合到條件式存取評估中，以確保只有安全裝置能夠存取資源。 

### <a name="microsoft-cloud-app-security"></a>Microsoft 雲端應用程式安全性
Microsoft Cloud App Security 利用 Microsoft Defender for Endpoint endpoint 信號來允許直接查看 cloud 應用程式使用情形，包括使用不受支援的雲端服務 (陰影它) 從所有 Microsoft Defender for Endpoint 受監視裝置。

### <a name="microsoft-defender-for-identity"></a>適用於身分識別的 Microsoft Defender
可疑活動是指在使用者內容下執行的進程。 Microsoft Defender for Endpoint 和 Azure ATP 之間的整合，可讓您靈活地進行跨活動和身分識別的網路安全性調查。

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office
[Office 365 的 Defender](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 可協助您的組織避免電子郵件中的惡意程式碼或檔案中的 Atp 安全連結、Atp 安全附件、高級反網路釣魚和欺騙智慧功能。 Office 365 ATP 和 Microsoft Defender for Endpoint 之間的整合，可讓安全性分析師進行上游調查，以調查攻擊的進入點。 透過威脅智慧共用，攻擊可以包含並封鎖。 

>[!NOTE]
> 在過去30天內，會顯示事件的 Defender for Office 365 資料。 針對警示，Office 365 資料的 Defender 會根據第一個啟用時間來顯示。 之後，Office 365 的資料就不再提供。

### <a name="skype-for-business"></a>商務用 Skype
商務用 Skype 整合提供一種方法，讓分析員透過來自入口網站的簡單按鈕，與可能已遭破壞的使用者或裝置擁有者進行通訊。

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
使用 Microsoft 365 Defender 時，Microsoft Defender for Endpoint 和各種 Microsoft security 解決方案組成的整合內發佈的後續企業防護套件，可共同整合在端點、身分識別、電子郵件和應用程式中，以偵測、避免、調查和自動回應複雜的攻擊。 
 
[深入瞭解 Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>相關主題
- [設定整合及其他高級功能](advanced-features.md)
- [Microsoft 365 Defender 概述](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [開啟 Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [使用條件式存取來保護使用者、資料和裝置](conditional-access.md)
