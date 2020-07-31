---
title: 設定條件式存取原則
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
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何要求 MFA 和設定適用于商務用 Microsoft 365 的條件式存取原則。
ms.openlocfilehash: 917fb52eb5034c3dda28c277b9e86e04db6cac62
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527195"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>需要多重要素驗證並設定條件式存取原則

您可以使用多重要素驗證和條件式存取原則來保護您的資料存取權。 這會增加大量額外的安全性。 Microsoft 提供一組為所有客戶建議的基準條件式存取原則。 基準原則是一組預先定義的原則，可協助保護組織不受許多常見的攻擊。 這些常見的攻擊可能包括密碼噴塗、重新顯示和網路釣魚。

這些原則要求系統管理員和使用者輸入第二種形式的驗證（稱為多重要素驗證，或 MFA）符合某些條件。 例如，如果您組織中的使用者企圖從不同的國家/地區或從未知的裝置登入 Microsoft 365，該登入可能會被視為危險。 使用者必須提供另一種形式的驗證（例如，指紋或程式碼），以證明其身分識別。 

目前的基準原則包括下列各項：
- 在 Microsoft 365 系統管理中心中設定：
    - **需要對系統管理員進行 MFA** -針對最具特權的系統管理員角色（包括全域管理員），需要多重要素驗證。
    - 使用者**保護**：只有在登入危險時，才需要使用者的多重要素驗證。 
- 在 Azure Active Directory 入口網站中設定：
    - **封鎖舊版驗證**-舊版用戶端應用程式和某些新的應用程式不會使用較新、更安全的驗證通訊協定。 這些繼承應用程式可略過條件式存取原則，並對您的環境進行未授權的存取。 這個原則會封鎖不支援條件式存取之用戶端的存取權。 
    - **需要 MFA For Service management** -需要多重要素驗證以存取管理工具，包括 Azure 入口網站（您設定基準原則的位置）。 

Microsoft 建議您啟用所有的基準原則。 啟用這些原則之後，系統會提示系統管理員和使用者註冊 Azure Multi-Factor 驗證。

如需這些原則的詳細資訊，請參閱[什麼是基準原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="require-mfa"></a>需要 MFA

若要要求所有使用者使用第二種形式的 ID: 登入

1. 移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然後選擇 [**設定**]。

2. 在 [安裝] 頁面上，選擇 [**建立更安全**的智慧卡] 中的 [**查看**]。


    ![讓登入更安全的卡片。](../media/setupmfa.png)
3. 在 [使登入更安全] 頁面上，選擇 [**入門**]。
 
4. 在 [強化登入安全性] 窗格中，選取 [**需要系統管理員的多重要素驗證**] 旁的核取方塊，並**要求使用者註冊多重要素驗證，並在偵測到風險時，封鎖存取權**。
    請務必在 [**尋找使用者**] 方塊中，從 MFA 要求中排除[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或「中斷玻璃」管理帳戶。
    
    ![增強內建安全性頁面。](../media/requiremfa.png)

5. 選擇頁面底部的 [**建立原則**]。

## <a name="set-up-baseline-policies"></a>設定基準原則

1. 移至[azure 入口網站](https://portal.azure.com)，然後流覽至 [ **azure Active Directory** \> **條件式存取**]。
    
    基準原則會列在頁面上，您可以看到在您完成[要求 mfa](#require-mfa)中的步驟後，必須啟用**mfa 的系統管理員**和**使用者保護**。

    ![列出條件式存取之基準原則的頁面。](../media/casettings.png)
2. 請參閱下列每個原則的特定指示：

    - [需要對系統管理員進行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [需要 MFA 進行服務管理](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以設定額外的原則，例如要求核准的用戶端應用程式。 如需詳細資訊，請參閱[條件式存取檔](https://docs.microsoft.com/azure/active-directory/conditional-access/)。
