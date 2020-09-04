---
title: '資料調查 (預覽中支援的檔案類型) '
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 列出支援的檔案類型及可供查看以進行資料調查 (預覽) 的檢視器的表格。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95af625ece261061d6f797b50a382b1905254326
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357735"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>資料調查 (預覽中支援的檔案類型) 

資料調查 (預覽) 會以數種不同的方式支援許多檔案類型，如下表所述。 此清單尚未完成，我們會在繼續進行驗證測試時，新增檔案類型。 該表也會指出在您檢查證據時，是否可以在可用的檢視器中查看檔案類型。

| Mime 類型 | 檔類別 | 原生檢視器 | 文字檢視器 | 批註檢視器 | 容器提取 | Extensions |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | 文件 | 是 | 是 | 是 | 否 | .doc; .dat |
| application/pdf | 文件 | 是 | 是 | 是 | 否 | .pdf |
| application/rtf | 文件 | 是 | 是 | 是 | 否 | .rtf;。醫生 |
| application/vnd.ms-excel。 ms-excel | 文件 | 是 | 是 | 是 | 否 | .xls; .dat |
| ms-excel 的 macroenabled （vnd.ms-excel） | 生產力/開放式檔案格式 | 是 | 是 | 否 | 否 | 。 xlsb |
| ms-excel macroenabled （vnd.ms-excel） | 文件 | 是 | 是 | 是 | 否 | 。 xlsm |
| ms-excel macroenabled （vnd.ms-excel） | 生產力/開放式檔案格式 | 否 | 是 | 否 | 否 | 。 xltm |
| application/vnd.ms-excel。 ms-outlook | 生產力 | 否 | 否 | 否 | 否 | .msg |
| application/vnd.ms-excel。 ms-outlook-pst | 生產力/共同作業 | 否 | 否 | 否 | 是 | .pst |
| application/vnd.ms-excel。 ms-powerpoint | 文件 | 是 | 是 | 是 | 否 | .ppt; .pps;。鍋 |
| application/vnd.ms-word.document macroenabled | 文件 | 是 | 是 | 是 | 否 | .docm |
| ms-word macroenabled （vnd.ms-excel） | 文件 | 是 | 是 | 是 | 否 | normal.dotm |
| oasis。 text vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | odt  |
| openxmlformats-officedocument presentationml。簡報中的 vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | .pptx |
| openxmlformats-officedocument 的 presentationml。投影片放映 vnd.ms-excel | 生產力/開放式檔案格式 | 是 | 是 | 是 | 否 | 。 ppsx |
| openxmlformats-officedocument presentationml。 vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | 。 potx |
| openxmlformats-officedocument 的 spreadsheetml （應用程式/vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | .xlsx |
| openxmlformats-officedocument spreadsheetml。 vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | 。 .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 文件 | 是 | 是 | 是 | 否 | .docx |
| openxmlformats-officedocument wordprocessingml。 vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | 。 dotx |
| application/vnd.ms-excel。 visio | 文件 | 是 | 是 | 是 | 否 | .vsd |
| application/x-7z-壓縮 | 封存/容器 | 否 | 否 | 否 | 是 | .7z |
| application/xhtml + xml | 文件 | 是 | 是 | 是 | 否 | 的 xhtml |
| application/xml | 文件 | 是 | 是 | 是 | 否 | .xml |
| application/x-msaccess | 文件 | 是 | 是 | 是 | 否 | .mdb |
| application/x-mspublisher | 文件 | 是 | 是 | 是 | 否 | pub |
| application/x-已壓縮的 rar | 封存/容器 | 否 | 否 | 否 | 是 | rar |
| application/zip | 封存/容器 | 否 | 否 | 否 | 是 | .zip |
| 影像/bmp | 影像 | 是 | 是 | 是 | 否 | .bmp |
| 影像/emf | 影像 | 是 | 是 | 是 | 否 | .emf |
| image/gif | 文件 | 是 | 是 | 是 | 否 | .gif |
| 影像/jpeg | 影像 | 是 | 是 | 是 | 否 | .jpg;. jpeg; .dat;。jpgt |
| image/png | 影像 | 是 | 是 | 是 | 否 | .png |
| 影像/tiff | 影像 | 是 | 是 | 是 | 否 | .tif |
| image/vnd.ms-excel | 文件 | 是 | 是 | 是 | 否 | dwg;。dxf |
| image/wmf | 文件 | 是 | 是 | 是 | 否 | .wmf |
| message//rfc822 | 生產力/共同作業 | 否 | 否 | 否 | 否 | .eml |
| 文字/csv | 文件 | 是 | 是 | 是 | 否 | .csv |
| 文字/html | 文件 | 是 | 是 | 是 | 否 | .html;。shtml; .htm |
| 文字/無格式 | 文件 | 是 | 是 | 是 | 否 | .txt; .css;。con;. pl; .csv; .dat |
| 文字/電子名片-連絡人 | 文件 | 是 | 是 | 是 | 否 | .vcf |
||||||||
