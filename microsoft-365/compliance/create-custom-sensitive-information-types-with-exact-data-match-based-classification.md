---
title: 使用精確資料比對建立自訂敏感性資訊類型
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型。
ms.openlocfilehash: a639c71753602ffd381c9240cf6e7273f3ba8bbe
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38708057"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="dec9b-103">使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="dec9b-103">Create custom sensitive information types with exact data match based classification</span></span>

## <a name="overview"></a><span data-ttu-id="dec9b-104">概觀</span><span class="sxs-lookup"><span data-stu-id="dec9b-104">Overview</span></span>

<span data-ttu-id="dec9b-105">[自訂敏感性資訊類型](custom-sensitive-info-types.md) 用來協助防止意外或不當地共用敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="dec9b-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="dec9b-106">身為系統管理員，您可以使用 [安全性與合規性中心](create-a-custom-sensitive-information-type.md) 或 [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) 來根據模式、辨識項 (關鍵字如 *員工*、 *徽章*、 *識別碼*等)、鄰近字元 (辨識項與特定模式中字元的鄰近程度)，以及信賴等級，來定義自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="dec9b-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="dec9b-107">這類自訂敏感性資訊類型符合許多組織的業務需求。</span><span class="sxs-lookup"><span data-stu-id="dec9b-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="dec9b-108">但是，如果您想要使用確切資料值，而非僅比對泛型模式的自訂敏感性資訊類型，該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="dec9b-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="dec9b-109">使用以精確資料比對 (EDM) 為基礎的分類，您可以建立其設計目的為以下的自訂敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="dec9b-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="dec9b-110">動態且可更新；</span><span class="sxs-lookup"><span data-stu-id="dec9b-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="dec9b-111">更可調整；</span><span class="sxs-lookup"><span data-stu-id="dec9b-111">be more scalable;</span></span>
- <span data-ttu-id="dec9b-112">造成較少的誤判；</span><span class="sxs-lookup"><span data-stu-id="dec9b-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="dec9b-113">使用結構化的敏感性資料；</span><span class="sxs-lookup"><span data-stu-id="dec9b-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="dec9b-114">更安全地處理敏感性資訊；以及</span><span class="sxs-lookup"><span data-stu-id="dec9b-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="dec9b-115">能與數個 Microsoft 雲端服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dec9b-115">be used with several Microsoft cloud services.</span></span>

![以 EDM 為基礎的分類](media/EDMClassification.png)

<span data-ttu-id="dec9b-117">以 EDM 為基礎的分類可讓您建立自訂敏感性資訊類型，其參考敏感性資訊資料庫中的確切值。</span><span class="sxs-lookup"><span data-stu-id="dec9b-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="dec9b-118">資料庫可以每日或每週重新整理，而且可以包含最多 1 千萬列資料。</span><span class="sxs-lookup"><span data-stu-id="dec9b-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="dec9b-119">因此，隨著員工、病患或客戶來來去去，以及記錄變更，您的自訂敏感性資訊類型會維持最新且適用。</span><span class="sxs-lookup"><span data-stu-id="dec9b-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="dec9b-120">同時，您可以對原則使用以 EDM 為基礎的分類，例如 [資料外洩防護原則](data-loss-prevention-policies.md) (DLP) 或  [Microsoft Cloud App Security 檔案原則](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dec9b-121">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="dec9b-121">Required licenses and permissions</span></span>

<span data-ttu-id="dec9b-122">您必須是全域系統管理員、合規性系統管理員或 Exchange Online 系統管理員，才能執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="dec9b-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="dec9b-123">若要深入了解 DLP 權限，請參閱 [權限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="dec9b-124">在正式推出時，以 EDM 為基礎的分類將包含在下列訂閱中</span><span class="sxs-lookup"><span data-stu-id="dec9b-124">When generally available, EDM-based classification will be included in these subscriptions</span></span>

- <span data-ttu-id="dec9b-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dec9b-125">Office 365 E5</span></span>
- <span data-ttu-id="dec9b-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dec9b-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="dec9b-127">Microsoft 365 資訊保護和合規性</span><span class="sxs-lookup"><span data-stu-id="dec9b-127">Microsoft 365 Information Protection and Compliance</span></span>
- <span data-ttu-id="dec9b-128">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="dec9b-128">Office 365 Advanced Compliance</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="dec9b-129">工作流程概覽</span><span class="sxs-lookup"><span data-stu-id="dec9b-129">The work flow at a glance</span></span>

