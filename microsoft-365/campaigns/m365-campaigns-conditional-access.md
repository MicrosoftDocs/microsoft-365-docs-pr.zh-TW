---
title: 開啟安全性預設值
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
description: 瞭解安全性預設如何協助您提供預先設定的安全性設定，以保護您的組織免受身分識別相關的攻擊。
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398288"
---
# <a name="turn-on-security-defaults"></a>開啟安全性預設值

安全性預設值可提供 Microsoft 代表組織所管理的預先設定安全性設定，協助保護您的組織免受身分識別相關的攻擊。 這些設定包括針對所有系統管理員和使用者帳戶啟用多重要素驗證 (MFA) 。 對大多數的組織而言，安全性預設值提供好的額外登入安全性。

如需安全性預設值及其強制原則的詳細資訊，請參閱 [安全性預設值為何？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果您的訂閱是在10月22日2019（或後）完成，則會自動啟用安全性預設值，您 &mdash; 應該檢查您的設定以確認。

若要在 Azure Active Directory (Azure AD) 中啟用安全性預設值，或查看是否已啟用這些預設值：

1. 使用全域系統管理員認證登入<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>。

2. 在左窗格中，選取 [**全部顯示]，** 然後在 [系統 **管理中心**] 底下，選取 [ **Azure Active Directory**]。

3. 在 **Azure Active Directory 系統管理中心** 的左窗格中，選取 [ **Azure Active Directory**]。

4. 從儀表板的左側功能表中，選取 [ **管理** ] 區段中的 [ **屬性**]。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Azure Active Directory 系統管理中心的螢幕擷取畫面，顯示內容功能表項目目的位置。":::

5. 在 [ **屬性** ] 頁面的底部，選取 [ **管理安全性預設值**]。

6. 在右窗格中，您將會看到 [ **啟用安全性預設值** ] 設定。 如果選取 **[是]** ，則安全性預設值已啟用，不需要進一步的動作。 如果目前未啟用安全性預設值，請選取 **[是]** 加以啟用，然後選取 [ **儲存**]。

> [!NOTE]
> 如果您已使用條件式存取原則，則必須在使用安全性預設值之前將其關閉。
>
> 您可以使用安全性預設值或條件式存取原則，但不能同時使用這兩種原則。

## <a name="consider-using-conditional-access"></a>考慮使用條件式存取

如果您的組織有複雜的安全性需求，或需要更細微地控制安全性原則，則應該考慮使用條件式存取，而不是安全性預設值，以取得類似或更高的安全性狀況。 

條件式存取可讓您建立及定義回應登入事件並在使用者獲准存取應用程式或服務之前要求其他動作的原則。 條件式存取原則可以細微且特定，可讓使用者在任何時刻和何地都能獲得生產力，但同時也會保護您的組織。

安全性預設值可供所有客戶使用，而條件式存取需要授權執行下列其中一個計畫：

- Azure Active Directory 進階版 P1 或 P2
- Microsoft 365 商務進階版
- Microsoft 365 E3 或 E5
- Enterprise行動 & 安全性 E3 或 E5

如果您想要使用條件式存取來設定與安全性預設啟用的原則同等的原則，請參閱下列逐步指南：

- [要求系統管理員使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Azure 管理需要 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [封鎖舊版驗證](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [要求所有使用者使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [需要 azure ad MFA 註冊](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)-需要 azure ad 身分識別保護，也就是 Azure Active Directory 進階版 P2 的一部分

若要深入瞭解條件式存取，請參閱 [什麼是條件式存取？](/azure/active-directory/conditional-access/overview) 如需建立條件式存取原則的詳細資訊，請參閱 [建立條件式存取原則](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。

> [!NOTE]
> 如果您有提供條件式存取的計畫或授權，但尚未建立任何條件式存取原則，您可以使用安全性預設值。 不過，您必須先關閉安全性預設值，才能使用條件式存取原則。
