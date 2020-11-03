---
title: 使用 Microsoft 365 部署資料隱私權法規的資訊保護
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 設定安全性和服務基礎結構，以保護您的資訊並遵守資料隱私權規定。
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842293"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>使用 Microsoft 365 部署資料隱私權法規的資訊保護

您的組織可能會受到區域資料隱私權法規的制約，需要您保護、管理及提供對您的 IT 基礎結構（包括內部部署和雲端）中儲存的個人資訊的權利及控制。 資料隱私權規定的最佳範例是歐盟的一般資料保護法規 (GDPR) 。 無法遵守資料隱私權規定可能會造成大量罰款。

365 Microsoft 團隊中的資料類型範例包括 Microsoft 團隊、Exchange 中的電子郵件，以及 SharePoint 和 OneDrive 中的檔案。 此解決方案提供有關如何評估風險及識別資訊、保護、管理及回應資料隱私權事件，以供 Microsoft 365 服務中儲存的個人資料（受限於資料隱私權法規）的指導。

![何謂資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

其他資訊也會提供使用 Microsoft 365 身分識別、裝置和威脅防護控制的資料隱私權需求。 

若要符合保護資訊以符合資料隱私權規定的準則，請使用下列 Microsoft 365 功能。

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 合規性管理員 | 管理法規遵從性活動、取得目前的規範設定的整體分數，以及在 Microsoft 365 規範中心的此工作流程型風險評估工具中尋找改進的建議。 | Microsoft 365 E3 和 E5 |
| Microsoft Defender for Office 365 | 保護您的 Microsoft 365 應用程式和資料不受攻擊，例如電子郵件訊息、Office 文件和共同作業工具。 | Microsoft 365 E3 和 E5 | 
| 敏感度標籤 | 在電子郵件、文件或網站上套用具有不同保護層級的標籤，可以在不影響使用者工作效率和共同作業能力的情況下對組織的資料進行分類和保護。 | Microsoft 365 E3 和 E5 |
| 資料外洩防護 (DLP) | 偵測、警告，並封鎖風險、不慎或不當的共用，例如共用包含個人資訊的資料 (內部和外部)。 | Microsoft 365 E3 和 E5 | 
| 資料保留標籤和原則 | 實施資訊控管控制，例如資料的保留時間以及對客戶個人資料儲存的要求，以符合組織的原則或資料法規。 | Microsoft 365 E3 和 E5 |
| 電子郵件加密 | 在組織內外的人員之間傳送和接收加密的電子郵件訊息，包含管制資料，例如客戶的個人資料。 | Microsoft 365 E3 和 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>此解決方案中指導方針的組織

為了協助您瞭解可供您識別、管理、控制及監視個人資料是否受一或多項隱私權相關的法規制約的 Microsoft 365 工具，本指南會組織成幾節。
 
![針對資料隱私權規定實施資訊保護的步驟](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

每個章節都對應此方案中的個別文章。

>[!Note]
>如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。

>[!Important]
>遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。 您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>規劃：評估資料隱私權風險及識別敏感專案

評估貴組織所需的資料隱私權規定和風險，是開始實施增強功能（包括透過 Microsoft 365 設定可實現）的重要第一步。 這可能包括您的組織需要遵守之監管控制的整體準備工作或特定機密資訊類型的識別，以及在 Microsoft 365 環境中的出現。

如需詳細資訊，請參閱 [評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>追蹤：執行風險評估，並檢查您的合規性分數

合規性管理員（適用于 Microsoft 365 規範中心）提供了內建的功能，可用於追蹤及管理整體的改善動作，以及與您套用至多個資料隱私權法規相關的功能。

利用每項法規特有的綜合評估範本，您可以在其中追蹤所選取之每個評估範本的動作專案，以及查看特定的規章控制，以及將它們與特定動作相關聯。

如需詳細資訊，請參閱 [Use 合規性管理員管理改進動作](information-protection-deploy-compliance.md)。

## <a name="prevent-protect-personal-data"></a>防止：保護個人資料

Microsoft 365 提供許多身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。 

如需詳細資訊，請參閱 [使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。

本文簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關 Microsoft 365 解決方案的清單，並提供詳細資訊的連結，可協助您處理任何執行需求。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保護受資料隱私權法規制約的資訊

資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40保護 GDPR 的範例集合中的四個數據隱私權規定，LGPD 法案 Act (CCPA) 、HIPAA-高科技 (美國衛生保健隱私權法案) 及巴西資料保護法案 () 。

如需詳細資訊，請參閱 [保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。

本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受資料隱私權法規制約的資訊

針對您的環境可採用的個人資訊控管，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四個數據隱私權規定中的超過二十五個控制措施。

如需詳細資訊，請參閱 [管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。

在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>調查：監控、調查資料隱私權事件，並作出回應

在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。 

針對上述各項，具有程式、程式及其他檔，都很重要，都是示範規章主體的合規性。

如需詳細資訊，請參閱 [監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。
