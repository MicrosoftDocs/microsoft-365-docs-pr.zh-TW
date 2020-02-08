---
title: Office 365 開發/測試環境中的 GDPR 探索、保護和報告
description: 展示 Office 365 中的 GDPR 功能。
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.openlocfilehash: f7bf98da5d358f9b76f38372353a1c2a9d0d45d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594087"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a>Office 365 開發/測試環境中的 GDPR 探索、保護和報告

 **摘要：** 展示 Office 365 中的 GDPR 功能。 
  
本文將說明如何在 Office 365 開發/測試環境中設定及展示一般資料保護規定 (GDPR) 的個人識別資訊 (PII) 探索、保護及報告。
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a>階段 1：建立及設定您的試用版 Office 365 訂閱

首先，請遵循 [Office 365 開發/測試環境階段 2](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) 一文中的步驟進行。

接下來，請使用下列步驟來設定電子文件探索管理員：

1. 使用全域管理員帳戶登入 Office 365 試用版租用戶。
2. 從 Office 365 首頁上，按一下 [安全性與合規性]****。
3. 在新的 [安全性與合規性] 索引標籤中，按一下 [權限] **** >  [電子文件探索管理員]****。
4. 按一下 [電子文件探索管理員] 的 [編輯]****，然後按一下 [選擇電子文件探索管理員]****。
5. 按一下 [+ 新增]****、搜尋您的全域系統管理員帳戶名稱，然後以電子文件探索管理員身分新增您的全域系統管理員帳戶。
6. 按一下 [完成] **** >  [儲存] **** >  [關閉]****。
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a>階段 2：將個人識別資訊新增至租用戶

在這個階段中，您要使用 PII 建立一組範例國際銀行帳號 (IBAN) 的文件，並將其儲存在您 Office 365 開發/測試環境中的 SharePoint Online 網站上。

1. 在本機電腦上，開啟 Microsoft Word。
2. 在 Word 檔案中將下表貼上，並在本機電腦上將它儲存為 'IBANs.docx'。
    
    數字  |國家/地區  |代碼 |IBAN  |
    |---------|---------|---------|---------|
    |1     |  奧地利 SEPA      | AT            |AT611904300234573201       |
    |2     |  保加利亞 SEPA       |BG    |BG80BNBG96611020345678      |
    |3     |  丹麥 SEPA      |   DK      |DK5000400440116243      |
    |4     |  芬蘭 SEPA      |   FI      |FI2112345600000785         |
    |5     |  法國 SEPA       |   FR      |FR1420041010050500013M02606         |
    |6     |  德國 SEPA      |   DE      |DE89370400440532013000         |
    |7     |  希臘 SEPA       |   GR      |GR1601101250000000012300695         |
    |8     |  義大利 SEPA       |    IT     |GR1601101250000000012300695         |
    |9     |  荷蘭 SEPA      |   NL      |    NL91ABNA0417164300     |
    |10     | 波蘭 SEPA       |  PL       | PL27114020040000300201355387        |

附註：此範例資料集衍生自公開提供的資訊，而且旨在用於測試目的而已。

3. 在瀏覽器的新索引標籤中，輸入：**https://**\<YourTenantName\>**.sharepoint.com**
4. 按一下 [文件]**** 以開啟此網站的文件庫。如果系統提示您進行新的清單體驗導覽，請按 [下一步]****，直到完成為止。
5.  按一下 [上傳] **** >  [檔案]****，然後選取您在步驟 2 中建立的 IBANs.docx。

  
## <a name="phase-3-demonstrate-data-discovery"></a>階段 3：展示資料探索

在這個階段中，您展示的搜尋會根據包含 IBAN 的內容，尋找在階段 2 中所建立及儲存的文件。

1. 在 [安全性與合規性] 索引標籤中，按一下 [首頁]****，然後按一下 [搜尋與調查] **** >  [內容搜尋]****。
2. 按一下 [+]**** 來建立新的搜尋項目。
3. 請在新的視窗中提供下列資訊：  
    a. 名稱：IBAN 搜尋  
    b. 您需要我們查看哪裡？：**選擇要搜尋的特定網站**(按一下 [+]****)，然後輸入網站的 URL：**https://**\<您的租用戶名稱\>**.sharepoint.com/**  
    c. 按一下 [新增]****，然後按一下 [確定]****。如果您看到警告，請按一下 [確定]****。  
    d. 在 [新的搜尋]**** 視窗上按 [下一步]****。  
    e. 針對**您需要我們尋找什麼？**：**SensitiveType：「國際銀行帳號 (IBAN)」**，然後按一下 [搜尋]****。

