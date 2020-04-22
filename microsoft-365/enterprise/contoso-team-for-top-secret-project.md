---
title: Contoso Corporation 的機密專案小組
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何對重要專案的高管制資料使用團隊，以開發新的產品和服務套件。
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636495"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation 的機密專案小組

在執行異地的執行中，Contoso 的 CEO 會定購一套新的產品和服務，並在今後五年中，讓 Contoso 的贏利翻倍。 開發商務、工程及市場計畫的重要專案是「**專案 2** 」和整個公司的主要人員都是 recruited。 

調查和開發的時程表已緊密，這表示共同作業必須有效並提供安全的會議、進行中的交談及檔案儲存。

專案2所產生的可傳送作業是商務計畫、產品及工程規格，以及 Word、Excel 及 PowerPoint 檔案形式的行銷材料和排程。 

由於其敏感性，對這些檔案的存取權如下：

- 限制為 Project 2 小組成員。
- 使用資料遺失防護（DLP）原則進行保護，以避免專案2小組成員在小組外共用這些專案。
- 以只允許存取專案2小組成員的許可權加密及保護，即使檔案是在 Contoso 以外發佈。

Contoso IT 人員使用專案2和這些步驟的[高管制資料的小組](secure-teams-highly-regulated-data-scenario.md)。

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>步驟1：建立私人團隊並鎖定基礎 SharePoint 網站

為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定了[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。

接下來，Contoso IT 管理員建立一個名為 Project 2 的新私人團隊，並新增專案2個人的使用者帳戶為成員。

接下來，他們設定網站的其他許可權設定，以防止 Project 2 共用網站的存取權，並防止其他人要求存取網站。

如需設定詳細資料，請參閱[SharePoint 高管制小組的設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)。

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>步驟2：設定保留標籤的 DLP 原則和基礎網站 

首先，Contoso 系統管理員會將現有的**高度機密**保留標籤套用至專案2小組之基礎 SharePoint 網站的 [**檔**] 區段中。

接下來，他們建立新的 DLP 原則，名稱為**Project 2** ：

- 使用高度機密保留標籤。
- 當使用者嘗試在 Contoso 以外的 Project 2 小組中共用檔案時，封鎖使用者。

如需設定詳細資料，請參閱[使用保留標籤和 DLP 保護小組中](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)的檔案。

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a>步驟3：為專案2小組建立敏感度標籤

Contoso admins 建立一個名為「**專案 2** 」的新敏感度標籤：

- 需要加密。
- 允許 Project 2X Microsoft 365 群組的共同撰寫許可權。

以下是專案2小組所產生的設定。

![專案2小組的產生設定](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
基礎專案 2 SharePoint 網站的 [檔] 區段中的檔案受到下列保護：

- 網站許可權，只允許存取 Project 2 之專案 365 2 群組的成員。
- 高度機密保留標籤，會自動指派給新的檔案。
- 一個 DLP 原則，使用高度機密保留標籤和設定，以封鎖檔案與外部使用者共用。
- 專案2敏感度標籤，其會在移動或複製到網站時，與檔案一起旅行的加密和許可權。

以下是儲存在基礎專案2網站中的檔案範例，具有高管制保留標籤，以及指派 Project 2/2 敏感度標籤。

![儲存在基準專案2網站中的檔案範例](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>步驟4：訓練有素的專案2小組成員

Contoso 安全性人員會在必要課程中訓練專案2小組成員：

- 如何存取新的 Project 2 小組、使用會議和聊天，以及如何在小組檔案上共同作業。
- 如何在小組中建立新檔案，並上傳在本機建立的新檔案。
- 有關 DLP 原則如何在外部共用檔案的示範。
- 如何使用專案2敏感度標籤來標示檔案。
- 示範 Project 2X 標籤如何保護檔案的示範，甚至是在離開小組時。

最終結果是一種安全的環境，在此環境中，Project 2 小組成員在安全的環境中共同合作，以進行聊天、會議及檔。

在幾個實例中，Project 2 小組成員會將專案2標籤所保護的檔案下載到本機磁片磁碟機，以供離線工作使用。 不過，當您開啟認證時出現要求時，使用者已意識到其錯誤並加以刪除。

由於小組的共同作業環境和 Microsoft 365 的安全性功能，Project 2X 的詳細資料會在專案期間內保密。 Contoso 宣告其計畫，而且正在將新產品及服務推出給其客戶和投資者的愉悅感，以及其競爭者的 chagrin。

## <a name="next-step"></a>下一步

[部署](deploy-microsoft-365-enterprise.md)您組織中的 Microsoft 365 企業版。

## <a name="see-also"></a>請參閱

[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)