|<span data-ttu-id="dec9b-130">階段</span><span class="sxs-lookup"><span data-stu-id="dec9b-130">Phase</span></span>  |<span data-ttu-id="dec9b-131">需要的項目</span><span class="sxs-lookup"><span data-stu-id="dec9b-131">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="dec9b-132">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="dec9b-132">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="dec9b-133">(視需要)</span><span class="sxs-lookup"><span data-stu-id="dec9b-133">(As needed)</span></span><br/><span data-ttu-id="dec9b-134">- [編輯資料庫結構描述](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dec9b-134">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="dec9b-135">- [移除結構描述](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dec9b-135">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="dec9b-136">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="dec9b-136">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dec9b-137">- .xml 格式的資料庫結構描述 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="dec9b-137">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="dec9b-138">- .xml 格式的規則套件 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="dec9b-138">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="dec9b-139">- 安全性與合規性中心的系統管理員權限 (使用 PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dec9b-139">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="dec9b-140">第 2 部分：編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="dec9b-140">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="dec9b-141">(視需要)</span><span class="sxs-lookup"><span data-stu-id="dec9b-141">(As needed)</span></span><br/>[<span data-ttu-id="dec9b-142">重新整理資料</span><span class="sxs-lookup"><span data-stu-id="dec9b-142">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="dec9b-143">- 自訂安全性群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="dec9b-143">- Custom security group and user account</span></span><br/><span data-ttu-id="dec9b-144">- 具有 EDM 上傳代理程式電腦的本機系統管理員存取權</span><span class="sxs-lookup"><span data-stu-id="dec9b-144">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="dec9b-145">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="dec9b-145">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dec9b-146">- 重新整理資料的程序和排程</span><span class="sxs-lookup"><span data-stu-id="dec9b-146">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="dec9b-147">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="dec9b-147">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="dec9b-148">- 具有 DLP 的 Office 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="dec9b-148">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="dec9b-149">- 已啟用以 EDM 為基礎的分類功能</span><span class="sxs-lookup"><span data-stu-id="dec9b-149">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="dec9b-150">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="dec9b-150">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="dec9b-151">設定和配置以 EDM 為基礎的分類涉及將敏感性資料儲存為 .csv 格式、定義您的敏感性資訊的資料庫結構描述、建立規則套件，以及上傳結構描述和規則套件。</span><span class="sxs-lookup"><span data-stu-id="dec9b-151">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="dec9b-152">定義用於敏感性資訊的資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="dec9b-152">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="dec9b-153">找出您要使用的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="dec9b-153">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="dec9b-154">將資料匯出至應用程式，例如 Microsoft Excel，並將檔案以 .csv 格式儲存。</span><span class="sxs-lookup"><span data-stu-id="dec9b-154">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="dec9b-155">資料檔案可能包含：</span><span class="sxs-lookup"><span data-stu-id="dec9b-155">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="dec9b-156">最多 1 千萬列敏感性資料</span><span class="sxs-lookup"><span data-stu-id="dec9b-156">Up to 10 million rows of sensitive data</span></span>
      - <span data-ttu-id="dec9b-157">每個資料來源最多 32 個資料行 (欄位)</span><span class="sxs-lookup"><span data-stu-id="dec9b-157">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="dec9b-158">最多 5 個資料行 (欄位) 標示為可搜尋</span><span class="sxs-lookup"><span data-stu-id="dec9b-158">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="dec9b-159">以 .csv 檔案格式將敏感性資料結構化，使得第一列包含用於以 EDM 為基礎的分類的欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="dec9b-159">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="dec9b-160">在您的 .csv 檔案中，您可能會有欄位名稱，例如 "ssn"、"birthdate"、"firstname"、"lastname" 等等。</span><span class="sxs-lookup"><span data-stu-id="dec9b-160">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="dec9b-161">舉例來說，我們的 .csv 檔案稱為 *PatientRecords.csv*，且其資料行包括 *PatientID*、 *MRN*、 *LastName*、 *FirstName*、 *SSN* 等。</span><span class="sxs-lookup"><span data-stu-id="dec9b-161">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="dec9b-162">以 .xml 格式定義用於敏感性資訊資料庫的結構描述 (類似以下的範例)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-162">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="dec9b-163">將此結構描述檔案命名為 edm.xml，然後設定它，使得資料庫中的每一個資料行都會有使用語法 \<Field name="" searchable=""/\> 的行。</span><span class="sxs-lookup"><span data-stu-id="dec9b-163">Name this schema file edm.xml, and configure it such that for each column in the database, there is a line that uses the syntax \<Field name="" searchable=""/\>.</span></span>

      - <span data-ttu-id="dec9b-164">使用資料行名稱作為 *欄位名稱* 值。</span><span class="sxs-lookup"><span data-stu-id="dec9b-164">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="dec9b-165">對您想讓它可供搜尋最多 5 個欄位的欄位，使用 *searchable="true"* 。</span><span class="sxs-lookup"><span data-stu-id="dec9b-165">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="dec9b-166">您必須至少將一個欄位指定為可搜尋。</span><span class="sxs-lookup"><span data-stu-id="dec9b-166">You must designate a minimum of one field as searchable.</span></span>

<span data-ttu-id="dec9b-167">例如，下列 .xml 檔會為病患記錄資料庫定義結構描述，並將五個欄位指定為可搜尋： *PatientID*、 *MRN*、 *SSN*、 *Phone* 以及  *DOB* </span><span class="sxs-lookup"><span data-stu-id="dec9b-167">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

<span data-ttu-id="dec9b-168">(您可以複製、修改及使用我們的範例)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-168">(You can copy, modify, and use our example.)</span></span>

 ```xml
<EdmSchema xmlns="https://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records" version="1">
            <Field name="PatientID" searchable="true" />
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</EdmSchema>
```

4. <span data-ttu-id="dec9b-169">[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-169">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

5. <span data-ttu-id="dec9b-170">若要上傳資料庫結構描述，請執行下列 Cmdlet，一次一個：</span><span class="sxs-lookup"><span data-stu-id="dec9b-170">To upload the database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="dec9b-171">系統會提示您確認，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dec9b-171">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="dec9b-172">確認</span><span class="sxs-lookup"><span data-stu-id="dec9b-172">Confirm</span></span>
>
> <span data-ttu-id="dec9b-173">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="dec9b-173">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="dec9b-174">將匯入資料存放區 'patientrecords' 的新 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="dec9b-174">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
>
> <span data-ttu-id="dec9b-175">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="dec9b-175">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="dec9b-176">若要不確認即變更，請在步驟 5 中改用此 Cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="dec9b-176">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="dec9b-177">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="dec9b-177">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dec9b-178">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="dec9b-178">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="dec9b-179">既然已定義您敏感性資訊資料庫的結構描述，下一個步驟是設定規則套件。</span><span class="sxs-lookup"><span data-stu-id="dec9b-179">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="dec9b-180">繼續前往 [設定規則套件](#set-up-a-rule-package)這一節。</span><span class="sxs-lookup"><span data-stu-id="dec9b-180">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="dec9b-181">編輯以 EDM 為基礎的分類的結構描述</span><span class="sxs-lookup"><span data-stu-id="dec9b-181">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="dec9b-182">如果您想要變更 edm.xml 檔案，例如變更哪些欄位用於以 EDM 為基礎的分類，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="dec9b-182">If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="dec9b-183">編輯您的 edm.xml 檔案 (這是本文 [定義結構描述](#define-the-schema-for-your-database-of-sensitive-information) 一節所討論的檔案)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-183">Edit your edm.xml file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="dec9b-184">[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-184">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

3. <span data-ttu-id="dec9b-185">若要更新資料庫結構描述，請執行下列 Cmdlet，一次一個：</span><span class="sxs-lookup"><span data-stu-id="dec9b-185">To update your database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="dec9b-186">系統會提示您確認，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dec9b-186">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="dec9b-187">確認</span><span class="sxs-lookup"><span data-stu-id="dec9b-187">Confirm</span></span>
>
> <span data-ttu-id="dec9b-188">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="dec9b-188">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="dec9b-189">將更新資料存放區 'patientrecords' 的 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="dec9b-189">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
>
> <span data-ttu-id="dec9b-190">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="dec9b-190">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="dec9b-191">若要不確認即變更，請在步驟 3 中改用此 Cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="dec9b-191">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="dec9b-192">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="dec9b-192">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dec9b-193">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="dec9b-193">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="dec9b-194">移除以 EDM 為基礎的分類的結構描述</span><span class="sxs-lookup"><span data-stu-id="dec9b-194">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="dec9b-195">(如有需要) 如果您想要移除 EDM 型分類使用的結構描述，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dec9b-195">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="dec9b-196">[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-196">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

2. <span data-ttu-id="dec9b-197">執行下列 PowerShell Cmdlet，將 "patientrecords" 的資料存放區名稱取代為您要移除的資料存放區名稱：</span><span class="sxs-lookup"><span data-stu-id="dec9b-197">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

```powershell
Remove-DlpEdmSchema -Identity patientrecords
```

<span data-ttu-id="dec9b-198">系統會提示您確認，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dec9b-198">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="dec9b-199">確認</span><span class="sxs-lookup"><span data-stu-id="dec9b-199">Confirm</span></span>
>
> <span data-ttu-id="dec9b-200">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="dec9b-200">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="dec9b-201">將移除資料存放區 'patientrecords' 的 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="dec9b-201">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
>
> <span data-ttu-id="dec9b-202">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="dec9b-202">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
>  <span data-ttu-id="dec9b-203">若要不確認即變更，請在步驟 2 中改用此 Cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="dec9b-203">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="dec9b-204">設定規則套件</span><span class="sxs-lookup"><span data-stu-id="dec9b-204">Set up a rule package</span></span>

1. <span data-ttu-id="dec9b-205">以 .xml 格式建立規則套件 (使用 Unicode 編碼方式)，類似下列範例。</span><span class="sxs-lookup"><span data-stu-id="dec9b-205">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="dec9b-206">(您可以複製、修改及使用我們的範例)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-206">(You can copy, modify, and use our example.)</span></span>

<span data-ttu-id="dec9b-207">當您設定規則套件時，請務必正確地參照您的 .csv 檔案和 edm.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="dec9b-207">When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file.</span></span> <span data-ttu-id="dec9b-208">您可以複製、修改及使用我們的範例。</span><span class="sxs-lookup"><span data-stu-id="dec9b-208">You can copy, modify, and use our example.</span></span> <span data-ttu-id="dec9b-209">在此範例 xml 中，必須自訂下列欄位，才能建立您的 EDM 敏感性類型：</span><span class="sxs-lookup"><span data-stu-id="dec9b-209">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

- <span data-ttu-id="dec9b-210">**RulePack id 與 ExactMatch id**：使用 [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 產生 GUID。</span><span class="sxs-lookup"><span data-stu-id="dec9b-210">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

- <span data-ttu-id="dec9b-211">**資料存放區**：此欄位會指定要使用的 EDM 查閱資料存放區。</span><span class="sxs-lookup"><span data-stu-id="dec9b-211">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="dec9b-212">您要提供已設定之 EDM 結構描述的資料來源名稱。</span><span class="sxs-lookup"><span data-stu-id="dec9b-212">You provide a data source name of a configured EDM Schema.</span></span>

- <span data-ttu-id="dec9b-213">**idMatch**：此欄位會指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="dec9b-213">**idMatch**: This field points to the primary element for EDM.</span></span>
  - <span data-ttu-id="dec9b-214">相符項目：指定要在完全查閱中使用的欄位。</span><span class="sxs-lookup"><span data-stu-id="dec9b-214">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="dec9b-215">您要在資料存放區的 EDM 結構描述中，提供可搜尋的欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="dec9b-215">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
  - <span data-ttu-id="dec9b-216">分類：此欄位會指定可觸發 EDM 查閱的敏感性類型符合項目。</span><span class="sxs-lookup"><span data-stu-id="dec9b-216">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="dec9b-217">您可以提供現有內建或自訂分類的名稱或 GUID。</span><span class="sxs-lookup"><span data-stu-id="dec9b-217">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

- <span data-ttu-id="dec9b-218">**相符項目：** 此欄位會指向 idMatch 鄰近位置的其他辨識項。</span><span class="sxs-lookup"><span data-stu-id="dec9b-218">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
  - <span data-ttu-id="dec9b-219">相符項目：您要在資料存放區的 EDM 結構描述中，提供任何欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="dec9b-219">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
- <span data-ttu-id="dec9b-220">**資源：** 此區段會在多個地區設定中，指定敏感性類型的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="dec9b-220">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
  - <span data-ttu-id="dec9b-221">idRef：您要提供 ExactMatch id 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="dec9b-221">idRef: You provide GUID for ExactMatch id.</span></span>
  - <span data-ttu-id="dec9b-222">編輯結構描述名稱與描述：視需要自訂。</span><span class="sxs-lookup"><span data-stu-id="dec9b-222">Name & des Editing the schema criptions: customize as required.</span></span>

```xml
<RulePackage xmlns="https://schemas.microsoft.com/office/2018/edm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care EDM Rulepack</Name>
        <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
```

1. <span data-ttu-id="dec9b-223">執行下列 PowerShell Cmdlet 以上傳規則套件，一次一個：</span><span class="sxs-lookup"><span data-stu-id="dec9b-223">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

```powershell
$rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
```

<span data-ttu-id="dec9b-224">此時，您已設定以 EDM 為基礎的分類。</span><span class="sxs-lookup"><span data-stu-id="dec9b-224">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="dec9b-225">下一個步驟是要對敏感性資料編製索引，然後上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="dec9b-225">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="dec9b-226">回想一下前面的程序，我們的 PatientRecords 結構描述將五個欄位定義為可搜尋： *PatientID*、 *MRN*、 *SSN*、 *Phone* 和  *DOB*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-226">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="dec9b-227">我們的範例規則套件包含這些欄位，並會參照資料庫結構描述檔案 (edm.xml)，一個 *ExactMatch* 項目會有一個可搜尋欄位。</span><span class="sxs-lookup"><span data-stu-id="dec9b-227">Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="dec9b-228">請考慮下列 ExactMatch 項目：</span><span class="sxs-lookup"><span data-stu-id="dec9b-228">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="dec9b-229">請注意本範例中的下列重點：</span><span class="sxs-lookup"><span data-stu-id="dec9b-229">In this example, note the following:</span></span>

- <span data-ttu-id="dec9b-230">資料存放區名稱會參照稍早建立的 .csv 檔案： **dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="dec9b-230">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="dec9b-231">idMatch 值會參照可搜尋的欄位，其列於資料庫結構描述檔案： **idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="dec9b-231">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="dec9b-232">分類值會參照現有或自訂敏感性資訊類型： **classification = "U.S. Social Security Number (SSN)"** </span><span class="sxs-lookup"><span data-stu-id="dec9b-232">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="dec9b-233">(在此案例中，我們使用美國社會安全號碼作為現有的敏感性資訊類型)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-233">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="dec9b-234">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="dec9b-234">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="dec9b-235">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="dec9b-235">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="dec9b-236">第 2 部分：編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="dec9b-236">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="dec9b-237">在此階段，您會設定自訂安全性群組和使用者帳戶，並設定 EDM 上傳代理程式工具。</span><span class="sxs-lookup"><span data-stu-id="dec9b-237">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="dec9b-238">然後，您會使用工具來為敏感性資料編製索引，並上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="dec9b-238">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="dec9b-239">設定安全性群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="dec9b-239">Set up the security group and user account</span></span>

1. <span data-ttu-id="dec9b-240">以全域系統管理員身分，前往系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com/))，並 [建立名為 EDM\_DataUploaders 的安全性群組](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) 。</span><span class="sxs-lookup"><span data-stu-id="dec9b-240">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com/)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called EDM\_DataUploaders.</span></span>

2. <span data-ttu-id="dec9b-241">將一或多個使用者新增至 *EDM\_DataUploaders* 安全性群組 </span><span class="sxs-lookup"><span data-stu-id="dec9b-241">Add one or more users to the *EDM\_DataUploaders* security group.</span></span> <span data-ttu-id="dec9b-242">(這些使用者將管理敏感性資訊的資料庫)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-242">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="dec9b-243">請確定管理敏感性資料的每個使用者，為用於 EDM 上傳代理程式之電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="dec9b-243">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="dec9b-244">設定 EDM 上傳代理程式</span><span class="sxs-lookup"><span data-stu-id="dec9b-244">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="dec9b-245">在開始此程序之前，請確定您是  *EDM\_DataUploaders*  安全性群組的成員，以及您電腦上的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="dec9b-245">Before you begin this procedure, make sure that you are a member of the *EDM\_DataUploaders* security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="dec9b-246">下載並安裝 [EDM 上傳代理程式](https://go.microsoft.com/fwlink/?linkid=2088639)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-246">Download and install the [EDM Upload Agent](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="dec9b-247">根據預設，安裝位置應該是 C:\\Program Files\\Microsoft\\EdmUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="dec9b-247">By default, the installation location should be C:\\Program Files\\Microsoft\\EdmUploadAgent.</span></span>

2. <span data-ttu-id="dec9b-248">若要授權 EDM 上傳代理程式，請開啟 Windows 命令提示字元 (以系統管理員身分)，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dec9b-248">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="dec9b-249">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="dec9b-249">Sign in to Office 365 for business with your work or school account.</span></span>

<span data-ttu-id="dec9b-250">下一個步驟是使用 EDM 上傳代理程式來為敏感性資料編製索引，然後上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="dec9b-250">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="dec9b-251">編製索引及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="dec9b-251">Index and upload the sensitive data</span></span>

<span data-ttu-id="dec9b-252">將敏感性資料檔案 (回想我們的範例是 *PatientRecords.csv*) 儲存至電腦上的本機磁碟機 </span><span class="sxs-lookup"><span data-stu-id="dec9b-252">Save the sensitive data file (recall our example is *PatientRecords.csv*) to the local drive on the machine.</span></span> <span data-ttu-id="dec9b-253">(我們將範例 *PatientRecords.csv* 檔案儲存至 C:\\Edm\\Data)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-253">(We saved our example *PatientRecords.csv* file to C:\\Edm\\Data.)</span></span>

<span data-ttu-id="dec9b-254">若要為敏感性資料編製索引並上傳，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dec9b-254">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="dec9b-255">範例：**EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="dec9b-255">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="dec9b-256">若要在隔離的環境中區隔並執行敏感性資料的索引，請分別執行索引和上傳步驟。</span><span class="sxs-lookup"><span data-stu-id="dec9b-256">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="dec9b-257">若要為敏感性資料編製索引，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dec9b-257">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="dec9b-258">範例：**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="dec9b-258">Example: **EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="dec9b-259">若要上傳已編製索引的資料，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dec9b-259">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="dec9b-260">範例：**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="dec9b-260">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="dec9b-261">若要確認您的敏感性資料已上傳，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dec9b-261">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="dec9b-262">您會看到資料存放區的清單，以及其上次更新時間。</span><span class="sxs-lookup"><span data-stu-id="dec9b-262">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="dec9b-263">針對 [重新整理您的敏感性資訊資料庫](#refreshing-your-sensitive-information-database)，繼續設定程序和排程。</span><span class="sxs-lookup"><span data-stu-id="dec9b-263">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="dec9b-264">此時，您已準備好使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="dec9b-264">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="dec9b-265">例如，您可以 [使用以 EDM 為基礎的分類來設定 DLP 原則](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-265">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="dec9b-266">重新整理您的敏感性資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="dec9b-266">Refreshing your sensitive information database</span></span>

<span data-ttu-id="dec9b-267">您可以每日或每週重新整理您的敏感性資訊資料庫，而 EDM 上傳工具可以重新為敏感性資料編製索引，然後重新上傳已編製索引的資料。</span><span class="sxs-lookup"><span data-stu-id="dec9b-267">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="dec9b-268">決定您重新整理敏感性資訊資料庫的程序和頻率 (每日或每週)。</span><span class="sxs-lookup"><span data-stu-id="dec9b-268">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="dec9b-269">將敏感性資料重新匯出至應用程式，例如 Microsoft Excel，並將檔案儲存為 .csv 格式。</span><span class="sxs-lookup"><span data-stu-id="dec9b-269">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="dec9b-270">當您遵循 [編製索引及上傳敏感性資料](#index-and-upload-the-sensitive-data)中所述的步驟時，請保留所使用的相同檔案名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="dec9b-270">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

> [!NOTE]
> <span data-ttu-id="dec9b-271">如果 .csv 檔案的結構 (欄位名稱) 沒有任何變更，重新整理資料時，您不需要對資料庫結構描述檔案進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="dec9b-271">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="dec9b-272">但如果您必須進行變更，請務必相應地編輯資料庫結構描述和規則套件。</span><span class="sxs-lookup"><span data-stu-id="dec9b-272">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="dec9b-273">使用 [工作排程器](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) 將 [編製索引及上傳敏感性資料](#index-and-upload-the-sensitive-data) 程序中的步驟 2 和 3 自動化。</span><span class="sxs-lookup"><span data-stu-id="dec9b-273">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="dec9b-274">您可以使用數個方法來排程工作：</span><span class="sxs-lookup"><span data-stu-id="dec9b-274">You can schedule tasks using several methods:</span></span>

| <span data-ttu-id="dec9b-275">**方法**</span><span class="sxs-lookup"><span data-stu-id="dec9b-275">**Method**</span></span>             | <span data-ttu-id="dec9b-276">**處理方式**</span><span class="sxs-lookup"><span data-stu-id="dec9b-276">**What to do**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="dec9b-277">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dec9b-277">Windows PowerShell</span></span>     | <span data-ttu-id="dec9b-278">請參閱 [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) 文件，以及本文中的 [範例 PowerShell 指令碼](#example-powershell-script-for-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="dec9b-278">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
| <span data-ttu-id="dec9b-279">工作排程器 API</span><span class="sxs-lookup"><span data-stu-id="dec9b-279">Task Scheduler API</span></span>     | <span data-ttu-id="dec9b-280">請參閱 [工作排程器](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) 文件</span><span class="sxs-lookup"><span data-stu-id="dec9b-280">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
| <span data-ttu-id="dec9b-281">Windows 使用者介面</span><span class="sxs-lookup"><span data-stu-id="dec9b-281">Windows user interface</span></span> | <span data-ttu-id="dec9b-282">在 Windows 中，按一下 [開始] \*\*\*\*，然後輸入工作排程器。</span><span class="sxs-lookup"><span data-stu-id="dec9b-282">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="dec9b-283">接著，在結果清單中，以滑鼠右鍵按一下 [工作排程器] \*\*\*\*，然後選擇 [以系統管理員身分執行] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-283">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="dec9b-284">工作排程器的範例 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="dec9b-284">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="dec9b-285">本節包含的範例 PowerShell 指令碼，可供您用來對編製資料索引及上傳已編製索引的資料工作進行排程：</span><span class="sxs-lookup"><span data-stu-id="dec9b-285">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="dec9b-286">在相同的步驟中排程索引並上傳</span><span class="sxs-lookup"><span data-stu-id="dec9b-286">To schedule index and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ‘ /HashLocation’ + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="dec9b-287">在個別的步驟中排程索引和上傳</span><span class="sxs-lookup"><span data-stu-id="dec9b-287">To schedule index and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="dec9b-288">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="dec9b-288">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="dec9b-289">Exchange Online 用 Office 365 DLP (電子郵件)、商務用 OneDrive (檔案)、Microsoft Teams (交談) 和 Microsoft Cloud App Security DLP 原則將支援 EDM 敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="dec9b-289">Office 365 DLP for Exchange Online (email), OneDrive for Business (files), Microsoft Teams (conversations) and Microsoft Cloud App Security DLP policies will support EDM sensitive information types.</span></span>

<span data-ttu-id="dec9b-290">下列案例的 EDM 敏感性資訊類型目前正在開發中，但尚未提供：</span><span class="sxs-lookup"><span data-stu-id="dec9b-290">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="dec9b-291">SharePoint 用 Office 365 DLP (檔案)</span><span class="sxs-lookup"><span data-stu-id="dec9b-291">Office 365 DLP for SharePoint (files)</span></span>
- <span data-ttu-id="dec9b-292">自動分類敏感度標籤和保留標籤</span><span class="sxs-lookup"><span data-stu-id="dec9b-292">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="dec9b-293">使用 EDM 建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="dec9b-293">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="dec9b-294">前往安全性與合規性中心 ([https://protection.office.com](https://protection.office.com/))。</span><span class="sxs-lookup"><span data-stu-id="dec9b-294">Go to the Security & Compliance Center</span></span>

2. <span data-ttu-id="dec9b-295">按一下 [資料外洩防護] \*\*\*\* \>[原則] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-295">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="dec9b-296">選擇 [建立原則] \*\*\*\* \>[自訂] \*\*\*\* \>[下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-296">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="dec9b-297">在 [為您的原則命名] \*\*\*\* 索引標籤上，指定名稱和描述，然後選擇 [下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-297">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="dec9b-298">在 [選擇位置] \*\*\*\* 索引標籤上，選取 [讓我選擇特定位置] \*\*\*\*，然後選擇 [下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-298">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="dec9b-299">在 [狀態] \*\*\*\* 資料行中，選取 [Exchange 電子郵件、OneDrive 帳戶、Teams 交談和頻道訊息] \*\*\*\* ，然後選擇 [下一步] \*\*\*\* </span><span class="sxs-lookup"><span data-stu-id="dec9b-299">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span> <span data-ttu-id="dec9b-300">(注意：SharePoint 網站目前不支援 EDM，因此 DLP 原則將不會在 EDM 的 Sharepoint 中偵測檔案)</span><span class="sxs-lookup"><span data-stu-id="dec9b-300">(Note: EDM is currently not supported in SharePoint sites and DLP policy will not detect files in Sharepoint for EDM)</span></span>

7. <span data-ttu-id="dec9b-301">在 [原則設定] \*\*\*\* 索引標籤上，選擇 [使用進階設定] \*\*\*\*，然後選擇 [下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-301">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="dec9b-302">選擇 [+ 新增規則] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-302">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="dec9b-303">在 [名稱] \*\*\*\* 區段中，指定規則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="dec9b-303">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="dec9b-304">在 [條件] \*\*\*\* 區段的 [+ 新增條件] \*\*\*\* 清單中，選擇 [內容包含敏感性類型] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-304">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="dec9b-305">![內容包含敏感性資訊類型](media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="dec9b-305">![Content contains sensitive info types](media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="dec9b-306">搜尋您設定規則套件時建立的敏感性資訊類型，然後選擇 [+ 新增] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-306">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="dec9b-307">接著，選擇 [完成] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-307">Then choose **Done**.</span></span>

12. <span data-ttu-id="dec9b-308">完成選取規則的選項，例如 **使用者通知**、 **使用者覆寫**、 **事件報告**等等，然後選擇 [儲存] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-308">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="dec9b-309">在 [原則設定] \*\*\*\* 索引標籤上，檢閱您的規則，然後選擇 [下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-309">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="dec9b-310">指定是否立即開啟原則、測試它，或是保持關閉。</span><span class="sxs-lookup"><span data-stu-id="dec9b-310">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="dec9b-311">接著，選擇 [下一步] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-311">Then choose **Next**.</span></span>

15. <span data-ttu-id="dec9b-312">在 [檢閱您的設定] \*\*\*\* 索引標籤上，檢閱您的原則。</span><span class="sxs-lookup"><span data-stu-id="dec9b-312">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="dec9b-313">視需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="dec9b-313">Make any needed modifications.</span></span> <span data-ttu-id="dec9b-314">準備就緒時，選擇 [建立] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dec9b-314">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="dec9b-315">允許大約一小時的時間，讓您的新 DLP 原則在您的整個資料中心生效。</span><span class="sxs-lookup"><span data-stu-id="dec9b-315">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dec9b-316">相關文章</span><span class="sxs-lookup"><span data-stu-id="dec9b-316">Related articles</span></span>

[<span data-ttu-id="dec9b-317">內建的敏感性資訊類型以及其尋求的目標</span><span class="sxs-lookup"><span data-stu-id="dec9b-317">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="dec9b-318">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="dec9b-318">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="dec9b-319">DLP 原則的概觀</span><span class="sxs-lookup"><span data-stu-id="dec9b-319">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="dec9b-320">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dec9b-320">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

[<span data-ttu-id="dec9b-321">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="dec9b-321">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)

## <a name="feedback"></a><span data-ttu-id="dec9b-322">意見反應</span><span class="sxs-lookup"><span data-stu-id="dec9b-322">Feedback</span></span>

<span data-ttu-id="dec9b-323">已啟用 GitHub 意見反應，但只能在公用網站上新增問題。</span><span class="sxs-lookup"><span data-stu-id="dec9b-323">GitHub feedback is enabled, but adding issues is only available on the public site.</span></span>
