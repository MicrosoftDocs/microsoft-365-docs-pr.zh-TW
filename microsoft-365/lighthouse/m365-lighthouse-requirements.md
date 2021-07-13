---
title: Microsoft 365 Lighthouse 的需求
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) ，取得 Microsoft 365 Lighthouse 使用的需求清單。
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395073"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse 的需求

> [!NOTE]
> 本文所述的功能都是在預覽中進行變更，而且只有符合本文所列需求的合作夥伴才能使用。 如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse 是協助受管理的服務提供者 (MSPs) 安全性及管理裝置、資料和使用者規模，以供小型和中型企業 (SMB) 客戶使用的系統管理員入口網站。  

MSPs 必須在雲端解決方案提供者 (CSP) 程式中註冊，以供間接轉銷商或直銷者使用 Microsoft 365 Lighthouse。  

此外，每個 MSP 客戶租使用者必須符合下列需求，才能使用 Microsoft 365 Lighthouse： 
 
- 已委派的系統管理員許可權 (MSP 的)  
- 至少一個 Microsoft 365 商務進階版授權 
- 授權的使用者少於500個  

## <a name="requirements-for-enablingdevice-management"></a>啟用裝置管理的需求   

若要在裝置管理頁面上查看客戶租使用者裝置，MSP 必須執行下列作業：    

- 在 Microsoft 端點管理員 (MEM) 中登記所有客戶裝置。如需詳細資訊，請參閱[在 Microsoft Intune 中註冊裝置](/mem/intune/enrollment/)。
- 將規範原則指派給所有客戶裝置。如需詳細資訊，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。 

## <a name="requirements-for-enabling-usermanagement"></a>啟用使用者管理的需求 

若要讓客戶資料顯示在使用者管理頁面（包括危險的使用者、多因素驗證及密碼重設）的報表上，客戶租使用者必須具有 Azure Active Directory 進階版 P1 或更新版本的授權。 Microsoft 365 商務進階版附帶 Azure AD Premium P1。   

## <a name="requirements-for-enablingthreat-management"></a>啟用威脅管理的需求 

若要在威脅管理頁面上查看客戶承租人裝置和威脅，您必須在 Microsoft 端點管理員 (MEM 中登記所有客戶租使用者裝置，並執行 Microsoft Defender 防毒軟體以加以保護) 。  

如需詳細資訊，請參閱[在 Microsoft Intune 中註冊裝置](/mem/intune/enrollment/)。  

Microsoft Defender 防毒軟體是 Windows 作業系統的一部分，且預設會在執行 Windows 10 的裝置上啟用。  

> [!NOTE] 
> 如果您使用非 Microsoft 防病毒方案，而不是 Microsoft Defender 防毒軟體，則 Microsoft Defender 防毒軟體會自動停用。 當您卸載非 Microsoft 防病毒解決方案時，會自動啟用 Microsoft Defender 防毒軟體，以保護您的 Windows 裝置免受威脅。    

## <a name="related-content"></a>相關內容   

[設定 Microsoft 365 Lighthouse 入口網站安全性](m365-lighthouse-configure-portal-security.md) (文章) \
[Microsoft 365 Lighthouse 裝置符合性頁面概述](m365-lighthouse-device-compliance-page-overview.md) (文章) \
[Microsoft 365 Lighthouse 使用者] 頁面概述](m365-lighthouse-users-page-overview.md) (文章) \
[Microsoft 365 Lighthouse 威脅管理頁面概述](m365-lighthouse-threat-management-page-overview.md) (文章) \
[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml)   (篇文章) 

