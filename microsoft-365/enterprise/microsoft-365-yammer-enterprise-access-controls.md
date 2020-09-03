---
title: Microsoft 365 Yammer 企業版存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文包含在實際執行環境中 Yammer 企業存取控制的簡短摘要。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332661"
---
# <a name="yammer-enterprise-access-controls"></a>Yammer 企業存取控制 

對 Yammer 實際執行環境所做的實際和邏輯存取，只限于一小組人員 (基礎結構和作業) 。 與其他 Microsoft 365 工程師一樣，Yammer 工程師也可讓使用者存取客戶資料。 您必須使用具有有限的核准者的即時存取控制系統來要求存取，類似于密碼箱。 核准者會驗證要求 (例如，他們會驗證要求是否根據需求、業務案例、時間等 ) 進行合法，然後核准或拒絕要求。 若要求遭到核准，就會將 JIT 存取權授與已定義和限制的時間。 超過存取時間之後，access 會自動到期。

與其他 Microsoft 365 服務一樣，所有的 Yammer 實際執行環境存取都會使用多重要素驗證。 所有存取和命令歷史記錄都是由 Yammer 安全小組所交為使用者，並定期登入及檢查。

如需 Yammer 管理和管理的詳細資訊，請參閱 [Yammer 系統管理](https://docs.microsoft.com/yammer/yammer-landing-page)說明。