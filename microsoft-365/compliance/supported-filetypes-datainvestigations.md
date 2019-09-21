---
title: 支援的檔案類型中的資料調查 （預覽）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 60e4baf2df94793b532fb4035a34ca3c7a5cd332
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077502"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>支援的檔案類型中的資料調查 （預覽）

資料調查 （預覽） 支援許多檔案類型中數種不同的方式下, 表所述。 這份清單未完成，並為我們繼續我們驗證測試，我們會將新增新的檔案類型。 表也表示是否檢視可用的檢視器中的檔案類型時您正在檢閱證據。

| Mime 類型 | 檔案類別 | 原生檢視器 | 文字檢視器 | 加上註解檢視器 | 容器擷取 | Extensions |
| :- | :- | :- | :- | :- | :- | :- |
| 應用程式/msword | Document | 是 | 是 | 是 | 否 | .doc;.dat |
| 應用程式/pdf | Document | 是 | 是 | 是 | 否 | .pdf |
| 應用程式/rtf | Document | 是 | 是 | 是 | 否 | .rtf;。doc |
| 應用程式/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | .xls;.dat |
| application/vnd.ms-excel.sheet.binary.macroenabled.12 | 生產力 / Open Document 格式 | 是 | 是 | 否 | 否 | .xlsb |
| application/vnd.ms-excel.sheet.macroenabled.12 | Document | 是 | 是 | 是 | 否 | .xlsm |
| application/vnd.ms-excel.template.macroenabled.12 | 生產力 / Open Document 格式 | 否 | 是 | 否 | 否 | .xltm |
| 應用程式/vnd.ms-outlook | 生產力 | 否 | 否 | 否 | 否 | .msg |
| 應用程式/vnd.ms-outlook 的 pst | 生產力 / 共同作業 | 否 | 否 | 否 | 是 | .pst |
| 應用程式/vnd.ms-powerpoint | Document | 是 | 是 | 是 | 否 | .ppt，.pps;。pot |
| application/vnd.ms-word.document.macroenabled.12 | Document | 是 | 是 | 是 | 否 | .docm |
| application/vnd.ms-word.template.macroenabled.12 | Document | 是 | 是 | 是 | 否 | .dotm |
| application/vnd.oasis.opendocument.text | Document | 是 | 是 | 是 | 否 | .odt;  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | 是 | 是 | 是 | 否 | .pptx |
| application/vnd.openxmlformats-officedocument.presentationml.slideshow | 生產力 / Open Document 格式 | 是 | 是 | 是 | 否 | .ppsx |
| application/vnd.openxmlformats-officedocument.presentationml.template | Document | 是 | 是 | 是 | 否 | .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | 是 | 是 | 是 | 否 | .xlsx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.template | Document | 是 | 是 | 是 | 否 | .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | 是 | 是 | 是 | 否 | .docx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.template | Document | 是 | 是 | 是 | 否 | .dotx |
| application/vnd.visio | Document | 是 | 是 | 是 | 否 | .vsd |
| 應用程式/x-7z-壓縮 | 封存 / 容器 | 否 | 否 | 否 | 是 | .7z |
| 應用程式/xhtml + xml | Document | 是 | 是 | 是 | 否 | .xhtml |
| 應用程式/xml | Document | 是 | 是 | 是 | 否 | .xml |
| 應用程式/x-msaccess | Document | 是 | 是 | 是 | 否 | .mdb |
| 應用程式/x-mspublisher | Document | 是 | 是 | 是 | 否 | .pub |
| 應用程式/x-rar-壓縮 | 封存 / 容器 | 否 | 否 | 否 | 是 | .rar |
| 應用程式/zip | 封存 / 容器 | 否 | 否 | 否 | 是 | .zip |
| image/bmp | 影像 | 是 | 是 | 是 | 否 | .bmp |
| image/emf | 影像 | 是 | 是 | 是 | 否 | .emf |
| image/gif | Document | 是 | 是 | 是 | 否 | .gif |
| image/jpeg | 影像 | 是 | 是 | 是 | 否 | .jpg、.jpeg、.dat;。jpgt |
| image/png | 影像 | 是 | 是 | 是 | 否 | .png |
| image/tiff | 影像 | 是 | 是 | 是 | 否 | .tif |
| image/vnd.dwg | Document | 是 | 是 | 是 | 否 | .dwg;。dxf; |
| image/wmf | Document | 是 | 是 | 是 | 否 | .wmf |
| message/rfc822 | 生產力 / 共同作業 | 否 | 否 | 否 | 否 | .eml |
| 文字/csv | Document | 是 | 是 | 是 | 否 | .csv |
| 文字/html | Document | 是 | 是 | 是 | 否 | .html;。shtml;.htm |
| 文字/一般 | Document | 是 | 是 | 是 | 否 | .txt;.css;。詐騙、.pl、.csv、.dat |
| 文字/vcard-連絡人 | Document | 是 | 是 | 是 | 否 | .vcf |
||||||||
