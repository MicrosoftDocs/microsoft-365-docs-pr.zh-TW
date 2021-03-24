---
title: 委派管理常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在 Microsoft 合作夥伴和轉銷商的 Microsoft 365 中，查看有關委派管理工作的常見問題及解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058907"
---
# <a name="delegated-administration-faq"></a>委派管理常見問題集

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本文提供 microsoft 合作夥伴和轉銷商中 Microsoft 365 的委派管理工作的常見問題和解答。 委派管理包括管理 Exchange Online Protection (EOP) 設定其他承租人 (公司) 的功能。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>我是轉銷商，我需要管理客戶承租人。 這是如何運作的？

如果您是 Microsoft 合作夥伴或轉銷商，而且您已註冊成為 Microsoft advisor，您可以在客戶的 Microsoft 365 組織中要求 _委派管理_ 功能。

委派管理可讓您管理 Microsoft 365 (包括 EOP 設定) 如您是該組織內的系統管理員。 下列清單說明設定委派管理的步驟：

1. 註冊成為 [Microsoft Office 365 Advisor](https://partner.microsoft.com/?cloudbenefits)。

2. 註冊委派管理。 在您開始管理客戶的承租人之前，必須以委派的管理員身分授權您。 若要取得他們的核准，您必須先 [傳送給他們，以取得委派管理的服務](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 您也可以稍後為客戶提供委派管理。

3. 使用 [新增、變更或刪除訂閱顧問合作夥伴](../../admin/misc/add-partner.md)中的步驟，建立委派的系統管理員帳戶。

請造訪協力廠商 [：組建您的商務和管理合作夥伴訂閱](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) ，以取得如何設定委派管理的詳細資訊。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>我是客戶，不是轉銷商。 如何設定 subtenants 的委派系統管理員？

「委派管理」只適用于轉銷商和合作夥伴。 不過，有一個範例 PowerShell 腳本，可協助您將原則套用至 subtenants (公司) 。 如需詳細資訊，請參閱 [將 EOP 設定套用至多個承租人的範例腳本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>我可以防止我的 subtenant 系統管理員修改我的原則嗎？

否。 Microsoft 365 目前並未具備這項功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>我是否可以在所有的 subtenants 中取得整合報告？

在您管理的公司內整合報告無法在 Microsoft 365 系統管理中心報告中使用。 不過，您可以使用 [Microsoft Graph](/graph/overview)取得報告。