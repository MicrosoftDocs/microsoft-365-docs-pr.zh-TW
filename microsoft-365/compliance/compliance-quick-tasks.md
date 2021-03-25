---
title: 開始使用 Microsoft 365 合規性的快速工作
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: 深入瞭解將協助您快速開始使用 Microsoft 365 中的合規性的工作。
ms.openlocfilehash: 503e15c8b363dcd63c010d31384565f6e1a8af61
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197920"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>開始使用 Microsoft 365 合規性的快速工作

如果您是 Microsoft 365 規範的新功能，並想知道從何處開始，本文會提供基本規範的指導方針和優先順序重要的任務。 本文將協助您快速開始管理及監控資料、保護資訊，以及最小化內部使用者風險。

如果您想要瞭解如何最佳地管理風險、保護您的資料，以及與新的遠端員工保持相容的規章和標準，本文也會很有説明。 員工現在會以新的方式共同合作及彼此連線，這表示您現有的規範程式和控制項可能需要加以調整。 在您的組織中識別及管理這些新的合規性風險，對保護您的資料和減少威脅和風險都很重要。

在您完成這些基本規範工作之後，請考慮採用其他 Microsoft 365 合規性解決方案，以擴充組織中的合規性覆蓋範圍。

## <a name="task-1-configure-compliance-permissions"></a>任務1：設定合規性許可權

請務必管理貴組織中的哪些人員可以存取 Microsoft 365 合規性中心，以查看內容和執行管理工作。 Microsoft 365 提供與相容性和使用 Microsoft 365 規範中心所包含之工具相關的管理角色。

從為組織中的人員指派合規性許可權開始，讓他們能夠執行這些工作，並防止未經授權的人員存取其責任以外的區域。 在您開始設定及執行 Microsoft 365 隨附的規範解決方案之前，您會想確定已將適當的人員指派給 **合規性資料管理員** 和 **合規性管理員** 管理員角色。 您也需要指派 Azure Active Directory 全域讀取器角色的使用者，以在合規性管理員中查看資料。

