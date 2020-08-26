---
title: 允許來賓和外部 B2B 存取的身分識別和裝置存取原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述建議的條件式存取和相關原則，以保護來賓和外部使用者的存取。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898101"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>允許來賓和外部 B2B 存取的原則
本文說明如何調整建議的常見身分識別和裝置存取原則，以允許 (來賓和外部使用者 B2B 帳戶存取權) 。 本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。

這些建議適用于保護的 **基準** 層。 不過，您可以根據您對 **機密** 和 **高管制** 保護的需求細微性來調整建議。 

提供 B2B 使用者驗證您的 Azure AD 租使用者的路徑，不會讓這些使用者存取您的整個環境。 B2B 使用者只能存取與其共用的資源 (例如，在條件式存取原則中授與服務內) 的檔案。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>更新共同原則以允許及保護來賓和外部存取 

下圖說明一般身分識別和裝置存取原則，並指出 (包含鉛筆圖示) 要新增或更新以保護來賓和外部存取的原則。 

![保護來賓存取的原則更新摘要](../media/identity-access-ruleset-guest.png)

下表列出您必須更新或建立的原則。 通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。

|保護層級|原則|其他相關資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[需要對來賓和外部使用者永遠進行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|建立此新規則，並將其套用至來賓和外部使用者。 在 [登入風險] 下，將所有選項保留未勾選狀態，永遠強制執行 MFA。|
|        |[當登入風險為*中*或*高*時，需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此規則，以排除來賓和外部使用者。|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此規則，以排除來賓和外部使用者。|

若要在條件式存取規則中包含或排除來賓和外部使用者，請按一下 [包含或排除] 索引標籤，並檢查 **所有來賓和外部使用者**。

![用於排除來賓之控制項的畫面捕獲](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>其他相關資訊

### <a name="guests-vs-external-users"></a>來賓與外部使用者
在 Azure AD 中，來賓和外部使用者皆相同。 這兩種皆為來賓的使用者類型。 來賓使用者 B2B 使用者。

Microsoft 小組會區別來賓使用者與應用程式中的外部使用者，但是在驗證時，這兩個使用者都 B2B 使用者。 如需小組來賓和外部使用者的詳細資訊，請參閱 [啟用使用者的來賓和外部存取](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>需要對來賓和外部使用者永遠進行 MFA
此規則會提示客人在您的租使用者中註冊 MFA，不論他們是否已在其主承租人中為 MFA 註冊。 當存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>從風險型 MFA 排除來賓和外部使用者
雖然組織可以對使用 Identity Protection 的 B2B 使用者強制執行風險原則原則，但由於使用者在其主目錄中的身分識別，對資原始目錄中 B2B 共同作業使用者實施身分識別保護時，有一些限制。 由於這些限制，Microsoft 建議您從以風險為基礎的 MFA 原則中排除來賓使用者，並要求這些使用者永遠使用 MFA。 

如需詳細資訊，請參閱 [B2B 協同作業使用者的身分識別保護限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>從裝置管理排除來賓和外部使用者 
只有一個組織可以管理裝置。 如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。 

## <a name="next-steps"></a>後續步驟

[瞭解如何啟用小組條件式存取](teams-access-policies.md)

