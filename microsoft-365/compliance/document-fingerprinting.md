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
ms.openlocfilehash: 1542b956d0a1f662e059ca59ea346a8afc439c83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918499"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="1f796-105">文件指紋</span><span class="sxs-lookup"><span data-stu-id="1f796-105">Document Fingerprinting</span></span>

<span data-ttu-id="1f796-106">組織中的資訊工作者在其日常工作中會處理許多不同的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="1f796-106">Information workers in your organization handle many kinds of sensitive information during a typical day.</span></span> <span data-ttu-id="1f796-107">在安全性與 &amp; 合規性中心，記錄指紋可讓您透過識別整個組織中所使用的標準表單，來保護這項資訊。</span><span class="sxs-lookup"><span data-stu-id="1f796-107">In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization.</span></span> <span data-ttu-id="1f796-108">本主題說明文件指紋背後的概念，以及如何使用 PowerShell 建立一個概念。</span><span class="sxs-lookup"><span data-stu-id="1f796-108">This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="1f796-109">文件指紋的基本案例</span><span class="sxs-lookup"><span data-stu-id="1f796-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="1f796-110">檔指紋為數據遺失防護 (DLP) 功能會將標準表單轉換成敏感資訊類型，您可以在 DLP 原則的規則中使用。</span><span class="sxs-lookup"><span data-stu-id="1f796-110">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies.</span></span> <span data-ttu-id="1f796-111">例如，您可以根據空白專利範本建立文件指紋，然後再建立 DLP 原則，以偵測及封鎖所有填入敏感內容的傳出專利範本。</span><span class="sxs-lookup"><span data-stu-id="1f796-111">For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in.</span></span> <span data-ttu-id="1f796-112">您也可以設定 [原則提示](use-notifications-and-policy-tips.md) ，以通知寄件者他們可能會傳送敏感資訊，而寄件者應確認收件者有資格接收專利權。</span><span class="sxs-lookup"><span data-stu-id="1f796-112">Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents.</span></span> <span data-ttu-id="1f796-113">此程序適用於您的組織中所使用的任何文字型表單。</span><span class="sxs-lookup"><span data-stu-id="1f796-113">This process works with any text-based forms used in your organization.</span></span> <span data-ttu-id="1f796-114">您可以上傳的表單還包括：</span><span class="sxs-lookup"><span data-stu-id="1f796-114">Additional examples of forms that you can upload include:</span></span>
  
- <span data-ttu-id="1f796-115">政府表單</span><span class="sxs-lookup"><span data-stu-id="1f796-115">Government forms</span></span>
- <span data-ttu-id="1f796-116">1996 年健康保險流通與責任法案 (HIPAA) 符合性表單</span><span class="sxs-lookup"><span data-stu-id="1f796-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>  
- <span data-ttu-id="1f796-117">人力資源部門的員工資訊表單</span><span class="sxs-lookup"><span data-stu-id="1f796-117">Employee information forms for Human Resources departments</span></span>
- <span data-ttu-id="1f796-118">特別為您的組織建立的自訂表單</span><span class="sxs-lookup"><span data-stu-id="1f796-118">Custom forms created specifically for your organization</span></span>

<span data-ttu-id="1f796-119">在理想情況下，您的組織應已建立使用特定表單來傳輸敏感資訊的商業實務準則。</span><span class="sxs-lookup"><span data-stu-id="1f796-119">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information.</span></span> <span data-ttu-id="1f796-120">在您上載空白表單轉換為檔指紋並設定對應的原則之後，DLP 便會偵測輸出郵件中符合該指紋的任何檔。</span><span class="sxs-lookup"><span data-stu-id="1f796-120">After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>

## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="1f796-121">文件指紋的運作方式</span><span class="sxs-lookup"><span data-stu-id="1f796-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="1f796-122">您可能已猜到文件並沒有實際的指紋，但此名稱仍有助於闡述功能。</span><span class="sxs-lookup"><span data-stu-id="1f796-122">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature.</span></span> <span data-ttu-id="1f796-123">如同人類的指紋具有獨特的型態，文件也會有獨特的文字模式。</span><span class="sxs-lookup"><span data-stu-id="1f796-123">In the same way that a person's fingerprints have unique patterns, documents have unique word patterns.</span></span> <span data-ttu-id="1f796-124">當您上傳檔案時，DLP 會識別檔中的唯一字模式、根據該模式建立檔指紋，並使用該檔指紋來偵測包含相同模式的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="1f796-124">When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern.</span></span> <span data-ttu-id="1f796-125">正因如此，上載表單或範本能夠產生最有效的文件指紋類型。</span><span class="sxs-lookup"><span data-stu-id="1f796-125">That's why uploading a form or template creates the most effective type of document fingerprint.</span></span> <span data-ttu-id="1f796-126">每個填寫表單的人都會使用同一組原始文字，然後再將其本身的文字新增至文件中。</span><span class="sxs-lookup"><span data-stu-id="1f796-126">Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document.</span></span> <span data-ttu-id="1f796-127">只要輸出檔案不受密碼保護，且包含原始表單中的所有文字，DLP 便可判斷檔是否符合檔指紋。</span><span class="sxs-lookup"><span data-stu-id="1f796-127">As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f796-128">現在，DLP 可以在 Exchange online 中使用檔指紋作為偵測方法。</span><span class="sxs-lookup"><span data-stu-id="1f796-128">For now, DLP can use document fingerprinting as a detection method in Exchange online only.</span></span>

