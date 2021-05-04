---
title: 了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)
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
description: 深入瞭解 Microsoft Teams 中的預設資料遺失防護原則
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114141"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)

[資料遺失防護](dlp-learn-about-dlp.md)功能已擴充，可納入 Microsoft Teams 聊天及通道訊息，包括私人通道郵件。 在此版本中，我們會為第一次客戶建立「合規性中心」的預設 DLP 原則。

## <a name="applies-to"></a>適用於

以下列一或多個授權授權的任何租使用者，且具有作用中 Teams 使用者
 
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
> ![預設 Teams DLP 原則](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>編輯或刪除預設原則

若要 [編輯預設原則以取得較佳效能，或將其刪除](create-test-tune-dlp-policy.md#tune-a-dlp-policy)，只需使用具有 **DLP 合規性管理** 許可權的帳戶。 如需詳細資訊，請參閱 [許可權](create-test-tune-dlp-policy.md#permissions)。

