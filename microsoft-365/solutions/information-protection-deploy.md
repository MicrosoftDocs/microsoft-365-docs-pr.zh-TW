---
title: 使用 Microsoft 365 部署資料隱私權法規的資訊保護
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
description: 設定安全性和服務基礎結構，以保護您的資訊並遵守資料隱私權規定。
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695102"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>使用 Microsoft 365 部署資料隱私權法規的資訊保護

這項解決方案提供有關如何規劃及保護 Microsoft 365 服務中儲存的個人資料，以及可能遵循資料隱私權法規（如歐盟一般資料保護規定（GDPR））的指導方針。 此解決方案著重于適用的 Microsoft 資訊保護和符合性功能、Microsoft 規範分數和評估工具，以協助您瞭解資料。 
 
其他資訊也會提供使用 Microsoft 身分識別、裝置和威脅防護控制的資料隱私權需求，以及資料事件探索和回應工具。 

## <a name="organization-of-this-guidance-material"></a>本指南資料的組織

為了協助您瞭解可供您識別、管理、控制及監視個人資料是否受一或多項隱私權相關的法規制約的 Microsoft 365 工具，本指南會組織成幾節。
 
![部署資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-deploy-grid.png)

每個章節都對應此方案中的個別文章。

>[!Note]
>如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。

>[!Important]
>遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。 您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>規劃：評估資料隱私權風險及識別敏感專案 

評估貴組織所需的資料隱私權規定和風險，是開始實施增強功能（包括透過 Microsoft 365 設定可實現）的重要第一步。 這可能包括您的組織需要遵守之監管控制的整體準備工作或特定機密資訊類型的識別，以及在 Microsoft 365 環境中的出現。

如需詳細資訊，請參閱[評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。

## <a name="track-use-compliance-score-and-compliance-manager"></a>追蹤：使用合規性分數和合規性管理員 

合規性分數和合規性管理員提供一組整合的工具，可在 Microsoft 365 合規性系統管理中心和服務信任入口網站中使用。 這些工具共同為您提供內建的功能，可以追蹤和管理整體的整體功能，以及與您所進行的多個資料隱私權法規相關的功能。

這些工具也可讓您利用各項法規特有的內建評估範本，您可以在其中追蹤選取的每個評估範本的動作專案，以及查看特定的規章控制項，並將它們與特定動作相關聯。

如需詳細資訊，請參閱[使用合規性分數和合規性管理員管理改進動作](information-protection-deploy-compliance.md)。

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>禁止：針對資料隱私權規定使用身分識別、裝置和威脅防護

Microsoft 365 提供許多身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。 

如需詳細資訊，請參閱[使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。

本文簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關 Microsoft 365 解決方案的清單，並提供詳細資訊的連結，可協助您處理任何執行需求。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保護受資料隱私權法規制約的資訊

資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40保護 GDPR 的範例集合中的四個數據隱私權規定、加州消費者保護法（美國衛生保健隱私權法案）和巴西資料保護法案（LGPD）等各項的資訊控制。

如需詳細資訊，請參閱[保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。

本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受資料隱私權法規制約的資訊

針對您的環境可採用的個人資訊控管，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四個數據隱私權規定中的超過二十五個控制措施。

如需詳細資訊，請參閱[管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。

在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>調查：監控並回應資料隱私權法規的使用

在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。 

針對上述各項，具有程式、程式及其他檔，都很重要，都是示範規章主體的合規性。

如需詳細資訊，請參閱[監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。