<span data-ttu-id="1f796-129">下列範例說明您根據專利範本建立文件指紋時所將發生的情況；但實際上您可使用任何表單作為建立文件指紋的基礎。</span><span class="sxs-lookup"><span data-stu-id="1f796-129">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a><span data-ttu-id="1f796-130">比對專利範本之文件指紋的專利文件範例</span><span class="sxs-lookup"><span data-stu-id="1f796-130">Example of a patent document matching a document fingerprint of a patent template</span></span>

![Document-Fingerprinting-diagram.png](../media/Document-Fingerprinting-diagram.png)
  
<span data-ttu-id="1f796-132">「專利範本」會包含空白欄位「專利職稱」、「Inventors」和「描述」，以及每個欄位的描述（即 word 模式）。</span><span class="sxs-lookup"><span data-stu-id="1f796-132">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern.</span></span> <span data-ttu-id="1f796-133">當您上傳原始的專利權範本時，它會以其中一個支援的檔案類型和純文字格式。</span><span class="sxs-lookup"><span data-stu-id="1f796-133">When you upload the original patent template, it's in one of the supported file types and in plain text.</span></span> <span data-ttu-id="1f796-134">DLP 會將此文字模式轉換成檔指紋，這是一個包含原始文字的唯一雜湊值的小型 Unicode XML 檔案，而且指紋會儲存為 Active Directory 中的資料分類。</span><span class="sxs-lookup"><span data-stu-id="1f796-134">DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory.</span></span> <span data-ttu-id="1f796-135"> (做為安全性的措施，原始檔案本身不會儲存在服務上;只會儲存雜湊值，而且無法從雜湊值重新建立原始檔案。 ) 專利指紋會變成機密資訊類型，您可以將其與 DLP 原則產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1f796-135">(As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy.</span></span> <span data-ttu-id="1f796-136">將指紋與 DLP 原則建立關聯之後，DLP 便會偵測任何包含符合專利指紋之檔的外寄電子郵件，並根據組織的原則處理這些檔。</span><span class="sxs-lookup"><span data-stu-id="1f796-136">After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="1f796-137">例如，您可以設定 DLP 原則，以防止正職員工對外傳送包含專利的郵件。</span><span class="sxs-lookup"><span data-stu-id="1f796-137">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents.</span></span> <span data-ttu-id="1f796-138">DLP 將使用專利指紋來偵測專利權，並封鎖這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1f796-138">DLP will use the patent fingerprint to detect patents and block those emails.</span></span> <span data-ttu-id="1f796-139">或者，您可以允許法務部門將專利傳送至其他組織，因為這是業務上的需要。</span><span class="sxs-lookup"><span data-stu-id="1f796-139">Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so.</span></span> <span data-ttu-id="1f796-140">您可以在 DLP 原則中建立特定部門的例外狀況，以允許這些部門傳送敏感資訊，或者，您可以允許他們以業務理由覆寫原則提示。</span><span class="sxs-lookup"><span data-stu-id="1f796-140">You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="1f796-141">支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="1f796-141">Supported file types</span></span>

<span data-ttu-id="1f796-142">檔指紋支援的檔案類型與郵件流程規則中支援的檔案類型相同 (也稱為 transport rules) 。</span><span class="sxs-lookup"><span data-stu-id="1f796-142">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1f796-143">如需支援的檔案類型清單，請參閱 [郵件流程規則內容檢查支援的檔案類型](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。</span><span class="sxs-lookup"><span data-stu-id="1f796-143">For a list of supported file types, see [Supported file types for mail flow rule content inspection](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).</span></span> <span data-ttu-id="1f796-144">有關檔案類型的快速附注：郵件流程規則或檔指紋都不支援 dotx 檔案類型，因為這是 Word 的範本檔案，所以很容易混淆。</span><span class="sxs-lookup"><span data-stu-id="1f796-144">One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word.</span></span> <span data-ttu-id="1f796-145">您在本主題和其他文件指紋主題中所看見的「範本」一詞，都是指您建立為標準表單的文件，而不是範本檔案類型。</span><span class="sxs-lookup"><span data-stu-id="1f796-145">When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="1f796-146">文件指紋的限制</span><span class="sxs-lookup"><span data-stu-id="1f796-146">Limitations of document fingerprinting</span></span>

