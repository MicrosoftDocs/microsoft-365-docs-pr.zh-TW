---
title: 開始使用測試人員風險管理
description: 設定貴組織的測試人員風險管理。
keywords: Microsoft 365, 測試人員風險管理, 風險管理, 合規性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: a995b6fdbbff36c6466f5e55cda9d7e196fa2c02
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927027"
---
# <a name="get-started-with-insider-risk-management"></a>開始使用測試人員風險管理

使用「有問必答風險管理」原則，識別危險的活動和管理工具，以應對組織中的風險警示。 完成下列步驟來設定必要條件及設定有問必答風險管理原則。

>[!IMPORTANT]
>Microsoft 365 測試人員風險管理解決方案提供租用戶層級選項，以協助客戶在使用者層級加強內部管理。 租用戶層級系統管理員可設定權限，以提供組織成員此解決方案的存取權，並設定 Microsoft 365 合規性中心內的資料連接器，以匯入相關資料來支援使用者層級識別潛在危險活動。 客戶可以透過系統管理員的身分識別與員工的行為、字元或效能相關的資訊，並將其提供給組織中的其他人。 此外，客戶也承認他們必須執行與雇用相關的個別使用者行為、字元或效能相關的完整調查，而不只是依賴「內部使用者風險管理」服務的洞察力。 客戶完全負責使用 Microsoft 365 內幕風險管理服務，以及任何相關的功能或服務，遵循所有適用的法律，包括與個別使用者識別及任何修正動作相關的法律。

如需有關測試人員風險原則如何協助您管理組織風險的詳細資訊，請參閱 [Microsoft 365 中的測試人員風險管理](insider-risk-management.md)。

## <a name="subscriptions-and-licensing"></a>訂閱與授權

開始使用「內幕風險管理」之前，您應該先確認您的 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何附加元件。 若要存取及使用「內幕風險管理」，您的組織必須具備下列其中一項訂閱或附加元件：

- Microsoft 365 E5 訂閱 (付費或試用版本) 
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 合規性附加元件
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 「內幕人員風險管理附加元件」
- Microsoft 365 A5 訂閱 (付費或試用版本) 
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 合規性附加元件
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 內幕人士風險管理附加元件
- Microsoft 365 G5 訂閱 (付費或試用版本) 
- Microsoft 365 G3 訂閱 + Microsoft 365 G5 合規性附加元件
- Microsoft 365 G3 訂閱 + Microsoft 365 G5 有問必答風險管理附加元件
- Office 365 E3 訂閱 + Enterprise 可移動性和 Security E3 + Microsoft 365 E5 合規性附加元件

包含在「內幕風險管理」原則中的使用者必須指派上述其中一個授權。

