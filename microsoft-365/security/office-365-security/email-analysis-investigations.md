---
title: Microsoft Defender for Office 365 調查中的電子郵件分析
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動化的事件回應、調查、修正及威脅防護
description: 請參閱調查中的電子郵件分析在 Microsoft Defender 中的運作方式 Office 365。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d222e1c8b6b5ca9e111b1dbe6b7fb31138a157b2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395049"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 調查中的電子郵件分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在自動調查提醒期間，Microsoft Defender for Office 365 會分析原始電子郵件是否有威脅，並識別與原始電子郵件和潛在攻擊一部分相關的其他電子郵件。 這種分析很重要，因為電子郵件攻擊很少會包含單一電子郵件。

自動化調查的電子郵件分析會透過原始電子郵件中的屬性來識別電子郵件群集，以查詢您的組織所傳送及接收的電子郵件。 這與分析員在瀏覽器或高級搜尋中尋找相關電子郵件的安全性作業類似。 許多查詢是用來識別比對的電子郵件，因為攻擊者通常會對電子郵件參數進行變形，以避免安全性偵測。 聚簇分析會執行這些檢查，以決定如何處理調查中所涉及的電子郵件：

- 電子郵件分析會利用原始電子郵件–寄件者值中的屬性，從原始電子郵件–寄件者值 (IP 位址、傳送網域) 和內容 (主旨，) ，以尋找相關的電子郵件，來建立查詢 (叢集) 的電子郵件。
- 如果分析原始電子郵件的 URLs 和檔案，識別某些惡意 (（例如惡意程式碼或網路釣魚) ），則也會建立包含惡意 URL 或檔案的查詢或電子郵件的聚簇。
- 電子郵件聚簇分析會計算與叢集中相符的電子郵件相關的威脅，以判斷電子郵件是否為惡意、可疑或沒有明確威脅。 如果符合查詢的電子郵件叢集具有足夠的垃圾郵件、一般網路釣魚詐騙、高可信度網路釣魚或惡意程式碼威脅，電子郵件叢集便會收到套用威脅類型的電子郵件。 
- 電子郵件聚分析也會檢查電子郵件群集中原始電子郵件和電子郵件的最新傳遞位置，以協助識別電子郵件是否可能仍然需要移除或已被修正或防止。 這種分析很重要，因為攻擊者可能會對惡意內容加上安全性和保護等原則。 這項功能會導致惡意內容仍會留在信箱中，即使已偵測到一或多個惡意電子郵件，並以零小時的自動防護 (ZAP) 進行移除。
- 因惡意程式碼、高可信度網路釣魚、惡意檔案或惡意 URLs 威脅而被視為惡意的電子郵件群集，會在 (收件匣] 或 [垃圾郵件] 資料夾) 時，將電子郵件，虛刪除電子郵件。 如果惡意電子郵件或電子郵件叢集只是「不在信箱中」 (封鎖、隔離、失敗、虛刪除等等 ) 或「內部部署/外部」沒有在雲端信箱中，則不會設定任何擱置的動作以加以移除。
- 如果有任何電子郵件群集決定要成為惡意郵件，則由該叢集識別的威脅會套用回檔查中所涉及的原始電子郵件。 這種行為類似于使用電子郵件搜尋結果的安全性作業分析員，以根據相符的電子郵件判斷原始電子郵件的判定。 此結果可確保不論原始電子郵件的 URLs、檔案或來源電子郵件指示器是否偵測到，系統都可以透過個人化、morphing、規避或其他攻擊者的技術，識別可能 evading 偵測的惡意電子郵件。
- 在使用者損損調查中，會建立其他電子郵件群集，以找出信箱所建立的潛在電子郵件問題。 此套裝程式括 (很好的電子郵件叢集，來自使用者、潛在的資料 exfiltration，以及潛在的命令/控制電子郵件) 、可疑的電子郵件， (包含垃圾郵件或一般網路釣魚) 網路的電子郵件，以及惡意電子郵件群集 (包含惡意程式碼或高可信度網路釣魚) 的電子郵件。 這些電子郵件群集會提供安全作業分析員資料，以判斷可能需要解決的其他問題，以及哪些電子郵件可能會觸發原始的提醒 (例如，觸發使用者傳送限制的網路釣魚/垃圾郵件）) 

