---
title: 案例研究-Contoso 會快速設定冒犯性語言原則，以進行 Microsoft Teams、Exchange 和 Yammer 通訊
description: Contoso 的案例研究，以及如何快速設定通訊相容性原則，以監視 Microsoft Teams、Exchange Online 和 Yammer 通訊中的冒犯性語言。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: b44977252b18c29a5f05a67f4ffbdb7dc85a8188
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256780"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>案例研究-Contoso 會快速設定冒犯性語言原則，以進行 Microsoft Teams、Exchange 和 Yammer 通訊

Microsoft 365 中的通訊法規遵從性，可協助您在組織中偵測、捕獲和處理不適當的郵件，以將通訊風險降至最低。 預先定義和自訂原則可讓您針對原則相符項目掃描內部和外部通訊，以便由指定的檢閱者加以檢查。 檢閱者可以調查組織中已掃描的電子郵件、Microsoft Teams、Yammer 或協力廠商通訊，並採取適當的修正動作，以確保它們符合您組織的郵件標準。

Contoso Corporation 是虛構組織，需要快速設定可監視攻擊性語言的原則。 他們已使用 Microsoft 365 主要是針對其使用者提供電子郵件、Microsoft Teams 和 Yammer 支援，但有新的需求可強制實施公司原則，避免工作場所騷擾。 Contoso IT 系統管理員和合規性專家對使用 Microsoft 365 的基礎有基本瞭解，而且正在尋找如何快速開始使用通訊合規性的端對端指導方針。

此案例研究將提供相關基本概念，說明如何快速設定通訊合規性原則，以監視通訊中是否有攻擊性語言。 此指引包括：

- 步驟 1 - 規劃通訊合規性
- 步驟 2 - 存取 Microsoft 365 中的通訊合規性
- 步驟 3 - 設定必要條件並建立通訊合規性原則
- 步驟 4 - 警示的調查和補救

## <a name="step-1-planning-for-communication-compliance"></a>步驟1：規劃通訊規範

Contoso IT 系統管理員和合規性專家會參加線上網路研討會，以瞭解 Microsoft 365 中的合規性解決方案，決定通訊法規遵從性原則可協助他們符合減少工作地點騷擾的更新公司原則需求。 共同運作，他們已開發出一個計畫，用以建立及啟用通訊相容性原則，以監視 Microsoft Teams 中傳送的攻擊性語言、Yammer 中的私人郵件和社區交談，以及 Exchange Online 中傳送的電子郵件。 他們的計畫包括識別：

- 需要存取通訊規範功能的 IT 管理員。
- 需要建立及管理通訊原則的規範專家。
- 其他部門的合規性專家和其他同事 (人力資源、法律等 ) ，需要調查和修正通訊相容性警示。
- 將會在通訊相容性冒犯性語言原則範圍內的使用者。

### <a name="licensing"></a>授權

第一步是確認 Contoso 的 Microsoft 365 授權包含對通訊規範解決方案的支援。 若要存取和使用通訊法規遵從性，Contoso IT 管理員必須確認 Contoso 是否具備下列其中一項：

- Microsoft 365 E5 訂閱 (付費或試用版) 
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 合規性附加元件
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 「內幕人員風險管理附加元件」
- Microsoft 365 A5 訂閱 (付費或試用版) 
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 規範附加元件
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 「內幕人員風險管理附加元件」
- Microsoft 365G5 訂閱 (付費或試用版) 
- Microsoft 365G5 訂閱 + Microsoft 365 G5 合規性附加元件
- Microsoft 365G5 訂閱 + Microsoft 365 G5 有問必答風險管理附加元件
- Office 365 企業版E5 訂閱 (付費或試用版本) 
- Office 365 企業版E3 訂閱 + Office 365 進階合規性附加元件 (無法再供新訂閱使用，請參閱記事) 

他們也必須確認已包含在通訊合規性原則中的使用者，必須已獲指派上述其中一個授權。

> [!IMPORTANT]
> Office 365 進階合規性不再以獨立訂閱銷售。 當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。

