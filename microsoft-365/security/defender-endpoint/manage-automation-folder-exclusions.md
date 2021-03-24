---
title: 管理自動化資料夾排除
description: 新增「自動化」資料夾排除，以控制從自動調查中排除的檔案。
keywords: 管理，自動化，排除，封鎖，乾淨，惡意
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
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057340"
---
# <a name="manage-automation-folder-exclusions"></a>管理自動化資料夾排除 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

自動化資料夾排除可讓您指定自動調查將略過的資料夾。 

您可以控制下列您想略過之資料夾的屬性：
- 資料夾 
- 檔案副檔名
- 檔案名稱


**資料夾**<br>
您可以指定要略過的資料夾及其子資料夾。 


>[!NOTE]
>此時，您可以使用萬用字元來排除尚未支援的目錄下的檔案。 


**延伸模組**<br>
您可以指定要排除在特定目錄中的副檔名。 這種擴充功能可防止攻擊者使用排除的資料夾來隱藏利用漏洞。 副檔名明確定義要忽略的檔案。 

**檔案名稱**<br>
您可以指定要在特定目錄中排除的檔案名。 這些名稱是防止攻擊者使用排除的資料夾來隱藏利用漏洞的方式。 名稱明確定義要忽略的檔案。 



## <a name="add-an-automation-folder-exclusion"></a>新增自動化資料夾排除
1. 在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。  

2. 按一下 [ **新增資料夾排除**]。  

3. 輸入資料夾詳細資料：

    - 資料夾
    - Extensions
    - 檔案名稱
    - 描述
    

4. 按一下 **[儲存]**。

>[!NOTE]
> 收集或檢查排除的檔案的即時回應命令會失敗，錯誤如下：「File 已排除」。 此外，自動調查會忽略排除的專案。

## <a name="edit-an-automation-folder-exclusion"></a>編輯自動化資料夾排除 
1. 在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。 

2. 在資料夾排除上按一下 [ **編輯** ]。  

3. 更新規則的詳細資料，然後按一下 [ **儲存**]。

## <a name="remove-an-automation-folder-exclusion"></a>移除自動化資料夾排除 
1. 在功能窗格中，選取 [**設定**  >  **自動化資料夾排除**]。  
2. 按一下 [ **移除排除**]。 


## <a name="related-topics"></a>相關主題
- [管理自動化的允許/封鎖清單](manage-indicators.md)
- [管理自動化檔上傳](manage-automation-file-uploads.md)
