---
title: 文件指紋
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 「文件指紋」可識別您的組織中所使用的標準表單，以協助您保護此類資訊。 本主題說明文件指紋背後的概念，以及如何使用 PowerShell 建立一個概念。
ms.openlocfilehash: 392b42e779de249dddc0acb4c7c757a009f9f743
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086736"
---
# <a name="document-fingerprinting"></a>文件指紋

組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。 在安全性與 &amp; 合規性中心，記錄指紋可讓您透過識別整個組織中所使用的標準表單，來保護這項資訊。 本主題說明文件指紋背後的概念，以及如何使用 PowerShell 建立一個概念。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文件指紋的基本案例

檔指紋為數據遺失防護 (DLP) 功能會將標準表單轉換成敏感資訊類型，您可以在 DLP 原則的規則中使用。 例如，您可以根據空白專利範本建立文件指紋，然後再建立 DLP 原則，以偵測及封鎖所有填入敏感內容的傳出專利範本。 您也可以設定 [原則提示](use-notifications-and-policy-tips.md) ，以通知寄件者他們可能會傳送敏感資訊，而寄件者應確認收件者有資格接收專利權。 此程序適用於您的組織中所使用的任何文字型表單。 您可以上傳的表單還包括：
  
- 政府表單
- 1996 年健康保險流通與責任法案 (HIPAA) 符合性表單  
- 人力資源部門的員工資訊表單
- 特別為您的組織建立的自訂表單

在理想情況下，您的組織應已建立使用特定表單來傳輸敏感資訊的商業實務準則。 在您上載空白表單轉換為檔指紋並設定對應的原則之後，DLP 便會偵測輸出郵件中符合該指紋的任何檔。

## <a name="how-document-fingerprinting-works"></a>文件指紋的運作方式

您可能已猜到文件並沒有實際的指紋，但此名稱仍有助於闡述功能。 如同人類的指紋具有獨特的型態，文件也會有獨特的文字模式。 當您上傳檔案時，DLP 會識別檔中的唯一字模式、根據該模式建立檔指紋，並使用該檔指紋來偵測包含相同模式的輸出檔案。 正因如此，上載表單或範本能夠產生最有效的文件指紋類型。 每個填寫表單的人都會使用同一組原始文字，然後再將其本身的文字新增至文件中。 只要輸出檔案不受密碼保護，且包含原始表單中的所有文字，DLP 便可判斷檔是否符合檔指紋。

> [!IMPORTANT]
> 現在，DLP 只能在 Exchange online 中使用檔指紋作為偵測方法。

下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>比對專利範本之文件指紋的專利文件範例

![檔指紋的圖表。](../media/Document-Fingerprinting-diagram.png)
  
「專利範本」會包含空白欄位「專利職稱」、「Inventors」和「描述」，以及每個欄位的描述（即 word 模式）。 當您上傳原始的專利權範本時，它會以其中一個支援的檔案類型和純文字格式。 DLP 會將此文字模式轉換成檔指紋，這是一個包含原始文字的唯一雜湊值的小型 Unicode XML 檔案，而且指紋會儲存為 Active Directory 中的資料分類。  (做為安全性的措施，原始檔案本身不會儲存在服務上;只會儲存雜湊值，而且無法從雜湊值重新建立原始檔案。 ) 專利指紋會變成機密資訊類型，您可以將其與 DLP 原則產生關聯。 將指紋與 DLP 原則建立關聯之後，DLP 便會偵測任何包含符合專利指紋之檔的外寄電子郵件，並根據組織的原則處理這些檔。 

例如，您可以設定 DLP 原則，以防止正職員工對外傳送包含專利的郵件。 DLP 將使用專利指紋來偵測專利權，並封鎖這些電子郵件。 或者，您可以允許法務部門將專利傳送至其他組織，因為這是業務上的需要。 您可以在 DLP 原則中建立特定部門的例外狀況，以允許這些部門傳送敏感資訊，或者，您可以允許他們以業務理由覆寫原則提示。
  
### <a name="supported-file-types"></a>支援的檔案類型

檔指紋支援的檔案類型與郵件流程規則中支援的檔案類型相同 (也稱為 transport rules) 。 如需支援的檔案類型清單，請參閱 [郵件流程規則內容檢查支援的檔案類型](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。 有關檔案類型的快速附注：郵件流程規則或檔指紋都不支援 dotx 檔案類型，因為這是 Word 的範本檔案，所以很容易混淆。 您在本主題和其他文件指紋主題中所看見的「範本」一詞，都是指您建立為標準表單的文件，而不是範本檔案類型。
  
#### <a name="limitations-of-document-fingerprinting"></a>文件指紋的限制

檔指紋在下列情況下將不會偵測到敏感資訊：
  
- 檔案受密碼保護
- 檔案只包含影像
- 文件未包含原始表單中所有用來建立文件指紋的文字
- 大於 10 MB 的檔案

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 建立以檔指紋為基礎的分類規則套件

請注意，目前您可以使用安全性與合規性中心的 PowerShell，只建立檔指紋 &amp; 。 若要連線，請參閱[連線 to Security & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)]。

DLP 使用分類規則套件來偵測敏感內容。 若要根據檔指紋建立分類規則套件，請使用 **新的-DlpFingerprint** 和 **DlpSensitiveInformationType** Cmdlet。 由於 **DlpFingerprint** 的結果不會儲存在資料分類規則之外，因此您必須在相同的 PowerShell 會話中執行 **new-DlpFingerprint** and **new-DlpSensitiveInformationType** 或 **Set DlpSensitiveInformationType** 。 下列範例會根據 C:\My Documents\Contoso Employee Template.docx 檔案建立新的文件指紋。 您可以將新的指紋儲存為變數，以便在同一 PowerShell 會話中搭配 **新的 DlpSensitiveInformationType** Cmdlet 使用。
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

您現在可以使用 **DlpSensitiveInformationType** Cmdlet 來尋找所有 DLP 資料分類規則套件，在此範例中，「Contoso 客戶機密」是「資料分類規則套件」清單的一部分。 
  
最後，在安全性與合規性中心將「Contoso 客戶機密」資料分類規則套件新增至 DLP 原則 &amp; 。 這個範例會將規則新增至名為 "ConfidentialPolicy" 的現有 DLP 原則中。

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

您也可以在 Exchange Online 中使用郵件流程規則中的資料分類規則套件，如下列範例所示。 若要執行這個命令，您必須先[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 另外請注意，規則套件從安全性合規性中心同步處理至 Exchange 系統管理中心所需的時間 &amp; 。
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP 現在會偵測符合 Contoso 客戶 Form.docx 檔指紋的檔。
  
如需語法及參數的資訊，請參閱：

- [新 DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [新 DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
