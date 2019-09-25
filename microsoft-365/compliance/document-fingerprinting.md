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
# <a name="document-fingerprinting"></a><span data-ttu-id="a2cdd-105">文件指紋</span><span class="sxs-lookup"><span data-stu-id="a2cdd-105">Document Fingerprinting</span></span>

<span data-ttu-id="a2cdd-106">組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-106">Information workers in your organization handle many kinds of sensitive information during a typical day.</span></span> <span data-ttu-id="a2cdd-107">在安全&amp;合规性中心，文档指纹识别通过识别整个组织使用的标准表单，使您能够更轻松地保护此信息。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-107">In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization.</span></span> <span data-ttu-id="a2cdd-108">本主题介绍文档指纹识别背后的概念，以及如何使用 PowerShell 创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-108">This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="a2cdd-109">文件指紋的基本案例</span><span class="sxs-lookup"><span data-stu-id="a2cdd-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="a2cdd-110">文档指纹识别是一种数据丢失防护 （DLP） 功能，可将标准表单转换为敏感信息类型，您可以在 DLP 策略的规则中使用。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-110">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies.</span></span> <span data-ttu-id="a2cdd-111">例如，您可以根據空白專利範本建立文件指紋，然後再建立 DLP 原則，以偵測及封鎖所有填入敏感內容的傳出專利範本。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-111">For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in.</span></span> <span data-ttu-id="a2cdd-112">或者，您可以设置[策略提示，](use-notifications-and-policy-tips.md)以通知发件人他们可能正在发送敏感信息，并且发件人应验证收件人是否有资格接收专利。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-112">Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents.</span></span> <span data-ttu-id="a2cdd-113">此程序適用於您的組織中所使用的任何文字型表單。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-113">This process works with any text-based forms used in your organization.</span></span> <span data-ttu-id="a2cdd-114">您可以上傳的表單還包括：</span><span class="sxs-lookup"><span data-stu-id="a2cdd-114">Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="a2cdd-115">政府表單</span><span class="sxs-lookup"><span data-stu-id="a2cdd-115">Government forms</span></span>
    
- <span data-ttu-id="a2cdd-116">1996 年健康保險流通與責任法案 (HIPAA) 符合性表單</span><span class="sxs-lookup"><span data-stu-id="a2cdd-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="a2cdd-117">人力資源部門的員工資訊表單</span><span class="sxs-lookup"><span data-stu-id="a2cdd-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="a2cdd-118">特別為您的組織建立的自訂表單</span><span class="sxs-lookup"><span data-stu-id="a2cdd-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="a2cdd-119">在理想情況下，您的組織應已建立使用特定表單來傳輸敏感資訊的商業實務準則。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-119">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information.</span></span> <span data-ttu-id="a2cdd-120">上载要转换为文档指纹的空表单并设置相应的策略后，DLP 将检测出站邮件中与该指纹匹配的任何文档。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-120">After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="a2cdd-121">文件指紋的運作方式</span><span class="sxs-lookup"><span data-stu-id="a2cdd-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="a2cdd-122">您可能已猜到文件並沒有實際的指紋，但此名稱仍有助於闡述功能。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-122">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature.</span></span> <span data-ttu-id="a2cdd-123">如同人類的指紋具有獨特的型態，文件也會有獨特的文字模式。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-123">In the same way that a person's fingerprints have unique patterns, documents have unique word patterns.</span></span> <span data-ttu-id="a2cdd-124">上传文件时，DLP 会标识文档中的唯一字型，基于该模式创建文档指纹，并使用该文档指纹检测包含相同模式的出站文档。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-124">When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern.</span></span> <span data-ttu-id="a2cdd-125">正因如此，上載表單或範本能夠產生最有效的文件指紋類型。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-125">That's why uploading a form or template creates the most effective type of document fingerprint.</span></span> <span data-ttu-id="a2cdd-126">每個填寫表單的人都會使用同一組原始文字，然後再將其本身的文字新增至文件中。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-126">Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document.</span></span> <span data-ttu-id="a2cdd-127">只要出站文档不受密码保护，并且包含原始表单中的所有文本，DLP 就可以确定文档是否与文档指纹匹配。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-127">As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="a2cdd-128">下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="a2cdd-129">**比對專利範本之文件指紋的專利文件範例**</span><span class="sxs-lookup"><span data-stu-id="a2cdd-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![文档指纹图.png](media/Document-Fingerprinting-diagram.png)
  
