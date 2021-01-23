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
description: 瞭解可協助在 Microsoft 365 中快速開始使用合規性的工作。
ms.openlocfilehash: 36b6e2bd0d0339241748499826edf061a7259317
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928627"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>開始使用 Microsoft 365 合規性的快速工作

如果您是 Microsoft 365 合規性的新功能，並想瞭解從何處著手，本文提供基本操作指引，並優先處理重要的合規性工作。 本文可協助您快速著手管理及監控資料、保護資訊，並將 Insider 風險最小化。

如果您在算出如何以最佳方式管理風險、保護您的資料，並維持與新遠端員工符合法規與標準，本文也很有説明。 員工現在以新的方式共同合作並彼此聯繫，這表示您現有的合規性程式與控制措施可能需要調整。 識別和管理貴組織中這些新的合規性風險，對於保護您的資料並將威脅與風險最小化至關重要。

在您完成這些基本合規性工作之後，請考慮執行其他 Microsoft 365 合規性解決方案來擴大貴組織的合規性涵蓋範圍。

## <a name="task-1-configure-compliance-permissions"></a>工作 1：設定合規性許可權

管理貴組織中誰具有 Microsoft 365 合規性中心的存取權，以查看內容並執行管理工作非常重要。 Microsoft 365 提供合規性以及使用 Microsoft 365 規範中心內工具的特定系統管理角色。

首先，將合規性許可權指派給貴組織人員，這樣他們才能執行這些工作，並防止未經授權的人員存取其責任以外的區域。 在您開始設定及執行 Microsoft 365 中包含的合規性解決方案之前，請務必先將適當的人員指派給合規性資料系統管理員和合規性系統管理員角色。 您也需要將使用者指派給 Azure Active Directory 全域讀取者角色，以在合規性管理員中查看資料。

