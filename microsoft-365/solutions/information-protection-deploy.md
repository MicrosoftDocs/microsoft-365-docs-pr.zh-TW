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
description: 在 Microsoft 365 中為數據隱私權法規（如 GDPR 和加州消費者隱私權法案 (CCPA) （包括 Microsoft Teams、SharePoint 和電子郵件）設定資訊保護。
ms.openlocfilehash: c0ffe7cf850ec6e7ae8c974f983ce43668bf6f30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287708"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>使用 Microsoft 365 部署資料隱私權法規的資訊保護

您的組織可能會受到區域資料隱私權法規的制約，需要您保護、管理及提供對您的 IT 基礎結構（包括內部部署和雲端）中儲存的個人資訊的權利及控制。 資料隱私權規定的最佳範例是歐盟的一般資料保護法規 (GDPR) 。 無法遵守資料隱私權規定可能會造成大量罰款。

Microsoft 365 中的資料類型範例包括 Microsoft Teams 中的交談會話、Exchange 中的電子郵件，以及 SharePoint 及 OneDrive 中的檔案。 這項解決方案提供有關如何評估風險和採取適當動作來保護 Microsoft 365 中個人資料的指導。 這包括識別個人資訊，讓您可以保護、管理及回應資料隱私權事件。

![何謂資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

其他資訊也是針對您的資料隱私權需求，使用 Microsoft 365 身分識別、裝置和威脅防護控制時所提供。

觀看此影片以取得部署程序的概觀。
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

這些 Microsoft 365 的功能和功能可協助您符合保護資訊的準則。

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 合規性管理員 | 管理法規遵從性活動、取得您目前的規範設定的整體分數，並尋找改進的建議。 這是 Microsoft 365 合規性中心中以工作流程為基礎的風險評估工具。 | Microsoft 365 E3 和 E5 |
| 適用於 Office 365 的 Microsoft Defender | 保護您的 Microsoft 365 應用程式和資料不受攻擊，例如電子郵件訊息、Office 文件和共同作業工具。 | Microsoft 365 E3 和 E5 |
| 敏感度標籤 | 分類及保護貴組織的資料，而不會阻礙使用者的生產力和其共同作業的能力。 在電子郵件、檔案或網站上放置具有不同保護層級的標籤。 | Microsoft 365 E3 和 E5 |
| 資料外洩防護 (DLP) | 偵測、警告和封鎖包含個人資訊（內部及外部）的危險、無意或不適當共用資料。 | Microsoft 365 E3 和 E5 |
| 資料保留標籤和原則 | 實施資訊管理控制措施。 這包括決定要保留資料的時間長度 (例如與客戶相關的個人資料) ，以符合組織的原則或資料法規。 | Microsoft 365 E3 和 E5 |
| 電子郵件加密 | 在組織內部和外部的人員之間傳送及接收加密的電子郵件，以保護個人資料。 | Microsoft 365 E3 和 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>此解決方案中指導方針的組織

為了協助您瞭解可用來協助您達成一或多項隱私權相關規章的 Microsoft 365 工具，本指南已分為各節。

![針對資料隱私權規定實施資訊保護的步驟](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

這兩個區段分別對應于此方案中的個別文章。

> [!NOTE]
> 如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。

> [!IMPORTANT]
> 遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。 您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>規劃：評估資料隱私權風險及識別敏感專案

評估貴組織所需的資料隱私權規定和風險，是開始實施改進功能（包括 Microsoft 365 中的設定功能）之前必須先做的重要第一步。 這項工作可以包含您的組織需要遵守監管控制規範的整體準備情況評估或特定機密資訊類型的識別。

如需詳細資訊，請參閱 [評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>追蹤：執行風險評估，並檢查您的合規性分數

合規性管理員可在 Microsoft 365 合規性中心中提供，讓您能夠追蹤和管理整體的整體功能，以及與套用至您的多個資料隱私權法規相關的綜合動作。

您可以使用每個法規特有的內建評估範本，您可以在其中追蹤選取的每個評估範本的動作專案，以及查看特定的規章控制項，並將其與特定動作相關聯。

如需詳細資訊，請參閱 [Use 合規性管理員管理改進動作](information-protection-deploy-compliance.md)。

## <a name="prevent-protect-personal-data"></a>防止：保護個人資料

Microsoft 365 提供身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。

如需詳細資訊，請參閱 [使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。

本文將簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關的 Microsoft 365 解決方案清單，並提供詳細資訊的連結，可協助您處理任何的執行需求。

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保護受資料隱私權法規制約的資訊

資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40個控制措施，以保護 GDPR 的範例集合中的四個數據隱私權規定，例如，加州消費者 Protection 法案 (CCPA) ，HIPAA-高科技 (美國衛生保健隱私權法案) ，以及巴西資料保護法案 (LGPD) 。

如需詳細資訊，請參閱 [保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。

本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受資料隱私權法規制約的資訊

針對您的環境可採用的個人資訊控管控制，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四種資料隱私權規定中的超過24個控制項。

如需詳細資訊，請參閱 [管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。

在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>調查：監控、調查資料隱私權事件，並作出回應

在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。

使用這些功能的程式、程式及其他檔，都很重要，就是示範規章主體的合規性。

如需詳細資訊，請參閱 [監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。

## <a name="training-for-administrators"></a>系統管理員訓練

Microsoft 相關訓練模組可協助您深入瞭解資訊保護的重要功能。


#### <a name="information-protection"></a>資訊保護

|培訓：|使用 Microsoft 365 保護企業資訊|
|:---|:---|
|![Teams info protection 訓練圖示](../media/protect-enterprise-information-microsoft-365.svg)|保護您組織資訊的方式比以往更具挑戰性。 使用 Microsoft 365 保護企業資訊學習路徑將討論如何防止您的敏感資訊意外地過度分享或誤用、如何探索和分類資料、如何使用敏感度標籤保護資料，以及如何監視和分析您的敏感資訊以避免資料遺失。 這種教學途徑可協助您準備 Microsoft 365 認證：安全性系統管理員關聯並 Microsoft 365 認證： Enterprise 管理專家認證。<br><br>1小時 Learning 路徑-5 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>身分識別和存取

|培訓：|使用 Azure Active Directory 保護身分識別和存取|
|:---|:---|
|![身分識別和存取訓練圖示](../media/protect-identity-and-access-with-microsoft-365.svg)|身分識別和存取學習路徑涵蓋最新的身分識別和存取技術、強化驗證所需的工具，以及組織內部身分識別保護的指導方針。 Microsoft 存取和身分識別技術可讓您保護組織的身分識別 (無論是內部部署或雲端)，還能讓您的使用者從任何位置安全地工作。 這個學習路徑可協助您準備 Microsoft 365 認證：安全性系統管理員助理和 Microsoft 365 認證：企業管理員專家認證。<br><br>2小時 52 min-Learning Path-6 模組|

> [!div class="nextstepaction"]
> [開始 >](/learn/modules/m365-identity-overview/introduction/)