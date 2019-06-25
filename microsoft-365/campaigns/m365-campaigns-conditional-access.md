---
title: 設定條件式存取原則
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
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何要求 MFA 和設定 Microsoft 365 商務的條件式存取原則。
ms.openlocfilehash: 08e9365e8aad37e2412a6d739b41f2328c1aa277
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183256"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>需要多重要素驗證, 並設定條件式存取原則

您可以使用多重要素驗證和條件式存取原則來保護您的資料存取。 這些新增了大量額外的安全性。 Microsoft 提供一組適用于所有客戶的基準條件式存取原則。 基準原則是一組預先定義的原則, 可協助保護組織不受許多常見攻擊。 這些常見攻擊可能包括密碼噴塗、重新顯示和網路釣魚。

這些原則需要系統管理員和使用者在符合特定條件時輸入第二種形式的驗證 (稱為「多重要素驗證」或「MFA」)。 例如, 如果您組織中的使用者嘗試從不同的國家或從未知的裝置登入 Microsoft 365, 則可能會將登入視為危險。 使用者必須提供一種額外的驗證形式 (例如指紋或程式碼) 來證明其身分識別。 

目前的基準原則包括下列各項:
- 在 Microsoft 365 系統管理中心設定:
    - **需要**對系統管理員進行 MFA-對於最具特權的系統管理員角色 (包括全域管理員), 需要多重要素驗證。
    - 使用者**保護**—只有當登入有危險時, 才需要使用者的多重要素驗證。 
- 在 Azure Active Directory 入口網站中設定:
    - **封鎖舊版驗證**-較舊的用戶端應用程式和部分新的應用程式不會使用較新、更安全的驗證通訊協定。 這些較舊的應用程式可以略過條件式存取原則, 並對您的環境進行未經授權的存取。 此原則會封鎖不支援條件式存取的用戶端存取權。 
    - **需要 MFA For Service management** --需要多重要素驗證來存取管理工具, 包括 Azure 入口網站 (您設定基準原則)。 

Microsoft 建議您啟用所有的基準原則。 啟用這些原則之後, 系統會提示系統管理員和使用者註冊 Azure 多重要素驗證。

如需這些原則的詳細資訊, 請參閱[何謂基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="require-mfa"></a>需要 MFA

若要要求所有使用者使用第二種 ID 形式登入:

1. 移至系統管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , 然後選擇 [**設定**]。

2. 在 [安裝程式] 頁面上, 選擇 [**建立登入更安全**的卡] 中的 [ **View** ]。


    ![請登入更安全的卡。](media/setupmfa.png)
3. 在 [啟用登入更安全] 頁面上, 選擇 [**開始**]。
 
4. 在 [強化登入安全性] 窗格上, 選取 [**要求系統管理員多重要素驗證**] 旁的核取方塊, 並**要求使用者註冊多重要素驗證, 並在偵測到風險時封鎖存取權**。
    請務必從 [**尋找使用者**] 方塊中的 MFA 需求排除[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或「中斷玻璃」系統管理帳戶。
    
    ![增強 [內接安全性] 頁面。](media/requiremfa.png)

5. 選擇頁面底部的 [**建立原則**]。

## <a name="set-up-baseline-policies"></a>設定基準原則

1. 移至[azure 入口網站](https://portal.azure.com), 然後流覽至**azure Active Directory** \> **條件式存取**。
    
    基準原則會列在頁面上, 您可以在完成[需要 mfa](#require-mfa)的步驟之後, 看到 [需要 mfa 的系統管理員] 和 [使用者保護] 已啟用。

    ![列出條件式存取的基準原則的頁面。](media/casettings.png)
2. 請參閱每個原則的下列特定指示:

    - [需要對系統管理員進行 MFA](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [使用者需要 MFA](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [封鎖舊版驗證](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [需要 MFA 來進行服務管理](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以設定額外的原則, 例如要求核准的用戶端應用程式。 如需詳細資訊, 請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。
