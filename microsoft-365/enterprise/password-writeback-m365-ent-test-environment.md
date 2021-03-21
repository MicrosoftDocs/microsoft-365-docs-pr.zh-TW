---
title: 適用於 Microsoft 365 測試環境的密碼回寫
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 摘要：設定適用於 Microsoft 365 測試環境的密碼回寫。
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921477"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>適用於 Microsoft 365 測試環境的密碼回寫

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

使用者可以使用密碼寫回以透過 Azure Active Directory (Azure AD) （然後將其複寫至您的本機 Active Directory 網域服務 (AD DS) ）來更新其密碼。 使用密碼回寫時，使用者不必透過內部部署 AD DS （儲存其原始使用者帳戶）來更新其密碼。 這可協助漫遊或遠端使用者沒有其內部部署網路的遠端存取連線。

本文說明如何設定您的 Microsoft 365 測試環境，以進行密碼回寫。

設定密碼寫回的測試環境包括兩個階段：
- [階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [階段 2：啟用適用於 TESTLAB AD DS 網域的密碼回寫](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理

首先，依照 [ [密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理] 中的指示進行。 您產生的設定如下所示：
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此組態包含：
  
- Microsoft 365 E5 試用版或付費訂閱。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。
- Azure AD Connect 會在 APP1 上執行，以將 TESTLAB AD DS 網域同步至 Microsoft 365 訂閱的 Azure AD 租用戶。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>階段 2：啟用適用於 TESTLAB AD DS 網域的密碼回寫

首先，使用全域系統管理員角色設定使用者 1 帳戶。

1. 從 [Microsoft 365 系統管理中心](https://portal.microsoft.com)，使用您的全域系統管理員帳戶登入。

2. 選取 [作用中 **使用者**]。
 
3. 在 [作用中 **使用者** ] 頁面上，選取 [ **user1** ] 帳戶。

4. 在 [ **user1** ] 窗格中，選取 [**角色**] 旁的 [**編輯**]。

5. 在 [ **編輯使用者角色** ] 窗格的 user1 上，選取 [ **全域管理員**]，然後選取 [ **儲存**]，然後選取 [ **關閉**]。

接下來，使用安全性設定來配置使用者 1 帳戶，該安全性設定允許其代表 TESTLAB AD DS 網域中的其他使用者變更密碼。

1. 從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。

2. 從 APP1 的桌面，選取 [ **開始**]，輸入 [ **active**]，然後選取 [ **active Directory 使用者和電腦**]。

3. 在功能表列上，選取 [ **View**]。 若未啟用 [ **高級功能** ]，請將其選取加以啟用。

4. 在樹狀窗格中，選取並按住 (，或以滑鼠右鍵按一下 [) 您的網域 **]，然後選取 [** 內容]，然後選取 [ **安全性** ] 索引標籤。

5. 選取 [ **高級**]。

6. 在 [ **許可權** ] 索引標籤上，選取 [ **新增**]。

7. 選取 [ **選取主體**]，輸入 [ **User1**]，然後選取 **[確定]**。

8. 在 [適用於] 中，選取 [子系使用者物件]。

9. 在 [使用權限] 下，選取下列動作：

    - **變更密碼**
    - **重設密碼**

10. 在 [內容] 下，選取下列動作：
    - **撰寫 lockoutTime**
    - **撰寫 pwdLastSet**

11. 選取 **[確定]** 三次，以儲存變更。

12. 關閉 [Active Directory 使用者及電腦]。

接著，在 APP1 上設定 Azure AD Connect 以進行密碼回寫。

1. 如有需要，請以 TESTLAB\User1 帳戶連線至 APP1。

2. 從 APP1 的桌面，按兩下 [Azure AD Connect]。

3. 在 [ **歡迎] 頁面** 上，選取 [ **設定**]。

4. 在 [ **其他** 工作] 頁面上，選取 [ **自訂同步處理選項**]，然後選取 **[下一步]**。

5. 在 [連線 **到 AZURE AD]** 頁面上，輸入您的全域系統管理員帳號憑證，然後選取 **[下一步]**。

6. 在 [ **連接目錄] 和 [** **網域/OU 篩選** ] 頁面上，選取 **[下一步]**。

7. 在 [ **選用功能** ] 頁面上，選取 [ **密碼回寫**]，然後選取 **[下一步]**。

8. 在 [ **準備設定** ] 頁面上，選取 [ **設定** 並等候處理常式完成]。

9. 當您看到設定完成時，請 **選取 [** 結束]。

您現在可以為未連線到模擬內部網路之虛擬網路的電腦上的使用者測試密碼回寫。

您產生的設定如下所示：

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

此組態包含：

- 使用 DNS 網域 TESTLAB 的 Microsoft 365 E5 試用版或付費訂閱。\<*your domain name*> 註冊。
- 簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。
- Azure AD Connect 會在 APP1 上執行，以將來自 Microsoft 365 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。
- 密碼回寫已啟用，因此使用者可以透過 Azure AD 變更其密碼，而不需要連線到簡化的內部網路。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)