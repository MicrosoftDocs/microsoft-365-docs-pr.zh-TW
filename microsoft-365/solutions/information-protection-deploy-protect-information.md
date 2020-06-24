---
title: 保護受資料隱私權法規制約的資訊
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 部署 Microsoft 365 安全性和合規性功能，並保護您的個人資訊。
ms.openlocfilehash: 2ec8d280d650606921becb6120546b52253620f4
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844689"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>保護受資料隱私權法規制約的資訊

您的訂閱可使用許多資訊保護控制，以協助解決資料隱私權合規性需求和規定。 包括一般資料保護規定（GDPR）、HIPAA-高科技（美國衛生保健隱私權法案）、加州消費者防護法案（CCPA）和巴西資料保護法案（LGPD）。

這些控制項位於下列解決方案範圍內：

- 敏感度標籤
- 資料外洩防護 (DLP)
- Office 郵件加密（OME）
- 小組和網站存取控制

>[!Note]
>此解決方案說明安全性和合規性功能，以保護受資料隱私權法規制約的資訊。 如需 Microsoft 365 中安全性功能的完整清單，請參閱[microsoft 365 安全性檔案](https://docs.microsoft.com/microsoft-365/security/)。 如需 Microsoft 365 中符合性功能的完整清單，請參閱[microsoft 365 規範檔](https://docs.microsoft.com/microsoft-365/compliance/)。
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>影響資訊保護控制的資料隱私權法規

以下是可能與資訊保護控制相關之資料隱私權法規的範例清單：

- GDPR 第5篇（1）（f））
- GDPR 文章（32）（1）（a）
- LGPD 文章46
- HIPAA-高科技（45 CFR 164.312 （e）（1））
- HIPAA-高科技（45 C.F.R。 164.312 （e）（2）（ii））

請參閱[評估資料隱私權風險及識別敏感專案文章](information-protection-deploy-assess.md)，以取得上述各項的詳細資訊。

資訊保護的資料隱私權法規建議：

- 保護避免遺失或未經授權的存取、使用方式和/或傳輸。
- 以風險為基礎的保護機制應用程式。
- 適當時使用加密。

您的組織可能也想要保護 Microsoft 365 內容，以供其他用途，例如其他法規遵從性需求或商務原因。 在整體資訊保護規劃、實施和管理的過程中，建立您的資訊保護架構以進行資料隱私權。

為了協助您開始使用 Microsoft 365 中的資訊保護架構，下列各節包含 Microsoft 365 的相關功能和改進動作的簡短清單。 此清單包含適用于資料隱私權規定的功能和改進動作。 不過，如果目前的功能主要取代舊的功能，此清單並不包含舊版技術。 例如，SharePoint 和 OneDrive 的資訊版權管理（IRM）不會包含在清單中，但會包含敏感度標籤。

## <a name="managing-information-protection-in-microsoft-365"></a>在 Microsoft 365 中管理資訊保護

Microsoft[資訊保護解決方案](../compliance/protect-information.md)包含許多 microsoft 365、microsoft Azure 和 microsoft Windows 的整合式功能。 在 Microsoft 365 中，資訊保護解決方案包括：

- [使用客戶金鑰的服務加密](../compliance/customer-key-overview.md)
- [機密資訊類型](../compliance/what-the-sensitive-information-types-look-for.md)（在[評估資料隱私權風險及識別敏感專案文章](information-protection-deploy-assess.md)中所述）
- [敏感性標籤](../compliance/sensitivity-labels.md) 
  - 服務/容器層級
  - 用戶端/內容層級
  - 在 SharePoint 和 OneDrive 中的靜止資料自動化
- 資料外洩防護 (DLP)
- [Office 365 郵件加密新功能（OME）](../compliance/ome.md)和 OME[高級郵件加密](../compliance/ome-advanced-message-encryption.md)

此外，網站和文件庫層級保護是在任何保護架構中包含的重要機制。

如需 Microsoft 365 以外的其他資訊保護功能資訊，請參閱：

- [Microsoft Cloud Application Security （MCAS）](https://docs.microsoft.com/cloud-app-security/)
- [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows 資訊保護](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>敏感度標籤

Microsoft 資訊保護架構中的靈敏度標籤可讓您分類及保護組織的資料，而不會阻礙使用者的生產力和其共同作業的能力。

![Microsoft 365 中的敏感度標籤](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>敏感度標籤的必要條件

在執行下列的任何敏感度標籤型功能之前，請先完成這些活動：

1. 瞭解下列各項：
   - **業務需求。** 建立在您的企業中套用敏感度標籤的業務原因。 例如，您的資訊保護的資料隱私權需求。
   - **敏感度標籤功能。** 敏感度標籤會變得很複雜，所以請務必先閱讀[靈敏度標籤檔](../compliance/sensitivity-labels.md)，然後再開始著手。
   - **需要記住的重要事項**敏感度標籤會在 Microsoft 合規性系統管理中心中管理，但目標和應用程式選項會有很大的差異。
      - 容器層級的網站、群組及小組都有敏感性標籤（這些設定不適用於容器內部的內容）。 當您布建網站、群組或小組時，會將這些專案發佈給使用者和群組。
      - 使用中內容有敏感性標籤。 這些也會發佈給使用者或群組，使用者或群組是手動套用的，或會在下列情況下自動套用：
        - 檔案會開啟/編輯/儲存至使用者的桌面或 SharePoint 網站。
        - 電子郵件會進行起草及傳送。
      - 除了透過 Exchange 透過 Exchange 傳送電子郵件之外，還會在 rest 的 SharePoint 和 OneDrive 中，自動應用程式的敏感標籤。 這兩個網站都是針對所有網站或特定專案，並自動套用到這些環境中的 rest 檔案。

2. 合理使用過去或替代方法來標籤的目前敏感度

   - Azure 資訊保護

      目前的靈敏度標籤配置可能需要與任何現有的[Azure 資訊保護](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)標籤實施進行協調。
   - OME

      如果您打算使用新式敏感度標籤來進行電子郵件保護，且現有的電子郵件加密方法（如 OME）已存在，則可以共存，但您應該瞭解應該套用的情況。 請參閱[Office 365 郵件加密新功能（OME）](#office-365-message-encryption-ome-new-capabilities)，其中包括比較新式敏感度標籤類型保護與 OME 型防護的表格。

3. 規劃整合到更廣泛的資訊保護架構。 在與 OME 共存的位置上，目前的靈敏度標籤可以像是 Microsoft 365 資料遺失防護（DLP）和 Microsoft Cloud App Security 等相關功能使用。 請參閱[敏感度標籤和 Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) ，以實現您資料隱私權相關的資訊保護目標。

4. 開發靈敏度標籤分類和控制配置。 請參閱[資料分類和敏感度標籤分類法](https://aka.ms/dataclassificationwhitepaper)。

### <a name="general-guidance"></a>一般指導方針

1. **架構定義。** 使用技術功能來套用標籤和保護之前，請在您的組織中工作以定義分類架構。 您可能已經有分類架構，可讓您更輕鬆地新增個人資料。 
2. **開始。** 請先決定要執行的標籤數量和名稱。 執行這項活動，不需擔心使用哪種技術及標籤的套用方式。 請全域套用整個組織中的架構，包括位於內部部署和其他雲端服務中的資料。
3. **其他建議**設計及實施原則、標籤和條件時，請考慮遵循下列建議：

   - **使用現有的分類架構（如果有的話）。** 許多組織已使用某種形式的資料分類。 請仔細評估現有的標籤架構，如果可能的話，請使用它。 使用您的使用者可以辨識的熟悉標籤，將會促進採用。
   - **從小開始。** 實際上沒有限制您可以建立的標籤數目。 不過，大量的標籤與子標籤會導致採用速度變慢。
   - **使用案例和使用案例。** 識別組織內常見的使用案例，並使用衍生自您所使用之資料隱私權法規的案例。 確認預想的標籤和分類設定在實踐中是否可以運作。
   - **針對新標籤提出每個要求。** 每個案例或使用案例實際上都需要新標籤，還是可以使用您已有的功能？ 保留標籤的最小值可提升採用。
   - **使用主要部門的子標籤。** 有些部門需要特定標籤的特定需求。 將這些標籤定義為現有標籤的子標籤，並考慮使用指派給使用者群組的範圍式原則，而不是全域性。
   - **考慮範圍原則。** 以使用者子集為目標的原則，會使標籤超載。 限定範圍的原則可讓您指派角色或部門特定標籤或子標籤，只供員工在該特定部門工作。 
   - **使用有意義的標籤名稱。** 請不要使用行話、標準或縮寫做為標籤名稱。 嘗試使用與使用者 resonate 的名稱，以提升採用。 請不要使用像 PII、PCI、HIPAA、LBI、MBI 和 HBI 的標籤，考慮諸如非企業、公開、一般、機密和高度機密的名稱。

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>建立及部署網站、群組及小組的敏感度標籤

當您在 Microsoft 365 規範中心建立[靈敏度標籤](../compliance/sensitivity-labels-teams-groups-sites.md)時，您現在可以將其套用至這些容器：

- Microsoft 小組網站
- Microsoft 365 群組（以前稱為 Office 365 群組）
- SharePoint 網站

使用下列標籤設定來協助保護這些容器中的內容：

- Microsoft 365 群組連線的小組網站的隱私權（公開或私人）
- 外部使用者存取
- 從未受控裝置存取

針對資料隱私權，若要避免將用來儲存具有敏感個人資料之內容的容器的外部共用，請將包含資料的檔案標記為私密，並需要受管理的裝置。

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>建立及部署內容的敏感度標籤

套用至檔案的敏感度標籤可讓您加密其內容、為內容加上浮水印，以及定義 Office 應用程式內容的其他控制項，包括網頁上的 Outlook 和 Office。

當您準備好使用敏感度標籤來開始保護組織的資料時：

1. **建立標籤。** 根據貴組織用於不同內容敏感度層級的分類法，建立您的敏感度標籤並加以命名。 如需開發分類分類法的詳細資訊，請參閱[資料分類和敏感度標籤分類白皮書](https://aka.ms/dataclassificationwhitepaper)。
2. **定義每個標籤的功能。** 設定您想要與每個標籤相關聯的保護設定。 例如，您可能希望低敏感度內容（例如「一般」標籤）只套用標頭或頁尾，而敏感度內容（例如「機密」標籤）應具備浮水印並啟用加密。
3. **發佈標籤。** 設定好敏感度標籤之後，請使用標籤原則加以發佈。 決定哪些使用者和群組應具有標籤，以及所要使用的原則設定。 單一標籤可重複使用。 您可以定義一次，然後將其包含在指派給不同使用者的數個標籤原則中。

一旦您從 Microsoft 365 規範中心發行敏感度標籤，他們就會開始出現在[Office 應用程式](../compliance/sensitivity-labels-office-apps.md)中，讓使用者在建立或編輯內容時進行分類及保護。

![Microsoft 365 中的靈敏度標籤部署流程](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

針對資料隱私權，您可以手動將敏感度標籤與加密及其他規則套用至包含機密個人資訊的電子郵件或內容。

>[!Note]
>套用啟用加密功能的敏感度標籤會對電子郵件套用一些與 OME 的重疊功能。 請參閱[安全電子郵件案例與 OME 和敏感度標籤的比較](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)。

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>使用者編輯檔或撰寫電子郵件時的用戶端自動標籤

當您建立靈敏度標籤時，當內容符合您指定的條件時，可[自動將該標籤指派](../compliance/apply-sensitivity-label-automatically.md)給內容（包括電子郵件）。

自動將敏感度標籤套用到內容很重要，因為：

- 您不需要訓練您的使用者使用各個分類的時機。
- 您不需要仰賴使用者正確地將所有內容分類。
- 使用者不再需要了解原則，而是可以專心於工作。

自動標示功能支援為使用者推薦標籤，以及自動套用標籤。 但是在這兩種情況下，使用者都會決定接受或拒絕標籤，以協助確保正確為內容套用標籤。

此用戶端加標籤對於文件有最小延遲，因為您甚至可以在儲存文件之前套用標籤。 不過，並非所有用戶端應用程式都支援自動套用標籤。 Azure 資訊保護統一標籤用戶端和[某些版本的 Office 應用](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)程式都支援這項功能。

如需設定指示，請參閱 how [to configure auto-標記 For Office app](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

針對資料隱私權，您可以自動套用敏感度標籤，以包含機密個人資訊的內容。

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>內容已儲存時服務端自動標籤

此方法稱為使用敏感度標籤自動分類。 您也可能會聽到這種情況，稱為自動貼上靜態資料（針對 SharePoint 和 OneDrive 中的檔）和傳輸中的資料（適用于 Exchange 所傳送或接收的電子郵件）。 若為 Exchange，它不會包含靜止信箱中的電子郵件。
 
因為此標籤是由服務本身所套用，而不是由使用者應用程式來套用，所以您不需要擔心使用者有哪些應用程式，以及哪些版本。 如此一來，您就能立即在整個組織中使用這項功能，並且適用於大規模套用標籤。 自動套用標籤原則不支援建議的標籤，因為使用者不會與套用標籤程序進行互動。 相反地，系統管理員會在模擬模式中執行原則，以協助確保在實際套用標籤之前，內容正確套用標籤。

如需設定指示，請參閱 how [to configure SharePoint、OneDrive 和 Exchange 的自動標記原則](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。

針對關注網站中的資料隱私權，將敏感度標籤用於包含機密個人資訊的自動加密內容。

## <a name="data-loss-prevention"></a>資料外洩防護 

您可以使用 Microsoft 365 中的[資料遺失防護（DLP）](../compliance/data-loss-prevention-policies.md)偵測、警告和封鎖危險、不慎或不適當的共用，例如在內部和外部包含個人資訊的共用資料。

DLP 可讓您：

- 識別及監視危險的共用活動。
- 以上下文相關的指導方針教育使用者作出正確的決策。
- 強制執行沒有 inhibiting 生產力之內容的資料使用原則。
- 與分類及標籤整合，以在共用時偵測及保護資料。

### <a name="supported-workloads-for-dlp"></a>DLP 支援的工作量

透過 Microsoft 365 規範中心的 DLP 原則，您可以識別、監視和自動保護 Microsoft 365 中的多個位置的機密專案，例如 Exchange Online、SharePoint、OneDrive 和 Microsoft 團隊。

例如，您可以識別任何含有儲存在任何 OneDrive 網站中的信用卡號碼的檔，也可以只監視特定人員的 OneDrive 網站。

您也可以在本機安裝的 Excel、PowerPoint 及 Word 版本中監視和保護機密專案，這包括識別敏感專案及套用 DLP 原則的功能。 當人們共用這些 Office 應用程式的內容時，DLP 會提供連續監控。

![DLP 支援的工作量](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

下圖顯示保護個人資料之 DLP 的範例。

![使用 DLP 保護個人資料的範例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP 是用來識別包含狀況記錄的檔或電子郵件，然後自動封鎖該檔的存取權，或封鎖電子郵件的傳送。 DLP 接著會以原則提示通知收件者，並將警示傳送給使用者和系統管理員。

### <a name="planning-for-dlp"></a>規劃 DLP

規劃 DLP 原則： 

- 您的業務需求。

- 組織的風險評估[，如評估資料隱私權風險及識別敏感專案文章](information-protection-deploy-assess.md)所述。

- 其他資訊保護和控管機制，或為數據隱私權進行規劃。

- 根據評估[資料隱私權風險及識別敏感專案文章](information-protection-deploy-assess.md)中所述，您已根據評估運作識別個人資料的機密資訊類型。 DLP 原則條件可以以機密資訊類型和保留標籤為基礎。

- 保留標籤您將需要指定 DLP 條件。 如需詳細資訊，請參閱[管理組織中資料隱私權規定](information-protection-deploy-govern.md)的相關資訊。

- 持續性的 DLP 原則管理，需要組織中的某人針對敏感資訊類型、保留標籤、法規及符合性原則中的變更，運作及調整原則。

雖然在 DLP 原則條件中無法使用敏感度標籤，但根據敏感資訊類型，您可以根據敏感資訊類型自動套用的機密標籤，防止存取的某些保護案例可以得以實現。 如果已就地確定強大的靈敏度，請考慮是否應該使用 DLP 來增加保護，因為：

  - DLP 可以防止共用檔案。 敏感度標籤只會阻止存取。

  - DLP 在規則、條件及動作方面具有更細微的控制層級。

  - DLP 原則可以套用到小組聊天和通道訊息。 敏感度標籤只適用于檔和電子郵件。


### <a name="dlp-policies"></a>DLP 原則

DLP 原則是在 Microsoft 合規性系統管理中心中設定，並指定保護的層級、原則所要尋找的敏感資訊類型，以及目標工作負載。 其基本元件是由識別保護和資料類型所組成。

![Microsoft 365 中的 DLP 原則設定](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

以下是 GDPR 知曉的 DLP 原則範例。

![GDPR 知曉的 DLP 原則範例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

如需建立及套用 DLP 原則的詳細資訊，請參閱[本文](../compliance/create-test-tune-dlp-policy.md)。

### <a name="protection-levels-for-data-privacy"></a>資料隱私權的保護層級

下表列出使用 DLP 增強保護的三種設定。

![使用 DLP 的資料隱私權保護層級](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

第一個設定、意識，可以做為滿足資料隱私權規定之法規遵從性需求的起點和最低的保護層級。

>[!Note]
>隨著保護層級的增加，在某些情況下，使用者共用和存取訊號的能力將會降低，而且可能會影響其生產力或完成日常工作的能力。
>

為了協助您的員工在提高保護層級時，維持在更安全的環境中，您可以花時間訓練及教育其新的安全性原則及程式。

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>使用敏感度標籤與 DLP 的範例

敏感度標籤可以搭配 DLP 一起使用，以在高度管制的環境中提供資料隱私權。 以下是整合部署的主要步驟：

1. 會記錄資料隱私權的規章和業務需求。
2. 根據資料隱私權的考慮，目標資料來源、類型及擁有權都有其相關的特徵。
3. 已建立的整體策略，可滿足需求和保護及控制資料隱私權的熱點。
4. 解決資料隱私權控制策略的分階段行動計畫即會放入到位。

決定這些元素之後，您可以使用敏感資訊類型、敏感度，以及將 DLP 原則放在一起。 下圖顯示範例。

![使用 DLP 之敏感度標籤的範例](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[查看較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

以下是一些使用 DLP 和敏感度標籤的資料保護案例，如圖所示。

| 案例 | 程序 |
|:-------|:-----|
| A | <ol><li>內容的敏感度標籤是由系統管理員發佈給使用者和群組，以供手動或自動向內容和電子郵件應用程式使用。 </li><li>使用者 A 會以手動方式或自動方式套用標籤與內容互動時，已套用加密或其他設定。 </li><li>使用者 A 會將受保護的電子郵件或檔案傳送給使用者 B （來賓使用者）。 </li></ol> |
| B | 由系統管理員發佈給使用者 A 封鎖的 DLP 原則，可將電子郵件和/或檔案傳送給使用者 B。 |
| C |  [擁有者無法邀請來賓] 設定的「敏感度」標籤會發佈給使用者 A，其可布建小組小組或 SharePoint 網站。 網站的另一個使用者會選擇性地嘗試與使用者 B 共用檔案，但 DLP 會封鎖該檔案。 |
| D | 自動應用程式網站內容的敏感度標籤會發佈到一或多個網站，提供另一層保護，進而產生受保護的網站。 |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 郵件加密（OME）的新功能

人們經常會使用電子郵件來交換器密專案，例如患者健康資訊或客戶和員工資訊。 電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。

透過[OME](../compliance/ome.md)，您可以在組織內部和外部的人員之間傳送和接收加密的郵件。 OME 與 Outlook.com、Yahoo！、Gmail 及其他電子郵件服務搭配使用。 OME 可協助確保只有預定的收件者可以查看郵件內容。

針對資料隱私權，您可以使用 OME 來保護包含敏感專案的內部郵件。 Office 365 郵件加密是以 Microsoft Azure 版權管理（Azure RMS）為基礎的線上服務，這是 Azure 資訊保護的一部分。 這包括加密、身分識別和授權原則，以協助保護您的電子郵件。 您可以使用 rights management 範本、[不要轉寄] 選項及 [僅限加密] 選項來加密郵件。

您也可以定義郵件流程規則，以套用這種保護。 例如，您可以建立規則，要求所有傳送給特定收件者的郵件，或在主旨行中包含特定關鍵字的郵件，也指定收件者無法複製或列印郵件的內容。

此外，OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)可協助您符合法規遵從性義務，需要更多彈性控制外部收件者，以及其對加密電子郵件的存取權。 使用 Microsoft 365 中的 OME Advanced Message Encryption，您可以控制在組織外共用的敏感電子郵件，其自動原則會偵測到敏感資訊類型。 

針對資料隱私權，如果您需要與外部一方共用電子郵件，您可以指定到期日和吊銷郵件。 您只能撤銷及設定傳送給外部收件者之郵件的到期日。

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>保護電子郵件案例與 OME 和敏感度標籤的比較

套用至使用加密的電子郵件的 OME 和敏感度標籤有一些交疊，所以請務必瞭解可能適用的案例，如下表所示。

| 案例 | 敏感度標籤 | OME |
|:-------|:-----|:-------|
| 內部 + 合作夥伴 <br> 安全地在內部使用者與信任的合作夥伴之間進行通訊及共同作業 | 建議–具有完整自訂分類和保護的標籤 | Yes –只對無分類的加密或不轉寄保護 |
| 外部團體 <br> 與任何外部/消費者使用者安全地進行通訊及共同作業 | 是–標籤中的預先定義收件者 | 建議–根據收件者的即時保護 |
| 內部 + 協力廠商，具有到期/撤銷 <br> 使用到期及撤銷的內部使用者和信任的合作夥伴來控制郵件和內容的存取 | 建議使用存取時間進行完整的自訂保護，使用者可以手動追蹤和撤銷檔 | 否–內部郵件沒有撤銷或到期 |
| 具有到期/撤銷的外部方 <br> 使用已到期及撤銷的外部/消費者使用者來控制郵件和內容的存取 | Yes –使用者可以手動追蹤檔 | 建議（E5）–系統管理員可以從安全性 & 規範中心撤銷郵件 |
| 自動標籤 <br> 組織想要自動保護具有特定機密內容和/或特定收件者的郵件/附件 | 建議（E5）-在 Exchange 和 Outlook 用戶端中自動標記，擴充郵件流程規則和 DLP 原則 | Yes-郵件流程規則和 DLP 原則，只含加密或不轉寄保護 |
||||

在這兩種方法之間，使用者與系統管理員的經驗也會有差異。

## <a name="teams-with-protection-for-highly-sensitive-data"></a>具有高度機密資料保護的團隊

若要將個人資料儲存至小組中的資料隱私權規定的組織，請參閱[Configure a team with security 隔離](secure-teams-security-isolation.md)，它提供下列各項的詳細指導方針和設定步驟：

- 身分識別與裝置存取
- 建立私人團隊
- 鎖定基礎小組網站許可權
- 使用加密的群組型敏感度標籤
