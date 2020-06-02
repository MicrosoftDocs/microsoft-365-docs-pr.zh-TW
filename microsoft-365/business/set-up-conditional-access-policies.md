---
title: 設定 Microsoft 365 活動的條件式存取原則
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何設定 Microsoft 365 活動的條件式存取原則，以增加大量額外的安全性。
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470640"
---
# <a name="set-up-conditional-access-policies"></a>設定條件式存取原則

本文適用于 Microsoft 365 商務版 Premium。

[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則會增加大量額外的安全性。 Microsoft 提供一組為所有客戶建議的基準條件式存取原則。 基準原則是一組預先定義的原則，可協助保護組織不受許多常見的攻擊。 這些常見的攻擊可能包括密碼噴塗、重新顯示和網路釣魚。

這些原則要求系統管理員和使用者在符合特定條件時，輸入第二種形式的驗證（稱為多重驗證或 MFA）。 例如，如果使用者從不同的國家/地區登入，則可能會認為登入是危險的，而且使用者必須提供其他形式的驗證。 

目前的基準原則包括下列各項：
- **需要對系統管理員** &ndash; 進行 MFA需要對最具許可權的系統管理員角色（包括全域管理員）進行多重要素驗證。
- **使用者保護** &ndash;只有在登入危險時，才需要使用者的多重要素驗證。 
- **封鎖舊版驗證** &ndash;舊版用戶端應用程式和某些新的應用程式不會使用較新、更安全的驗證通訊協定。 這些繼承應用程式可略過條件式存取原則，並對您的環境進行未授權的存取。 這個原則會封鎖不支援條件式存取之用戶端的存取權。 
- **需要 MFA 進行服務管理** &ndash;需要多重要素驗證，以存取管理工具，包含 Azure 入口網站（您設定基準原則的位置）。 

Microsoft 建議您啟用所有的基準原則。 啟用這些原則之後，系統會提示系統管理員和使用者註冊 Azure Multii 要素驗證。

如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="set-up-baseline-policies"></a>設定基準原則

1. 移至[azure 入口網站](https://portal.azure.com)，然後流覽至 [ **azure Active Directory** \> **條件式存取**]。
    
    基準原則會列在頁面上。 <br/> <br/>
    ![列出條件式存取之基準原則的頁面。](../media/baslinepolicies.png)
1. 請參閱下列每個原則的特定指示：

  - [需要對系統管理員進行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [需要 MFA 進行服務管理](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以設定許多額外的原則，例如要求核准的用戶端應用程式。 如需詳細資訊，請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。