<span data-ttu-id="a2cdd-131">专利模板包含空白字段"专利标题"、"发明者"和"描述"以及每个字段的说明，即"模式"一词。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-131">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern.</span></span> <span data-ttu-id="a2cdd-132">当您上传原始专利模板时，它位于受支持的文件类型之一和纯文本中。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-132">When you upload the original patent template, it's in one of the supported file types and in plain text.</span></span> <span data-ttu-id="a2cdd-133">DLP 将此字模式转换为文档指纹，文档指纹是一个小型 Unicode XML 文件，其中包含表示原始文本的唯一哈希值，指纹将保存为 Active Directory 中的数据分类。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-133">DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory.</span></span> <span data-ttu-id="a2cdd-134">（作为安全措施，原始文档本身不会存储在服务上;仅存储哈希值，并且无法从哈希值重建原始文档。然后，专利指纹将成为您可以与 DLP 策略关联的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-134">(As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy.</span></span> <span data-ttu-id="a2cdd-135">将指纹与 DLP 策略关联后，DLP 会检测任何包含与专利指纹匹配的文档的出站电子邮件，并根据组织的策略处理这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-135">After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="a2cdd-136">例如，您可以設定 DLP 原則，以防止正職員工對外傳送包含專利的郵件。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-136">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents.</span></span> <span data-ttu-id="a2cdd-137">DLP 将使用专利指纹来检测专利并阻止这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-137">DLP will use the patent fingerprint to detect patents and block those emails.</span></span> <span data-ttu-id="a2cdd-138">或者，您可以允許法務部門將專利傳送至其他組織，因為這是業務上的需要。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-138">Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so.</span></span> <span data-ttu-id="a2cdd-139">您可以在 DLP 原則中建立特定部門的例外狀況，以允許這些部門傳送敏感資訊，或者，您可以允許他們以業務理由覆寫原則提示。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-139">You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="a2cdd-140">支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="a2cdd-140">Supported file types</span></span>

<span data-ttu-id="a2cdd-141">文档指纹支持邮件流规则（也称为传输规则）中支持的相同文件类型。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-141">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a2cdd-142">有关支持的文件类型列表，请参阅[邮件流规则内容检查支持的文件类型。](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)</span><span class="sxs-lookup"><span data-stu-id="a2cdd-142">For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).</span></span> <span data-ttu-id="a2cdd-143">关于文件类型的一个快速说明：邮件流规则和文档指纹都不支持 .dotx 文件类型，这可能会令人困惑，因为这是 Word 中的模板文件。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-143">One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word.</span></span> <span data-ttu-id="a2cdd-144">您在本主題和其他文件指紋主題中所看見的「範本」一詞，都是指您建立為標準表單的文件，而不是範本檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-144">When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="a2cdd-145">文件指紋的限制</span><span class="sxs-lookup"><span data-stu-id="a2cdd-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="a2cdd-146">在以下情况下，文档指纹检测不会检测到敏感信息：</span><span class="sxs-lookup"><span data-stu-id="a2cdd-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="a2cdd-147">檔案受密碼保護</span><span class="sxs-lookup"><span data-stu-id="a2cdd-147">Password protected files</span></span>
    
- <span data-ttu-id="a2cdd-148">檔案只包含影像</span><span class="sxs-lookup"><span data-stu-id="a2cdd-148">Files that contain only images</span></span>
    
- <span data-ttu-id="a2cdd-149">文件未包含原始表單中所有用來建立文件指紋的文字</span><span class="sxs-lookup"><span data-stu-id="a2cdd-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="a2cdd-150">使用 PowerShell 创建基于文档指纹的分类规则包</span><span class="sxs-lookup"><span data-stu-id="a2cdd-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="a2cdd-151">请注意，您当前只能通过在安全&amp;合规性中心中使用 PowerShell 来创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-151">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a2cdd-152">要连接，请参阅[连接到安全&合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-152">To connect, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="a2cdd-153">DLP 使用分类规则包来检测敏感内容。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-153">DLP uses classification rule packages to detect sensitive content.</span></span> <span data-ttu-id="a2cdd-154">要基于文档指纹创建分类规则包，请使用**New-Dlp指纹**和新的**Dlp 敏感信息类型**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-154">To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets.</span></span> <span data-ttu-id="a2cdd-155">由于**New-DlpFingerprint**的结果不存储在数据分类规则之外，因此您始终在同一类型中运行**新 DlpFingerprint**和新**Dlp 敏感信息类型**或**Set-Dlp 敏感信息类型**PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-155">Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session.</span></span> <span data-ttu-id="a2cdd-156">下列範例會根據 C:\My Documents\Contoso Employee Template.docx 檔案建立新的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-156">The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx.</span></span> <span data-ttu-id="a2cdd-157">您可以将新指纹存储为变量，以便可以将其与同一 PowerShell 会话中的**New-Dlp 敏感信息类型**cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-157">You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="a2cdd-158">現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="a2cdd-159">现在，您可以使用**Get-Dlp 敏感信息类型**cmdlet 查找所有 DLP 数据分类规则包，在此示例中，"Contoso 客户机密"是数据分类规则包列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="a2cdd-160">最后，将"Contoso 客户机密"数据分类规则包添加到安全&amp;合规性中心的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-160">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a2cdd-161">本示例将规则添加到名为"机密策略"的现有 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-161">This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="a2cdd-162">您还可以在 Exchange Online 中的邮件流规则中使用数据分类规则包，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-162">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example.</span></span> <span data-ttu-id="a2cdd-163">要运行此命令，首先需要连接到[Exchange 在线 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-163">To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a2cdd-164">另请注意，规则包从安全&amp;合规性中心同步到 Exchange 管理中心需要时间。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-164">Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="a2cdd-165">DLP 现在检测与 Contoso 客户表单.docx 文档指纹匹配的文档。</span><span class="sxs-lookup"><span data-stu-id="a2cdd-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="a2cdd-166">有关语法和参数信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a2cdd-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="a2cdd-167">新 Dlp指纹</span><span class="sxs-lookup"><span data-stu-id="a2cdd-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="a2cdd-168">新 Dlp 敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a2cdd-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="a2cdd-169">删除-敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a2cdd-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="a2cdd-170">设置-Dlp 敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a2cdd-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="a2cdd-171">获取-Dlp 敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a2cdd-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