如需設定許可權並指派系統管理員角色的逐步指引，請參閱 [安全性 & 合規性中心的許可權](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

## <a name="task-2-know-your-state-of-compliance"></a>工作2：知道您的合規性狀態

如果您不知道所在的位置，很難知道要移往何處。 符合您的合規性需求，包括瞭解目前的風險層級，以及這些不斷變更的時間可能需要哪些更新。 您的組織是否為符合性需求的新功能，或具備管理您行業之標準及規定的深度經驗，您可以採取的單一最佳做法，以瞭解您的組織所在的位置。

[Microsoft 合規性管理員](compliance-manager.md) 可協助您瞭解組織的合規性狀況，並強調可能需要改進的區域。 合規性管理員使用集中式儀表板計算以風險為基礎的分數，測量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。 您也可以使用合規性管理員來追蹤所有風險評估。 它提供工作流程功能，可透過一般工具協助您有效率地完成風險評估。

如需開始使用合規性管理員的逐步指引，請參閱 [合規性管理員](compliance-manager-setup.md)入門。

>[!IMPORTANT]
>對大多數的組織而言，安全性和合規性已緊密整合。 您的組織必須處理基本的安全性、威脅防護和身分識別與存取管理區域，以協助為安全性和合規性提供深層防禦方法。
>
>在 Microsoft 365 security center 中檢查您的 [microsoft 365 安全分數](../security/defender/microsoft-secure-score.md) ，並完成下列文章中所述的工作：
>
> - [安全性藍圖-前30天、90天和之後的頭等大事](../security/office-365-security/security-roadmap.md)
> - [最常見的12個任務，可供安全性小組用來支援在家運作](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>工作3：為您的組織啟用審核

現在，您已經決定組織目前的狀態，以及誰可以管理規範功能，下一步是確認您已具備執行規范調查的資料，並為組織中的網路和使用者活動產生報告。 啟用審核也是本文稍後所述之規範解決方案的重要必要條件。

「審核」記錄提供的資訊是協助您管理法規遵從性需求的有用工具，可協助您管理及監視需要改進的合規性區域。 在記錄活動之前，必須先啟用審核記錄，然後才能搜尋審核記錄。 啟用時，您組織中的使用者和系統管理員活動會記錄在審核記錄中，並在90天內保留，而且會根據指派給使用者的授權，最多一年。

如需開啟審計的逐步指示，請參閱 [開啟或關閉審計記錄搜尋](turn-audit-log-search-on-or-off.md)。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>工作4：建立原則以警示潛在的合規性問題

Microsoft 提供了數個內建的警示原則，可協助識別系統管理許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 預設會開啟這些原則，但您可能需要設定自訂警示，以協助管理組織特有的規範需求。

使用警示原則及警示儀表板工具來建立自訂的警示原則，並查看使用者執行符合原則條件的活動時所產生的警示。 某些範例可能是使用警示原則來追蹤影響組織中符合性需求、許可權及資料遺失事件的使用者和系統管理員活動。

如需建立自訂報警原則的逐步指引，請參閱 [安全性與合規性中心中的警示原則](alert-policies.md)。

## <a name="task-5-classify-and-protect-sensitive-data"></a>任務5：分類及保護機密資料

為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不再會停留在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而當內容漫遊時，您會希望以符合組織的商務及合規性原則的安全、受保護的方式漫遊。

[敏感度標籤](sensitivity-labels.md) 可讓您分類及保護組織的資料，同時確保使用者生產力和其共同作業能力不會形式妨礙。 使用敏感度標籤強制加密和使用限制會套用視覺標記，並保護跨平臺和裝置（內部部署和雲端）的資訊。

如需設定及使用敏感度標籤的逐步指引，請參閱 [開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。 如需敏感度標籤授權資訊，請參閱 [Microsoft 365 授權指南以取得安全性 & 符合性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

## <a name="task-6-configure-a-retention-policy"></a>任務6：設定保留原則

[保留原則](retention.md)可讓您主動決定是否要保留內容、刪除內容或兩者，保留，然後在指定的保留期間結束時刪除內容。 這些動作可能需要遵循行業法規和內部原則，以及在訴訟或違反安全性的情況下降低風險。

當內容受制于保留原則時，使用者可以繼續編輯和使用內容，只要沒有任何變更。 內容會就地保留在其原始位置。 不過，如果有人編輯或刪除遵守保留原則的內容，則原始內容的複本會儲存至保留原則的安全位置，而該內容的保留原則就會生效。

您可以快速為 Microsoft 365 環境中的多個位置（例如 Exchange mail、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組）放置保留原則。 這個原則可以自動包含的信箱或網站數目沒有任何限制。 不過，如果您需要獲得更選擇性的設定，您可以設定特定位置的保留原則，並包含或排除網站或使用者，這樣做會這麼做。

如需設定保留原則的逐步指引，請參閱 [建立及設定保留](create-retention-policies.md)原則。 如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>工作7：設定機密資訊和冒犯性語言原則

保護機密資訊和偵測和作用於工作場所騷擾的事件，是遵守內部原則和標準的重要部分。 Microsoft 365 中的[通訊法規遵從性](communication-compliance-feature-reference.md)協助您快速偵測、捕獲和採取電子郵件和 Microsoft 小組通訊的修正動作，協助將這些風險降至最低。 這包括不適當的通訊，包含與您組織內部和外部的敏感資訊共用的猥褻、威脅及騷擾和通訊。

預先定義的 *冒犯性語言和反騷擾* 原則範本可讓您掃描內部及外部通訊的原則符合性，以供指定的檢閱者檢查。 檢閱者可以調查組織中已掃描的電子郵件、Microsoft 團隊、Yammer 或協力廠商通訊，並採取適當的補救措施，以確保符合組織的標準。

預先定義的 *機密資訊* 原則範本可協助您快速建立一個原則，以掃描電子郵件和 Microsoft 小組通訊包含定義的機密資訊類型或關鍵字，以確保重要資料不會與不應該存取的人員共用。 這些活動會包含有關內幕交易或其他 collusion 活動上的機密專案或特定行業規則的未經授權通訊。

如需規劃及設定通訊相容性的逐步指引，請參閱 [規劃通訊符合性](communication-compliance-plan.md) 及 [開始使用通訊相容性](communication-compliance-configure.md)。 如需通訊相容性授權資訊，請參閱 [Microsoft 365 授權指南以取得安全性 & 符合性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)。

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>任務8：查看您的敏感專案發生的情況

敏感度標籤、機密資訊類型、保留標籤與原則及 trainable 分類器可用來分類及標記不同 Exchange、SharePoint 及 OneDrive 中的機密專案，如先前的工作所示。 您的快速任務旅程中的最後一個步驟是查看已標示哪些專案，以及您的使用者對這些敏感專案採取的動作。 [內容流覽](data-classification-content-explorer.md) 器和 [活動瀏覽器](data-classification-activity-explorer.md) 提供此可見度。

### <a name="content-explorer"></a>內容總管
 內容瀏覽器可讓您以原生格式來查看已分類為敏感資訊類型的所有專案，或是由 trainable 分類程式屬於特定分類的專案，以及已套用靈敏度或保留標籤的所有專案。

如需使用內容瀏覽器的逐步指引，請參閱 [瞭解資料資料分類概述](data-classification-overview.md)，並 [開始使用內容瀏覽器](data-classification-content-explorer.md)。

### <a name="activity-explorer"></a>活動總管
活動 explorer 可協助您監視整個分類及標示的敏感專案所進行的作業：
- SharePoint
- Exchange
- OneDrive

有超過 30 個不同的篩選可使用，其中包括：

- 日期範圍
- 活動類型
- 位置
- 使用者
- 敏感度標籤
- 保留標籤
- 檔案路徑
- DLP 原則

如需使用活動 explorer 的逐步指引，請參閱 [活動瀏覽器入門](data-classification-activity-explorer.md)。

## <a name="next-steps"></a>後續步驟

現在，您已經為組織設定合規性管理的基礎知識，請考慮在 Microsoft 365 中遵循下列規範解決方案，以協助您保護機密資訊，並偵測並處理其他的內幕程式風險。

### <a name="configure-retention-labels"></a>設定保留標籤

保留原則會在容器層級套用至諸如 SharePoint 網站和 Exchange 信箱等位置， [保留標籤](retention.md#retention-labels) 允許對保留和刪除原則進行更特定的目標。 例如，在檔或電子郵件訊息層級，使用者也可以手動套用，除了管理員之外的自動應用程式之外，使用者也可以手動套用。 您也可以將保留標籤套用至 SharePoint 中的文件庫、資料夾或檔集，讓儲存在該位置的所有檔繼承預設的保留標籤。

此外，保留標籤支援 [記錄管理](records-management.md) ，將內容標示為記錄。 發生這種情況時，標籤會針對可能需要的內容，進行其他限制，以協助您的組織遵守法規需求。

如需建立及發佈保留標籤的逐步指引，請參閱下列指導：
- [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
- [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)

若要開始使用記錄管理，請參閱 [記錄管理](get-started-with-records-management.md)入門。

### <a name="identify-and-define-sensitive-information-types"></a>識別及定義敏感資訊類型

根據組織資料中資訊所包含的模式，定義敏感資訊類型。 使用 [內建的敏感資訊類型](./sensitive-information-type-entity-definitions.md) 可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等等。 或建立您組織特有的 [自訂敏感度資訊類型](create-a-custom-sensitive-information-type.md) 。

如需定義自訂敏感資訊類型的逐步指引，請參閱在 [安全性 & 規範中心建立自訂機密資訊類型](./create-a-custom-sensitive-information-type.md)。

### <a name="prevent-data-loss"></a>防止資料遺失

[資料遺失防護 (DLP) 原則](data-loss-prevention-policies.md) 可讓您識別、監視和自動保護 Microsoft 365 組織內的敏感資訊。 使用 DLP 原則來識別跨 Microsoft 服務的敏感專案、防止意外共用機密專案，以及協助使用者瞭解如何保持相容性，而不中斷其工作流程。

如需設定 DLP 原則的逐步指引，請 [建立、測試及調整 dlp 原則](create-test-tune-dlp-policy.md)。 如需資料遺失管理授權資訊，請參閱 [Microsoft 365 的安全性授權指南以取得安全性 & 合規性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="detect-and-act-on-insider-risks"></a>偵測與處理內部人員風險

越來越多的員工可以透過各種平臺和服務來建立、管理及共用資料，以不斷增加存取權。 在大多數的情況下，組織的資源和工具有限，可找出並減輕整個組織的風險，同時也符合規範需求和員工隱私權標準。 這些風險可能包括透過非有意 oversharing 或惡意目的，向外盜竊員工和組織外資訊的資料洩漏等資料竊取。

Microsoft 365 中的[內幕程式風險管理](insider-risk-management-policies.md)使用全面的服務和協力廠商指標，協助您快速識別、會審和採取危險的使用者活動。 透過使用 Microsoft 365 和 Microsoft Graph 中的記錄，「有問必答風險管理」可讓您定義特定原則，以識別風險指示器，並採取行動以減輕這些風險。

如需規劃及設定有問必答風險管理原則的逐步指引，請參閱 [plan for 有問必答風險](insider-risk-management-plan.md) 管理，並 [開始使用「內幕風險](insider-risk-management-configure.md)管理」。 如需內幕風險管理授權資訊，請參閱 [Microsoft 365 的安全性授權指南以取得安全性 & 合規性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)。