---
title: 管理指示器
ms.reviewer: ''
description: 管理檔雜湊、IP 位址、URLs 或網域的指標，以定義實體的偵測、預防和排除。
keywords: import，標記，list，ioc，csv，管理，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060115"
---
# <a name="manage-indicators"></a>管理指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. 在功能窗格中，選取 [**設定**  >  **指示器**]。

2. 選取您想要管理之實體類型的索引標籤。  

3. 更新指示器的詳細資料，然後按一下 [ **儲存** ]，如果您想要從清單中移除該實體，請按一下 [ **刪除** ] 按鈕。

## <a name="import-a-list-of-iocs"></a>匯入 IoCs 清單

您也可以選擇上載 CSV 檔，以定義指示器的屬性、要採取的動作和其他詳細資料。

下載範例 CSV，以瞭解支援的欄屬性。

1. 在功能窗格中，選取 [**設定**  >  **指示器**]。

2. 選取您要匯入指示器之實體類型的索引標籤。

3. 選取 [匯 **入**  >  **選擇** 檔案]。 

4. 選取 [匯入]。 針對您想要匯入的所有檔案執行這項操作。 

5. 選取 **[完成]**。

下表顯示支援的參數。

參數 | 類型    |   描述
:---|:---|:---
indicatorType | Enum | 指標的類型。 可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。 **Required**
indicatorValue | 字串 | [指示器](ti-indicator.md)實體的身分識別。 **Required**
action | Enum | 將在組織中探索指示器時所採取的動作。 可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。 **Required**
標題 | String | 指示器警示標題。 **Required**
描述 | 字串 |  標記的描述。 **Required**
expirationTime | DateTimeOffset | 指示器的到期時間，格式為 YYYY-MM-DDTHH： MM： SS。0Z。 **Optional**
嚴重性 | Enum | 指標的嚴重性。 可能的值為：「資訊」、「低」、「中」和「高」。 **Optional**
recommendedActions | 字串 | TI 指標警示建議的動作。 **Optional**
rbacGroupNames | 字串 | 標記將套用到的 RBAC 群組名稱的以逗號分隔的清單。 **Optional**
類別 | 字串 | 警示的類別。 範例包括：執行和憑證存取。 **Optional**
mitretechniques| 字串 | MITRE 以逗號分隔)  (的技術代碼/識別碼。 如需詳細資訊，請參閱 [Enterprise 戰術](https://attack.mitre.org/tactics/enterprise/)。 **選用** 建議您在 MITRE 技術時新增類別中的值。

如需詳細資訊，請參閱 [Microsoft Defender 的端點警示類別現在已與 MITRE ATT&CK！](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)。


## <a name="see-also"></a>另請參閱
- [建立指示器](manage-indicators.md)
- [建立檔案的指示器](indicator-file.md)
- [為 IPs 和 URLs/網域建立指示器](indicator-ip-domain.md)
- [根據憑證建立指示器](indicator-certificates.md)