如果您沒有現有的 Microsoft 365 企業版 E5 計畫，而且想要嘗試擁有者風險管理，您可以 [將 microsoft 365 新增](/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 Enterprise E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>步驟1：啟用內部人員風險管理的許可權

>[!Important]
>設定角色群組之後，最多可能需要30分鐘的時間，才能將角色群組許可權套用至組織中指派給指派的使用者。

有四個角色群組，用來設定許可權以管理「內幕風險管理」功能。 若要繼續這些設定步驟，您的租使用者管理員必須先將您指派給「 **內幕人員風險管理** 」或「 **內幕風險管理** 」管理角色群組。 若要在初始設定之後存取及管理有問必答風險管理功能，使用者必須是至少一個「內幕風險管理」角色群組的成員。

根據您的規範管理小組的結構，您可以選擇將使用者指派給特定角色群組，以管理不同的集一組內幕風險管理功能。 若要在 Office 365 安全性 & 規範中心及管理角色群組中查看 [ **許可權** ] 索引標籤，您必須被指派至「 *組織管理* 」角色群組，或是必須被指派 *角色管理* 角色。 設定有問必答風險管理時，請從下列角色群組選項中選擇：

| **角色群組** | **角色權限** |
| :------------- | :------------------- |
| **有問必答風險管理** | 使用此角色群組，在單一群組中管理組織的有問必答風險管理。 新增指派管理員、分析員、調查人員和審計員的所有使用者帳戶，您可以在單一群組中設定「有問必答風險管理」許可權。 這個角色群組包含所有的「內幕風險管理」許可權角色和相關聯的許可權。 這項設定是快速開始使用「內幕風險管理」的最簡單方法，而且很適合不需要個別使用者群組定義個別許可權的組織。 |
| **測試人員風險管理系統管理員** | 使用此角色群組開始設定「有問必答風險管理」和更新後的成員，以將內幕風險管理員與定義的群組隔離。 這個角色群組中的使用者可以啟用和查看分析 insights，以及建立、讀取、更新和刪除內部使用者風險管理原則、全域設定和角色群組指派。 |
| **測試人員風險管理分析員** | 使用此群組可將許可權指派給將擔當「有問必答風險案例分析」的使用者。 這個角色群組中的使用者可以存取及流覽所有的內幕人士風險管理提醒、案例、分析真知灼見及通知範本。 他們無法存取「內部使用者風險」內容瀏覽器。 |
| **測試人員風險管理調查員** | 使用此群組可將許可權指派給將充當內部使用者風險資料調查人員的使用者。 在所有情況下，此角色群組中的使用者都可以存取所有的內幕程式風險管理提醒、案例、通知範本及內容瀏覽器。 |
| **內部人員風險管理審計員** | 使用此群組可將許可權指派給使用者，以進行審核的「內幕風險管理」活動。 這個角色群組中的使用者可以存取「內幕人員風險審核記錄」。 |

> [!NOTE]
> 目前不支援這些角色群組的特殊身分識別管理 (PIM) 。 若要深入瞭解 PIM，請參閱 [在特權身分識別管理中指派 AZURE AD role](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>將使用者新增至「內幕風險管理」角色群組

完成下列步驟，以將使用者新增至「內部使用者風險管理」角色群組：

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。

2. 在安全性與 &amp; 合規性中心，移至 [ **許可權**]。 選取連結，以在 Office 365 中檢視及管理角色。

3. 選取您想要新增使用者的「內幕風險管理」角色群組，然後選取 [ **編輯角色群組**]。

4. 在左側瀏覽窗格中選取 **[選擇成員]**，然後選取 **[編輯]**。

5. 選取 **[新增]**，然後針對所有要新增至角色群組的使用者勾選核取方塊。

6. 選取 **[新增]**，然後選取 **[完成]**。

7. 選取 **[儲存]** 以將使用者新增至角色群組。 選取 **[關閉]** 以完成步驟。

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>步驟2：啟用 Microsoft 365 審核記錄

「內幕風險管理」針對使用者真知灼見和在原則及分析見解中識別的活動，使用 Microsoft 365 的審計記錄。 Microsoft 365 的審計記錄檔是組織內所有活動的摘要，而內幕程式風險管理原則可能會使用這些活動來產生原則 insights。

如需開啟審計的逐步指示，請參閱 [開啟或關閉審計記錄搜尋](turn-audit-log-search-on-or-off.md)。 在您開啟審核後，會顯示一則訊息，指出已準備好審核記錄，而且您可以在準備完成後數小時執行搜尋。 您只需執行這項動作一次。 如需使用 Microsoft 365 審核記錄的詳細資訊，請參閱 [搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>步驟3：啟用和查看「有問必答風險分析 insights (選用) 

「內部使用者風險管理分析」可讓您在組織中評估潛在的內幕用風險，而不需設定任何內部擁有者風險原則。 這項評估可協助您的組織識別潛在的使用者風險的潛在方面，並協助決定您可以考慮設定的有問必答風險管理原則類型和範圍。 這項評估還可以協助您判斷現有原則的額外授權或未來優化的需求。 分析掃描結果可能需要長達48小時的時間，才能獲得深入查看報告。 若要深入瞭解分析深入瞭解，請參閱 [有問必答風險管理設定：分析 (預覽) ](insider-risk-management-settings.md#analytics-preview)。

若要啟用「內幕風險分析」，您必須是「 *內部使用者風險管理*」、「 *內幕人員風險管理*」或「Microsoft 365 *全域系統管理員* 」角色群組的成員。

完成下列步驟以啟用「內幕風險分析」：

1. 在 [Microsoft 365 規範中心](https://compliance.microsoft.com)，移至「 **內幕人員風險管理**」。
2. 在 [有問必答風險管理 **概述**] 索引標籤上 **，選取 [在** 您的組織卡片中掃描上的 **會員風險**]。此動作會開啟組織的分析掃描。 您也可以在組織中開啟掃描，方法是導覽至「**內幕風險設定**  >  **分析」 (預覽)** 並啟用 **掃描您租使用者的使用者活動，以識別潛在的內幕電腦風險**。
3. 在 [ **分析詳細資料** ] 窗格中，選取 [ **執行掃描]，以啟動組織的掃描**。 分析掃描結果最多可能需要24小時的時間，才能獲得深入查看報告。

在複查分析 insights 之後，請選擇「內部使用者風險原則」，並設定最符合貴組織的有問必答風險降低策略的相關先決條件。

## <a name="step-4-configure-prerequisites-for-policies"></a>步驟4：設定原則的必要條件

大多數的內幕風險管理原則都具有必須針對原則指示器所設定的必要條件，以產生相關的活動警示。 根據您計畫為組織設定的原則，設定適當的必要條件。

### <a name="configure-microsoft-365-hr-connector"></a>設定 Microsoft 365 HR connector

測試人員風險管理支援從協力廠商風險管理和人力資源平台匯入使用者和記錄資料。 Microsoft 365 人力資源 (HR) 資料連線器可讓您從 CSV 檔提取人力資源資料，包括使用者終止日期、最後雇傭日期、效能改進計畫通知、效能檢查動作和工作層級變更狀態。 這項資料可協助磁片箱風險管理原則中的警示指示器，而且在設定組織中的完整風險管理範圍時，是一項重要的部分。 如果您為組織設定多個 HR 連接器，「內部使用者風險管理」會自動從所有 HR 連接器提取指示器。

使用下列原則範本時，需要使用 Microsoft 365 HR 連接器：

- 脫離使用者資料竊取
- 脫離使用者的安全性原則違規
- 不滿的使用者違反安全性原則
- 因不滿使用者的資料洩漏

如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱 [設定連接器以匯入 HR 資料](import-hr-data.md) 文章。 設定 HR 連接器之後，請回到這些設定步驟。

### <a name="configure-data-loss-prevention-dlp-policies"></a>設定資料遺失防護 (DLP) 原則

「內幕風險管理」支援使用 DLP 原則，以協助識別敏感資訊到有害的各方，以取得高嚴重性層級 DLP 警示。 使用任何 **資料洩漏** 範本設定有問必答風險管理原則時，您必須將特定的 DLP 原則指派給原則。

DLP 原則可協助識別使用者為敏感資訊的高嚴重性 DLP 警示啟用內幕風險管理中的風險計分，這是在組織中設定完整風險管理範圍的重要部分。 如需有關有問必答風險管理和 DLP 原則整合及規劃考慮的詳細資訊，請參閱「 [有問必答風險管理原則](insider-risk-management-policies.md#general-data-leaks)」。

>[!IMPORTANT]
>請確認您已完成下列作業：
>
>- 您瞭解及正確地設定 DLP 和有問必答風險管理原則中的範圍內使用者，以產生您預期的原則覆蓋範圍。
>- 請確定與這些範本搭配使用之內幕原則管理的 DLP 原則中的 [ **附隨報告** ] 設定為 *高* 嚴重性層級警示設定。 不會從 DLP 原則產生「內幕風險管理」提醒，其 **附隨報告** 欄位設定為 [ *低* ] 或「 *中*」。

使用下列原則範本時，需要 DLP 原則：

- 一般資料洩漏
- 依優先使用者的資料洩漏

如需為組織設定 DLP 原則的逐步指引，請參閱 [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md) 文章。 設定 DLP 原則後，請返回這些設定步驟。

### <a name="configure-priority-user-groups"></a>設定優先順序使用者群組

有問必答風險管理包含的支援指派優先順序使用者群組給原則，以協助識別重要位置的使用者特有的風險活動、高層次的資料和網路存取，或過去的風險行為歷史。 建立優先順序使用者群組，並將使用者指派至群組協助範圍原則，以說明這些使用者所呈現的獨特情況。

使用下列原則範本時，需要優先順序的使用者群組：

- 依優先順序的使用者所破壞的安全性原則
- 依優先使用者的資料洩漏

如需建立優先順序使用者群組的逐步指引，請參閱 [開始使用「會員風險管理」管理設定](insider-risk-management-settings.md#priority-user-groups-preview) 文章。 設定優先順序使用者群組之後，請回到這些設定步驟。

### <a name="configure-physical-badging-connector-optional"></a>設定實體聲譽徽章授予連接器 (選用) 

有問必答風險管理支援從實體控制和存取平臺匯入使用者和記錄資料。 實體聲譽徽章授予連接器可讓您從 JSON 檔案中拉入 access 資料，包括使用者 IDs、存取點 IDs、存取時間和日期，以及存取狀態。 這項資料可協助磁片箱風險管理原則中的警示指示器，而且在設定組織中的完整風險管理範圍時，是一項重要的部分。 如果您為組織設定一個以上的實體聲譽徽章授予連接器，「內部使用者風險管理」會自動從所有實體聲譽徽章授予連接器中拉出指示器。 來自實體聲譽徽章授予連接器的資訊，會在使用所有有問必答風險原則範本時，補充其他會員風險的信號。

>[!IMPORTANT]
>若要使用或關聯使用實體控制和存取平臺之事件資料的委任及終止使用者相關的通知資料，您也必須設定 Microsoft 365 HR connector。 如果您啟用實體聲譽徽章授予連接器但未啟用 Microsoft 365 HR connector，「內部使用者風險管理」原則只會處理組織中使用者未授權實體存取的事件。

如需設定組織之實體聲譽徽章授予連接器的逐步指引，請參閱 [設定連接器以匯入實體聲譽徽章授予資料](import-physical-badging-data.md) 文章。 在您設定連接器之後，請回到這些設定步驟。

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>設定 Microsoft Defender for Endpoint (optional) 

[Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 是一種企業端點安全性平臺，旨在協助商業網路避免、偵測、調查和回應高級威脅。 若要更好地瞭解組織中的安全性違規，您可以匯入並篩選 Defender，以取得來自「內部使用者風險管理安全性違規原則」原則的原則中所使用的活動。

如果您建立安全性侵犯原則，您必須在組織中設定 Microsoft Defender for a 端點，並在 Defender Security Center 中啟用內部使用者風險管理整合的 Endpoint Endpoint，以匯入安全性侵犯警示。 如需有關需求的詳細資訊，請參閱 [Microsoft Defender For 端點文章的最低需求](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) 。

請參閱 [configure The defender For endpoint 文章中的「設定高級功能](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) 」，以取得為內部會員風險管理整合的端點設定 Defender 的逐步指引。 設定 Microsoft Defender for 端點後，請回到這些設定步驟。

## <a name="step-5-configure-insider-risk-settings"></a>步驟5：設定有問必答風險設定

「[內部使用者風險」設定](insider-risk-management-settings.md)會套用至所有的內幕風險管理原則，不論您在建立原則時所選擇的範本為何。 設定是使用「 **內幕風險設定** 」控制項設定，其位於所有「內幕人員風險管理」索引標籤的頂端。 這些設定會控制隱私權、指示器、監控視窗和智慧偵測。

在設定原則之前，請定義下列「內幕人員風險設定」：

1. 在 [Microsoft 365 規範中心](https://compliance.microsoft.com)內，移至「 **有問必答風險管理** 」，然後從任何頁面的右上角選取「 **有問必答風險設定** 」。
2. 在 [ **隱私權** ] 頁面上，選取顯示原則警示的個人資訊的隱私權設定。
3. **在 [指標**] 頁面上，選取您要套用到所有內部使用者風險原則的警示指示器。

    >[!IMPORTANT]
    >您必須選取一或多個指標，才能接收您原則中所定義之危險活動的警示。 如果 [設定] 中未設定指示器，指標將無法在內部的風險原則中選擇。

4. 在 [ **原則時段** ] 頁面上，選取 [原則時段](insider-risk-management-settings.md#policy-timeframes) ，當使用者觸發內部使用者風險原則的相符時，就會變成作用中的使用者。
5. 在 [ **智慧** 偵測] 頁面上，為「內部人員風險原則」設定下列設定：
    - [檔案類型排除](insider-risk-management-settings.md#file-type-exclusions)
    - [不尋常檔案活動的臨界值](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [警示音量層級](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint 警示狀態](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [網域設定](insider-risk-management-settings.md#domains-preview)
6. 在 [ **匯出提醒** ] 頁面上，根據需要，使用 Office 365 管理 APIs 啟用「匯出的會員風險警示資訊」。
7. 在 [ **優先順序使用者群組** ] 頁面上，建立 [優先順序] 使用者群組，並在 **步驟 3** 中建立使用者時新增使用者。
8. 在 [ **電源自動流程** ] 頁面上，設定「內幕人員風險流程範本」的流程，或是建立新的流程。 如需逐步指引，請參閱入門的「 [內幕人員風險管理設定](insider-risk-management-settings.md#power-automate-flows-preview) 」文章。
9. 在 [ **優先順序資產] 頁面** 上，設定優先順序資產，以使用實體聲譽徽章授予連接器所匯入的實體控制和存取平臺中的資料。 如需逐步指引，請參閱入門的「 [內幕人員風險管理設定](insider-risk-management-settings.md#priority-physical-assets-preview) 」文章。
10. 在 [ **Microsoft 小組** ] 頁面上，讓 Microsoft 團隊能夠與「內幕風險管理」整合，以自動建立小組以進行案例或使用者共同作業。 如需逐步指引，請參閱入門的「 [內幕人員風險管理設定](insider-risk-management-settings.md#microsoft-teams-preview) 」文章。
11. 選取 [ **儲存** ] 以啟用內部使用者風險原則的這些設定。

## <a name="step-6-create-an-insider-risk-management-policy"></a>步驟6：建立內部人員風險管理原則

測試人員風險管理原則包括指派的使用者，並定義針對警示設定的風險指標類型。 必須先設定原則，活動才會觸發警示。 使用 [原則] 嚮導來建立新的「有問必答風險管理」原則。

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至 **[測試人員風險管理]**，然後選取 **[原則]** 索引標籤。
2. 選取 [ **建立原則** ] 以開啟原則嚮導。
3. 在 [ **原則範本** ] 頁面上，選擇 [原則] 類別，然後選取新原則的範本。 這些範本是由條件和指示器所組成，用來定義您想要偵測和調查的風險活動。 檢查範本必要條件、觸發事件及偵測到的活動，確認此原則範本符合您的需求。

    >[!IMPORTANT]
    >某些原則範本具有必須針對原則進行設定以產生相關警示的必要條件。 若尚未設定適用的原則必要條件，請參閱上述的 **步驟 4** 。

4. 選取 **[下一步]** 繼續。
5. 在 [ **名稱與描述** ] 頁面上，完成下欄欄位：
    - **Name (必要)**：輸入原則的易記名稱。 建立原則之後，就無法變更此名稱。
    - **說明 (選用)**：輸入原則的說明。

6. 選取 **[下一步]** 繼續。
7. 在 [ **使用者和群組** ] 頁面上，選取 [ **包含所有使用者和群組** ] 或 [ **包含特定使用者和群組** ]，以定義要包含在原則中的使用者或群組，或您是否已選擇優先級使用者型範本;選取 [ **新增] 或 [編輯優先順序使用者群組**]。 選取 [ **包含所有使用者和群組** ]，就會尋找組織中所有使用者和群組的觸發事件，以開始指派原則的風險分數。 選取 [ **包含特定的使用者和群組** ] 可讓您定義要指派給原則的使用者和群組。
8. 選取 **[下一步]** 繼續。
9. 在 [ **要設定優先順序的內容** ] 頁面上，如有需要，您可以指派 () 要設定優先順序的來源，這會增加為這些來源產生高嚴重性警示的可能性。 選取下列其中一個選項：

    - **我想要指定 SharePoint 網站、敏感度標籤和/或機密資訊類型為優先順序內容**。 選取此選項會在嚮導中啟用詳細資料頁面以設定這些通道。
    - **我不想立即指定優先順序內容 (您可以在建立原則之後執行此動作)**。 選取此選項將會略過嚮導中的通道詳細資料頁面。

10. 選取 **[下一步]** 繼續。

11. 如果您選取 [ **我想要指定 SharePoint 網站、敏感度標籤和/或機密資訊類型為** 上一個步驟中的優先順序內容，您會看到 *SharePoint 網站*、 *敏感資訊類型* 和 *敏感度標籤* 的詳細資料頁面。 使用這些詳細資料頁面來定義要在原則中設定優先順序的 SharePoint、機密資訊類型和敏感度標籤。

    - **SharePoint 網站**：選取 [ **新增 SharePoint 網站** ]，然後選取您具有存取權的 SharePoint 網站，並要設定優先順序。 例如，*"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感性資訊類型**：選取 **[新增敏感性資訊類型]**，然後選取要設定優先順序的敏感性類型。 例如，*[美國銀行帳戶號碼]* 和 *[信用卡號碼]*。
    - **敏感度標籤**：選取 **[新增敏感度標籤]**，然後選取要設定優先順序的標籤。 例如，*[機密]* 和 *[密碼]*。

12. 選取 **[下一步]** 繼續。
13. 在 [**指示器與觸發事件**] 頁面上，您會看到您已在「**內幕使用者風險設定** 指示器」頁面上定義為可用的 [指示器](insider-risk-management-settings.md#indicators)  >   。 如果您在嚮導的開頭選取 *資料洩漏* 範本，必須從 [ **dlp 原則** ] 下拉式清單中選取 dlp 原則，以啟用原則的觸發指標或選取內建的觸發事件。

    >[!IMPORTANT]
    >如果無法選取此頁面上的指標，您必須選取要對所有原則啟用的指示器。 您可以使用嚮導中的 [**開啟** 指標] 按鈕，或是在 [**有問必答風險管理**  >  **設定**  >  **原則指示器**] 頁面上選取指標。

    選取您要套用到原則的指示器。 如果您不想使用這些指標的預設原則閾值設定，請停用 [ **使用 Microsoft 建議的預設閾值** ]，然後為每個選取的指示器輸入臨界值。

    - 如果您已選取至少一個 *辦公室* 或 *裝置* 指標，請視需要選取 [ **風險分數 boosters** ]。 風險分數 boosters 只適用于選取的指示器。
    - 如果您已選取 *資料竊取* 或 *資料洩漏* 原則範本，請選取一或多個 **順序偵測** 方法和 **累計的 exfiltration 偵測** 方法，套用至原則。

14. 選取 **[下一步]** 繼續。
15. 在 [ **標記閾值** ] 頁面上，選取使用預設指示器閾值的選項，或為個別指示器指定自訂閾值。 針對每個指示器，選擇適當的層級以產生所需的活動警示層級。
16. 選取 **[下一步]** 繼續。
17. 在 [ **複查** ] 頁面上，複查您為原則選取的設定，以及您選擇的任何建議或警告。 選取 **[編輯]** 以變更任何原則值，或選取 **[提交]** 來建立並啟用原則。

## <a name="next-steps"></a>後續步驟

完成這些步驟以建立第一個測試人員風險管理原則後，您會在大約 24 小時後開始從活動指標收到警示。 請視需要使用本文步驟4中的指導方針，或 [建立新的內幕檔風險原則](insider-risk-management-policies.md#create-a-new-policy)中的步驟，來設定其他原則。

若要深入瞭解如何調查「內幕風險預警」和「 **警示」儀表板**，請參閱「 [有問必答風險管理」提醒](insider-risk-management-alerts.md)。
