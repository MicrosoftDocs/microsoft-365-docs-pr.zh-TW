---
title: EOP 中的功能權限
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 執行工作以管理 Microsoft Exchange Online Protection (EOP) 所需的權限會視您正在管理的功能而異。
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638115"
---
# <a name="feature-permissions-in-eop"></a>EOP 中的功能權限

執行工作以管理 Exchange Online Protection （EOP）所需的許可權會視您正在管理的功能而異。

若要設定 EOP，您必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection 權限

若要找出管理 EOP 功能需要什麼權限，請參閱下表。如果某項功能列出一個以上的角色群組，您只需要被指派其中一個角色群組即可使用此功能。

|**功能**|**必要的權限**|
|:-----|:-----|
|反惡意程式碼|組織管理 <br/><br/> 檢疫管理|
|反垃圾郵件|組織管理 <br/><br/> 檢疫管理|
|郵件流程規則|組織管理 <br/><br/> 記錄管理|
|網域|組織管理 <br/><br/> 僅限檢視組織管理|
|進階威脅防護 (ATP)|組織管理 <br/><br/> 檢疫管理|
|Microsoft 365 連接器|組織管理|
|郵件追蹤|組織管理 <br/><br/> 僅限檢視組織管理|
|組織組態|組織管理|
|隔離|組織管理 <br/><br/> 僅限檢視組織管理 <br/><br/> 檢疫管理|
|使用者、連絡人及角色群組|組織管理 <br/><br/> 僅限檢視組織管理 <br/><br/> 檢疫管理|
|通訊群組和安全性群組|組織管理 <br/><br/> 僅限檢視組織管理 <br/><br/> 檢疫管理|
|檢視報告|組織管理：存取郵件保護報告。 <br/><br/> View-Only 收件者：存取郵件保護報告。  <br/><br/> 規範管理：存取郵件保護報告及資料遺失防護（DLP）報告（如果您的訂閱具有 DLP 功能）。|
