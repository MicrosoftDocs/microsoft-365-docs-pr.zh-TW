---
title: 在 Microsoft 365 中查看目錄同步處理錯誤
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: 瞭解如何在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤及可能的修正。
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907501"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>在 Microsoft 365 中查看目錄同步處理錯誤

您可以在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤。 只會顯示使用者物件錯誤。 若要使用 PowerShell 查看錯誤，請參閱 [使用 DirSyncProvisioningErrors 識別物件](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)。

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤

若要在 Microsoft 365 系統管理中心中查看任何錯誤：
  
1. 使用全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。 
    
2. 在 **首頁** 上，您會看到 [ **使用者管理** 卡]。 
    
    ![Microsoft 365 系統管理中心中的使用者管理卡](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. 在卡片上，選擇 [ **AZURE AD Connect]** 底下的 [**同步處理錯誤**]，以查看 [**目錄同步處理錯誤**] 頁面上的錯誤。   
    
    ![「目錄同步處理錯誤」頁面的範例](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. 選擇任何錯誤以顯示詳細資料窗格，顯示有關錯誤的資訊，以及如何修正該錯誤的秘訣。

   ![目錄同步處理錯誤詳細資料的範例](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
查看之後，請參閱 [修正 Microsoft 365 目錄同步處理的問題](fix-problems-with-directory-synchronization.md) ，修正任何已識別的問題。