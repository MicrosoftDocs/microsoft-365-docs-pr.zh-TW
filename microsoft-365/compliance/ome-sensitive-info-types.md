---
title: 使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要： Office 365 敏感資訊類型的郵件加密原則。
ms.openlocfilehash: a3767fb0f9fe5e565c49db4f9da94d75a3cee8a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601790"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a>使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則

您可以使用 [Exchange 郵件流程規則] 或 [Office 365 資料外洩防護 (DLP) 來建立敏感資訊類型原則與 Office 365 郵件加密。 若要建立 Exchange 郵件流程規則，您可以使用 Exchange 系統管理中心 (EAC) 或 PowerShell。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>若要建立原則在 EAC 中使用郵件流程規則

登入 Exchange 系統管理中心 (EAC)，並移至 [**郵件流程** > **規則**。 在 [規則] 頁面上建立適用於 Office 365 郵件加密的規則。 您可以建立規則，例如目前狀態的特定關鍵字或郵件或附件中的敏感資訊類型的條件為基礎。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>若要建立原則藉由使用 PowerShell 中的郵件流程規則

使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段，連線至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。 使用 Set-irmconfiguration 和 New-transportrule 指令程式來建立原則。

## <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 建立範例郵件流程規則

若要建立 Exchange 郵件流程規則，會自動加密傳送與組織外部的電子郵件的 PowerShell 中執行下列命令*僅加密*如果電子郵件或其附件包含下列的敏感資訊類型的原則：

- 阿拉巴馬州銀行路由號碼
- 信用卡號碼
- 藥物執法機構 (DEA) 編號
- 美國 / 英國 護照號碼
- 美國銀行帳戶號碼
- 美國個別 Taxpayer 識別號碼 (ITIN)
- 美國社會安全號碼 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

如需詳細資訊，請參閱[Set-irmconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)和[New-transportrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)。

## <a name="how-recipients-access-attachments"></a>收件者存取附件的方式

Office 365 加密郵件之後，收件者有不受限制存取附件當他們存取，並開啟其加密的電子郵件。

## <a name="to-prepare-for-this-change"></a>若要準備進行這項變更

若要更新任何適用的使用者文件和訓練資料準備，這項變更您組織中的人員。 視您的使用者與共用這些 Office 365 郵件加密的資源：

- [傳送、 檢視和回覆加密郵件的電腦版 Outlook 中](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 基本版影片： Office 郵件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>稽核記錄中檢視這些變更

Office 365 稽核這項活動，並可供 Office 365 系統管理員。 這項操作是 'New-transportrule' 和程式碼片段的稽核記錄搜尋的安全性 & 合規性中心中來自範例稽核項目是下方：

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>若要停用或自訂的敏感資訊類型原則

一旦您已經建立 Exchange 郵件流程規則，您可以[停用或編輯規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**在 Exchange 系統管理中心 (EAC) 和停用的規則 「*加密外寄機密電子郵件 （超出方塊規則）*」。
