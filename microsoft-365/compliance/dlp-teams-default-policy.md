---
title: '深入瞭解 Microsoft 小組 (預覽中的預設資料遺失防護原則) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 深入瞭解 Microsoft 小組的預設資料遺失防護原則
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826231"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>深入瞭解 Microsoft 小組 (預覽中的預設資料遺失防護原則) 

[資料遺失防護](data-loss-prevention-policies.md) (DLP) 功能已經過擴充，可包括 Microsoft 團隊聊天和通道訊息，包括私人通道訊息。 在此版本中，我們會為第一次客戶建立「合規性中心」的預設 DLP 原則。

## <a name="applies-to"></a>適用於

以下列一或多個授權授權的任何租使用者，以及具有作用中團隊使用者的任何租使用者
 
- ME5, 
- MA5, 
- E5/A5 規範 
- IP + G， 
- OE5, 
- O365 高級規範 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>預設原則的功能為何？

預設的 DLP 原則會追蹤組織內部及外部共用的所有信用卡號碼。 針對租使用者的所有使用者，預設為此原則。 它不會產生任何原則秘訣給使用者，但是會產生警示事件，也會觸發「低嚴重性」電子郵件至系統管理員 (新增于原則) 中。 管理員可以透過登入規範中心，查看活動並編輯原則詳細資料。

系統管理員可以在「 [規範中心](https://compliance.microsoft.com/compliancesettings) 」 > 資料遺失防護原則」頁面中查看此原則。


> [!div class="mx-imgBorder"]
> ![預設團隊 DLP 原則](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>編輯或刪除預設原則

若要 [編輯預設原則以取得較佳效能，或將其刪除](create-test-tune-dlp-policy.md#tune-a-dlp-policy)，只需使用具有 **DLP 合規性管理** 許可權的帳戶。 如需詳細資訊，請參閱 [許可權](create-test-tune-dlp-policy.md#permissions)。