有關設定許可權及將人員指派給系統管理員角色的逐步指引，請參閱安全性& [中心的許可權](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

## <a name="task-2-know-your-state-of-compliance"></a>工作 2：知道您的合規性狀態

如果您不知道您在哪裡，就很難知道要前往何處。 滿足您的合規性需求包括瞭解您的目前風險層級，以及這些改變時期可能需要哪些更新。 無論您的組織是合規性要求的新使用者，或對於規範您產業的標準和法規有深入的經驗，您改善合規性最好的方式就是了解貴組織的目前情況。

[Microsoft 合規性管理員](compliance-manager.md) 可協助瞭解貴組織的合規性狀態，並突顯可能需要改進的區域。 合規性管理員使用集中式儀表板來計算以風險為基礎的分數，衡量完成有助於降低資料保護和法規標準相關風險的動作進度。 您也可以使用合規性管理員工具來追蹤您的所有風險評定。 它提供工作流程功能，可透過共同工具，有效率地完成您的風險評定。

有關開始使用合規性管理員的逐步指引，請參閱合規性管理員 [入門](compliance-manager-setup.md)。

>[!IMPORTANT]
>安全性與合規性是大多陣列織緊密整合在一起。 貴組織必須處理基本安全性、威脅防護，以及身分識別與存取管理區域，協助提供針對安全性與合規性的深入防護方式。
>
>在 [Microsoft 365](../security/mtp/microsoft-secure-score.md) 安全性中心檢查您的 Microsoft 365 安全分數，並完成下列文章所述的工作：
>
> - [安全性藍圖 - 前 30 天、前 90 天及之後的主要優先順序](../security/office-365-security/security-roadmap.md)
> - [安全小組支援在家工作的前 12 項工作](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>工作 3：為貴組織啟用稽核

現在您決定好貴組織的目前狀態，以及哪些人可以管理合規性功能，接下來就是確定您擁有資料，可以進行合規性調查並產生組織中網路與使用者活動的報告。 啟用稽核也是本文稍後說明的合規性解決方案的重要先決條件。

稽核記錄提供的深入資訊是一項寶貴的工具，可協助比對合規性要求的解決方案，可協助您管理及監控需要改進的合規性領域。 稽核記錄必須先啟用，才能記錄活動，您才能搜尋稽核記錄。 啟用時，貴組織的使用者和系統管理活動會記錄在稽核記錄中，並保留 90 天，最多保留一年 ，視指派給使用者授權的不同。

有關開啟稽核的逐步指示，請參閱開啟或關閉稽核記錄 [搜尋](turn-audit-log-search-on-or-off.md)。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>工作 4：建立相關政策以提醒您潛在的合規性問題

Microsoft 提供數個內建警示原則，可協助識別系統管理許可權濫用、惡意識別活動、潛在外部和內部威脅，以及資訊管理風險。 預設會開啟這些設定，但您可能需要設定自訂警示，協助管理貴組織特定的合規性要求。

使用警示策略和警示儀表板工具建立自訂警示策略，並查看當使用者執行符合該政策條件的活動時所產生的警示。 部分範例可能會使用警示策略來追蹤影響貴組織中合規性要求、許可權和資料遺失事件的使用者和系統管理員活動。

有關建立自訂警示策略的逐步指引，請參閱安全性與合規性中心的警示 [政策](alert-policies.md)。

## <a name="task-5-classify-and-protect-sensitive-data"></a>工作 5：分類及保護機密資料

為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不再會停留在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而當內容漫遊時，您會希望以符合組織的商務及合規性原則的安全、受保護的方式漫遊。

[敏感度標籤](sensitivity-labels.md) 讓您分類及保護貴組織的資料，同時確保使用者生產力及其共同作業能力沒有障礙。 使用敏感度標籤來強制執行加密和使用限制，以使用視覺標記，並保護跨平臺和裝置、內部部署和雲端的資訊。

有關設定和使用敏感度標籤的逐步指引，請參閱開始使用 [敏感度標籤](get-started-with-sensitivity-labels.md)。 有關敏感度標籤授權資訊，請參閱 [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)安全性與合規性&指南。

## <a name="task-6-configure-a-retention-policy"></a>工作 6：設定保留原則

保留 [策略](retention.md) 可讓您主動決定是否要保留內容、刪除內容，或兩者同時保留，然後在指定的保留期間結束時刪除內容。 您可能需要採取這些動作來遵守產業法規和內部政策，並降低訴訟或安全性外泄時的風險。

當內容受保留原則所影響時，人員可以繼續編輯及處理內容，就像沒有變更一樣。 內容會保留在其原始位置。 但如果有人編輯或刪除受保留原則保護的內容，原始內容的一份副本會儲存到安全的位置，當該內容的保留政策生效時，該內容會保留在這裡。

您可以針對 Microsoft 365 環境中多個位置快速設定保留原則，例如 Exchange 郵件、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組。 此政策可自動包含的信箱或網站數量沒有限制。 但如果您需要取得更多選擇性選項，您可以針對特定位置進行保留原則，並包含或排除網站或使用者。

有關設定保留原則的逐步指引，請參閱建立 [及設定保留原則](create-retention-policies.md)。 如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>工作 7：設定敏感性資訊和令人反感的語言政策

保護敏感性資訊，以及偵測工作場所騷擾事件並採取行動，是遵守內部政策與標準的重要一部分。 [](communication-compliance-feature-reference.md) Microsoft 365 中的通訊合規性可協助快速偵測、捕捉電子郵件和 Microsoft Teams 通訊並採取補救動作，協助您將這些風險降至最低。 這些包括包含不專業、威脅、騷擾和在組織內外共用敏感性資訊的不當通訊。

預先定義的令人反感 *語言* 和反騷擾政策範本可讓您掃描內部與外部通訊以尋找政策比對結果，以便讓指定的檢定者檢定。 評論者可以調查貴組織中掃描的電子郵件、Microsoft Teams、Yammer 或協力廠商通訊，並採取適當的補救動作，以確保他們符合貴組織的標準。

預先定義的敏感性資訊政策範本可協助快速建立用於掃描電子郵件和 Microsoft Teams 通訊的範本，其中包含已定義的敏感性資訊類型或關鍵字，以確保重要資料不會與不應該存取的人共用。 這些活動可能包括有關機密專案的未經授權的通訊，或有關 Insider 交易或其他拼貼活動的產業特定規則。

有關規劃及設定通訊合規性的逐步指引，請參閱通訊合規性規劃及[](communication-compliance-plan.md)[開始使用通訊合規性](communication-compliance-configure.md)。 有關通訊合規性授權資訊，請參閱安全性與合規性 [的 Microsoft 365 &指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)。

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>工作 8：查看機密專案的情況

敏感度標籤、敏感性資訊類型、保留標籤和策略，以及可訓練的分類器，可用來分類和標示 Exchange、SharePoint 和 OneDrive 中的機密專案，如您先前所看過的一樣。 快速工作旅程的最後一個步驟是查看已標示哪些專案，以及您的使用者會針對這些機密專案採取哪些動作。 [內容瀏覽器](data-classification-content-explorer.md)[和活動瀏覽器提供](data-classification-activity-explorer.md)此可見度。

### <a name="content-explorer"></a>內容總管
 內容流覽程式可讓您以原始格式，來查看所有已分類為機密資訊類型或屬於特定分類之專案，以及所有已使用敏感度或保留標籤的專案。

有關使用內容總管的逐步指引，請參閱瞭解您的資料 [- 資料分類概](data-classification-overview.md)觀，以及開始使用 [內容總管](data-classification-content-explorer.md)。

### <a name="activity-explorer"></a>活動 Explorer
活動 Explorer 可協助監控分類和標示的機密專案已完成的工作，包括：
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

有關使用活動 Explorer 的逐步指引，請參閱開始使用[活動 Explorer。](data-classification-activity-explorer.md)

## <a name="next-steps"></a>後續步驟

現在，您為貴組織已針對合規性管理基本操作，請考慮 Microsoft 365 中的下列合規性解決方案，來説明您保護敏感性資訊，並偵測並解決其他內部人員風險。

### <a name="configure-retention-labels"></a>設定保留標記

保留原則在容器層級會適用于 SharePoint 網站和 Exchange 信箱等位置，保留[](retention.md#retention-labels)標記可針對保留和刪除原則設定更特定的目標。 例如，在檔或電子郵件訊息層級，使用者除了系統管理員自動申請之外，也可以手動進行申請。 您也可以將保留標籤套用至 SharePoint 中的文件庫、資料夾或檔集，以便所有儲存在該位置的檔繼承預設保留標籤。

此外，保留標記可 [支援記錄管理](records-management.md) ，以將內容標記為記錄。 當發生這種情況時，標籤會針對協助貴組織遵守法規要求所需之內容施加額外限制。

有關建立及發佈保留標籤的逐步指引，請參閱下列指引：
- [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
- [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)

若要開始使用記錄管理，請參閱開始使用 [記錄管理](get-started-with-records-management.md)。

### <a name="identify-and-define-sensitive-information-types"></a>識別及定義敏感性資訊類型

根據組織資料中資訊中包含的模式定義敏感性資訊類型。 使用 [內建的敏感性資訊類型](what-the-sensitive-information-types-look-for.md) 可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等。 或建立您 [組織](create-a-custom-sensitive-information-type.md) 特定的自訂敏感度資訊類型。

有關定義自訂敏感性資訊類型的逐步指引，請參閱安全性與合規性中心中的建立自訂 [&類型](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)。

### <a name="prevent-data-loss"></a>防止資料遺失

[DLP (防護) ](data-loss-prevention-policies.md) 讓您識別、監控及自動保護整個 Microsoft 365 組織的敏感性資訊。 使用 DLP 策略識別 Microsoft 服務中的機密專案、避免意外共用機密專案，以及協助使用者瞭解如何符合規範，而不會中斷其工作流程。

有關設定 DLP 策略的逐步指引，請 [建立、測試和調整 DLP 政策](create-test-tune-dlp-policy.md)。 有關資料遺失管理授權資訊，請參閱安全性與合規性 [的 Microsoft 365 &指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="detect-and-act-on-insider-risks"></a>偵測並防範 Insider 風險

員工越來越能夠跨各種平臺與服務建立、管理及共用資料。 在大多數的情況下，組織在識別及減輕全組織風險的同時，也符合合規性需求和員工隱私權標準，其資源與工具有限。 這些風險可能包括離職員工的資料竊取，以及不小心過度共用或惡意目的而將資訊洩漏到組織外部。

Microsoft 365 中的 Insider Risk [management](insider-risk-management-policies.md)使用完整服務及協力廠商標記，可協助您快速識別、分類及處理有風險的使用者活動。 使用 Microsoft 365 和 Microsoft Graph 中的記錄，Insider 風險管理可讓您定義特定政策，以識別風險標記並採取行動，以減少這些風險。

有關規劃及設定 Insider 風險管理策略的逐步指引，請參閱 Insider [風險管理](insider-risk-management-plan.md) 規劃及開始使用 [Insider 風險管理](insider-risk-management-configure.md)。 有關內部人員風險管理授權的資訊，請參閱安全性與合規性 [的 Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)&指南。
