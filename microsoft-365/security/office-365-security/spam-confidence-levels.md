---
title: 垃圾郵件信賴等級
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 當電子郵件通過垃圾郵件篩選會指派的垃圾郵件計分。 該分數是對應至個別的垃圾郵件信賴等級 (SCL) 分級，並在 X 標頭中加上戳記。 服務採取動作時取決於垃圾郵件信賴解譯的 SCL 分級的郵件。 下表顯示由篩選以及對每個分級的輸入郵件採取的預設動作如何解譯不同 SCL 分級。
ms.openlocfilehash: 93b3886e1128024f3f7f2a844e2ed603e27d9b2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078241"
---
# <a name="spam-confidence-levels"></a>垃圾郵件信賴等級

當電子郵件通過垃圾郵件篩選會指派的垃圾郵件計分。 該分數是對應至個別的垃圾郵件信賴等級 (SCL) 分級，並在 X 標頭中加上戳記。 服務採取動作時取決於垃圾郵件信賴解譯的 SCL 分級的郵件。 下表顯示由篩選以及對每個分級的輸入郵件採取的預設動作如何解譯不同 SCL 分級。
  
|**SCL 分級**|**垃圾郵件信賴解譯**|**預設動作**|
|:-----|:-----|:-----|
|-1|非垃圾郵件來自 [安全寄件者，安全的收件者或安全列 （信任的合作夥伴） 的 IP 位址。|將郵件傳遞至收件者的收件匣。|
|0、1|非垃圾郵件因為已掃描郵件，並判定為初始狀態。|將郵件傳遞至收件者的收件匣。|
|5、 6|垃圾郵件|將郵件傳遞至收件者的垃圾郵件] 資料夾。|
|7、 8、 9|高信賴度的垃圾郵件|將郵件傳遞至收件者的垃圾郵件] 資料夾。|
   
> [!TIP]
> SCL 分級的 2、 3、 4、 7 和 8 不是由服務設定。 SCL 分級為 5 或 6 會被視為可疑的垃圾郵件，也就是較不一定要大於 SCL 分級為 9，這會被視為特定垃圾郵件的垃圾郵件。 垃圾郵件和高信賴度垃圾郵件的不同動作可以透過您在 Exchange 系統管理中心中的內容篩選原則設定。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 您也可以設定為 > 中所述[來設定垃圾郵件信賴等級 (SCL) 郵件中的使用郵件流程規則](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)使用郵件流程規則 （也稱為傳輸規則），符合特定條件的郵件的 SCL 分級。 如果您使用郵件流程規則來設定的 scl 值為 7、 8 或 9 郵件會被視為高信賴度垃圾郵件。 
  
||
|:-----|
|![LinkedIn Learning 的短圖示](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。|
   

