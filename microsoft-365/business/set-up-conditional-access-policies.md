---
title: 設定 Microsoft 365 行銷活動的條件式存取原則
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何為 Microsoft 365 行銷活動設定條件式存取原則。
ms.openlocfilehash: 1ef90bd77da43ded624d85cef9c7a33beec74345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064596"
---
# <a name="set-up-conditional-access-policies"></a>設定條件式存取原則

[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則增加大量額外的安全性。 Microsoft 對於所有客戶提供一組建議的比較基準條件式存取原則。 [比較基準原則是一組預先定義的原則，以協助保護組織免受許多常見的攻擊。 密碼噴灑、 重新顯示和網路釣魚，可以包含這些常見的攻擊。

這些原則需要系統管理員和使用者輸入驗證 （稱為多重要素驗證] 或 [MFA） 第二個表單時符合特定條件。 例如，如果使用者從不同的國家/地區登入，登入小可能會被視為風險，使用者必須提供其他形式的驗證。 

目前，基準原則包括下列：
- **系統管理員需要 MFA** &ndash;最小權限的系統管理員角色，包括全域系統管理員需要多重要素驗證。
- **使用者保護**&ndash;需要多重要素驗證的使用者，只有當時，登入風險。 
- **封鎖舊版驗證**&ndash;較舊的用戶端應用程式和一些新的應用程式不使用較新、 更安全的驗證通訊協定。 這些較舊的應用程式可以略過條件式存取原則，且未經授權存取您的環境。 從用戶端不支援條件式存取此原則封鎖存取。 
- **需要 MFA 服務管理的**&ndash;需要多重要素驗證管理工具]，包括 （在您設定基準原則） 的 Azure 入口網站的存取。 

Microsoft 建議您啟用所有的這些基準原則。 啟用這些原則之後，系統管理員和使用者將會提示註冊為 Azure Multii 雙因素驗證。

如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="set-up-baseline-policies"></a>[比較基準原則設定

1. 移至[Azure 入口網站](https://portal.azure.com)，然後再瀏覽至 [ **Azure Active Directory** \> **條件式存取**。
    
    [比較基準原則會列在 [] 頁面上。 <br/> <br/>
    ![] 頁面會列出基準條件式存取原則。](../media/baslinepolicies.png)
1. 請參閱下列的特定指示，針對每個原則：

  - [系統管理員需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [需要 MFA 的服務管理](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以設定許多額外的原則，例如需要核准的用戶端應用程式。 如需詳細資訊，請參閱[條件式存取文件](https://docs.microsoft.com/azure/active-directory/conditional-access/)。
