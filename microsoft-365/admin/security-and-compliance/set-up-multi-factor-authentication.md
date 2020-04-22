---
title: 設定使用者的多重要素驗證
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
description: 瞭解如何使用安全性預設值為使用者設定多重要素驗證。
monikerRange: o365-worldwide
ms.openlocfilehash: 1000689794b8b5471efa898e731fd75a0e5a8cce
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665629"
---
# <a name="set-up-multi-factor-authentication"></a>設定多重要素驗證
  
> [!IMPORTANT]
> 如果您在2019年10月21日後購買訂閱或試用版，且意外提示您進行多重要素驗證（MFA），則會自動為您的訂閱啟用[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

每個新的 Microsoft 365 訂閱都會自動開啟[安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 這表示每位使用者都必須設定多重要素驗證（MFA），並在其行動裝置上安裝 Microsoft 驗證應用程式。 如需詳細資訊，請參閱[Set UP MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。

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

將會在需要時向所有其他使用者要求執行其他驗證。

> [!NOTE]
> 您必須是全域系統管理員才能設定或修改 MFA <br><br>
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

如果您先前已設定具有基準原則的 MFA，[您必須將其關閉以開啟安全性預設值](#move-from-baseline-policies-to-security-defaults)。 不過，如果您有 Microsoft 365 商務或您的訂閱包含[Azure Active Directory Premium P1 或 Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)，您也可以設定[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)原則。 若要使用條件式存取原則，您必須確定已停用安全性預設值，且已啟用[新式驗證](#enable-modern-authentication-for-your-organization)。

> [!TIP]
> 若要向您的使用者說明如何設定 Microsoft 驗證器應用程式，請參閱[使用 Microsoft 驗證與 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)。

## <a name="manage-security-defaults"></a>管理安全性預設

1. 使用全域系統管理員認證登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。
2. 移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3. 在頁面底部，選擇 [管理安全性預設]****。
4. 選擇 **[是]** 啟用安全性預設值，並選擇 [**否**] 以停用安全性預設值，然後選擇 [**儲存**]。

## <a name="move-from-baseline-policies-to-security-defaults"></a>從基準原則移至安全性預設

1. 移至 [[條件式存取原則] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2. 選擇 [**開啟**的每一個基準原則]，並將 [**啟用原則**] 設定為 [**關閉**]。
3. 移至 [ [Azure Active Directory-屬性] 頁面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4. 在頁面底部，選擇 [**管理安全性預設值**]，然後在 [**啟用安全性預設**值] 窗格中，設定 [**啟用安全性預設值**] 切換為 **[是]**，然後選擇 [**儲存**]。 

## <a name="enable-modern-authentication-for-your-organization"></a>為您的組織啟用新式驗證

所有 Office 2016 用戶端應用程式都透過使用 Active Directory Authentication Library (ADAL) 來支援 MFA。 這表示 Office 2016 用戶端不需要 App 密碼。 不過，您必須確定已啟用 ADAL 或新式驗證的 Microsoft 365 訂閱。

1. 若要啟用新式驗證，請從[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)選取 [設定]**** \> [設定]****，然後在 [服務]**** 索引標籤中，從清單選擇 [新式驗證]****。

2. 在 [**新式驗證**] 面板中，選取 [**啟用新式驗證（建議）** ] 方塊，然後選擇 [**儲存變更**]。 

    ![已勾選啟用核取方塊的新式驗證面板。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 到2017年8月為止，所有包含商務用 Skype online 和 Exchange online 的新 Microsoft 365 訂閱預設都會啟用新式驗證。 若要檢查您的商務用 Skype Online 的新式驗證狀態，您可以使用商務用 Skype Online PowerShell 搭配全域系統管理員認證。 執行 Get-CsOAuthConfiguration 以檢查 -ClientADALAuthOverride 的輸出。 如果 -ClientADALAuthOverride 是 'Allowed'，新式驗證即已開啟。
若要檢查您的 Exchange Online 的 MA 狀態，請造訪[啟用 Exchange Online 中的新式驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

## <a name="related-articles"></a>相關文章

[保護商務用 Microsoft 365 方案的十大方式](secure-your-business-data.md)

[為 Windows 裝置上的 Office 2013 啟用新式驗證](enable-modern-authentication.md)
