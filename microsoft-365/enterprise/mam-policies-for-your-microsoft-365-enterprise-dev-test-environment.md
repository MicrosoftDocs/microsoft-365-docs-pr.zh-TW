---
title: Microsoft 365 企業版的裝置規範遵守原則測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 若要新增至 Microsoft 365 企業版的 Intune 裝置規範遵守原則測試環境中使用此測試實驗室指南。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866748"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版的裝置規範遵守原則測試環境

使用本文中的指示，您可以將 Intune 裝置規範原則新增至 Microsoft 365 企業版測試環境。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要設定 MAM 原則的最小需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要模擬企業中設定 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>階段 2： 建立 Windows 10 裝置的裝置規範原則

在此階段中，您會建立 Windows 10 裝置的裝置規範原則。
  
1. 移至 [Office 入口網站 ([https://office.com](https://office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。
    
2. 在瀏覽器的新] 索引標籤上開啟 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。

3. 在 Azure 的入口網站] 索引標籤中瀏覽器中，在功能窗格] 中按一下 [**所有服務**、 並輸入**Intune**，然後按一下都 [ **Intune**。
    
4. 如果您看到**尚未啟用尚未裝置管理**訊息**Microsoft Intune** blade 上，按一下它。在**行動裝置管理授權**blade 中，按一下 [ **Intune MDM 授權**、 及 [**選擇**。重新整理您瀏覽器] 索引標籤。
    
5. 在左側瀏覽窗格中，按一下 [群組]****。
    
6. 在**群組所有群組**blade 中，按一下 [ **+ 新群組**。
    
7. 在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入**受管理的 Windows 10 裝置的使用者**在**成員資格類型**] 中選取 [**已指派**] 和 [**建立**。 
    
8. 關閉**群組**blade。
    
11. 關閉**群組所有群組**blade。
    
12. 在**Microsoft Intune** blade、**快速工作**清單中，按一下 [**建立規範原則**。
    
13. 在**規範原則設定檔**blade 中，按一下 [**建立原則**。
    
14. 在**建立原則**blade，在 [**名稱**] 輸入**Windows 10**。**平台**，在選取**10 及更新版本的 Windows**、 在**Windows 10 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。關閉**Windows 10** blade。
    
15. 在**規範原則設定檔**blade 中，按一下 [ **Windows 10**原則名稱。
    
16. 在**Windows 10** blade 中，按一下 [**工作分派**，及 [**選取要包含的群組**。
    
17. **選取要包含的群組**blade，在 [**受管理的 Windows 10 裝置 users**群組，和 [**選取**。
    
18. 按一下 [**儲存**]，然後關閉 [ **Windows 10-工作分派**blade。
    
19. 關閉**規範原則設定檔**blade。
    
20. 在**Microsoft Intune** blade 中，按一下 [在左側導覽中的**用戶端應用程式**。
    
21. 在**用戶端應用程式**blade 中，按一下 [**應用程式**，然後按一下 [**新增**。 

22. 在**新增應用程式**blade 中，選取**類型的應用程式**]，然後選取 [ **Office 365 套裝軟體** **Windows 10** 。

23. 按一下 [**設定應用程式套件**，並再按一下 [**確定]**。

24. 按一下 [**應用程式套件資訊**、 輸入**套件名稱**] 中**的 Windows 10 Office 應用程式****套件描述**] 中，在**Office 應用程式的 Windows 10** ，然後按一下 [**確定]**。

25. 按一下 [**應用程式套件設定**、 選取**分號每年次**中**更新通道**，並再按一下 [**確定]**。

26. 在**新增 app** blade 中，按一下 [**新增]**。

您現在有裝置規範原則中的**Windows 10**裝置規範原則測試所選的應用程式與**受管理的 Windows 10 裝置的使用者**群組的成員。 
  
## <a name="next-step"></a>下一步

探索其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能與在測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 Enterprise 測試實驗室指南](m365-enterprise-test-lab-guides.md)。
  
[在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Enterprise 行動性 + 安全性 （EMS）](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
