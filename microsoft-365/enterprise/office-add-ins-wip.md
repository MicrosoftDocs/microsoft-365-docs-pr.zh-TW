---
title: 保護企業文件執行 Microsoft Office 增益集-Microsoft 365 企業版 |Microsoft 文件
description: 說明如何使用 WIP 和 Intune 來保護執行 Office 增益集的文件中的企業資料。
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6871f288a7e5849b147cbf0aedb056f84575f376
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866413"
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>使用 WIP 和 Intune 來保護執行 Office 增益集之文件中的企業資料
當組織中的使用者使用 Office 增益集與組織資料互動時，某些資料可能會有洩漏的風險。 當使用者執行 Office 增益集時，您可以使用 Windows 資訊保護 (WIP) 和 Microsoft Intune 來保護企業資料。

[WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 之前稱為企業資料保護 (EDP)，可讓企業保護智慧財產權和公司資料。 WIP 協助保護企業應用程式與資料，防止企業擁有的裝置和員工帶到公司的個人裝置意外洩漏資料，而且不需要對環境或其他應用程式進行任何變更。

[Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) 提供一組多樣的工具來管理複雜的行動環境。 Intune 的行動應用程式管理和裝置管理選項組合，可讓 IT 系統管理員和終端使用者彈性地管理及保護行動生產力。

您可以使用 Intune 來[建立及部署 WIP 原則](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy)。 透過 Intune，您可以選擇受保護的應用程式和 WIP 保護層級，並在網路上尋找企業資料。

透過 WIP 和 Intune：

-   企業可以合理地強制執行公司資料原則，即使資料已下載至個人裝置也一樣。

-   企業可以利用關聯式原則教育，讓使用者了解如何防止不慎將資料洩漏給未受管理的應用程式和服務。

-   終端使用者可以遵守公司資料原則，而不需要中斷其一般工作流程。

-   終端使用者可以順暢地在工作和個人生產力之間進行轉換。

當使用者未混合個人和企業內容時，WIP 和 Intune 會在背景以無訊息模式執行且幾乎不可見。

[Office 增益集](https://dev.office.com/docs/add-ins/overview/office-add-ins)是以 Web 技術為建置基礎。 它們將 Web 能力和資訊帶入 Office 應用程式。 增益集會透過 Office.js 中可用的 API 來與 Office 應用程式中的內容互動。 Office 增益集的核心原則包括：

-   **安全性**：Office JavaScript 平台架構可確保增益集程式碼已沙箱化，並在相對於 Office 主應用程式的個別處理序中執行。 這可讓平台在增益集不符合效能標準或可能為惡意時，通知使用者以採取矯正措施，並在某些情況下停用增益集。 此架構適用於支援 Office 增益集的所有平台。

-   **復原**：增益集平台的「跨處理序」本質可確保增益集本身不會影響 Office 主應用程式的效能或使用者體驗。 這對確保 Office 快速回應使用者動作很重要。

-   **跨平台**：只要寫入一次，就能在 Office 執行的所有位置執行。 Windows、Office Online、Mac 和 iPad 目前支援增益集。 Android 和通用平台即將推出增益集支援。

Office 增益集可以處理文件內的企業和潛在敏感性內容。 增益集是應用程式擴充性的一部分，從主應用程式原則繼承其存取權。 例如，如果 WIP 設定防止 Word 存取企業內容，增益集將無法存取 Word 文件中的企業內容。

增益集的其中一個目標是移除終端使用者的任何封鎖問題，同時確保企業系統管理員可視需要封鎖增益集。 Office 增益集中有關啟用資料保護的主要原則包括：

-   提供方法讓 IT 系統管理員禁止載入增益集。

-   減少或排除系統管理員提供企業可用的增益集時所需的工作。

-   減少增益集使用期間向終端使用者顯示的提示和訊息。

-   排除文件與增益集具有相同內容時向終端使用者顯示的提示。

## <a name="add-ins-and-wip"></a>增益集和 WIP

當您在環境中啟用 WIP 時，您可以啟用 Office 增益集的下列情節：

-   Office 增益集是透過文件內容來啟用。 若是 Outlook，增益集的內容是以目前有效信箱為基礎。 啟用增益集之前，信任提示中會清楚定義增益集權限。 使用者會決定增益集是否適用於特定文件，以及是否允許增益集執行。

-   系統管理員可以使用群組原則來封鎖所有 Office 市集增益集或所有 Office 增益集。這表示使用者只能從 [SharePoint 或 Office 365 公司目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)啟用信任的增益集。

-   系統管理員可以使用行動裝置管理 (MDM)，在防火牆層級封鎖增益集。 請注意，這不適用於行動裝置或攜帶您自己的裝置 (BYOD) 情節。

-   增益集會在企業與個人內容之間套用複製貼上作業。 例如，當使用者從企業內容複製增益集並貼到個人文件時，會顯示預設跨內容複製貼上提示。

下表列出啟用 WIP 時，企業及個人內容與文件中預期的增益集行為。

> [!NOTE]
> - 主應用程式內部和外部的剪下、複製和貼上作業在所有情節中都會如預期般運作。
> - 增益集服務的資料轉送在所有情節中均未受保護。

|**文件或信箱類型**|**個人內容中的增益集**|**企業內容中的增益集**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**個人**     |增益集會載入至個人內容。<br><br>不允許瀏覽至企業 URL (即使在其本身的應用程式定義域中也一樣)。<br><br>允許復原至個人 URL|增益集無法載入或啟用。<br><br>如果已提高文件內容的權限 (例如：藉由將它儲存至企業位置)：<br><br>- 允許瀏覽至企業 URL。<br><br>- 允許瀏覽至個人 URL。|
|**企業**   |增益集會載入至企業內容。<br><br>允許瀏覽至企業 URL。<br><br>允許瀏覽至個人 URL。|增益集會載入至企業內容。<br><br>允許瀏覽至企業 URL。<br><br>允許瀏覽至個人 URL。|
|**未儲存**      |增益集會載入至個人內容。<br><br>不允許瀏覽至企業 URL (即使在其本身的應用程式定義域中也一樣)。<br><br>允許瀏覽至個人 URL。|增益集會載入至企業內容，而且文件會以無訊息模式轉換成企業內容。 這表示文件必須儲存至企業位置。<br><br>允許瀏覽至企業 URL。允許瀏覽至個人 URL。            |


## <a name="add-ins-and-intune"></a>增益集和 Intune

Word、Excel 和 PowerPoint 目前支援 iPad 版 Office 上的 Office 增益集。 Outlook 目前支援 iOS (iPad 和 iPhone) 上的增益集。 Outlook 系統管理員預設可以關閉增益集，包括開發人員安裝的增益集，而且只會啟用其組織所核准的特定增益集。 下表針對使用 Intune 應用程式防護工具之 iOS 版 Office 裝置上執行的增益集，概述其資料防護情節的支援。

> [!NOTE]
> 如需 Android 和 iOS 裝置上執行之 Outlook 增益集的資訊，請參閱 [Manage user access to add-ins for Outlook](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) (管理 Outlook 相關增益集的使用者存取權) 和 [Add-ins for Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx) (Outlook 的增益集)。

|**文件或信箱類型**|**使用 Intune 應用程式防護之 iOS 個人內容中的增益集<sup>*</sup>**|**使用 Intune 應用程式防護之 iOS 企業內容中的增益集<sup>*</sup>**|
|:-----|:-----|:-----|
|**個人**|增益集使用方式不會受到個人文件中 Intune 應用程式防護的影響。|增益集使用方式不會受到個人文件中 Intune 應用程式防護的影響。|
|**企業**|允許啟用個人增益集。<br><br>Intune 應用程式防護原則可以保護增益集與裝置上其他應用程式之間的剪下、複製、貼上和資料轉送情節。<br><br>增益集服務的資料轉送未受保護。|允許啟用企業增益集。 系統管理員可以控制要透過 Office 管理工具 [(Office 365 集中式部署)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f) 發佈哪些增益集。<br><br>Intune 應用程式防護原則可以保護增益集與裝置上其他應用程式之間的剪下、複製、貼上和資料轉送情節。<br><br>增益集服務的資料轉送未受保護。|

>**<sup>*</sup>** 系統管理員可以使用 [Office 365 集中式部署](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f)，直接從 Office 365 系統管理中心或使用 PowerShell 指令碼，將 Word、Excel 和 PowerPoint 增益集部署至個別使用者、群組或組織。 當使用者在 Windows、Mac 或 Office Online 上開啟 Office 應用程式時，會自動在其功能區上安裝增益集。

## <a name="summary"></a>[摘要]

如有 Office 增益集的相關原則，WIP 和 Intune 就可讓系統管理員管理企業資料，並提供終端使用者完成其工作所需的工具。 這會導致企業資料可能會在組織外部洩漏。 Office JavaScript API 目前無法讓開發人員辨識在 Office 文件與增益集之間轉送的資料類型。 開發人員必須向使用者呈現多個提示，而且在某些情況下會錯誤地將個人檔案標示為企業檔案，這對使用者體驗可能會有負面影響，而且不符合資料保護原則。

Microsoft 致力於保護客戶資料，並將繼續投入心力以改善 Intune 和 WIP 技術以及客戶體驗。

## <a name="learn-more"></a>進一步了解

-   [關於 Windows 資訊保護 (WIP) 的一般指導方針與最佳做法](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [什麼是 Intune？](https://docs.microsoft.com/intune/introduction-intune)

-   [裝置註冊方法概觀](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [變更 MDM 授權單位](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [準備好設定適用於 Windows 10 的應用程式保護原則](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
