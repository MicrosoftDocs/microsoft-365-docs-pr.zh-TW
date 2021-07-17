---
title: 針對 Office 365、構造、建立及設計框架，檢查 Microsoft Defender 的架構需求和規劃概念
description: Microsoft 365 Defender 中的 Microsoft Defender Office 365 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457877"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>查看 Microsoft Defender 以取得 Office 365 架構需求和重要概念


**適用於：**
- Microsoft 365 Defender

本文是為 Office 365 的 Microsoft Defender 設定評估環境過程中的[步驟1之 3](eval-defender-office-365-overview.md) 。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-office-365-overview.md)。

在啟用 Office 365 的 Defender 之前，請確定您瞭解架構並可滿足需求。 本文說明架構、重要概念，以及您的 Exchange Online 環境必須符合的必要條件。

## <a name="understand-the-architecture"></a>了解架構

下圖說明 Microsoft Defender for Office 的基準架構，其中可以包含協力廠商 SMTP 閘道或內部部署整合。 混合共存案例 (亦即，實際執行和線上) 都需要更複雜的設定，而且不會包含在本文或評估指導中。

![適用于 Office 365 的 Microsoft Defender 架構](../../media/defender/m365-defender-office-architecture.png)

下表說明此圖例。

|撥出  |說明  |
|---------|---------|
|1     | 外部寄件者的主機伺服器通常會對 MX 記錄執行公用 DNS 查閱，以提供目標伺服器轉送郵件。  這項參考可以直接 Exchange Online (EXO) 或已設定為要轉送 EXO 的 SMTP 閘道。  |
|2      | Exchange Online Protection 會協商及驗證輸入連線，並檢查郵件頭和內容，以決定所需的其他原則、標記或處理。  |
|3      | Exchange Online 會與 Microsoft Defender Office 365 整合，以提供更高級的威脅防護、減輕和修正。 |
|4      | 會處理不是惡意、封鎖或隔離的郵件，並傳遞至 EXO 中的收件者，而這些收件者與垃圾郵件、信箱規則或其他設定會評估並觸發使用者喜好設定。 |
|5      | 您可以使用 Azure AD 連線來啟用內部部署 Active Directory 的整合，以同步處理及布建具有郵件功能的物件和帳戶，以 Azure Active Directory 並最終 Exchange Online。 |
|6      | 整合內部部署環境時，強烈建議使用 Exchange 伺服器來支援管理和管理郵件相關的屬性、設定和設定 |
|7      | Microsoft Defender for Office 365 分享 Microsoft 365 Defender 以進行延伸偵測及回應 (XDR) 的信號。|

內部部署整合一般但選用。 如果您的環境僅限雲端，此指南也會為您運作。

## <a name="understand-key-concepts"></a>瞭解重要概念

下表識別重要概念，在評估、設定及部署 MDO 時，請務必瞭解。


|概念  |描述 |其他資訊  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) 是雲端架構篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼電子郵件。 EOP 包含 Exchange Online 中的所有 Microsoft 365 授權。     |   [Exchange Online Protection 概觀](../office-365-security/exchange-online-protection-overview.md)      |
|反惡意程式碼保護     |    在 EXO 中擁有信箱的組織，會自動抵禦惡意程式碼。     |  [EOP 中的反惡意程式碼保護](../office-365-security/anti-malware-protection.md)       |
|反垃圾郵件保護     |   在 EXO 中擁有信箱的組織，會自動抵禦垃圾郵件和垃圾郵件原則。      |  [EOP 中的反垃圾郵件保護](../office-365-security/anti-spam-protection.md)       |
|防網路釣魚保護 |  MDO 提供更多有關 spear 網路釣魚、whaling、勒索軟體和其他惡意活動的高級反網路釣魚防護。   | [適用於 Office 365 的 Microsoft Defender 中的防網路釣魚防護](../office-365-security/anti-phishing-protection.md)   |
|反詐騙保護     |   EOP 包含的功能可協助您保護您的組織免受冒牌 (假冒) 寄件者。      |   [EOP 中的反詐騙保護](../office-365-security/anti-spoofing-protection.md)      |
|安全附件     |   保管庫附件會在傳送電子郵件之前，使用虛擬環境來檢查和 "引爆" 附件，以提供其他層級的保護。      |   [保管庫Microsoft Defender 中 Office 365 的附件](../office-365-security/safe-attachments.md)      |
|保管庫 SharePoint、OneDrive 和 Microsoft Teams 的附件     |    此外，SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件為已上傳至雲端儲存庫的檔案，提供額外的保護層級。     |  [適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|安全連結     | 保管庫連結是一種功能，可提供輸入電子郵件訊息中的 URL 掃描和修正，並在傳送或按一下這些連結之前提供驗證。        |   [保管庫Microsoft Defender 中 Office 365 的連結](../office-365-security/safe-links.md)      |
|    |         |         |

如需與 Office 之 microsoft defender 有關之功能的詳細資訊，請參閱[Microsoft defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="review-architecture-requirements"></a>評審架構需求
成功的 MDO 評估或生產試驗假設下列先決條件：
- 您目前在 Exchange Online 中的所有收件者信箱。
- 您的公用 MX 記錄會直接解析為 EOP 或協力廠商 SMTP 閘道，然後將輸入外部電子郵件直接轉送至 EOP。
- 您的主要電子郵件網域已設定為 Exchange Online 中的 *授權*。
- 您已成功部署和設定 *目錄架構邊緣封鎖* (DBEB) 適當。 如需詳細資訊，請參閱[使用目錄架構邊緣封鎖拒絕傳送給無效收件者的郵件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

> [!IMPORTANT]
> 如果這些需求不適用，或您仍然處於混合共存案例中，則 Microsoft Defender Office 365 評估可能需要更複雜或更高級的設定，這項指南並未完全涵蓋。

## <a name="siem-integration"></a>SIEM 整合

您可以整合 Microsoft Defender for with Azure Sentinel Office 365 與 Azure Sentinel 整合，以更全面地分析整個組織的安全性事件，並建立行動行動以取得有效且立即的回應。 如需詳細資訊，請參閱[連線來自 Microsoft Defender 的警示 Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection)。

Microsoft Defender for Office 365 也可以整合至其他安全性資訊和事件管理 (使用[Office 365 活動管理 API](/office/office-365-management-api/office-365-management-activity-api-reference)的 SIEM) 方案。

## <a name="next-steps"></a>後續步驟

步驟2之3：[啟用評估環境 Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)

回到概述，以[評估 Microsoft Defender 的 Office 365](eval-defender-office-365-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述 

