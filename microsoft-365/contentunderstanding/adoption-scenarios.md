---
title: Microsoft SharePoint Syntex 案例和使用案例
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 尋找有關如何在組織中使用 SharePoint Syntex 的案例。
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697056"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 案例和使用案例

使用下列範例案例，提示您如何在組織中使用 SharePoint Syntex。

- [案例：使用表單處理從發票追蹤資料](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [案例：使用檔瞭解追蹤合同中的資訊](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [案例：根據 SharePoint Syntex，避免記錄管理、檔管理及規範程式的風險](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [案例：從先前無法存取的檔捕獲資訊](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [案例：改善資料處理以提供真知灼見和分析](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [案例：自動化訂單處理](adoption-scenarios.md#scenario-automate-order-processing)
- [案例：簡化簽證更新程式](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>案例：使用表單處理從發票追蹤資料

例如，您可以使用 SharePoint Syntex 和 Power Automate 功能來設定處理常式，以追蹤和監控發票。

1. 設定儲存發票檔的文件庫。
1. 訓練模型，以辨識檔中的欄位。
1. 將您要追蹤的欄位解壓縮到清單中。
1. 設定流程以通知您特定的事件，例如：
    - 新增新的發票。
    - 發票超過其到期日。
    - 發票的數量大於您的自動核准金額。

![使用 SharePoint Syntex 和 Power Automate 來追蹤和監控發票](../media/content-understanding/process-invoices-flow.png)

當您自動化此案例時，您可以：

- 從發票自動提取資料，而不是手動提取資料，以節省時間和金錢。
- 使用工作流程檢查發票，並在發生問題時通知您，以減少潛在的錯誤並確保更好的相容性。

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>案例：使用檔瞭解追蹤合同中的資訊

在另一個範例中，您可以設定處理常式，識別您的公司與其他公司或個人的合約。 設定模型，以從這些合約提取重要資訊，例如用戶端名稱、費用、日期或其他重要資訊，並將資訊新增至文件庫中，您可以快速查看這些欄位。 請將保留標籤套用到文件庫，以確保在適當的時間長度之前，不能刪除合約，以符合您的商務法規。

1. 從內容中心開始，並建立新的檔瞭解合約模型。
1. Upload 範例檔，以取得正值和消極的範例，然後執行訓練以識別合同檔，並檢查結果。
1. 訓練解壓縮程式以識別合同中的欄位，例如用戶端名稱、費用和日期，然後測試解壓縮程式。
1. 模型完成時，將模型套用至您可以上傳合同的文件庫。
1. 將保留標籤套用至日期欄位，讓合同保留在文件庫中所需的時間長度。

![使用 SharePoint Syntex 和保留標籤來追蹤和監控合約](../media/content-understanding/process-contracts-flow.png)

當您自動化此案例時，您可以：

- 自動從合約提取資料，而不是手動提取資料，以節省時間和金錢。
- 使用保留標籤確保合約已正確保留，以確保更好地相容。

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>案例：根據 SharePoint Syntex，避免記錄管理、檔管理及規範程式的風險

降低風險是大多數公司的共同目標。 您可能需要：

- 在您的租使用者中提供/強制執行資訊管理的更好方法。
- 若要改善檔的分類、電子郵件及其他形式的通訊視為專案的「記錄」的系統。
- 若要審核收據、合約等等，以確保符合公司原則。
- 確定專案具備法規遵從性所需的所有檔。

設定一些與 SharePoint Syntex 相容的處理常式，以取得及適當分類、審核和旗標需要更好的控管的檔和表單。 您可以依靠 SharePoint Syntex，自動將內容分類，而不需依賴使用者手動標記，或是合規性小組手動套用控管規則和封存。 而且，您可以啟用簡化的搜尋體驗、管理資料量、套用記錄管理和保留原則，以確保法規遵從性，以及最佳作法封存及清除作法。

當您自動化此案例時，您可以放心進行下列安全：

- 法規遵從性是 upheld 和降低風險。
- 分類和記錄管理的一致性及正確套用。
- 控制內容量。
- 員工可以輕鬆地在正確的內容中探索正確的資訊。

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>案例：從先前無法存取的檔捕獲資訊

大多數的組織都有大量的法律檔、原則、合約、HR 檔和控管指導方針。 請挖掘這些資料存放區，以解壓重要資訊，例如：專案、磁區、主題、人員、地理區域等等。

例如，HR director 必須快速存取所有人力資源檔，包括簡歷、HR 原則及其他表單。 他們想要從簡歷和其他 HR 相關檔快速識別必要的資訊，而不需透過檔手動 sifting。 他們在尋找一種解決方案，可讓他們快速找出所需的資訊，而不必手動搜尋數千個簡歷、HR 原則，以及可能分散于多個網站的其他檔。

當您自動化此案例時，您可以：

- 從數位內容解除鎖定知識。
- 分類人力資源原則、簡歷、銷售檔、技術藍圖、帳戶計畫及提取資訊。
- 快速尋找您要尋找的正確資訊或檔。
- 立即獲得最新資訊的存取權。
- 縮短搜尋時間。

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>案例：改善資料處理以提供真知灼見和分析

例如，製藥公司可以使用 SharePoint Syntex，從 FDA 檔析取資訊，以回答他們的領導人所提出的問題。 讓答案變得更容易存取，可縮短產生這些回答所需的時間，並提高資料的可用性以產生更準確的領導問題答案。

例如，專案經理必須從我的領導小組快速為產品相關問題提供答案。 他們必須尋找與一個合併儀表板中的查詢相關的資訊和度量。 他們要尋找的解決方案會從產品標籤、產品 pamphlets 及其他材料提取所需的資訊，並產生整合報告，以供報告回其領導團隊時使用。

當您自動化此案例時，您可以：

- 縮短產生回應的時間。
- 提高資料的可用性。
- 提供更準確的答案。

## <a name="scenario-automate-order-processing"></a>案例：自動化訂單處理

使用 SharePoint Syntex，您可以縮短手動處理客戶訂單的時間。 例如，您可以使用 OCR 處理將訂單從傳真、電子郵件或紙張上傳至 SharePoint，然後從這些訂單中解壓縮中繼資料，以便您可以使用自動化程式來完成這些訂單。

例如，供應鏈管理員想要減少手動資料輸入所造成的錯誤。 他們想要避免以手動形式查看輸入客戶訂單的資料， (紙張、傳真或電子郵件) ，以降低業務系統的錯誤。 他們需要套用 AI 和機器學習技巧的解決方案，以驗證內送訂單資訊、提取核心資料，並自動將其推入 ERP 系統，以進行訂單履行和調解。

當您自動化此案例時，您可以確定：

- 訂單和運送的精確度增加。
- 減少與訂單或運送錯誤相關的費用或處罰。
- 縮短開票或付款的延遲。
- 減少人員成本。

## <a name="scenario-simplify-visa-renewal-process"></a>案例：簡化簽證更新程式

SharePointSyntex 可協助您自動化重要合約資訊的提醒和續訂。 例如，HR 主管需要確定員工的簽證是最新的，且/或已在時間上更新。 他們想為人們提供簡單且直觀的處理常式來更新其簽證。 他們需要可從合約提取更新日期的解決方案，並在其更新日期接近時自動傳送員工提醒。

當您自動化此案例時，您可以確定：

- 減少非法規遵從性的層級。
- 已縮短手動提醒數目。
- 降低未達標的罰款數目。

## <a name="see-also"></a>另請參閱

[Microsoft SharePoint Syntex 採用：快速入門](adoption-getstarted.md)