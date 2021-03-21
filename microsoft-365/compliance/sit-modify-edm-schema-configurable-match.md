---
title: 修改精確資料比對模式以使用可設定比對
f1.keywords:
- NOCSH
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
description: 了解如何修改 EDM 結構描述以使用可設定比對。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e00466e4648ebe93f0658383515d1543f858e1b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919369"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="98899-103">修改精確資料比對模式以使用可設定比對</span><span class="sxs-lookup"><span data-stu-id="98899-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="98899-104">以精確資料比對 (EDM) 為基礎的分類可讓您參考敏感性資訊資料庫中的確切值來建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="98899-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="98899-105">當您需要在確切的字串中允許變數時，您可以使用 *可設定比對* 來告知 Microsoft 365 略過大小寫和一些分隔符。</span><span class="sxs-lookup"><span data-stu-id="98899-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="98899-106">使用這個程序來修改現有的 EDM 結構描述和資料檔案。</span><span class="sxs-lookup"><span data-stu-id="98899-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="98899-107">從電腦解除安裝您爲了 EDM 結構描述和資料檔案目的而用來連結 Microsoft 365 的 **EdmUploadAgent.exe**。</span><span class="sxs-lookup"><span data-stu-id="98899-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="98899-108">針對您透過以下連結的訂閲，下載合適的 **EdmUploadAgent.exe** 檔案：</span><span class="sxs-lookup"><span data-stu-id="98899-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="98899-109">[商業客戶 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 大多數商業客戶應使用這個</span><span class="sxs-lookup"><span data-stu-id="98899-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="98899-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 專門針對高安全性政府雲端用戶</span><span class="sxs-lookup"><span data-stu-id="98899-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="98899-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 專門針對美國國防部雲端客戶</span><span class="sxs-lookup"><span data-stu-id="98899-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="98899-112">授權 EDM 上傳代理、開啟命令提示字元視窗（以系統管理員身分），然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="98899-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="98899-113">如果您沒有現有結構描述的現存副本，您將需要下載現有結構描述的副本，並執行這個命令：</span><span class="sxs-lookup"><span data-stu-id="98899-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="98899-114">自訂結構描述，讓每個欄可利用「caseInsensitive 」和／或「ignoredDelimiters 」。</span><span class="sxs-lookup"><span data-stu-id="98899-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="98899-115">「caseInsensitive 」的預設值是 「否 」，而「ignoredDelimiters 」的則是空字串。</span><span class="sxs-lookup"><span data-stu-id="98899-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="98899-116">用於偵測常規 Regex 圖樣的基礎自訂敏感性資訊類型或內置的敏感資訊類型，必須支援偵測列出 ignoreDelimiters 的變數輸入。</span><span class="sxs-lookup"><span data-stu-id="98899-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="98899-117">例如，内置的美國社會安全編號 (SSN) 敏感性資訊類型可以偵測資料中有包括破折號、空格或構成 SSN 分組編號之間缺少空格的變數。</span><span class="sxs-lookup"><span data-stu-id="98899-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="98899-118">因此，針對 SSN 資料來説，唯一需要被包括在 EDM 的 ignoredDelimiters 的分隔符是：破折號和空格。</span><span class="sxs-lookup"><span data-stu-id="98899-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="98899-119">這裡有個範例結構描述，通過建立識別敏感性資料中大小寫變數所需的額外欄，來模擬不區分大小寫的比對。</span><span class="sxs-lookup"><span data-stu-id="98899-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="98899-120">在上述範例中，如果已經同時加上 `caseInsensitive` 和 `ignoredDelimiters`，則不再需要原本 `PolicyNumber` 欄的變數。</span><span class="sxs-lookup"><span data-stu-id="98899-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="98899-121">要更新這個結構描述，讓 EDM 使用可設定比對，請使用 `caseInsensitive` 和 `ignoredDelimiters` 旗標。</span><span class="sxs-lookup"><span data-stu-id="98899-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="98899-122">以下是如何運作：</span><span class="sxs-lookup"><span data-stu-id="98899-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="98899-123">`ignoredDelimiters` 旗標支援任何非英數字元的字元，這裡有些範例：</span><span class="sxs-lookup"><span data-stu-id="98899-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="98899-124">\.</span><span class="sxs-lookup"><span data-stu-id="98899-124">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

<span data-ttu-id="98899-125">`ignoredDelimiters` 旗標不支援：</span><span class="sxs-lookup"><span data-stu-id="98899-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="98899-126">0-9 字元</span><span class="sxs-lookup"><span data-stu-id="98899-126">characters 0-9</span></span>
- <span data-ttu-id="98899-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="98899-127">A-Z</span></span>
- <span data-ttu-id="98899-128">a-z</span><span class="sxs-lookup"><span data-stu-id="98899-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="98899-129">使用[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="98899-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

7. <span data-ttu-id="98899-130">一次執行一個下方的 cmdlets 以更新您的結構描述：</span><span class="sxs-lookup"><span data-stu-id="98899-130">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="98899-131">如果需要時，更新資料檔案以配合新版本的結構描述</span><span class="sxs-lookup"><span data-stu-id="98899-131">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="98899-132">您也可以選擇在上傳之前通過以下命令對 CSV 檔案進行驗證：</span><span class="sxs-lookup"><span data-stu-id="98899-132">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="98899-133">所有 EdmUploadAgent.exe 的相關資訊 > 已支援的參數執行</span><span class="sxs-lookup"><span data-stu-id="98899-133">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="98899-134">開啟命令提示字元視窗（以系統管理員身分），然後執行下列命令以雜湊和上傳您的敏感性資料：</span><span class="sxs-lookup"><span data-stu-id="98899-134">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="98899-135">相關文章</span><span class="sxs-lookup"><span data-stu-id="98899-135">Related articles</span></span>

- [<span data-ttu-id="98899-136">使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="98899-136">Create a custom sensitive information type with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="98899-137">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="98899-137">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="98899-138">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="98899-138">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="98899-139">DLP 原則的概觀</span><span class="sxs-lookup"><span data-stu-id="98899-139">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="98899-140">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="98899-140">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="98899-141">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="98899-141">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)