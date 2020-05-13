---
title: 委派管理常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 本主題為想要執行委派 Microsoft 365 管理工作的 Microsoft 合作夥伴和轉銷商提供 FAQs 和解答。
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209520"
---
# <a name="delegated-administration-faq"></a>委派管理常見問題集

本主題針對想要執行委派管理工作（包括管理其他租使用者（公司）的 Exchange Online Protection （EOP）的 Microsoft 合作夥伴和轉銷商提供常見問題和解答。

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>我是轉銷商，我需要管理客戶的承租人;這是如何運作的？

如果您是 Microsoft 合作夥伴或轉銷商，而且您已註冊成為 Microsoft advisor，您可以在系統管理中心中要求管理其租使用者的許可權。 這稱為「委派管理」，可讓您管理其 Microsoft 365 租使用者（包括 EOP 設定），如同您是組織內的系統管理員。 執行委派管理的步驟如下：

1. 註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。

2. 註冊委派管理。 在您開始管理客戶的帳戶之前，必須以委派的管理員身分授權。 若要取得他們的核准，您必須先[傳送給他們，以取得委派管理的服務](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 （您也可以稍後為客戶提供委派管理）。

3. 使用[新增、變更或刪除訂閱顧問合作夥伴](https://docs.microsoft.com/office365/admin/misc/add-partner)中的步驟，建立委派的系統管理員帳戶。

請造訪協力廠商[：組建您的商務和管理合作夥伴訂閱](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)，以取得如何設定委派管理的詳細資訊。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>我是客戶，而不是轉銷商，如何設定子承租人的委派系統管理員？

委派的管理目前只有轉銷商和合作夥伴才能使用。 不過，我們提供了一個範例 Windows PowerShell 腳本，可協助您將原則套用至您的子承租人（公司）。 如需詳細資訊，請參閱[將 EOP 設定套用至多個承租人的範例腳本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>我是否可以防止子租使用者系統管理員修改我的原則？

Microsoft 365 目前並未具備這項功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>我是否可以取得所有我子承租人的整合報告？

目前您管理的公司內的整合報告無法供 Microsoft 365 系統管理中心報告使用。 不過，您可以使用[Microsoft Graph](https://docs.microsoft.com/graph/overview)來執行此動作。
