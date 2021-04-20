---
title: 成為適用於端點的 Microsoft Defender 合作夥伴
ms.reviewer: ''
description: 深入瞭解整合解決方案與 Microsoft Defender for Endpoint 的步驟和需求，並提供合作夥伴
keywords: partner，integration，方案驗證，認證，需求，成員，misa，應用程式入口網站
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893314"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>成為適用於端點的 Microsoft Defender 合作夥伴

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

若要成為 Defender for Endpoint solution partner，您必須遵循並完成下列步驟。

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>步驟1：訂閱 Endpoint Developer 授權的 Microsoft Defender
訂閱 [Microsoft Defender For Endpoint Developer 授權](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9)。 訂閱功能可讓您使用 Microsoft Defender for Endpoint 租使用者和最多10個裝置，以開發與 Microsoft Defender for Endpoint 整合的解決方案。 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>步驟2：滿足解決方案驗證和認證需求
若要 (讓技術合作夥伴保證整合運作的最佳方式是讓客戶可以在 Microsoft Defender Security Center) 中使用 [協力廠商 [應用程式] 頁面](https://securitycenter.microsoft.com/interoperability/partners)上的 [**建議** 協力廠商] 選項，並將其測試並 demoed 至 microsoft defender for Endpoint 團隊。

一旦 Microsoft Defender for Endpoint 小組已複習並核准整合，我們就會指導您在 Microsoft 智慧型安全性關聯上加入為合作夥伴。

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>步驟3：成為 Microsoft 智慧型 Security Association 成員
[Microsoft 智慧型 Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) 是專為 Microsoft 安全性合作夥伴提供的程式，可協助您豐富安全性產品，並改善客戶對 Microsoft 安全產品的整合。

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>步驟4：在 Microsoft Defender for Endpoint partner 應用程式入口網站中列出
Microsoft Defender for Endpoint 支援協力廠商應用程式探索和整合，其使用內嵌在 Microsoft Defender for Endpoint management 入口網站的產品內 [合作夥伴頁面](partner-applications.md) 。 

若要讓您的公司在產品內第三頁面中列為合作夥伴，您必須提供下列資訊：

1.  (SVG) 的方形標誌。
2. 要呈現之產品的名稱。
3. 提供15個字的產品描述。
4. 連結至客戶的登陸頁面，以完成將會包含足夠資訊給客戶的整合或博客文章。 任何電子報（包括 Microsoft Defender for Endpoint product name）都應該由行銷及工程小組進行審閱。 請至少等候10天，以供審閱程式完成。
5.  如果您使用多承租人 Azure AD 方法，我們將需要 Azure AD 應用程式名稱，以追蹤應用程式的使用量。
6. 在針對 APIs 或圖形安全性 APIs 的每個 API 呼叫中，加入對 Microsoft Defender 所做的 User-Agent 欄位。 這將用於統計用途、疑難排解及夥伴識別。 此外，此步驟是 Microsoft 智慧型 Security Association 中的成員資格 (MISA) 的必要條件。

    請遵循下列步驟：
    
    - 將每個 HTTP 要求標頭中的 [User-Agent] 欄位設定為下列格式。

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - 例如，使用者代理程式： `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - 如需詳細資訊，請參閱 [RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43)。

與 Microsoft Defender for Endpoint 互動，可協助我們的共同客戶進一步簡化、整合和安排防禦。 我們很樂意選擇成為 Microsoft Defender for Endpoint partner，並透過預防和回應新式威脅，達到我們共同保護客戶及其資產的共同目標。

## <a name="related-topics"></a>相關主題
- [技術合作夥伴機會](partner-integration.md)
