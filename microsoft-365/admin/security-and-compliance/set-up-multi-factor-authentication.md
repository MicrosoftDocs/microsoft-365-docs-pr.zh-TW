---
title: 為 Office 365 使用者設定多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何使用安全性預設來設定 Office 365 使用者的多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 914d01bf2f045c6752aba4f2df3a204c6a21d09c
ms.sourcegitcommit: 4d4d27a49eb258dc560439ca4baf61ebb9c1eff3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2020
ms.locfileid: "43075605"
---
# <a name="set-up-multi-factor-authentication"></a>設定多重要素驗證
  
> [!IMPORTANT]
> 如果您在2019年10月21日之後購買訂閱或試用版，且意外提示您進行 MFA，[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)會自動為您的訂閱啟用。

每個新的商務用 Office 365 或 Microsoft 365 商務版訂閱都會自動開啟安全性預設。 這表示每位使用者都必須設定多重要素驗證 (MFA)，並在其行動裝置上安裝 Authenticator 應用程式。 如需詳細資訊，請參閱[設定 Office 365 的雙步驟驗證](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。  

每次登入時，需要使用下列九個系統管理員角色來執行其他驗證：
- 全域系統管理員
- SharePoint 系統管理員
- Exchange 系統管理員
- 條件式存取系統管理員
- 安全性系統管理員
- 服務台系統管理員或密碼管理員
- 計費管理員
- 使用者管理員
- 驗證管理員

將會在需要時向所有其他使用者要求執行其他驗證。 如需詳細資訊，請參閱[什麼是安全性預設？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> 您必須是 Office 365 全域系統管理員，才能設定或修改多重要素驗證。 <br><br>
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 [試用新的系統管理中心] **** 開關將它開啟。

如果您先前已使用基準原則設定 MFA，[您必須將其關閉並開啟安全性預設](#move-from-baseline-policies-to-security-defaults)。 不過，如果您有 Microsoft 365 商務版或您的訂閱包含 [Azure Active Directory Premium 1 或 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)，您也可以設定[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則。 若要使用條件式存取原則，您必須確定已啟用[新式驗證](#enable-modern-authentication-for-your-organization)。

> [!TIP]
> 若要向使用者說明如何設定 Authenticator 應用程式，請造訪[搭配 Office 365 使用 Microsoft Authenticator](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)。

## <a name="manage-security-defaults"></a>管理安全性預設

1. 使用全域系統管理員認證登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。
2. 移至 [Azure Active Directory 屬性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。

3. 在頁面底部，選擇 [管理安全性預設]****。
4. 選擇 [是]**** 可啟用安全性預設，以及 [否]**** 可停用安全性預設。

## <a name="move-from-baseline-policies-to-security-defaults"></a>從基準原則移至安全性預設

1. 在[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)中選取 [設定]****。

2. 在 [登入與安全性]**** 旁，於 [讓登入更安全]**** 下選取 [檢視]****。

3. 在 [讓登入更安全]**** 下，選取 [管理]****。 

4. 在 [Azure 入口網站條件式存取原則]**** 頁面上，選擇 [開啟]**** 的每個基準原則，然後將它們設定為 [關閉]****。
5. 移至 [Azure Active Directory 屬性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)頁面。
6. 在頁面底部，選擇 [管理安全性預設]****，並在 [啟用安全性預設]**** 窗格中，將 [啟用安全性預設]**** 切換設為 [是]****。 

## <a name="enable-modern-authentication-for-your-organization"></a>為您的組織啟用新式驗證

所有 Office 2016 用戶端應用程式都透過使用 Active Directory Authentication Library (ADAL) 來支援 MFA。 這表示 Office 2016 用戶端不需要 App 密碼。 不過，您必須確認您的 Office 365 訂閱已針對 ADAL 或新式驗證啟用。

1. 若要啟用新式驗證，請從[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)選取 [設定]**** \> [設定]****，然後在 [服務]**** 索引標籤中，從清單選擇 [新式驗證]****。

2. 在 [新式驗證]**** 面板中，勾選 [啟用新式驗證]**** 方塊。 

    ![已勾選啟用核取方塊的新式驗證面板。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 從 2017 年 8 月起，包含商務用 Skype Online 和 Exchange Online 的所有新 Office 365 租用戶，皆會預設啟用新式驗證。 若要檢查您的商務用 Skype Online 的新式驗證狀態，您可以使用商務用 Skype Online PowerShell 搭配全域系統管理員認證。 執行 Get-CsOAuthConfiguration 以檢查 -ClientADALAuthOverride 的輸出。 如果 -ClientADALAuthOverride 是 'Allowed'，新式驗證即已開啟。
若要檢查您的 Exchange Online 的 MA 狀態，請造訪[啟用 Exchange Online 中的新式驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

## <a name="related-articles"></a>相關文章

[保護 Office 365 和 Microsoft 365 商務方案的前 10 個最佳方法](secure-your-business-data.md)

[為 Windows 裝置上的 Office 2013 啟用新式驗證](enable-modern-authentication.md)
