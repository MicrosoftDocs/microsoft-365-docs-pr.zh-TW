---
title: 適用于 Microsoft 365 企業版測試環境的裝置合規性原則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，將 Intune 裝置相容性原則新增至您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686751"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>適用于 Microsoft 365 企業版測試環境的裝置合規性原則

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

透過本文中的指示，您可以將 Windows 10 裝置和 Microsoft 365 應用程式 enterprise 的 Intune 裝置符合性原則，新增至 Microsoft 365 for enterprise test 環境。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式設定 MAM 原則，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定 MAM 原則，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>階段2：建立 Windows 10 裝置的裝置合規性原則

在此階段中，您會為 Windows 10 裝置建立裝置符合性原則。
  
1. 移至 [microsoft 365 系統管理中心](https://admin.microsoft.com) ，並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。
    
2. 在您的瀏覽器的新索引標籤上，開啟 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。

3. 從瀏覽器的 [Azure 入口網站] 索引標籤中，于搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。
    
4. 如果您看到 [ **Microsoft Intune** ] 窗格中**沒有啟用 [裝置管理**] 的訊息，請按一下該窗格。 在 [行動 **裝置管理授權** ] 窗格中，按一下 [ **Intune MDM 核證機關**]，然後按一下 **[選擇**]。 重新整理瀏覽器索引標籤。
    
5. 在左側瀏覽窗格中，按一下 [群組]****。
    
6. 在 [ **群組-所有群組** ] 窗格中，按一下 [ **+ 新增群組**]。
    
7. 在 [**群組**] 窗格中，選取 [ **Microsoft 365** Or **Group type**的**安全性**]，並在 [**名稱**] 中輸入**Managed Windows 10 device users** ，選取 [在**成員資格類型**中**指派**]，然後按一下 [**建立**]。 
    
8. 按一下 [ **Microsoft Intune**]。 在 [ **Microsoft Intune** ] 窗格的 [ **快速作業** ] 清單中，按一下 [ **建立符合性原則**]。
    
9. 在 [ **合規性原則設定檔** ] 窗格中，按一下 [ **建立原則**]。
    
10. 在 [ **建立原則** ] 窗格的 [ **名稱**] 中，輸入 **Windows 10**。 在 [**平臺**] 中，選取 [ **windows 10 和更新版本**]，在**windows 10 符合性原則**窗格中按一下 **[確定]** ，然後按一下 [**建立**]。 
    
11. 按一下 [ **合規性原則設定檔**]，然後按一下 **Windows 10** 原則名稱。
    
12. 在 [ **Windows 10** ] 窗格中，按一下 [ **指派**]，然後按一下 [ **選取要包含的群組**]。
    
13. 在 [ **選取要包含的群組** ] 窗格中，按一下 [ **受管理的 Windows 10 裝置使用者** ] 群組，然後按一下 [ **選取**]。
    
14. 按一下 [ **儲存**]，按一下 **[Microsoft Intune-簡介**]，然後按一下左側導覽中的 [ **用戶端應用程式** ]。
    
15. 在 [ **用戶端應用程式** ] 窗格中，按一下 [ **應用程式**]，然後按一下 [ **新增**]。 

16. 在 [**新增應用程式**] 窗格中，選取 [**應用程式類型**]，然後選取 [ **Microsoft 365 套件**] 底下的**Windows 10** 。

17. 在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件資訊**]。
 
18. 在 [**應用程式套件資訊**] 窗格中，輸入「適用于**套件名稱**和套件的**Microsoft 365 應用程式**」**描述**。
按一下 [確定]。

19. 在 [ **新增應用程式** ] 窗格中，選取 [ **設定應用程式套件**]，然後按一下 **[確定]**。

20. 在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件設定**]。

21. 在 [ **更新通道**] 中，選取 [ **半年 Enterprise**]，然後按一下 **[確定]**。

22. 在 [ **新增應用程式** ] 窗格中，按一下 [ **新增**]。

現在，您已具備裝置符合性原則，可用於測試 **Windows 10** 裝置合規性原則中所選取的應用程式，以及 **受管理的 Windows 10 裝置使用者** 群組的成員。 請注意，選取 [Microsoft 365] 做為群組類型將會建立其他資源。 
  
## <a name="next-step"></a>下一步

在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。

## <a name="see-also"></a>請參閱

[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