<span data-ttu-id="1f796-147">檔指紋在下列情況下將不會偵測到敏感資訊：</span><span class="sxs-lookup"><span data-stu-id="1f796-147">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="1f796-148">檔案受密碼保護</span><span class="sxs-lookup"><span data-stu-id="1f796-148">Password protected files</span></span>
- <span data-ttu-id="1f796-149">檔案只包含影像</span><span class="sxs-lookup"><span data-stu-id="1f796-149">Files that contain only images</span></span>
- <span data-ttu-id="1f796-150">文件未包含原始表單中所有用來建立文件指紋的文字</span><span class="sxs-lookup"><span data-stu-id="1f796-150">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="1f796-151">使用 PowerShell 建立以檔指紋為基礎的分類規則套件</span><span class="sxs-lookup"><span data-stu-id="1f796-151">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="1f796-152">請注意，目前您可以使用安全性與合規性中心的 PowerShell，只建立檔指紋 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="1f796-152">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1f796-153">若要連接，請參閱 [connect To Security & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1f796-153">To connect, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="1f796-154">DLP 使用分類規則套件來偵測敏感內容。</span><span class="sxs-lookup"><span data-stu-id="1f796-154">DLP uses classification rule packages to detect sensitive content.</span></span> <span data-ttu-id="1f796-155">若要根據檔指紋建立分類規則套件，請使用 **新的-DlpFingerprint** 和 **DlpSensitiveInformationType** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1f796-155">To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets.</span></span> <span data-ttu-id="1f796-156">由於 **DlpFingerprint** 的結果不會儲存在資料分類規則之外，因此您必須在相同的 PowerShell 會話中執行 **new-DlpFingerprint** and **new-DlpSensitiveInformationType** 或 **Set DlpSensitiveInformationType** 。</span><span class="sxs-lookup"><span data-stu-id="1f796-156">Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session.</span></span> <span data-ttu-id="1f796-157">下列範例會根據 C:\My Documents\Contoso Employee Template.docx 檔案建立新的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="1f796-157">The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx.</span></span> <span data-ttu-id="1f796-158">您可以將新的指紋儲存為變數，以便在同一 PowerShell 會話中搭配 **新的 DlpSensitiveInformationType** Cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="1f796-158">You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span>
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="1f796-159">現在，我們要新建名為 "Contoso Employee Confidential" 的資料分類規則，並使其使用 C:\My Documents\Contoso Customer Information Form.docx 檔案的文件指紋。</span><span class="sxs-lookup"><span data-stu-id="1f796-159">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="1f796-160">您現在可以使用 **DlpSensitiveInformationType** Cmdlet 來尋找所有 DLP 資料分類規則套件，在此範例中，「Contoso 客戶機密」是「資料分類規則套件」清單的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f796-160">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="1f796-161">最後，在安全性與合規性中心將「Contoso 客戶機密」資料分類規則套件新增至 DLP 原則 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="1f796-161">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1f796-162">這個範例會將規則新增至名為 "ConfidentialPolicy" 的現有 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="1f796-162">This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="1f796-163">在 Exchange Online 中，您也可以使用郵件流程規則中的資料分類規則套件，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="1f796-163">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example.</span></span> <span data-ttu-id="1f796-164">若要執行此命令，您必須先連線 [到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1f796-164">To run this command, you first need to [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1f796-165">另外請注意，規則套件從安全性合規性中心同步處理至 Exchange 系統管理中心所需的時間 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="1f796-165">Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

<span data-ttu-id="1f796-166">DLP 現在會偵測符合 Contoso 客戶 Form.docx 檔指紋的檔。</span><span class="sxs-lookup"><span data-stu-id="1f796-166">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="1f796-167">如需語法及參數的資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1f796-167">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="1f796-168">新 DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="1f796-168">New-DlpFingerprint</span></span>](/powershell/module/exchange/New-DlpFingerprint)
- [<span data-ttu-id="1f796-169">新 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="1f796-169">New-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [<span data-ttu-id="1f796-170">Remove-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="1f796-170">Remove-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="1f796-171">Set-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="1f796-171">Set-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="1f796-172">DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="1f796-172">Get-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Get-DlpSensitiveInformationType)