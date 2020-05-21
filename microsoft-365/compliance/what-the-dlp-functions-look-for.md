---
title: DLP 功能所尋找的項目
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 敏感資訊類型會尋找特定的模式，並透過確認正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊來 corroborate。 此功能的部分功能是由內建函式執行。 本主題說明這些功能的含義，以協助您瞭解預先定義的機密資訊類型的運作方式。
ms.openlocfilehash: 710cd371cbf67a03d75a928baab4b63587cdcfc1
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327745"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 功能所尋找的項目

資料遺失防護（DLP）包含機密資訊類型，例如信用卡號碼和歐盟卡號，可供您在 DLP 原則中使用。 這些敏感資訊類型會尋找特定的模式，並加以 corroborate，方法是確認正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊。 此功能的部分功能是由內建函式執行。 例如，「信用卡號碼敏感資訊類型」會使用函數來尋找類似到期日的日期，以協助 corroborate 號碼是信用卡號碼。
  
本主題說明這些功能的含義，以協助您瞭解預先定義的機密資訊類型的運作方式。 如需詳細資訊，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
  
## <a name="func_us_date"></a>Func_us_date

此函數會以美國常用的格式來尋找日期。這包括「月/日/年」、「月-日-年」和「年月日」的格式。 月份的名稱或縮寫不區分大小寫。 
  
範例:
  
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

此函數會以歐盟常用的格式來尋找日期 （和美國以外的大部分地點）。 這包括格式「日/月/年」、「日-月-年」和「日月年」。 月份的名稱或縮寫不區分大小寫。
  
範例:
  
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
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 （已過時）

> [!NOTE]
> 此函數已過時，因為它只支援葡萄牙文月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。 
  
此函數會以葡萄牙文中常用的格式來尋找日期。 此函數的格式與 `Func_eu_date` 使用的語言不同。
  
範例:
  
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
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 （已過時）

> [!NOTE]
> 此函數已過時，因為它只支援荷蘭月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。 
  
此函數會以荷蘭文中常用的格式來尋找日期。 此函數的格式與 `Func_eu_date` 使用的語言不同。
  
範例:
  
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
    
  - jan jan maart apr mei 年9月8日9月 okt 年11月
    
## <a name="func_expiration_date"></a>Func_expiration_date

此函數會以信用卡和轉帳卡所使用的格式來尋找日期，而不是以月為單位來扣除天數。 此函數會比對「月/年」、「月-年」、「[month name] 年] 和「[month 簡寫] 年 "格式的日期。 月份的名稱或縮寫不區分大小寫。
  
範例:
  
- MM/YY--例如01/11 或1/11
    
- MM/YYYY--例如01/2011 或1/2011
    
- MM-YY--例如01-22 或1-11
    
- MM-YYYY--例如01-2000 或1-2000
    
下列格式支援 YY 或 YYYY：
  
- 例如，Month-YYYY--。Jan-2010 或一月-2010 或 Jan-10 或年1月
    
- Month YYYY--例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"
    
- MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"
    
- Month/YYYY--例如，' 一月份/2010 ' 或 ' Jan/2010 ' or "Jan/10" 或 "Jan/10"
    
公認的月份名稱：
  
- 英文
    
  - 一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月
    
  - Jan 02 月4月8日在十二月
    
## <a name="func_us_address"></a>Func_us_address

此函數會尋找美國的狀態名稱或郵政縮寫後接有效的郵遞區號，就像在通信地址中使用。 郵遞區號必須是與美國州名稱或縮略語相關聯的正確郵遞區號之一。 美國的狀態名稱及郵遞區號不能以標點符號或字母分隔。
  
範例:
  
- 華盛頓98052
    
- 華盛頓98052-9998
    
- WA 98052
    
- WA 98052-9998
    

