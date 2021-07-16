---
title: Microsoft Teams 中的多地理位置功能
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: 深入瞭解 Teams 如何搭配 Microsoft 365 多地理位置運作。
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453522"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Microsoft Teams 中的多地理位置功能

Teams 中的多地理位置功能可讓 Teams 聊天資料儲存在靜止的指定地理位置。 聊天室資料是由聊天訊息所組成，包括私人郵件、通道訊息和交談中使用的影像。

Teams 會使用慣用的資料位置 (PDL) 使用者和群組，以決定儲存資料的位置。 如果 PDL 未設定或無效，則會將資料儲存在租使用者的中央位置。

## <a name="user-chat"></a>使用者聊天

使用者聊天包括一對一、一對多及私人會議訊息。。

當建立新的使用者時，Teams 會讀取使用者的 PDL，並將其所有聊天資料儲存在該地理位置。

針對現有使用者，如果系統管理員為使用者新增或修改 PDL，該使用者的聊天資料會新增至遷移佇列中，以移至指定的地理位置。

「一對一」或「一對多」聊天的儲存位置是根據建立聊天的人員的 PDL。 如果使用者的 PDL 變更，聊天會遷移至新的地理位置。 會議聊天的儲存位置是以會議召集人的 PDL 為基礎。

若要尋找使用者 Teams 資料的目前位置，請[連接至 Teams PowerShell](/powershell/module/teams/connect-microsoftteams)並執行下列命令：

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>通道郵件

每個 Microsoft 365 群組都有一個慣用資料位置 (PDL) ，表示要儲存相關資料的地理位置。 Teams 會使用隨每個小組相關聯之群組的 PDL，來決定要為該小組儲存通道訊息資料的位置。 這包括專用通道，以及通道會議中所發生的聊天。

當使用者建立新的小組時，該使用者的 pdl 會決定指派給 Microsoft 365 群組的 pdl。 Group PDL 會決定團隊資料的儲存位置。 如果該使用者的 PDL 稍後變更，則不會變更群組的 PDL。

針對現有的小組，如果系統管理員為支援小組的 Microsoft 365 群組新增或修改 PDL，該小組的通道郵件資料會新增到遷移佇列中，以移至指定的地理位置。

變更 Microsoft 365 群組的 PDL 會將 Teams 資料排入佇列，以遷移至選取的位置。 不過，這不會自動遷移 SharePoint 的網站或與群組相關聯的檔案。 您必須在[將 SharePoint 網站移至不同的地理位置](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)時，依照下列程式，分別移動網站。 請務必執行這兩個步驟，以避免針對不同位置的一個群組 Teams 資料和 SharePoint 資料。

若要尋找小組資料的目前位置，請[連接至 Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ，並執行下列命令：

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>使用者體驗

Teams多地理位置對使用者而言是無縫的。 一旦您變更使用者或群組的 PDL，對應的資料就會排隊進行遷移，而且即使在進行遷移時，也會自動進行遷移，但不會影響使用者或其 Teams 用戶端。

## <a name="see-also"></a>請參閱

[Microsoft 365 多地理位置租用戶組態](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[管理多地理位置環境](administering-a-multi-geo-environment.md)

[管理多地理位置環境中的 Exchange Online 信箱](administering-exchange-online-multi-geo.md)
