---
title: 整合 Microsoft Defender for Endpoint with 其他 Microsoft 解決方案
description: 瞭解 Microsoft Defender for Endpoint 如何與其他 Microsoft 解決方案（包括 Microsoft Defender 身分識別和 Azure Defender）整合。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender，條件式存取，office，Microsoft Defender for Endpoint，microsoft defender for identity，microsoft defender for office，Azure Defender，microsoft cloud app security，azure sentinel
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
ms.openlocfilehash: 8973a78787345532055161507e2d30f75b3b2cf1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844967"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender for Endpoint 和其他 Microsoft 解決方案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>與其他 Microsoft 解決方案整合

Microsoft Defender for Endpoint 直接與各種 Microsoft 解決方案整合。

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender for Endpoint 提供綜合的伺服器保護解決方案，包括 (Windows 伺服器 EDR) 功能的端點偵測和回應。

### <a name="azure-sentinel"></a>Azure Sentinel
Microsoft Defender for Endpoint connector 可讓您將來自 Microsoft Defender for Endpoint 的警示資料流程成 Azure Sentinel。 這可讓您更深入地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。

### <a name="azure-information-protection"></a>Azure 資訊保護
近來，我們最近取代 Azure 資訊保護整合，因為在端點 DLP 功能中，會針對儲存在端點裝置上的機密資料，結合使用已改善的探索和保護解決方案，以更深入的方式與解決方案之間的整合。 這已于下列 [博客](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)宣告。 我們建議客戶移至使用端點 DLP。

### <a name="conditional-access"></a>條件式存取
Microsoft Defender for Endpoint 的動態裝置風險分數已整合到條件式存取評估中，以確保只有安全裝置能夠存取資源。 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security 利用 Microsoft Defender for endpoint 端點信號，允許直接查看 cloud 應用程式使用方式，包括使用不受支援的雲端服務 (陰影 IT) 從所有 Microsoft Defender for Endpoint 受監視裝置。

### <a name="microsoft-defender-for-identity"></a>適用於身分識別的 Microsoft Defender
可疑活動是指在使用者內容下執行的進程。 Microsoft Defender for Endpoint 和 Microsoft Defender 身分識別之間的整合，可讓您靈活地進行跨活動和身分識別的網路安全性調查。

### <a name="microsoft-defender-for-office"></a>Microsoft Defender Office
[Office 365 的 Defender](/office365/securitycompliance/office-365-atp) ，可透過安全連結、安全附件、高級反網路釣魚和欺騙智慧功能，協助您的組織避免電子郵件中的惡意程式碼。 microsoft defender for Office 365 和 microsoft defender for Endpoint 之間的整合，可讓安全性分析者深入查看攻擊的進入點。 透過威脅智慧共用，攻擊可以包含並封鎖。 

>[!NOTE]
> 在過去30天內顯示事件的 Office 365 資料的 Defender。 針對警示，Office 365 資料的 Defender 會根據第一個啟用時間來顯示。 之後，Office 365 中便無法再使用資料。

### <a name="skype-for-business"></a>商務用 Skype
商務用 Skype 整合提供一種方法，讓分析員透過來自入口網站的簡單按鈕，與可能已遭破壞的使用者或裝置擁有者進行通訊。

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
使用 Microsoft 365 defender 時，microsoft defender for Endpoint 和各種 Microsoft security 解決方案組成的整合發佈前防護套件，可內部整合在端點、身分識別、電子郵件和應用程式中，以偵測、避免、調查和自動回應複雜的攻擊。 
 
[深入瞭解 Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>相關主題
- [設定整合及其他高級功能](advanced-features.md)
- [Microsoft 365Defender 概述](/microsoft-365/security/defender/microsoft-threat-protection)
- [開啟 Microsoft 365 Defender](/microsoft-365/security/defender/mtp-enable)
- [使用條件式存取來保護使用者、資料和裝置](conditional-access.md)
