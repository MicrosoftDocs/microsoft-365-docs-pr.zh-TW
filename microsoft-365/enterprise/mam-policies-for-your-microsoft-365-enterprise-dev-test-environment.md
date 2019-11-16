---
title: 裝置合規性原則，您的 Microsoft 365 企業版測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南來新增 Intune 裝置合規性原則，以您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 6f37a898461ea67bc2927fcbac1a0f1b15adb036
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672559"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>裝置合規性原則，您的 Microsoft 365 企業版測試環境

*此測試實驗室指南僅可與 Microsoft 365 企業版測試環境。*

透過本文中的指示，您可以新增 Intune 裝置合規性政策至 Microsoft 365 企業版測試環境。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式設定 MAM 原則，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中設定的 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>階段 2： 建立 Windows 10 裝置的裝置合規性原則

在這個階段，您會建立 Windows 10 裝置的裝置合規性原則。
  
1. 移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並登入您的 Office 365 測試實驗室訂閱，以全域管理員帳戶。
    
2. 在瀏覽器的新] 索引標籤上開啟 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)。

3. 在瀏覽器中，瀏覽] 窗格中，在 Azure 入口網站] 索引標籤上按一下 [**所有服務**，請輸入**Intune**，和都 [ **Intune**。
    
4. 如果您看到**您尚未啟用尚未裝置管理**訊息在**Microsoft Intune** ] 刀鋒視窗上，按一下它。 在 [**行動裝置管理授權**] 刀鋒視窗中，按一下 [ **Intune MDM 授權單位**，，，然後按一下 [**選擇**。 重新整理您的瀏覽器索引標籤。
    
5. 在左側瀏覽窗格中，按一下 [群組]****。
    
6. 在 [**群組-所有群組**] 刀鋒視窗中，按一下 [ **+ 新增群組**]。
    
7. 在 [**群組**] 刀鋒視窗中，選取 [ **Office 365**或**安全性****群組類型？**，在 [**名稱**] 中，輸入**受管理的 Windows 10 裝置使用者**在 [**成員資格類型**] 中，選取 [**已指派**，然後按一下 [**建立**。 
    
8. 關閉 [群組]**** 刀鋒視窗。
    
11. 關閉 [**群組-所有群組**] 刀鋒視窗。
    
12. 在**Microsoft Intune** ] 刀鋒視窗中，在 [**快速工作**] 清單中，按一下 [**建立合規性政策**]。
    
13. 在 [合規性政策設定檔]**** 刀鋒視窗上，按一下 [建立政策]****。
    
14. 在 [**建立原則**] 刀鋒視窗中，在 [**名稱**] 中，輸入**Windows 10**。 在 [**平台**，選取 [ **Windows 10 和更新版本**在**Windows 10 合規性原則**] 刀鋒視窗中，按一下 [**確定]** ，然後按一下 [**建立**。 關閉**Windows 10** ] 刀鋒視窗。
    
15. 在 [**合規性政策設定檔**] 刀鋒視窗中，按一下 [ **Windows 10**原則名稱。
    
16. 在**Windows 10** ] 刀鋒視窗中，按一下 [**工作分派**，，然後按一下 [**選取要包含的群組**。
    
17. 在 [**選取要加入群組**] 刀鋒視窗上，按一下 [**管理 Windows 10 裝置使用者**] 群組中，，然後按一下 [**選取**。
    
18. 按一下 [**儲存**]，然後關閉 [ **Windows 10-指派**] 刀鋒視窗。
    
19. 關閉 [合規性政策設定檔]**** 刀鋒視窗上。
    
20. 在**Microsoft Intune** ] 刀鋒視窗上，按一下 [在左側導覽中的**用戶端應用程式**。
    
21. 在**用戶端應用程式**] 刀鋒視窗中，按一下 [**應用程式**，並再按一下 [**新增]**。 

22. 在 [**新增應用程式**] 刀鋒視窗中，選取**應用程式類型**]，然後選取 [ **Office 365 套件**] 下的**Windows 10** 。

23. 按一下 [**設定應用程式套件**，然後按一下 [**確定]**。

24. 按一下 [**應用程式套件資訊**，在**套件名稱**] 中， **Office 應用程式適用於 Windows 10**中**套件描述**] 中，輸入**Office 應用程式適用於 Windows 10** ，然後按一下 [**確定]**。

25. 按一下 [**應用程式套件設定**，在**更新通道**中，選取**半年**，然後按一下 [**確定]**。

26. 在 [**新增應用程式**] 刀鋒視窗中，按一下 [**新增**]。

您現在可以在**Windows 10**裝置合規性原則中進行測試選取的應用程式和**受管理的 Windows 10 裝置的使用者**群組的成員裝置合規性原則。 請注意，選取 [Office 365，因為群組類型會建立額外的資源。 
  
## <a name="next-step"></a>下一步

瀏覽其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能及測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。
  
[註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
