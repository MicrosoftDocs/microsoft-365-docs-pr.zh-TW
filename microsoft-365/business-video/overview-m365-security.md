---
title: 安全性 Microsoft 365 商務進階版概述
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 深入瞭解商務 Microsoft 365 隨附的安全性功能。
ms.openlocfilehash: 81b68bd4f41e53fb72dfee4345356c21a2040827
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842395"
---
# <a name="overview-of-security"></a>安全性概述

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 商務進階版提供威脅防護、資料保護和裝置管理功能，可協助您保護公司免受線上威脅和未經授權的存取，以及保護和管理手機、平板電腦和電腦上的公司資料。

|![威脅防護](../media/m365-business-security-threat-protection.png)<br/>[威脅防護](#threat-protection)|![與用戶端共同作業](../media/m365-business-security-data-protection.png) <br/>[資料保護](#data-protection) | ![裝置管理](../media/m365-business-security-device-management.png) <br/>[裝置管理](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>威脅防護

Microsoft 365 商務進階版包括[Office 365 的「高級威脅防護」 (ATP) ](safe-links.md)，這是一種雲端式電子郵件篩選服務，可防止惡意程式碼、勒索軟體、有害連結等等。 ATP 安全連結可保護您的電子郵件或 Office 檔中的惡意 URLs。 ATP 安全附件可保護您免受惡意程式碼和附件的郵件或檔的侵擾。

[多重要素驗證 (MFA) ](turn-on-mfa.md)或雙步驟驗證，需要您提供另一種形式的驗證（例如驗證碼），以在存取資源之前確認您的身分識別。

[Windows Defender](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10)針對病毒、惡意程式碼、間諜軟體和其他威脅，提供系統、檔案及線上活動的綜合保護。

## <a name="data-protection"></a>資料保護

Microsoft 365 商務進階版中的資料保護功能可協助確定重要的資料是安全的，且只有經過授權的人員才能存取。

您可以使用 [資料遺失防護 (DLP) ](set-up-dlp.md) 原則，識別及管理機密資訊（例如社會保險或信用卡號碼），使其不會錯誤共用。

[Office 365 郵件加密](/microsoft-365/compliance/ome)結合加密和存取許可權功能，協助確保只有預定的收件者可以查看郵件內容。 Office 365 郵件加密可搭配 Outlook .com、yahoo！、Gmail 及其他電子郵件服務使用。

[Exchange Online 封存](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description)是雲端式封存解決方案，可與 Microsoft Exchange 或 Exchange Online 搭配使用，以提供高級封存功能（包括保留和資料冗余）。 您可以使用保留原則來協助您的組織減少電子郵件和其他通訊相關的債務。 如果您的公司需要保留與訴訟相關的通訊，您可以使用 In-Place 保留和訴訟保留以保留相關的電子郵件。

## <a name="device-management"></a>裝置管理

Microsoft 365 商務進階版高級裝置管理功能可讓您監視及控制使用者可對註冊的裝置執行的作業。 這些功能包括條件式存取、行動[裝置管理 (MDM) ](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)、BitLocker 和自動更新。

您可以使用條件式存取原則，針對特定使用者和任務需要其他安全性措施。 例如，您可以要求多重要素驗證 (MFA) 或封鎖不支援條件式存取的用戶端。

使用 MDM，您可以協助保護和管理使用者的行動裝置，例如 iphone、ipad、Androids 和 Windows 電話。 您可以建立及管理裝置安全性原則，以遠端方式清除裝置，以移除所有公司資料、將裝置重設為出廠設定，以及查看詳細的裝置報告。

您可以啟用 BitLocker 加密，協助保護資料以防裝置遺失或遭盜，並啟用 Windows Exploit Guard，以提供勒索軟體的高級防護。

您可以設定自動更新，使最新的安全性功能和更新套用至所有使用者裝置。

## <a name="recommended-security-guidance"></a>建議的安全性指導方針

如果您有 Microsoft 商務進階版，設定安全性並安全地開始共同作業的最快速方法是遵循此文件庫中的指引：[適用於小型企業和活動的 Microsoft 365](../campaigns/index.md)。 本指引是與 Microsoft Defending Democracy 團隊合作開發，可保護所有小型企業客戶抵禦老練駭客發動的網路威脅。
