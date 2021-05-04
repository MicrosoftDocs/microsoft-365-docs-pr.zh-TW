---
title: 「資料遺失防護」 (DLP) 功能的尋找方式
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: 瞭解 DLP) 功能 (的資料遺失防護功能的尋找方式。
ms.openlocfilehash: 47eda79470fd131939c493ac4f66af6efea01dd6
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086510"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 功能所尋找的項目

資料遺失防護 (DLP) 原則可以使用敏感資訊類型來識別敏感專案。 信用卡號碼和歐盟借貸卡號碼是敏感資訊類型的範例。 敏感資訊類型會尋找特定的模式。 敏感資訊類型會透過查看其格式、其校驗和，尋找相關的關鍵字或其他資訊來驗證資料。 此功能的部分功能是由內建函式執行。 例如，「信用卡號碼敏感資訊類型」會使用函式來尋找格式類似到期日的日期。 這有助於 corroborate 號碼為信用卡號碼。
  
本文說明這些功能的含義，以協助您瞭解預先定義的機密資訊類型的運作方式。 如需詳細資訊，請參閱 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>函數資料表

|函數名稱  |function 動作  |是驗證程式|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|偵測和驗證阿根廷唯一稅務金鑰|否|
|Func_aba_routing|偵測 ABA 路由號碼| 是|
|Func_alabama_drivers_license_number|偵測 Alabama 駕駛執照號碼|否|
|Func_alaska_delaware_oregon_drivers_license_number|偵測阿拉斯加，特拉華州，俄勒岡駕駕執照號碼|否|
|Func_alaska_drivers_license_number|偵測阿拉斯加駕駛執照號碼|否|
|Func_alberta_drivers_license_number|偵測 Alberta 駕駛執照號碼|否|
|Func_Argentina_Unique_Tax_Key|偵測阿根廷唯一的稅碼|否|
|Func_arizona_drivers_license_number|偵測亞利桑那駕執照號碼|否|
|Func_arkansas_drivers_license_number|偵測 Arkansas 駕駛執照號碼|否|
|Func_australian_business_number|偵測澳大利亞商務電話號碼|否|
|Func_Australian_Company_Number|偵測澳大利亞公司號碼|否|
|Func_australian_medical_account_number|偵測澳大利亞醫療帳戶號碼|否|
|Func_australian_tax_file_number|偵測澳大利亞稅收檔編號|是|
|Func_austria_eu_ssn_or_equivalent|偵測奧地利的社會安全號碼|否|
|Func_austria_eu_tax_file_number|偵測奧地利稅收檔編號|否|
|Func_Austria_Value_Added_Tax|偵測奧地利加值稅|否|
|Func_belgium_national_number|偵測比利時國號碼|否|
|Func_belgium_value_added_tax_number|偵測比利時增值的稅號|否|
|Func_brazil_cnpj|偵測巴西法人編號 (CNPJ) |是|
|Func_brazil_cpf|偵測巴西 CPF|是|
|Func_brazil_rg|偵測巴西 RG|否|
|Func_british_columbia_drivers_license_number|偵測英屬哥倫比亞駕駛執照號碼|否|
|Func_bulgaria_eu_national_id_card|偵測保加利亞統一的民事編號|否|
|Func_california_drivers_license_number|偵測加州駕照編號|否|
|Func_canadian_sin|偵測加拿大 sin|是|
|Func_chile_id_card|偵測智利識別碼卡片|否|
|Func_china_resident_id|偵測中國居民識別碼|否|
|Func_colorado_drivers_license_number|偵測科羅拉多駕照編號|否|
|Func_connecticut_drivers_license_number|偵測 Connecticut 駕駛執照號碼|否|
|Func_credit_card|偵測信用卡|是|否|
|Func_croatia_id_card|偵測到克羅地亞識別碼卡片|否|
|Func_croatia_oib_number|偵測克羅地亞 OIB 號碼|否|
|Func_cyprus_eu_tax_file_number|偵測賽普勒斯稅收檔編號|否|
|Func_czech_id_card|偵測捷克 ID 卡|否|
|Func_czech_id_card_new_format|以新格式偵測捷克 ID 卡|否|
|Func_dea_number|偵測 DEA 號碼|是|
|Func_denmark_eu_tax_file_number|偵測丹麥個人身分識別號碼|否|
|Func_district_of_columbia_drivers_license_number|偵測的地區的哥倫比亞駕執照號碼|否|
|Func_estonia_eu_national_id_card|偵測愛沙尼亞個人識別碼|否|
|Func_eu_debit_card|偵測歐盟借貸卡|否|
|Func_finnish_national_id|偵測芬蘭國 ID|否|
|Func_florida_drivers_license_number|偵測佛羅里達駕照編號|否|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|偵測佛羅里達、Maryland、密歇根州 Minnesota 駕駛執照號碼|否|
|Func_formatted_itin|偵測已格式化的 US ITIN|是|
|Func_fr_insee|偵測法國 INSEE|否|
|Func_fr_passport|偵測法國護照|否|
|Func_france_eu_tax_file_number|偵測法國稅收檔編號|否|
|Func_france_value_added_tax_number|偵測法國加值稅號|否|
|Func_french_drivers_license|偵測法文駕駛執照|否|
|Func_french_insee|偵測法語 INSEE|否|
|Func_georgia_drivers_license_number|偵測格魯吉亞駕照編號|否|
|Func_german_drivers_license|偵測德國駕照|否|
|Func_german_passport|偵測德國護照|否|
|Func_german_passport_data|偵測德國護照|否|
|Func_germany_eu_tax_file_number|偵測德國稅收檔編號|否|
|Func_germany_value_added_tax_number|偵測德國增值的納稅號碼|否|
|Func_greece_eu_ssn|偵測希臘 sin (AMKA) |否|
|Func_hawaii_drivers_license_number|偵測夏威夷駕照號碼|否|
|Func_hong_kong_id_card |偵測中國香港 ID 卡|否|
|Func_hungarian_value_added_tax_number|偵測匈牙利值增加的稅務編號|否|
|Func_hungary_eu_national_id_card|偵測匈牙利個人身分識別號碼|否|
|Func_hungary_eu_ssn_or_equivalent|偵測匈牙利社會安全號碼|否|
|Func_hungary_eu_tax_file_number|偵測匈牙利稅收檔編號|否|
|Func_iban|偵測 IBAN|是|
|Func_idaho_drivers_license_number|偵測 Idaho 駕駛執照號碼|否|
|Func_illinois_drivers_license_number|偵測 Illinois 駕駛執照號碼|否|
|Func_india_aadhaar|偵測印度 aadhaar|是|
|Func_indiana_drivers_license_number|偵測印地安件駕駛執照號碼|否|
|Func_iowa_drivers_license_number|偵測 Iowa 駕駛執照號碼|否|
|Func_ireland_pps|偵測愛爾蘭 PPS|否|
|Func_israeli_national_id_number|偵測以色列國家 ID 號碼|否|
|Func_italy_eu_national_id_card |偵測義大利會計代碼|否|
|Func_italy_value_added_tax_number|偵測義大利增值的納稅號碼|否|
|Func_japanese_my_number_corporate|偵測日本我的數位公司|是|
|Func_japanese_my_number_personal|偵測日本我的號碼個人|是|
|Func_jp_bank_account|偵測日本銀行帳戶|否|
|Func_jp_bank_account_branch_code|偵測日本銀行帳戶分支碼|否|
|Func_jp_drivers_license_number|偵測日本駕駛執照號碼|否|
|Func_jp_passport|偵測日本護照|否|
|Func_jp_resident_registration_number|偵測日本居民註冊號碼|否|
|Func_jp_sin|偵測日本 SIN|否|
|Func_jp_sin_pre_1997|偵測日本 sin pre 1997|否|
|Func_kansas_drivers_license_number|偵測 Kansas 駕駛執照號碼|否|
|Func_kentucky_drivers_license_number|偵測 Kentucky 駕駛執照號碼|否|
|Func_kentucky_massachusetts_virginia_drivers_license_number|偵測 Kentucky，麻塞諸塞州弗吉尼亞州駕照編號|否|
|Func_latvia_eu_national_id_card|偵測拉脫維亞個人代碼|否|
|Func_lithuania_eu_tax_file_number|偵測到立陶宛個人程式碼|否|
|Func_louisiana_drivers_license_number|偵測 Louisiana 駕駛執照號碼|否|
|Func_luxemburg_eu_tax_file_number|偵測 (自然個人的 Luxemburg 國身分識別號碼) |否|
|Func_luxemburg_eu_tax_file_number_non_natural|偵測 (非自然人員的 Luxemburg 國身分識別號碼) |否|
|Func_maine_drivers_license_number|偵測 Maine 駕駛執照號碼|否|
|Func_manitoba_drivers_license_number|偵測 Manitoba 駕駛執照號碼|否|
|Func_maryland_drivers_license_number|偵測 Maryland 駕駛執照號碼|否|
|Func_massachusetts_drivers_license_number|偵測麻塞諸塞州駕駛執照號碼|否|
|Func_mexico_population_registry_code|偵測墨西哥填入登錄程式碼|否|
|Func_michigan_minnesota_drivers_license_number|偵測密歇根州的 Minnesota 駕駛執照號碼|否|
|Func_minnesota_drivers_license_number|偵測 Minnesota 駕駛執照號碼|否|
|Func_mississippi_oklahoma_drivers_license_number|偵測 Mississippi、Oklahoma 駕駛執照號碼|否|
|Func_missouri_drivers_license_number|偵測 Missouri 駕駛執照號碼|否|
|Func_montana_drivers_license_number|偵測 Montana 駕駛執照號碼|否|
|Func_nebraska_drivers_license_number|偵測 Nebraska 駕駛執照號碼|否|
|Func_netherlands_bsn|偵測荷蘭 BSN|否|
|Func_netherlands_eu_tax_file_number|偵測到荷蘭稅務檔編號|否|
|Func_netherlands_value_added_tax_number|偵測荷蘭增值的納稅號碼|否|
|Func_nevada_drivers_license_number|偵測 Nevada 駕駛執照號碼|否|
|Func_new_brunswick_drivers_license_number|偵測新的 Brunswick 駕駛執照號碼|否|
|Func_new_hampshire_drivers_license_number|偵測新的 Hampshire 駕駛執照號碼|否|
|Func_new_jersey_drivers_license_number |偵測新的 Jersey 駕駛執照號碼|否|
|Func_new_mexico_drivers_license_number |偵測新的墨西哥駕駛執照號碼|否|
|Func_new_york_drivers_license_number   |偵測紐約駕駛執照號碼|否|
|Func_new_zealand_bank_account_number   |偵測紐西蘭銀行帳戶號碼|否|
|Func_new_zealand_inland_revenue_number |偵測紐西蘭 inland 收入數目|否|
|Func_new_zealand_ministry_of_health_number|偵測新的紐西蘭健康情況號碼|否|
|Func_newfoundland_labrador_drivers_license_number|偵測紐芬蘭 Labrador 駕駛執照號碼|否|
|Func_newzealand_driver_license_number  |偵測紐西蘭駕駛執照號碼|否|
|Func_newzealand_social_welfare_number  |偵測紐西蘭社交 welfare 號碼|否|
|Func_north_carolina_drivers_license_number|偵測北卡羅萊納州駕駛執照號碼|否|
|Func_north_dakota_drivers_license_number|偵測北美 Dakota 駕駛執照號碼|否|
|Func_norway_id_number  |偵測挪威 ID 號碼|否|
|Func_nova_scotia_drivers_license_number|偵測 Nova Scotia 駕駛執照號碼|否|
|Func_ohio_drivers_license_number   |偵測 Ohio 駕駛執照號碼|否|
|Func_ontario_drivers_license_number    |偵測安大略駕駛執照號碼|否|
|Func_pennsylvania_drivers_license_number|偵測賓夕法尼亞州駕照編號|否|
|Func_pesel_identification_number   |偵測到波蘭國家識別碼 (PESEL) |否|
|Func_poland_eu_tax_file_number |偵測波蘭稅務檔案編號|否|
|Func_polish_national_id    |偵測波蘭身分識別卡|否|
|Func_polish_passport_number    |偵測波蘭文護照號碼|否|
|Func_polish_regon_number   |偵測波蘭 REGON 編號|否|
|Func_portugal_eu_tax_file_number|偵測葡萄牙納稅識別號碼|否|
|Func_prince_edward_island_drivers_license_number|偵測 Prince Edward 島駕駛執照號碼|否|
|Func_quebec_drivers_license_number |偵測到魁北克駕駛執照號碼|否|
|Func_randomized_formatted_ssn  |偵測隨機格式化的 US SSN|是|
|Func_randomized_unformatted_ssn|偵測隨機格式化的 US SSN|是|
|Func_rhode_island_drivers_license_number|偵測 Rhode 島駕駛執照號碼|否|
|Func_romania_eu_national_id_card   |偵測 CNP)  (的羅馬尼亞個人數位代碼|否|
|Func_saskatchewan_drivers_license_number|偵測薩斯駕駛執照號碼|否|
|Func_slovakia_eu_national_id_card  |偵測斯洛伐克個人號碼|否|
|Func_slovenia_eu_national_id_card  |偵測斯洛維尼亞唯一主公民號碼|否|
|Func_slovenia_eu_tax_file_number   |偵測斯洛維尼亞稅收檔編號|否|
|Func_south_africa_identification_number|偵測南非身分識別號碼|是|
|Func_south_carolina_drivers_license_number|偵測南部卡羅萊納州駕駛執照號碼|否|
|Func_south_dakota_drivers_license_number|偵測南 Dakota 駕駛執照號碼|否|
|Func_south_korea_resident_number   |偵測韓國居民號碼|否|
|Func_spain_eu_DL_and_NI_number_citizen |偵測西班牙 DL 和 NI 號碼公民|否|
|Func_spain_eu_DL_and_NI_number_foreigner|偵測西班牙 DL 和 NI 號碼 foreigner|否|
|Func_spain_eu_driver ' s_license_number  |偵測西班牙駕駛執照號碼|否|
|Func_spain_eu_tax_file_number  |偵測西班牙稅收檔編號|否|
|Func_spanish_social_security_number|偵測西班牙文的社交安全性號碼|否|
|Func_ssn   |偵測非隨機格式化的 US SSN 的函數|是|
|Func_sweden_eu_tax_file_number|偵測瑞典稅收檔編號|否|
|Func_swedish_national_identifier|偵測瑞典文國家識別碼|是|
|Func_swiss_social_security_number_ahv|偵測到瑞士社會安全號碼 AHV|否|
|Func_taiwanese_national_id |偵測臺灣國家 ID|否|
|Func_tennessee_drivers_license_number|偵測 Tennessee 駕駛執照號碼|否|
|Func_texas_drivers_license_number  |偵測德克薩斯駕照編號|否|
|Func_Thai_Citizen_Id   |偵測泰語公民識別碼|否|
|Func_Turkish_National_Id|偵測土耳其文國家識別碼|是|
|Func_uk_drivers_license|偵測英國駕照|否|
|Func_uk_eu_tax_file_number|偵測 UK 唯一的納稅人編號|否|
|Func_uk_nhs_number |偵測 UK NHS 號碼|是|
|Func_uk_nino   |偵測 UK NINO|否|
|Func_unformatted_canadian_sin|偵測未格式化的加拿大 SIN|否|
|Func_unformatted_itin  |偵測未格式化的 US ITIN|是|
|Func_unformatted_ssn   |偵測非隨機格式化的 US SSN|是|
|Func_usa_uk_passport   |偵測美國和英國護照|是|
|Func_utah_drivers_license_number|偵測猶他州駕照編號|否|
|Func_vermont_drivers_license_number|偵測 Vermont 駕駛執照號碼|否|
|Func_virginia_drivers_license_number|偵測弗吉尼亞州駕照編號|否|
|Func_washington_drivers_license_number|偵測華盛頓駕照編號|否|
|Func_west_virginia_drivers_license_number|偵測西佛吉尼亞州駕照編號|否|
|Func_wisconsin_drivers_license_number  |偵測 Wisconsin 駕駛執照號碼|否|
|Func_wyoming_drivers_license_number    |偵測 Wyoming 駕駛執照號碼|否|


## <a name="func_us_date"></a>Func_us_date

Func_us_date 會尋找常見的 U.S. 格式的日期。 通用格式為 "月/日/年"、「月-日-年」和「年月日」。 月份的名稱或縮寫不區分大小寫。 
  
範例：
  
- 2016年12月2日
    
- 2016年12月2日
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
公認的月份名稱：
  
- 英文
    
  - 一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月
    
  - Mar 年4月4月8日（11月11日）。
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates 尋找共同歐盟的日期 格式 (和大多數在美國以外的位置 ) ，例如「天/月/年」、「日-月-年」和「日月」。 月份的名稱或縮寫不區分大小寫。
  
範例：
  
- 2 Dec 2016
    
- 02 dec 2016
    
- 2 Dec 16
    
- 2/12/2016
    
- 02/12/16
    
- 2月2日-2016
    
- 2-12-16
    
公認的月份名稱：
  
- 英文
    
  - 一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月
    
  - Mar 年4月4月8日（11月11日）。
    
- 荷蘭文
    
  - januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月
    
  - jan jan maart apr mei 年9月8日9月 okt 年11月
    
- 法文
    
  - janvier，février，mars，avril，mai，juin juillet，août，septembre，octobre，novembre，décembre
    
  - janv. févr. mars avril mai juin juil。 août 年9月。 2008. 11 月。 déc.
    
- 德文
    
  - jänuar，februar，märz，四月，mai，juni juli，八月，九月份，oktober，11月，dezember
    
  - Jan./Jän。 März Apr Juni Juli 08 月 Okt。 Dez 年11月。
    
- 義大利文
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. 三月。 四月。 magg. giugno luglio ag。 sett. 奧特。 11 月。 Dic。
    
- 葡萄牙文
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai 06 年6月1日，設定為11月 dez
    
- 西班牙文
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero 年2月。 marzo abr。 mayo 年6月。 七月。 agosto/set。 2008. 11 月。 Dic。
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (已被取代) 

> [!NOTE]
> 此函數已過時，因為它只支援葡萄牙文月份名稱，而這些名稱現在已包含在  `Func_eu_date` 上述函數中。 
  
此函數會以葡萄牙文中常用的格式來尋找日期。 此函數的格式與  `Func_eu_date` 使用的語言不同。
  
範例：
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
公認的月份名稱：
  
- 葡萄牙文
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai 06 年6月1日，設定為11月 dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (已被取代) 

> [!NOTE]
> 此函數已過時，因為它只支援荷蘭月份名稱，而這些名稱現在已包含在  `Func_eu_date` 上述函數中。 
  
此函數會以荷蘭文中常用的格式來尋找日期。 此函數的格式與  `Func_eu_date` 使用的語言不同。
  
範例：
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
公認的月份名稱：
  
- 荷蘭文
    
  - januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月
    
  - jan jan maart apr mei 年6月8日9月9日在十二月進行 okt
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date 會尋找信用卡和轉帳卡常用格式的日期。 此函數會比對「月/年」、「月-年」、「[month name] 年] 和「[month 簡寫] 年 "格式的日期。 月份的名稱或縮寫不區分大小寫。
  
範例：
  
- MM/YY--例如01/11 或1/11
    
- MM/YYYY--例如01/2011 或1/2011
    
- MM-YY--例如01-22 或1-11
    
- MM-YYYY--例如01-2000 或1-2000
    
下列格式支援 YY 或 YYYY：
  
- Month-YYYY--2010 年1月1日或一月-2010 或 Jan-10 或年1月1日
    
- Month YYYY--例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"
    
- MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"
    
- Month/YYYY--例如，' 一月份/2010 ' 或 ' Jan/2010 ' or "Jan/10" 或 "Jan/10"
    
公認的月份名稱：
  
- 英文
    
  - 一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月
    
  - Jan 02 月4月8日在十二月
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address 會尋找美國的狀態名稱或郵政縮寫後接有效的郵遞區號。 郵遞區號必須是與美國州名稱或縮略語相關聯的正確郵遞區號之一。 美國的狀態名稱及郵遞區號不能以標點符號或字母分隔。
  
範例：
  
- 華盛頓98052
    
- 華盛頓98052-9998
    
- WA 98052
    
- WA 98052-9998
