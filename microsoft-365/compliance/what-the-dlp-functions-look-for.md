---
title: DLP 功能所尋找的項目
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
description: 敏感資訊類型尋找特定的模式，並證實來確保適當的格式設定、 強制執行總和檢查碼，並尋找相關的關鍵字或其他資訊。 某些這項功能是由內部函式執行。 本主題說明這些函式查詢，以協助您瞭解預先定義的敏感資訊類型的運作方式。
ms.openlocfilehash: c192a17c488e5a7252a3599204d2bdeda4d0637c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077642"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 功能所尋找的項目

資料外洩防護 (DLP) 包含敏感資訊類型，例如信用卡號碼和歐盟轉帳卡號碼，可供您在 DLP 原則中使用。 這些敏感資訊類型尋找特定的模式，並證實來確保適當的格式設定、 強制執行總和檢查碼，並尋找相關的關鍵字或其他資訊。 某些這項功能是由內部函式執行。 例如，信用卡號碼敏感資訊類型會使用函數來看起來像到期日，以協助證實格式化的日期數字是信用卡號。
  
本主題說明這些函式查詢，以協助您瞭解預先定義的敏感資訊類型的運作方式。 如需詳細資訊，請參閱[敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="func_us_date"></a>Func_us_date

此函數會尋找常用在美國格式的日期這包括格式 「 月/日/年 」、 「 月-日-年 」，以及 「 月份日期年份 」。 縮寫的月份的名稱不區分大小寫。 
  
範例:
  
- 2016 年 12 月 2日日
    
- 2016 年 12 月 2日日
    
- 12 / 02 2016
    
- 2016 年 12 月 2 日
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
接受的月份名稱：
  
- 英文
    
  - January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - 年 1 月 2005 年 2 月 Mar.2004 年 4 月可能年 6 月 7 月 ie Sept.年 10 月 11 Dec。
    
## <a name="func_eu_date"></a>Func_eu_date

此函數會尋找在 E.U.中常用的格式的日期 （與許多美國以外的位置）。 這包括格式 「 日/月/年 」、 「 日-月-年 」，以及 「 日月年 」。 縮寫的月份的名稱不區分大小寫。
  
範例:
  
- 2 年 12 月 2016
    
- 2016 年 12 月 02
    
- 2 年 12 月 16
    
- 2016 年 2 月 12 日
    
- 02/12/16
    
- 2-Dec-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 英文
    
  - January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - 年 1 月 2005 年 2 月 Mar.2004 年 4 月可能年 6 月 7 月 ie Sept.年 10 月 11 Dec。
    
- 荷蘭文
    
  - januari，februari，maart、 April、 mei、 juni、 juli、 奧古斯特一，September、 ocktober，年 10 月、 年 11 月、 年 12 月
    
  - 年 2 月 maart apr mei 年 7 月年 8 月 sep 年 10 月 okt 年 12 月
    
- 法文
    
  - janvier，février，mars，avril、 mai、 juin juillet、 août、 septembre、 octobre，novembre décembre
    
  - janv。 févr。 mars avril mai juin juil。 août 年。 oct。 11 月。 déc。
    
- 德文
    
  - jänuar，februar，märz，April，mai，juni juli，August，September，oktober，November，dezember
    
  - Jan。 / Jän。 2005 年 2 月 März 2004 年 4 月 Mai Juni Juli ie Sept.Okt。 11 Dez。
    
- 義大利文
    
  - gennaio，febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre，ottobre，novembre dicembre
    
  - genn。 febbr。 mar。 apr。 magg。 giugno luglio ag。 是家。 ott。 11 月。 字典。
    
- 葡萄牙文
    
  - janeiro fevereiro、 março、 marco、 abril、 maio、 junho、 julho，agosto，setembro、 outubro、 novembro、 dezembro
    
  - jan fev mar abr mai 年 7 月以前 11 月 dez 出設定
    
- 西班牙文
    
  - enero，febrero、 marzo、 abril、 mayo、 junio、 julio、 agosto、 septiembre，octubre，noviembre diciembre
    
  - enero 年。 marzo abr. mayo 年。 年 7 月。 agosto sept./集。 oct。 11 月。 字典。
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 （已過時）

> [!NOTE]
> 這個函數已過時，因為它支援僅葡萄牙文的月份名稱，這樣現在已包含於`Func_eu_date`上述函數。 
  
此函數會尋找常用於葡萄牙文格式的日期。 這個函數的格式是相同`Func_eu_date`、 如上所述僅中所用的語言。
  
範例:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2016 年 2 月 12 日
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 葡萄牙文
    
  - janeiro fevereiro、 março、 marco、 abril、 maio、 junho、 julho，agosto，setembro、 outubro、 novembro、 dezembro
    
  - jan fev mar abr mai 年 7 月以前 11 月 dez 出設定
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 （已過時）

> [!NOTE]
> 這個函數已過時，因為它支援僅荷蘭文的月份名稱，這樣現在已包含於`Func_eu_date`上述函數。 
  
此函數會尋找在荷蘭文中常用的格式的日期。 這個函數的格式是相同`Func_eu_date`、 如上所述僅中所用的語言。
  
範例:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2016 年 2 月 12 日
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 荷蘭文
    
  - januari，februari，maart、 April、 mei、 juni、 juli、 奧古斯特一，September、 ocktober，年 10 月、 年 11 月、 年 12 月
    
  - 年 2 月 maart apr mei 年 7 月年 8 月 sep 年 10 月 okt 年 12 月
    
## <a name="func_expiration_date"></a>Func_expiration_date

此函數會尋找常使用的信用卡和轉帳卡，但不包括因月份的天數的格式的日期。 此函數會比對中的 「 月/年 」、 「 月-年 」、 「 [月份名稱] 年 」 和 「 [月份縮寫] 年 」 格式的日期。 縮寫的月份的名稱不區分大小寫。
  
範例:
  
- MM/YY--例如，01/11 或 1/11
    
- MM/YYYY--例如，01/2011年或 1/2011
    
- MM-YY--例如，01-22 或 1-11
    
- MM-YYYY--例如，01-2000年或 1-2000
    
下列格式支援 YY 或 YYYY:
  
- -MONTH-YYYY-例如。Jan 2010 或 january 2010 或 Jan 10 或 january-10
    
- Month YYYY--例如，' january 2010' 或 'Jan 2010' 或' january 10' 或 ' Jan 10'
    
- MonthYYYY--例如，'january2010' 或 'Jan2010' 或 'january10' 或者 'Jan10'
    
- Month/YYYY--例如，' january/2010 '或' Jan/2010 '、 'january/10' 或 ' Jan/10 '
    
接受的月份名稱：
  
- 英文
    
  - January、 February、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - Jan 年 3 月 Apr 可能年 6 月 7 日年 10 月 11 月 12 月
    
## <a name="func_us_address"></a>Func_us_address

此函數尋找美國狀態名稱或郵寄縮寫後面接著有效的郵遞區號，就像它們用於郵寄地址。 郵遞區號必須是郵遞區號的下列其中一個正確的美國狀態名稱或縮寫相關聯。 美國狀態名稱和郵遞區號無法以字母或標點符號分隔。
  
範例:
  
- Washington 98052
    
- Washington 98052 9998
    
- WA 98052
    
- WA 98052 9998
    