4. 請確定您看到至少一個項目列在 **IBAN 搜尋**結果中。


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a>階段 4：透過 PowerShell 建立自訂的敏感資訊類型

在這個階段中，您要使用 Microsoft PowerShell 來建立虛構 Contoso 公司的自訂敏感資訊類型。Contoso 會使用 Contoso 客戶編號 (CCN) 來識別其客戶資料庫中的每位客戶。CCN 包含下列結構：
- 兩位數表示記錄所建立的年份。
    - Contoso 成立於 2002 年；因此，可能的最早值是 02。 
- 三位數代表建立記錄的夥伴機構。
    - 可能的機構值範圍介於 000 到 999。 
- 以字母字元來代表企業營運。
    - 可能的值是 a 到 z，且應該不區分大小寫。
- 一個四位數序號。 
    - 可能的序號值範圍從 0000 到 9999。   

Contoso 一律會以內部通信、外部通信、文件和其他形式使用 CCN 來參照客戶。Contoso 需要自訂的敏感項目類型來偵測 Office 365 內容中的 CCN 使用情形，以便他們可在使用此形式的個人識別資訊時提供保護。

1. 使用[使用多重要素驗證連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) 中的指示，並使用您全域系統管理員帳戶的 UPN 連線至安全性與合規性中心。
2. 執行下列 PowerShell 命令。

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. 請執行下列 PowerShell 命令，並以產生的 GUID 所列出的順序，將 GUID 複製到電腦上 [記事本] 的開啟執行個體。
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. 在您的本機電腦上，開啟另一個 [記事本] 的執行個體，並將下列內容貼入：

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. 將步驟 4 的 XML 文字中 GUID1、GUID2 和 GUID3 的值取代為其在步驟 3 中的值，然後使用 ContosoCCN.xml 的名稱，將內容儲存在本機電腦上。
6. 填入您 ContosoCCN.xml 檔案的路徑，然後執行下列命令。
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. 在 [安全性與合規性] 索引標籤中，按一下 [分類] **** >  [敏感資訊類型]****。您應該會在清單中看到 Contoso 客戶編號 (CCN)。

## <a name="phase-5-demonstrate-data-protection"></a>階段 5：展示資料保護

Office 365 中個人資訊的保護，包括使用資料外洩防護 (DLP) 功能。  您可以使用 DLP 原則自動保護整個 Office 365 的敏感性資訊。

您可以多種方式來提供保護。教育並提高以下認知：歐盟居民資料應儲存在您環境的何處以及您的員工被允許處理這些資料的方式，上述方式即代表一種使用 Office 365 DLP 的資訊保護層級。

在這個階段中，您會建立新的 DLP 原則，並展示如何將其套用至您在階段 2 的 SharePoint Online 中儲存的 IBANs.docx 檔案，以及您何時要嘗試傳送包含 IBAN 的電子郵件。