透過相似性和惡意實體查詢進行的電子郵件群集分析，可確保即使只識別出來自攻擊的一個電子郵件，也會完整識別及清理電子郵件問題。 您可以使用「電子郵件叢集詳細資料」側面板視圖中的連結，開啟 Explorer 或 Advanced 搜尋中的查詢，以執行更深入的分析，並視需要變更查詢。 如果您發現電子郵件叢集的查詢太窄或太廣 (包括不相關的電子郵件) ，這項功能就會啟用手動精簡和修正。

以下是調查中的電子郵件分析的其他增強功能。

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>AIR 調查會忽略高級傳遞專案 (SecOps 信箱和 PhishEDU 郵件) 

在電子郵件聚簇分析期間，所有的叢集查詢都會在高級傳遞原則中，忽略設定為安全性作業信箱的安全性信箱。 同樣地，電子郵件聚入功能會略過「高級傳遞原則」中設定的網路釣魚模擬 (教育) 郵件。 在查詢中不會顯示 SecOps 和 PhishEdu 排除值，以使叢集屬性更簡單且更容易讀取。 這項排除可確保威脅情報 (SecOps 信箱) 和網路釣魚模擬模擬 (PhishEdu) 會在威脅分析期間忽略，而且不會在任何修正期間遭到移除。 

>[!Note]
>當您從電子郵件叢集詳細資料中開啟電子郵件叢集以從瀏覽器中查看郵件時，PhishEdu 和 SecOps 信箱篩選器將會套用於 Explorer 中，但不會顯示。 如果您變更瀏覽器篩選、日期或重新整理頁面中的查詢，則會移除 PhishEdu/SecOps 篩選排除，並再次顯示符合這些專案的電子郵件。 如果您使用瀏覽器重新整理功能來重新整理瀏覽器頁面，則原始查詢篩選器將會重新載入，包括 PhishEdu/SecOps 篩選器，但移除所做的任何後續變更。
>

## <a name="air-updates-pending-email-action-status"></a>AIR 更新未決的電子郵件動作狀態

調查電子郵件分析會在調查時計算電子郵件威脅和位置，以建立調查證據和動作。 當調查以外的動作影響調查中所涉及的電子郵件時，這項資料可能會過時。 例如，安全性作業手動搜尋和修正可能會清除調查中包含的電子郵件。 同樣地，在平行調查中核准的刪除動作或以零小時的自動防護 (ZAP) 自動隔離動作可能已移除電子郵件。 此外，在電子郵件傳遞後延遲的威脅偵測可能會變更調查的電子郵件查詢/叢集中所包含的威脅數目。 

為了確保調查動作是最新的，任何具有擱置中動作的調查都會定期重新執行電子郵件分析查詢以更新電子郵件位置和威脅。 

- 當電子郵件叢集資料變更時，它會更新威脅及最新的傳遞位置計數。 
- 如果信箱中的電子郵件或電子郵件叢集已不存在，則會取消待處理的動作，而且惡意的電子郵件/群集視為已修正。
- 如以上所述，調查的所有威脅都會修正或取消，則調查會轉換為修正的狀態，並解決原始的警示。

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>電子郵件和電子郵件群集的事件證據顯示

事件的 [證據與回應] 索引標籤中的電子郵件證據現在會顯示下列資訊。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="證據與回應中的電子郵件分析資訊範例" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

從圖中編號的標注：

1. 除了 **行動中心** 之外，您也可以執行修正動作。
2. 您可以採取 **惡意** 的判定，進行電子郵件群集的修正動作 (但不是 **可疑**) 。
3. 若為垃圾郵件，則會將網路釣魚分為高信賴度和一般網路釣魚。

   針對惡意的判定，威脅類別包括惡意程式碼、高可信度網路釣魚、惡意 URL 和惡意檔。

   針對可疑的判定，威脅類別是垃圾郵件和一般網路釣魚。

4. 電子郵件計數依據是以最新的傳遞位置為基礎，且包含信箱中的電子郵件的計數器，而非信箱和內部部署的計數器。
5. 包含查詢的日期和時間，其可能會針對最新的資料進行更新。

在事件的 [ **實體** ] 索引標籤中的電子郵件或電子郵件群集，「 **避免** 」表示此專案的信箱中沒有惡意電子郵件 (郵件或叢集) 。 範例如下。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="避免的電子郵件範例" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

在此範例中，電子郵件是惡意的，而不是在信箱中。

## <a name="next-steps"></a>後續步驟

- [查看擱置中或已完成的修復動作](air-review-approve-pending-completed-actions.md)