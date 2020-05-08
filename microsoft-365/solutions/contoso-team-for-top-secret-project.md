---
title: Contoso Corporation 的最大機密專案的隔離團隊
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何使用具有安全性隔離的小組進行重要專案，以開發新的產品和服務套件。
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159452"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation 的最大機密專案的隔離團隊

在執行異地的執行中，Contoso 的 CEO 會定購一套新的產品和服務，並在今後五年中，讓 Contoso 的贏利翻倍。 開發商務、工程及市場計畫的重要專案是「**專案 2** 」和整個公司的主要人員都是 recruited。 

調查和開發的時程表已緊密，這表示共同作業必須有效並提供安全的會議、進行中的交談及檔案儲存。

專案2所產生的可傳送作業是商務計畫、產品及工程規格，以及 Word、Excel 及 PowerPoint 檔案形式的行銷材料和排程。 

由於其敏感性，對這些檔案的存取權如下：

- 限制為 Project 2 小組成員。
- 以只允許存取專案2小組成員的許可權進行加密及保護，即使這些檔案是在其安全資料夾以外的地方發佈也是一樣。

Contoso IT 人員使用具有專案2的[安全性隔離的團隊](secure-teams-security-isolation.md)和這些步驟。

## <a name="step-1-created-a-private-team"></a>步驟1：建立私人團隊

首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的[SharePoint 存取原則](../enterprise/sharepoint-file-access-policies.md)。

接下來，Contoso IT 管理員建立一個名為 Project 2 的新私人團隊，並新增專案2個人的使用者帳戶為成員。

如需設定詳細資料，請參閱[建立私人團隊](secure-teams-security-isolation.md#create-a-private-team)。

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>步驟2：為專案2小組建立敏感度標籤

Contoso admins 建立一個名為「**專案 2** 」的新敏感度標籤：

- 需要加密。
- 允許 Project 2X Microsoft 365 群組的共同撰寫許可權。

基礎專案 2 SharePoint 網站**的 [檔**] 區段中的檔案受到下列保護：

- 網站許可權，只允許存取 Project 2 之專案 365 2 群組的成員。
- 專案2敏感度標籤，其會在移動或複製到網站時，與檔案一起旅行的加密和許可權。

如需設定詳細資料，請參閱[建立靈敏度標籤](secure-teams-security-isolation.md#create-a-sensitivity-label)。

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>步驟3：設定基礎 SharePoint 網站

首先，為了保護小組的底層 SharePoint 網站的存取權，Contoso IT 管理員設定建議的[SharePoint 存取原則](../enterprise/sharepoint-file-access-policies.md)。

接下來，他們設定網站的其他許可權設定，以防止 Project 2 共用網站的存取權。 如需設定詳細資料，請參閱[使用安全隔離的團隊 SharePoint 設定](secure-teams-security-isolation.md#sharepoint-settings)。

以下是專案2小組所產生的設定。

![專案2小組的產生設定](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>步驟4：訓練有素的專案2小組成員

Contoso 安全性人員會在必要課程中訓練專案2小組成員：

- 如何存取新的 Project 2 小組、使用會議和聊天，以及如何在小組檔案上共同作業。
- 如何在小組中建立新檔案，並上傳在本機建立的新檔案。
- 有關 DLP 原則如何在外部共用檔案的示範。
- 如何使用專案2敏感度標籤來標示檔案。
- 示範 Project 2X 標籤如何保護檔案的示範，甚至是在離開小組時。

最終結果是一種安全的環境，在此環境中，Project 2 小組成員在安全的環境中共同合作，以進行聊天、會議及檔。

以下是儲存在基礎專案2網站中的檔案範例，並指派 Project 2 敏感度標籤。

![儲存在基準專案2網站中的檔案範例](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

在幾個實例中，Project 2 小組成員會將專案2標籤所保護的檔案下載到本機磁片磁碟機，以供離線工作使用。 不過，當您開啟認證時出現要求時，使用者已意識到其錯誤並加以刪除。

由於小組的共同作業環境和 Microsoft 365 的安全性功能，Project 2X 的詳細資料會在專案期間內保密。 Contoso 宣告其計畫，而且正在將新產品及服務推出給其客戶和投資者的愉悅感，以及其競爭者的 chagrin。

## <a name="next-step"></a>後續步驟

在您的組織中[部署具有安全性隔離的團隊](secure-teams-security-isolation.md)。