1. 從瀏覽器的 [安全性與合規性] 索引標籤中，按一下 [首頁]****。
2. 按一下 [資料遺失防護] **** >  [原則]****。
3. 按一下 [+ 建立原則]****。
4. 在 [從範本開始] 或 [建立自訂原則]**** 中，按一下 [自訂] **** >  [自訂原則] **** >  [下一步]****。
5. 在 [命名原則]**** 中，提供下列詳細資料，然後按 [下一步]****：a. 名稱：**歐盟市民 PII 原則** b. 描述：**保護歐洲市民的個人識別資訊**
6. 在 [選擇位置]**** 中，選取 [Office 365 中的所有位置]****。這將包含 Exchange 電子郵件中的內容和 OneDrive 與 SharePoint 文件。然後按 [下一步]****。
7. 在 [自訂您要保護的內容類型]**** 中，按一下 [尋找內容中包含：]****，然後按一下 [編輯]****。
8. 在 [選擇要保護的內容類型]**** 中，按一下 [新增] **** >  [敏感資訊類型]****。
9. 在 [敏感資訊類型]**** 中，按一下 [+ 新增]****。
10. 在 [敏感資訊類型]**** 中，搜尋 **IBAN**、選取 [國際銀行帳號 (IBAN)]**** 的核取方塊，然後按一下 [新增]****。
11. 請確認已新增 [國際銀行帳號 (IBAN)]**** 敏感資訊類型，然後按一下 [完成]****。
12. 在 [內容包含]**** 中，確認已新增敏感資訊類型，然後按一下 [儲存]****。
13. 在 [自訂您要保護的內容類型]**** 中，確認 [尋找內容中包含：]**** 包含 [國際銀行帳號 (IBAN)]****，然後按 [下一步]****。
14. 在 [當共用的內容中包含以下項目時進行偵測：]****，將值從 **10** 變更為 **1**，然後按 [下一步]****。
15. 在 [要先開啟原則或測試內容嗎?]**** 中，選擇下列設定，然後按 [下一步]****。  
    a. 選取 [我想要先進行測試]**** 的選項  
    b. 選取 [在測試模式中顯示原則提示]**** 的核取方塊 
16. 檢視設定之後，在 [檢視您的設定]**** 中，按一下 [建立]****。附註：建立新的 DLP 原則之後，需要一段時間才會生效。
17. 在本機電腦上，開啟瀏覽器的私人執行個體。
18. 在網址列中，輸入 **https://**\<您的租用戶名稱\>**.sharepoint.com**，並使用您的全域系統管理員帳戶登入。
19. 按一下 [文件]****。
20. 按一下名為 'IBANs.docx' 的檔案。您應該會看到「IBANs.docx 的原則提示」。IBANs.docx 檔案曾與外部收件者共用，因此會違反 DLP 原則。 
21. 在網址列中，輸入：`https://outlook.office365.com`
22. 按一下 [新增] **** -  [電子郵件訊息]****，並提供下列內容：  
    - **收件者：**\<個人電子郵件地址\>  
    - **主旨：** GDPR 測試  
    - **本文：** 複製值表格，如下所示。
  
        |數字  |國家/地區  |代碼 |IBAN  |
        |---------|---------|---------|---------|
        |1     |  奧地利 SEPA      | AT            |AT611904300234573201       |
        |2     |  保加利亞 SEPA       |BG    |BG80BNBG96611020345678      |
        |3     |  丹麥 SEPA      |   DK      |DK5000400440116243      |
        |4     |  芬蘭 SEPA      |   FI      |FI2112345600000785         |
        |5     |  法國 SEPA       |   FR      |FR1420041010050500013M02606         |
        |6     |  德國 SEPA      |   DE      |DE89370400440532013000         |
        |7     |  希臘 SEPA       |   GR      |GR1601101250000000012300695         |
        |8     |  義大利 SEPA       |    IT     |GR1601101250000000012300695         |
        |9     |  荷蘭 SEPA      |   NL      |   NL91ABNA0417164300      |
        |10     | 波蘭 SEPA       |  PL       | PL27114020040000300201355387        |

附註：此範例資料集衍生自公開提供的資訊，而且旨在用於測試目的而已。

23. 您會看到 DLP 原則已辨識出電子郵件內文包含 IBAN ，並會在郵件視窗頂端提供原則提示。
24. 關閉瀏覽器的私用執行個體。


## <a name="phase-6-demonstrate-reporting"></a>階段 6：展示報告
 
在這個階段中，您要根據階段 5 中所設定的 DLP 原則來展示 Office 365 報告。

   1. 從瀏覽器的 [安全性與合規性] 索引標籤中，按一下 [首頁]****。
   2. 按一下 [報告] **** >  [儀表板] **** >  [DLP 原則相符項目]****。
   3. DLP 原則可協助您識別及保護組織的敏感資訊。例如，您會在報告中看到原則已識別包含在 SharePoint Online 中儲存之 IBAN 的文件。
  
## <a name="see-also"></a>另請參閱

[GDPR 的 Office 365 資訊保護](office-365-information-protection-for-gdpr.md)

[GDPR for Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
