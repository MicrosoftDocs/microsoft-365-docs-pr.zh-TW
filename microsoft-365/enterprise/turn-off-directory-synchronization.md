---
title: 關閉 Microsoft 365 的目錄同步處理
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
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: 在本文中，尋找使用 PowerShell 關閉 Microsoft 365 的目錄同步處理的資訊。
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445705"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>關閉 Microsoft 365 的目錄同步處理
您可以使用 PowerShell 關閉目錄同步處理，並將同步處理的使用者轉換為僅限雲端。 不過，不建議您關閉目錄同步處理做為疑難排解步驟。 如果您需要協助進行目錄同步處理，請參閱[修正 Microsoft 365 文章的目錄同步處理問題](fix-problems-with-directory-synchronization.md)。 
  
如有需要，[請聯絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)商務產品的支援人員。
  
## <a name="turn-off-directory-synchronization"></a>關閉目錄同步處理  
若要關閉目錄同步處理：
  
1. 首先，安裝必要的軟體，並聯機至您的 Microsoft 365 訂閱。 如需相關指示，請參閱[Windows PowerShell Microsoft Azure Active Directory 模組的連線](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
    
2. 使用 [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) 停用目錄同步處理： 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>如果您使用此命令，您必須等候72小時，您才能重新開啟目錄同步處理。
>
