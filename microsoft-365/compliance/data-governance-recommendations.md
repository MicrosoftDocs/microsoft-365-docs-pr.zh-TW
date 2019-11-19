---
title: 如何辨識內容以提供資料控管建議
ms.author: brendonb
author: laurawi
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 安全性與合規性中心會根據貴組織目前的環境設定來提供資料控管建議，您只要按幾下就可以完成各項設定。某些建議會先偵測貴組織中的特定內容，然後提供管理該內容的建議步驟。例如，建議可能會偵測包含營運關鍵內容的項目 (如律師-委託人權限或 NDA 資訊)，然後讓您在這些項目上自動套用保留標籤，確保這些項目按照需求予以分類和保留。此主題列出您可能會看到的資料控管建議，並說明提出之每個建議所偵測到的內容。
ms.openlocfilehash: e860a41b616be2265904775a63454aba1a6040c1
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2019
ms.locfileid: "38708064"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>如何辨識內容以提供資料控管建議

Office 365 安全性與合規性中心會根據貴組織目前的環境設定來提供資料控管建議，您只要按幾下就可以完成各項設定。某些建議會先偵測貴組織中的特定內容，然後提供管理該內容的建議步驟。例如，建議可能會偵測包含營運關鍵內容的項目 (如律師-委託人權限或 NDA 資訊)，然後讓您在這些項目上自動套用保留標籤，確保這些項目按照需求予以分類和保留。

此主題列出您可能會看到的資料控管建議，並說明提出之每個建議所偵測到的內容。

## <a name="clean-up-voicemail"></a>清理語音信箱

在使用者的信箱中偵測到識別為「語音信箱」郵件類型的電子郵件訊息時，即會顯示此建議。深入了解 [Exchange 中的郵件內容](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)。

## <a name="label-attorney-client-privilege-content"></a>設定律師-委託人權限內容的標籤 

符合以下任一條件時，會顯示這個建議。

- 在電子郵件訊息內文中偵測到以下任何關鍵字組合：
    - ACP
    - Attorney Client Privilege (律師-委託人權限)
    - Attorney-Client Privilege (律師-委託人權限)
    - Attorney-Client Privileged (律師-委託人權限)

- 在 SharePoint 或 OneDrive 檔案中偵測到以下任何關鍵字組合：
    - ACP
    - Attorney-Client Privilege* (律師-委託人權限)
    - AC Privilege (AC 權限)

## <a name="retain-audio-files"></a>保留音訊檔案

在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>保留 CAD 檔案

在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>保留影像檔

在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>保留 NDA 內容 

符合以下任一條件時，會顯示這個建議。

- 在電子郵件訊息內文中偵測到以下任何關鍵字組合：
    - NDA
    - “Non-Disclosure Agreement” (保密合約)
    - “Non Disclosure Agreement” (保密合約)

- 在 SharePoint 或 OneDrive 的 .PDF 或 .DOC 檔案中偵測到以下任何關鍵字組合：
    - NDA
    - Non Disclosure Agreement (保密合約)

## <a name="retain-software-development-files"></a>保留軟體開發檔案

在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>保留影片檔案

在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
