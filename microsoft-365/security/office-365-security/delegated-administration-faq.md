---
title: 委派管理常見問題集
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 本主題為想要執行委派 Microsoft 365 管理工作的 Microsoft 合作夥伴和轉銷商提供 FAQs 和解答。
ms.openlocfilehash: d2411734e583cce2be817793e2b39abba2b186a5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036460"
---
# <a name="delegated-administration-faq"></a>委派管理常見問題集

本主題針對想要執行委派管理工作（包括管理其他租使用者（公司）的 Exchange Online Protection （EOP）的 Microsoft 合作夥伴和轉銷商提供常見問題和解答。

**問：我是轉銷商，需要管理客戶的承租人；該怎麼做？**

答： 如果您是 Microsoft 合作夥伴或轉銷商，而且您已註冊成為 Microsoft advisor，您可以在系統管理中心中要求管理其租使用者的許可權。 這稱為「委派管理」，可讓您管理其 Microsoft 365 租使用者（包括 EOP 設定），如同您是組織內的系統管理員。 執行委派管理的步驟如下：

1. 註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。

2. 註冊委派管理。 在您開始管理客戶的帳戶之前，必須以委派的管理員身分授權。 若要取得他們的核准，您必須先[傳送給他們，以取得委派管理的服務](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)。 （您也可以稍後為客戶提供委派管理）。

3. 使用[新增、變更或刪除訂閱顧問合作夥伴](https://docs.microsoft.com/office365/admin/misc/add-partner)中的步驟，建立委派的系統管理員帳戶。

請造訪協力廠商[：組建您的商務和管理合作夥伴訂閱](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)，以取得如何設定委派管理的詳細資訊。

**問：我是客戶，不是轉銷商，該如何為子承租人設定委派的系統管理員？**

答：委派的管理目前僅適用於轉銷商和合作夥伴。不過，我們提供範例 Windows PowerShell 指令碼，可協助您將原則套用到您的子承租人 (公司)。如需詳細資訊，請參閱 [套用 EOP 設定至多個承租人的範例指令碼](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

**問：可以防止我的子承租人管理員修改我的原則嗎？**

答： Microsoft 365 目前並未具備這項功能。

**問：我可以取得所有子承租人的彙總報告嗎？**

答： 目前您管理的公司內的整合報告無法供 Microsoft 365 系統管理中心報告使用。 不過，您可以使用[Microsoft Graph](https://docs.microsoft.com/graph/overview)來執行此動作。
