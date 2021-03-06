---
title: 使用 Office 365 郵件加密建立機密資訊類型原則
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
description: 瞭解如何使用 Office 365 郵件加密為組織建立機密資訊類型原則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927741"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>使用郵件加密為組織建立機密資訊類型原則

您可以使用 Exchange 郵件流程規則或資料遺失防護 (DLP) 建立具有 Office 365 郵件加密的敏感資訊類型原則。 若要建立 Exchange 郵件流程規則，您可以使用 Exchange admin center (EAC) 或 PowerShell。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>使用 EAC 中的郵件流程規則建立原則

 (EAC) 登入 Exchange 系統管理中心，然後移至 **郵件流程**  >  **規則**。 在 [規則] 頁面上，建立套用 Office 365 郵件加密的規則。 您可以根據狀況（例如郵件或附件中的某些關鍵字或機密資訊類型的存在性）來建立規則。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>若要使用 PowerShell 中的郵件流程規則建立原則

使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 使用 Set-IRMConfiguration 和 New-TransportRule Cmdlet 來建立原則。

## <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 建立的郵件流程規則範例

在 PowerShell 中執行下列命令，以建立 Exchange 郵件流程規則，此規則會在電子郵件或其附件包含下列機密資訊類型時，自動以 [僅限加密] 選項加密組織外傳送的電子郵件：

- ABA 路由號碼
- 信用卡號碼
- 藥物執行代理商 (DEA) 號碼
- 美國/英國 護照號碼
- 美國銀行帳戶號碼
- ITIN) 的美國個別納稅人識別號碼 (
-  (SSN) 的 U.S. 社會安全號碼

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

如需詳細資訊，請參閱 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 和 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-recipients-access-attachments"></a>收件者如何存取附件

在 Microsoft 加密郵件後，收件者在存取及開啟其加密的電子郵件時，可不受限制地存取附件。

## <a name="to-prepare-for-this-change"></a>準備進行此變更

您可能會想要更新任何適用的使用者檔和訓練材料，以準備組織中的人員進行此項變更。 視您的使用者分享下列 Office 365 郵件加密資源：

- [在電腦的 Outlook 中傳送、查看和回復加密郵件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365Essentials 影片： Office 郵件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>在審核記錄中查看這些變更

Microsoft 365 會審核此活動，並使其可供系統管理員使用。 作業是「New-TransportRule」，而安全性 & 規範中心的「審計記錄」搜尋中的範例審核專案片段如下：

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>停用或自訂敏感資訊類型原則

建立 Exchange 郵件流程規則之後，您可以在 Exchange 系統管理中心 (EAC) 中，移至 [**郵件流程** 規則] 以 [停用或編輯規則](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)，  >  並停用 [*加密輸出的敏感電子郵件 (現成的規則)*] 規則。