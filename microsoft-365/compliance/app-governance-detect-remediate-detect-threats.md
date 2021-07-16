---
title: 補救應用程式威脅
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 補救應用程式威脅。
ms.openlocfilehash: 73776621ef86523d64b2a216538412bb46ab5586
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420080"
---
# <a name="remediate-app-threats"></a>補救應用程式威脅

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

您可以透過 Microsoft 365 合規性中心之 Microsoft 應用程式控管章節的 **警示** 頁面，補救 Microsoft 365 租用戶的應用程式威脅。

![Microsoft 365 合規性中心的應用程式控管警示摘要頁面](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

預設 **警示** 會列出應用程式控管所產生的新增威脅警示，以及由作用中應用程式原則所產生的原則型警示。 您可以選取特定警示以檢視詳細資料，該警示會開啟警示窗格和其他警示資訊以及變更其狀態的能力。

![Microsoft 365 合規性中心的應用程式控管警示詳細資料頁面](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

從這個窗格，您可以取得這項額外資訊：

- 在 **描述** 欄位中有關警示的其他詳細資料。
- 從 **原則名稱** 欄位產生警示的應用程式原則名稱。 您也可以選取 **檢視原則**，以前往產生警示的應用程式原則。

您從 **動作** 設定自動補救的應用程式原則會顯示 **已解決** 的狀態。

您可以使用這些步驟補救應用程式警示：

1. 調查：檢查警示中的資訊，並將其狀態變更為 **標記進行中**。
2. 解決方案：調查之後，如有需要，在您租用戶之間將應用程式原則變更或持續的應用程式支援的判斷，可將其狀態變更為 **已解決**。

根據應用程式警示模式，您可以更新正確的應用程式原則，並變更其 **動作** 設定以執行自動補救。 這可移除您進行調查並手動解決由應用程式原則產生的未來警示之需求。 如需詳細資訊，請參閱 [管理您的應用程式原則](app-governance-app-policies-manage.md)。
