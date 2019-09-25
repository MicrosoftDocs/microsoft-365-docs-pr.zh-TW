---
title: 文件指紋
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 「文件指紋」可識別您的組織中所使用的標準表單，以協助您保護此類資訊。 本主题介绍文档指纹识别背后的概念，以及如何使用 PowerShell 创建文档指纹。
ms.openlocfilehash: 776410ec042e629e32fa6b03a2cb4fe0f2bacd2e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070110"
---
# <a name="document-fingerprinting"></a>文件指紋

組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 在安全&amp;合规性中心，文档指纹识别通过识别整个组织使用的标准表单，使您能够更轻松地保护此信息。 本主题介绍文档指纹识别背后的概念，以及如何使用 PowerShell 创建文档指纹。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文件指紋的基本案例

文档指纹识别是一种数据丢失防护 （DLP） 功能，可将标准表单转换为敏感信息类型，您可以在 DLP 策略的规则中使用。 例如，您可以根據空白專利範本建立文件指紋，然後再建立 DLP 原則，以偵測及封鎖所有填入敏感內容的傳出專利範本。 或者，您可以设置[策略提示，](use-notifications-and-policy-tips.md)以通知发件人他们可能正在发送敏感信息，并且发件人应验证收件人是否有资格接收专利。 此程序適用於您的組織中所使用的任何文字型表單。 您可以上傳的表單還包括： 
  
- 政府表單
    
- 1996 年健康保險流通與責任法案 (HIPAA) 符合性表單
    
- 人力資源部門的員工資訊表單
    
- 特別為您的組織建立的自訂表單
    
在理想情況下，您的組織應已建立使用特定表單來傳輸敏感資訊的商業實務準則。 上载要转换为文档指纹的空表单并设置相应的策略后，DLP 将检测出站邮件中与该指纹匹配的任何文档。
  
## <a name="how-document-fingerprinting-works"></a>文件指紋的運作方式

您可能已猜到文件並沒有實際的指紋，但此名稱仍有助於闡述功能。 如同人類的指紋具有獨特的型態，文件也會有獨特的文字模式。 上传文件时，DLP 会标识文档中的唯一字型，基于该模式创建文档指纹，并使用该文档指纹检测包含相同模式的出站文档。 正因如此，上載表單或範本能夠產生最有效的文件指紋類型。 每個填寫表單的人都會使用同一組原始文字，然後再將其本身的文字新增至文件中。 只要出站文档不受密码保护，并且包含原始表单中的所有文本，DLP 就可以确定文档是否与文档指纹匹配。
  
下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。
  
**比對專利範本之文件指紋的專利文件範例**

![文档指纹图.png](media/Document-Fingerprinting-diagram.png)
  
专利模板包含空白字段"专利标题"、"发明者"和"描述"以及每个字段的说明，即"模式"一词。 当您上传原始专利模板时，它位于受支持的文件类型之一和纯文本中。 DLP 将此字模式转换为文档指纹，文档指纹是一个小型 Unicode XML 文件，其中包含表示原始文本的唯一哈希值，指纹将保存为 Active Directory 中的数据分类。 （作为安全措施，原始文档本身不会存储在服务上;仅存储哈希值，并且无法从哈希值重建原始文档。然后，专利指纹将成为您可以与 DLP 策略关联的敏感信息类型。 将指纹与 DLP 策略关联后，DLP 会检测任何包含与专利指纹匹配的文档的出站电子邮件，并根据组织的策略处理这些电子邮件。 

例如，您可以設定 DLP 原則，以防止正職員工對外傳送包含專利的郵件。 DLP 将使用专利指纹来检测专利并阻止这些电子邮件。 或者，您可以允許法務部門將專利傳送至其他組織，因為這是業務上的需要。 您可以在 DLP 原則中建立特定部門的例外狀況，以允許這些部門傳送敏感資訊，或者，您可以允許他們以業務理由覆寫原則提示。
  
### <a name="supported-file-types"></a>支援的檔案類型

文档指纹支持邮件流规则（也称为传输规则）中支持的相同文件类型。 有关支持的文件类型列表，请参阅[邮件流规则内容检查支持的文件类型。](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection) 关于文件类型的一个快速说明：邮件流规则和文档指纹都不支持 .dotx 文件类型，这可能会令人困惑，因为这是 Word 中的模板文件。 您在本主題和其他文件指紋主題中所看見的「範本」一詞，都是指您建立為標準表單的文件，而不是範本檔案類型。
  
#### <a name="limitations-of-document-fingerprinting"></a>文件指紋的限制

在以下情况下，文档指纹检测不会检测到敏感信息：
  
- 檔案受密碼保護
    
- 檔案只包含影像
    
- 文件未包含原始表單中所有用來建立文件指紋的文字
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 创建基于文档指纹的分类规则包

请注意，您当前只能通过在安全&amp;合规性中心中使用 PowerShell 来创建文档指纹。 要连接，请参阅[连接到安全&合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

DLP 使用分类规则包来检测敏感内容。 要基于文档指纹创建分类规则包，请使用**New-Dlp指纹**和新的**Dlp 敏感信息类型**cmdlet。 由于**New-DlpFingerprint**的结果不存储在数据分类规则之外，因此您始终在同一类型中运行**新 DlpFingerprint**和新**Dlp 敏感信息类型**或**Set-Dlp 敏感信息类型**PowerShell 会话。 下列範例會根據 C:\My Documents\Contoso Employee Template.docx 檔案建立新的文件指紋。 您可以将新指纹存储为变量，以便可以将其与同一 PowerShell 会话中的**New-Dlp 敏感信息类型**cmdlet 一起使用。 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

现在，您可以使用**Get-Dlp 敏感信息类型**cmdlet 查找所有 DLP 数据分类规则包，在此示例中，"Contoso 客户机密"是数据分类规则包列表的一部分。 
  
最后，将"Contoso 客户机密"数据分类规则包添加到安全&amp;合规性中心的 DLP 策略中。 本示例将规则添加到名为"机密策略"的现有 DLP 策略中。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

您还可以在 Exchange Online 中的邮件流规则中使用数据分类规则包，如以下示例所示。 要运行此命令，首先需要连接到[Exchange 在线 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 另请注意，规则包从安全&amp;合规性中心同步到 Exchange 管理中心需要时间。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP 现在检测与 Contoso 客户表单.docx 文档指纹匹配的文档。
  
有关语法和参数信息，请参阅：

- [新 Dlp指纹](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [新 Dlp 敏感信息类型](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [删除-敏感信息类型](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [设置-Dlp 敏感信息类型](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [获取-Dlp 敏感信息类型](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