Contoso IT 管理員請採取下列步驟，確認 Contoso 的授權支援：

1. IT 管理員登入 **Microsoft 365 系統管理中心** <https://admin.microsoft.com> ，並流覽至 **Microsoft 365 系統管理中心**  >  **計費**  >  **授權**。

2. 在這裡，他們會確認他們有其中一個 [授權選項](communication-compliance-configure.md#subscriptions-and-licensing) ，其中包含對通訊相容性的支援。

![通訊規範授權](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>通訊相容性的許可權

有五個角色群組可用來設定管理通訊符合性功能的許可權。 若要在 Microsoft 365 合規性中心中以功能表選項來進行 **通訊相容性**，並繼續進行這些設定步驟，Contoso 系統管理員會被指派 *通訊合規性* 系統管理員角色。

Contoso 決定使用 *通訊合規性* 角色群組將所有通訊合規性管理員、分析員、調查人員和檢視器指派給群組。 這可讓 Contoso 快速快速開始，並最適合其相容性管理需求。

|**角色**|**角色權限**|
|:-----|:-----|
| **通訊相容性** | 使用此角色群組來管理單一群組中組織的通訊相容性。 新增指派管理員、分析員、調查人員和檢視器的所有使用者帳戶，您可以在單一群組中設定通訊合規性許可權。 此角色群組包含所有通訊符合性許可權角色。 這項設定是快速開始使用通訊相容性的最簡單方法，而且很適合不需要個別使用者群組定義個別許可權的組織。 |
| **通訊合規性系統管理員** | 使用此角色群組開始設定通訊相容性和更新後，以將通訊合規性管理員隔離成定義的群組。 指派給此角色群組的使用者，可以建立、讀取、更新和刪除通訊符合性原則、全域設定和角色群組指派。 指派給此角色群組的使用者無法查看郵件警示。 |
| **通訊法規遵從性分析師** | 使用此群組可將許可權指派給將充當通訊相容性分析員的使用者。 指派給此角色群組的使用者可以查看其被指派為檢閱者的原則、查看郵件中繼資料 (非郵件內容) 、升級至其他檢閱者，或傳送通知給使用者。 分析員無法解析待處理的警示。 |
| **通訊合規性調查員** | 使用此群組可將許可權指派給將充當通訊合規性調查人員的使用者。 指派給此角色群組的使用者可以查看郵件中繼資料和內容、升級至其他檢閱者、升級至 Advanced eDiscovery 案例、將通知傳送給使用者，以及解決警示。 |
| **通訊合規性檢視者** | 使用此群組可將管理通訊報告的許可權指派給使用者。 指派給此角色群組的使用者，可以存取通訊合規性首頁上的所有報告元件，並可以查看所有的通訊符合性報告。 |

1. Contoso IT 系統管理員可以使用全域管理員帳戶的認證來登入 **Office 365 安全性 & 規範中心** 許可權] [ (https://compliance.microsoft.com/permissions)](https://compliance.microsoft.com/permissions)頁面，並選取在 Microsoft 365 中查看及管理角色的連結。
2. 在 **安全性 & 規範中心** 內，他們會移至 [**許可權**]，然後選取在 Office 365 中查看及管理角色的連結。
3. 管理員選取 *通訊合規性* 角色群組，然後選取 [ **編輯角色群組**]。
4. 管理員從左功能窗格中，選取 **[選擇成員** ]，然後選取 [ **編輯**]。
5. 他們會選取 [ **新增** ]，然後選取所有將會管理通訊相容性、調查和審閱警示的 Contoso 使用者核取方塊。
6. 管理員選取 [ **新增**]，然後選取 [ **完成**]。
7. 他們會選取 [ **儲存** ]，將 Contoso 使用者新增至角色群組。 請選取 [ **關閉** ] 以完成步驟。

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>步驟2：存取 Microsoft 365 中的通訊符合性

設定通訊相容性的許可權之後，指派給通訊合規性角色群組的 Contoso IT 系統管理員和合規性專家便可在 Microsoft 365 中存取通訊規範解決方案。 Contoso IT 系統管理員和合規性專家有數種方式可以存取通訊相容性，並開始建立新的原則：

- 直接從通訊相容性解決方案開始
- 從 Microsoft 365 合規性中心開始
- 從 Microsoft 365 方案目錄開始
- 從 Microsoft 365 系統管理中心開始

### <a name="starting-directly-from-the-communication-compliance-solution"></a>直接從通訊相容性解決方案開始

存取方案最快的方式，就是直接登入 **通訊合規性** (<https://compliance.microsoft.com/supervisoryreview>) 解決方案。 使用此連結，Contoso IT 管理員和合規性專家將會被導向至通訊相容性一覽表儀表板，您可以在其中快速查看警示的狀態，並從預先定義的範本中建立新的原則。

![通訊合規性概觀](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>從 Microsoft 365 合規性中心開始

Contoso IT 系統管理員和合規性專家存取通訊合規性解決方案的另一種簡單方法，就是直接登入 **Microsoft 365 合規性中心** [ (https://compliance.microsoft.com)](https://compliance.microsoft.com)。 在登入之後，使用者只需要選取 ****[全部顯示] 控制項以顯示所有合規性解決方案，再選取 [通訊合規性]**** 解決方案，即可開始使用。

![合規性中心](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>從 Microsoft 365 方案目錄開始

Contoso IT 系統管理員和合規性專家也可以選擇 Microsoft 365 方案目錄，以存取通訊相容性解決方案。 在 **Microsoft 365 合規性中心** 的左側導覽中，選取 [**方案**] 區段中的 [**目錄**]，即可開啟列出所有 Microsoft 365 規範解決方案的方案目錄。 向下滾動至「 **內幕人員風險管理** 」區段，Contoso IT 系統管理員可以選取要開始的通訊相容性。 Contoso IT 管理員也會決定使用「顯示在導覽」控制項中，將通訊相容性解決方案固定至左功能窗格，以在使用者登入時更快速地進行存取。

![方案目錄](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>從 Microsoft 365 系統管理中心開始

若要在從 Microsoft 365 系統管理中心開始時存取通訊相容性，Contoso IT 系統管理員和合規性專家會登入 Microsoft 365 系統管理中心 [ (https://admin.microsoft.com)](https://admin.microsoft.com)並流覽 **Microsoft 365 系統管理中心**  >  **規範**。

![通訊符合性連結](../media/communication-compliance-case-compliance-link.png)

此巨集指令會開啟 **Office 365 安全性與合規性中心**，而且必須選取頁面上方橫幅中所提供之 **Microsoft 365 合規性中心** 的連結。

![Office 365 安全性與合規性中心](../media/communication-compliance-case-scc.png)

在 **Microsoft 365 合規性中心** 中，Contoso IT 系統管理員會選取 [**全部顯示**]，以顯示完整的規範方案清單。

![通訊符合性功能表](../media/communication-compliance-case-show-all.png)

選取 [ **全部顯示**] 之後，Contoso IT 管理員可以存取通訊規範解決方案。

![通訊合規性概觀](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>步驟3：設定必要條件及建立通訊相容性原則

若要開始使用通訊合規性原則，Contoso IT 系統管理員在設定新原則以監視攻擊性語言之前，必須先設定幾個必要條件。 完成這些必要條件之後，Contoso IT 系統管理員和合規性專家可以設定新的原則，而合規性專家可以開始調查並補救任何產生的警示。

### <a name="enabling-auditing-in-microsoft-365"></a>啟用 Microsoft 365 中的審計

通訊合規性需要稽核記錄，以顯示警示並追蹤檢閱者所採取的補救動作。 稽核記錄會摘錄與已定義的組織原則相關聯的所有活動，或通訊合規性原則有所變更的相關活動。

Contoso IT 系統管理員會檢閱並完成開啟稽核的[逐步指示](turn-audit-log-search-on-or-off.md)。 開啟稽核後，就會顯示一則訊息，表示正在準備稽核記錄，而他們可以在準備完成 (約幾小時) 後執行搜尋。 Contoso IT 系統管理員只需執行此動作一次。

### <a name="configuring-yammer-tenant-for-native-mode"></a>設定原生模式 Yammer 租使用者

通訊合規性要求組織的 Yammer 租使用者處於純模式，以監視私人郵件和公用社區交談中的冒犯性語言。

Contoso IT 系統管理員請確定他們已在[Microsoft 365 文章中查看 Yammer 原生模式的概覽](/yammer/configure-your-yammer-network/overview-native-mode)資訊，並遵循執行遷移工具的步驟，在 [[設定您的 Yammer 網路以進行 Microsoft 365 文章的原生模式]](/yammer/configure-your-yammer-network/native-mode)中執行遷移工具。

### <a name="setting-up-a-group-for-in-scope-users"></a>設定範圍內使用者的群組

Contoso 合規性專家想要將所有使用者新增至會監控冒犯性語言的通訊原則。 他們可以決定個別將每個使用者帳戶新增至原則，但他們決定使用此原則使用者的 **所有使用者** 通訊群組，都能輕鬆且節省時間。

他們必須建立新的群組，以包含所有 Contoso 使用者，讓他們採取下列步驟：

1. Contoso it 管理員會登入 **Microsoft 365 系統管理中心** [ https://admin.microsoft.com) (](https://admin.microsoft.com)並流覽至 **Microsoft 365 系統管理中心**  >  **群組**  >  **群組**。
2. 他們會選取 [**新增群組**]，並完成嚮導，以建立新的 *Microsoft 365 群組* 或 *通訊群組*。

    ![群組](../media/communication-compliance-case-all-employees.png)

3. 建立新群組後，他們必須將所有 Contoso 使用者新增至新群組。 他們會開啟 **Exchange 系統管理中心** [ (https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp)並流覽至 **Exchange 系統管理中心** 收件者  >    >  **群組**。 Contoso IT 管理員會選取 [成員資格] 區域以及他們建立的新 [ *所有員工* ] 群組，然後選取 [ **編輯** ] 控制項，將所有 Contoso 使用者新增至嚮導中的新群組。

    ![Exchange 系統管理中心](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>建立要監視攻擊性語言的原則

完成所有必要條件後，Contoso 的 IT 系統管理員和合規性專家即可設定通訊合規性原則以監視攻擊性語言。 使用新的攻擊性語言原則範本，可簡單快速地設定此原則。

1. Contoso IT 系統管理員和合規性專家登入 **Microsoft 365 合規性中心**，然後從左側導覽窗格中選取 [通訊合規性]**** 選項。 此動作會開啟 [概觀]**** 儀表板，該儀表板具有通訊合規性原則範本的快速連結。 他們選取範本 [開始使用]**** 範本，以選擇 ****[監視攻擊性語言]。

    ![通訊相容性冒犯性語言範本](../media/communication-compliance-case-template.png)

2. 在原則範本精靈上，Contoso IT 系統管理員和合規性專家共同完成三個必要欄位：**原則名稱**、**要監督的使用者或群組**，以及 **檢閱者**。
3. 由於此原則精靈已建議該原則的名稱，因此 IT 系統管理員和合規性專家決定保留建議的名稱，並專心處理其餘欄位。 他們會選取 [ *所有使用者* ] 群組中的 [ **要監督的使用者或群組** ] 欄位，並選取應調查和修正「 **檢閱者** 」欄位之原則警示的規範專家。 設定原則及開始收集警示資訊的最後一個步驟，是選取 [ **建立原則**]。

    ![通訊相容性冒犯性語言嚮導](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>步驟4：調查和修正警示

現在，監視攻擊性語言的通訊合規性原則已設定完成，Contoso 合規性專家的下一個步驟將是調查並補救該原則所產生的任何警示。 最多需要 24 小時，原則才能完整處理所有通訊來源通道中的通訊，並且在 **警示儀表板** 中顯示警示。

提醒產生之後，Contoso 合規性專家將遵循 [工作流程指示](communication-compliance-investigate-remediate.md) ，調查並修正冒犯性語言的問題。