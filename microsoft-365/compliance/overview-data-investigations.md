---
title: Microsoft 365 (預覽) 中的資料調查綜述
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-mar2020
description: 在本文中，您將深入瞭解 Microsoft 365 中的資料調查 (預覽) 工具。 「資料調查」工具可協助您評估和修正資料外泄。
ms.openlocfilehash: f3e08ca602d9d131cd25d234c96c660f0b9639aa
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906928"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 (預覽) 中的資料調查綜述

> [!IMPORTANT]
> Deliberation 與我們的客戶進行大量的和討論後，我們決定不要將「資料調查」工具發佈到「一般」可用性。 因此，我們會移除此工具及與現有資料調查案例相關的任何資料，2020年12月31日。  若要管理組織中的資料調查，建議您使用核心 eDiscovery 案例。 如果您需要搜尋並清除 Microsoft 365 的內容，請參閱下列文章： 
> - [eDiscovery 解決方案系列：資料外泄案例-搜尋和清除](data-spillage-scenariosearch-and-purge.md)
> - [搜尋並刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)

當包含機密、敏感或惡意內容的檔發佈至不受信任的環境時，就會發生資料溢出。 偵測到資料溢出時，必須快速包含環境、評估外泄的大小和位置、檢查其周圍的使用者活動，然後從服務中刪除濺入的資料。 使用新的資料調查 (預覽) 工具，您可以在 Office 365 中搜尋敏感、惡意或誤放的資料，調查發生的情況，並採取適當的動作來修正外泄。  

本文說明如何使用新的資料調查 (預覽) 工具中的功能來處理資料外泄案例。

## <a name="permissions"></a>權限

若要存取和進行資料調查，您必須是「資料調查人員」角色群組的成員。 如需詳細資訊，請參閱 [指派資料調查的許可權](data-investigations-permissions.md)。

## <a name="data-investigations-preview-workflow"></a>資料調查 (預覽) 工作流程 

下列各節將說明內建工作流程中的每個步驟 (預覽) 。 下列螢幕擷取畫面顯示名為「高風險」之調查的 [ **首頁** ] 索引標籤 *：「財務檔洩漏* 」。 

![「資料調查」工具中的工作流程](../media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>搜尋敏感、惡意或誤放的資料

使用 [ **搜尋** ] 索引標籤來建立搜尋，以尋找您要修復之資料的 Microsoft 365。 您可以建立並執行查詢型搜尋，以找出一組可能包含溢出資料的電子郵件訊息及檔，然後將其收集為證據以進行審閱及分析。 此外，您也可以使用搜尋工具來預覽範例檔，並查看可協助您優化和改善搜尋結果的搜尋統計資料。 當您認為搜尋結果包含所有與調查相關的資料時，您可以將搜尋結果新增至證據集，以進一步複查、影響評估，並視需要採取補救措施。 如需詳細資訊，請參閱 [在調查中搜尋資料](search-for-data.md)。

## <a name="review-and-investigate-evidence"></a>複查和調查證據

使用 [ **證據** ] 索引標籤，調查您從 live service 收集到的資料，在此案例中是 Office 365。 證據集中的資料是您收集的搜尋結果的快照。 當您以證據的方式新增搜尋結果時，會觸發處理常式，以提取檔案、中繼資料及文字。 完成此程式之後，「資料調查」工具便會建立所有資料的新索引，並將其新增至證據集。 針對任何時間敏感調查，這可讓您在即時服務) 中刪除位於原始內容位置 (的資料，同時調查您在隔離環境中收集的證據，以快速包含環境。 收集證據之後，您可以執行更多查詢，以根據時間範圍、檔案類型、資料擁有人及其他類型的條件來縮小資料。 例如，使用作者、寄件者和收件者條件，您可以快速識別參與資料溢出的人員，以及是否有任何溢出的資料與組織外部的人員共用。

您也可以對收集的證據執行高級分析。 這可為您提供一般主題，以及透過電子郵件執行緒、完全重複的重複專案組織證據，以協助您進行調查。 您可以使用解壓縮的文字視圖或原生檔案格式查看檔，並以調查結果標示。 如需詳細資訊，請參閱：

  - [檢閱辨識項中的資料](review-data-in-evidence.md)

  - [執行分析以更快速地調查](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>管理感興趣的人員

使用 [ **感興趣的人員** ] 索引標籤，新增及管理您在調查證據時所發現的利益人員。 當您新增感興趣的人員時，其資料來源（例如其信箱和 OneDrive 帳戶）便會加以識別和對應。 然後您可以只搜尋這些人員的內容位置，以限定搜尋範圍。 依興趣的人員劃分範圍時，搜尋會更有效率且準確，因為工具會 reprocesses 任何未編制索引的資料，例如影像或不受支援的檔案類型。 在 [ **興趣人** ] 索引標籤上，您也可以查看和搜尋這些人員的「審計記錄」活動，以進一步協助您進行調查。 您可以在整個調查中新增其他感興趣的人員。 如需詳細資訊，請參閱 [管理調查的相關人員](manage-people-of-interest.md)。

## <a name="indexing-the-data-of-people-of-interest"></a>為相關人員的資料編制索引

新增調查感興趣的人員會從人員的資料來源中重新索引任何已部分索引的專案。 此處理程式稱為「 *高級索引* 」。 高級索引 reprocesses 資料（例如影像和不支援的檔案類型），這樣當您執行搜尋來收集調查的資料時，就可以充分探索此資料。 使用 [ **處理** ] 索引標籤來監控高級索引的狀態，並修正使用稱為「 *錯誤修正* 」的處理常式可能發生的任何處理錯誤。 如需詳細資訊，請參閱 [在處理調查的資料時的錯誤修正](error-remediation.md)。

## <a name="exporting-data"></a>匯出資料

如果您想要匯出資料，請使用 [ **匯出** ] 索引標籤來管理匯出工作，並從證據集下載資料。 當您匯出證據時，會將資料上傳至 Azure 存放區位置，然後就可以下載到本機電腦。 在 [ **匯出** ] 索引標籤上，您可以取得 Azure 存放位置 URL 和儲存評估金鑰，這兩者都是下載匯出的資料。 如需詳細資訊，請參閱 [從調查中匯出資料](export-data.md)。

## <a name="managing-jobs"></a>管理工作

使用 [ **工作** ] 索引標籤可監視與調查相關之工作的長時間執行程式。 這包括執行搜尋的工作、將資料新增至證據集、重建資料索引，以及匯出證據。 例如，您可以在包含許多資料來源的 [ **搜尋** ] 索引標籤上建立搜尋。 [ **工作** ] 索引標籤上會顯示此搜尋流程的狀態。如需詳細資訊，請參閱 [管理工作中的資料調查](manage-jobs.md)。

## <a name="configuring-investigation-settings"></a>設定調查設定

使用 [ **設定** ] 索引標籤來設定調查範圍的設定。 這包括新增成員至調查、關閉或刪除調查，以及設定搜尋和分析行為。
