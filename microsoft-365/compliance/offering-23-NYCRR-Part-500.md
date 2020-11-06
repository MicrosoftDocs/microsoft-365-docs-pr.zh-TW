---
title: 標題 23 NYCRR 第 500 部分
description: Microsoft 準備了指南來解釋 Azure、Office 365 和 Power BI 如何協助金融機構符合 23 NYCRR 500 需求。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: fa76fefbeea2c8fc0226a85d5b12599839eba8ca
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920405"
---
# <a name="title-23-nycrr-part-500"></a>第 23 號 NYCRR 第 500 編

## <a name="title-23-nycrr-part-500-overview"></a>標題 23 NYCRR 第 500 部分概觀

In response to the significant and ever-increasing threats to the cybersecurity of information and financial systems, in 2017, the State of New York Department of Financial Services imposed a new set of cybersecurity requirements on financial institutions that are licensed or authorized to do business in the state. This regulation — Title 23 New York Codes, Rules, and Regulation Part 500: Cybersecurity Requirements for Financial Services Companies — is designed to protect customer data and the information technology systems of financial institutions such as state-chartered, private, and international banks, mortgage brokers, and insurance companies.

## <a name="microsoft-and-title-23-nycrr-part-500"></a>Microsoft 和標題 23 NYCRR 第 500 部分

Microsoft provides a comprehensive guide, [Microsoft Cloud Services: Supporting Compliance with NYDFS Cybersecurity Requirements](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides), for financial services regulated under Title 23 NYCRR Part 500. It explains in depth how Azure, Office 365, and Power BI cloud services support compliance with the requirements. Financial institutions that seek to operate in the global financial center of New York must meet them, so compliance is critical for many institutions.

請遵循此指導方針，以加快符合標題 23 NYCRR 第 500 部分：Microsoft 雲端服務：[支援符合 NYDFS 網路安全性需求](https://go.microsoft.com/fwlink/p/?linkid=2098969)

紐約法規要求每個金融機構：

- **Develop and maintain a robust cybersecurity program** starting with an assessment of the institution’s specific risk profile and then designing a program that addresses them. The [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332) was created to help financial services assess the risks of using Microsoft cloud services. It includes direct engagement with our engineers and corporate risk officers and access to our compliance and security experts.
- **Implement a comprehensive cybersecurity policy** that addresses information security, data governance and classification, access controls, business continuity, and the like. Microsoft offers guidance for developing this policy with in-depth information about our certifications and risk assessments; business continuity and disaster recovery metrics; and diagnostics for logging and auditing.
- [指定一名首席資訊安全長 (CISO)](https://go.microsoft.com/fwlink/?LinkId=829185) 以管理網路安全性計畫和強制執行原則。 為協助您的 CISO，Microsoft 透過 **Azure Defender** 、[Office 365 進階威脅分析](https://azure.microsoft.com/services/security-center/?v=17.23h) 和 [Power BI Security](https://docs.microsoft.com/advanced-threat-analytics/)，提供有關 Microsoft 雲端部署的深入網路安全性資訊。
- **Monitor and test the effectiveness of its cybersecurity program** : Microsoft provides information from audits of its cybersecurity practices that include continuous monitoring, periodic penetration testing, and vulnerability assessments. Customers can conduct their own tests without advance permission from Microsoft.
- **Maintain an audit trail.** Built-in audit functionalities of Azure, Office 365, and Power BI customers generate information that can be used to reconstruct financial transactions and develop audit trail information.
- **限制存取包含非公開資訊的資訊系統** ：Azure、Office 365 和 Power BI 提供針對每個服務原生的角色型存取控制 (RBAC) 程序，針對每個 Microsoft 系統管理員的嚴格安全性和存取需求，以及對每項提升權限要求之稽核的量值。
- **制定評估和測試外部開發應用程式安全性的程序** ：針對使用 Visual Studio 的開發人員，受管理程式碼的 [安全性規則](https://docs.microsoft.com/visualstudio/code-quality/security-rules-rule-set-for-managed-code)可協助確保在部署程式碼之前可檢測並減輕應用程式網路安全性威脅。
- **Use periodic risk assessments to design and enhance cybersecurity programs** : For customers, Microsoft aggregates information about security threats, provides roadmaps of change management, and regularly updates information about subcontractors. Microsoft also regularly conducts risk assessments of its own services, the results of which are available to customers.
- **Use qualified personnel to manage cybersecurity risks and oversee cybersecurity functions** : Microsoft employs stringent procedures for our employee access to your customer data. If we hire subcontractors, we remain responsible for service delivery, and ensure that subcontractors fully comply with Microsoft privacy and security commitments, including requirements for handling sensitive data, background checks, and non-disclosure agreements.
- **實作原則和程序以確保協力廠商服務提供者持有資訊安全性** ：Azure、Office 365 和 Power BI 讓多重要素驗證可供所有傳入公司網路的連結使用；實作控制措施 (包括加密) 以保護傳輸到外部網路和待用的非公開資訊，並提供 [Microsoft Online Services 條款](https://aka.ms/Online-Services-Terms)，可為客戶提供通知、事件調查和安全性事件的風險減輕。
- **實作資料保留和刪除原則與程序** ：您永遠可以存取和擷取儲存在 Azure、Office 365 和 Power BI 的客戶資料。
- **Monitor the activity of authorized users, detect unauthorized access, and offer regular cybersecurity awareness training to employees** : Azure, Office 365, and Power BI include outside-in monitoring to raise alerts about incidents, and extensive diagnostics for logging and auditing. [Microsoft Virtual Academy](https://mva.microsoft.com/) offers online training that covers the cybersecurity of Microsoft cloud services.
- **Develop plans to respond to and recover from cybersecurity incidents** : Microsoft helps you prepare for cybersecurity incidents using a defensive strategy to detect, predict, and prevent security breaches before they occur. When developing your own plans, you can draw on our incident management plan for responding to cybersecurity breaches.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://aka.ms/AzureCompliance)
- Intune
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中

## <a name="frequently-asked-questions"></a>常見問題集

**哪些機構受到此法規約束？**

請向紐約金融服務部諮詢[監督對象](https://go.microsoft.com/fwlink/p/?linkid=2099374)，以確定您的機構是否受此法規約束。

## <a name="resources"></a>資源

- [精選資源](https://www.microsoft.com/trustcenter/compliance/NYCRR)
- [紐約州金融服務部 23 NYCRR 500：金融服務公司的網路安全性需求](https://go.microsoft.com/fwlink/p/?linkid=2098976)
- [常見問題集：23 NYCRR 第 500 部分的網路安全性](https://go.microsoft.com/fwlink/p/?linkid=2098977)
- [Microsoft 雲端服務：支援符合 NYDFS 網路安全性需求](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="other-microsoft-resources-for-financial-services"></a>其他適用於金融服務的 Microsoft 資源

- [Microsoft 商務用雲端服務與金融服務](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Microsoft 雲端財務服務合規性計畫](https://www.microsoft.com/download/confirmation.aspx?id=55332)
- [Azure 的金融服務合規性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [共同承擔的雲端運算責任](https://aka.ms/sharedresponsibility)- 
