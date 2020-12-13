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
ms.openlocfilehash: 2211e4d99d97fcce241a5f4c3ea7c9d8122ca9d7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656797"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>修改精確資料比對模式以使用可設定比對

以精確資料比對 (EDM) 為基礎的分類可讓您參考敏感性資訊資料庫中的確切值來建立自訂敏感性資訊類型。 當您需要在確切的字串中允許變數時，您可以使用 *可設定比對* 來告知 Microsoft 365 略過大小寫和一些分隔符。 

> [!IMPORTANT]
> 使用這個程序來修改現有的 EDM 結構描述和資料檔案。

1. 從電腦解除安裝您爲了 EDM 結構描述和資料檔案目的而用來連結 Microsoft 365 的 **EdmUploadAgent.exe**。

2. 針對您透過以下連結的訂閲，下載合適的 **EdmUploadAgent.exe** 檔案：
    - [商業客戶 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 大多數商業客戶應使用這個
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 專門針對高安全性政府雲端用戶
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 專門針對美國國防部雲端客戶

3. 授權 EDM 上傳代理、開啟命令提示字元視窗（以系統管理員身分），然後執行下列命令：

   `EdmUploadAgent.exe /Authorize`

4. 如果您沒有現有結構描述的現存副本，您將需要下載現有結構描述的副本，並執行這個命令：

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. 自訂結構描述，讓每個欄可利用「caseInsensitive 」和／或「ignoredDelimiters 」。  「caseInsensitive 」的預設值是 「否 」，而「ignoredDelimiters 」的則是空字串。 

> [!NOTE]
> 用於偵測常規 Regex 圖樣的基礎自訂敏感性資訊類型或內置的敏感資訊類型，必須支援偵測列出 ignoreDelimiters 的變數輸入。 例如，内置的美國社會安全編號 (SSN) 敏感性資訊類型可以偵測資料中有包括破折號、空格或構成 SSN 分組編號之間缺少空格的變數。 因此，針對 SSN 資料來説，唯一需要被包括在 EDM 的 ignoredDelimiters 的分隔符是：破折號和空格。

這裡有個範例結構描述，通過建立識別敏感性資料中大小寫變數所需的額外欄，來模擬不區分大小寫的比對。

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

在上述範例中，如果已經同時加上 `caseInsensitive` 和 `ignoredDelimiters`，則不再需要原本 `PolicyNumber` 欄的變數。

要更新這個結構描述，讓 EDM 使用可設定比對，請使用 `caseInsensitive` 和 `ignoredDelimiters` 旗標。  以下是如何運作：

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

`ignoredDelimiters` 旗標支援任何非英數字元的字元，這裡有些範例：
- \.
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

`ignoredDelimiters` 旗標不支援：
- 0-9 字元
- A-Z
- a-z
- \"
- \,

6. 使用[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到安全性與合規性中心。

7. 一次執行一個下方的 cmdlets 以更新您的結構描述：

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. 如果需要時，更新資料檔案以配合新版本的結構描述

> [!TIP]
> 您也可以選擇在上傳之前通過以下命令對 CSV 檔案進行驗證：
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>所有 EdmUploadAgent.exe 的相關資訊 > 已支援的參數執行
>
> `EdmUploadAgent.exe /?`

9. 開啟命令提示字元視窗（以系統管理員身分），然後執行下列命令以雜湊和上傳您的敏感性資料：

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>相關文章

- [使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)
- [自訂敏感性資訊類型](custom-sensitive-info-types.md)
- [DLP 原則的概觀](data-loss-prevention-policies.md)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)
- [New-DlpEdmSchema](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)