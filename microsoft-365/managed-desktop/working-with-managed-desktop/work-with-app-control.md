---
title: 使用應用程式控制
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430444"
---
# <a name="work-with-app-control"></a>使用應用程式控制

在您的環境中部署應用程式控制後，您和 Microsoft 受管理的桌面作業都有持續的責任。 例如，您可能想要在環境中新增新的應用程式，或新增（或移除）受信任的簽署者。 若要改善安全性，在您將應用程式發行給使用者之前，必須先對所有應用程式進行代碼簽署。 應用程式的發行者詳細資料會包含有關簽署者的資訊。


## <a name="add-a-new-app"></a>新增應用程式

若要新增應用程式，請遵循下列步驟：

1. 將 app 新增至[Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)。
2. 將 app 部署到測試環中的任何裝置。 
3. 根據標準商務程式測試您的應用程式。 
4. 在 [**應用程式和服務 Logs\Microsoft\Windows\AppLocker**] 底下，檢查事件檢視器，尋找任何**8003**或**8006**事件。 這些事件表示應用程式會遭到封鎖。 如需所有應用程式鎖定事件及其意義的詳細資訊，請參閱[Using 事件檢視器 With AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
5. 如果您發現以上任何事件，請使用 Microsoft 受管理的桌面作業開啟簽署者要求。

## <a name="add-or-remove-a-trusted-signer"></a>新增（或移除）信任的簽署者

當您開啟簽章要求時，您必須先提供一些重要的 publisher 詳細資料。 請遵循下列步驟：

1. [收集發行者的詳細資料](#gather-publisher-details)。
2. 使用 Microsoft Managed Desktop Operations 開啟票證以要求籤署者規則，並包含下列詳細資料：  
    - 應用程式名稱 
    - 應用程式版本 
    - 描述 
    - 變更類型（"add" 或 "remove"）  
    - 發行者詳細資料（例如： "O = <publisher name> ，L = <location> ，S = State，C = Country"） 

> [!NOTE]
> 若要移除應用程式的信任，請遵循相同的步驟，但設定要*移除*的**變更類型**。

作業會逐步將原則部署到遵循此排程的部署群組：


|部署群組  |原則類型  |時程  |
|---------|---------|---------|
|測試     |  審計       |  Day 0       |
|名字     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 2 天       |
|廣泛     | Enforced        |  第 3 天       |


您可以在首次部署期間隨時暫停或回退部署。 若要這麼做，請使用 Operations 開啟另一個服務要求。

> [!NOTE]
> 如果您暫停簽章規則的發行，該規則必須在另一個首展開始之前還原或完成。

## <a name="gather-publisher-details"></a>收集發行者詳細資料

若要存取應用程式的發行者資料，請遵循下列步驟：

1. 在已套用稽核模式原則的測試環中，尋找 Microsoft 受管理的桌面裝置。 
2. 嘗試在裝置上安裝應用程式。
3. 開啟該裝置上的事件檢視器。 
4. 在事件檢視器中，流覽至 [**應用程式和服務 Logs\Microsoft\Windows**]，然後選取**AppLocker**。 
5. 尋找任何**8003**或**8006**事件，然後複製事件中的資訊： 
    - 應用程式名稱 
    - 應用程式版本 
    - 描述 
    - 發行者詳細資料（例如： "O = <publisher name> ，L = <location> ，S = State，C = Country"） 
