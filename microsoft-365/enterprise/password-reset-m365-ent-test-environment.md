---
title: 適用於 Microsoft 365 測試環境的密碼重設
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的密碼重設。
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921489"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>適用於 Microsoft 365 測試環境的密碼重設

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

Azure Active Directory (Azure AD) 自助密碼重設 (SSPR) 允許使用者重設或解除鎖定其密碼或帳戶。

本文說明如何在 Microsoft 365 測試環境中設定及測試密碼重設。

設定 SSPR 包含三個階段：
- [階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [階段 2：啟用密碼回寫](#phase-2-enable-password-writeback)
- [階段 3：設定及測試密碼重設](#phase-3-configure-and-test-password-reset)
    
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理

首先，依照 [ [密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理] 中的指示進行。 

您產生的設定如下所示：
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此組態包含：
  
- Microsoft 365 E5 試用版或付費訂閱。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。
- Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域同步至 Microsoft 365 訂閱的 Azure AD 租用戶。

## <a name="phase-2-enable-password-writeback"></a>階段 2：啟用密碼回寫

遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。

您必須啟用密碼回寫才能使用密碼重設。
  
## <a name="phase-3-configure-and-test-password-reset"></a>階段 3：設定及測試密碼重設

在此階段中，在 Azure AD 租使用者中透過群組成員資格來設定密碼重設，然後驗證它是否運作正常。

首先，在特定 Azure AD 群組中啟用該帳戶的密碼重設。

1. 從您瀏覽器的私用執行個體開啟 [https://portal.azure.com](https://portal.azure.com)，然後使用全域系統管理員帳戶的認證登入。
2. 在 azure 入口網站中，選取 [ **azure Active Directory**  >  **群組**] [  >  **新增群組**]。
3. 將 [群組類型] 設為 [安全性]、[群組名稱] 設為 [PWReset]，以及將 [成員類型] 設為 [指派]。
4. 選取 [ **成員**]，尋找並選取 [ **使用者 3**]，選取 [ **選取**]，然後選取 [ **建立**]。
5. 關閉 [群組] 窗格。
6. 在 [Azure Active Directory] 窗格中，選取左側導覽中的 [ **密碼重設** ]。
7. 在 [密碼重設屬性] 窗格中，選擇 [已啟用自助式密碼重設] 選項底下的 [已選取]。
8. 選取 [**選取群組**]，選取 [ **PWReset** ] 群組，然後選取 [**選取**  >  **儲存**]。
9. 關閉私用瀏覽器執行個體。

下一步，針對使用者3帳戶測試密碼重設。

1. 開啟新的私用瀏覽器執行個體，並瀏覽至 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。
1. 以「使用者 3」的認證登入。
1. 在 [ **需要詳細資訊**] 中，選取 **[下一步]**。 
1. 在 [避免您失去帳戶的存取權] 中，將認證電話設為您的手機號碼，並將認證電子郵件設為您的公司或個人電子郵件帳戶。
1. 驗證兩者後，選取 [ **看起來不錯**]，然後關閉瀏覽器的私人實例。
1. 在新的私用瀏覽器實例中，移至 [https://aka.ms/sspr](https://aka.ms/sspr) 。
1. 輸入使用者3帳戶名稱，並輸入 CAPTCHA 中的字元，然後選取 **[下一步]**。
1. 若要 **驗證步驟 1**，請選取 [ **電子郵件我的備選電子郵件**]，然後選取 [ **電子郵件**]。 當您收到電子郵件時，請輸入驗證碼，然後選取 **[下一步]**。
1. 在 [ **回到您的帳戶**] 中，輸入使用者3帳戶的新密碼，然後選取 **[完成]**。 請記下「使用者 3」帳戶變更的密碼，並儲存到安全的位置。
1. 在相同瀏覽器的新分頁中，前往 [https://portal.office.com](https://portal.office.com)，並以「使用者 3」帳戶名稱及新密碼登入。 您應該會看到 [Microsoft Office 首頁] 頁面。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)