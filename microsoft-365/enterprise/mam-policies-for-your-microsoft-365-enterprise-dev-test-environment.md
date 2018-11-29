---
title: Microsoft 365 企業版測試環境的 MAM 原則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 若要新增至 Microsoft 365 企業版的 Intune 行動應用程式管理 (MAM) 原則測試環境中使用此測試實驗室指南。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866748"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版測試環境的 MAM 原則

本文中的指示，與您新增至 Microsoft 365 企業版的 Intune 行動應用程式管理 (MAM) 原則測試環境。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要設定 MAM 原則的最小需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要模擬企業中設定 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>階段 2：建立和部署 iOS 和 Android 的裝置的 MAM 原則

在此階段中，您會建立和部署兩個不同的 MAM 原則：一個適用於 iOS 裝置，另一個適用於 Android 裝置。
  
1. 移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。
    
2. 在瀏覽器的新] 索引標籤上開啟 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。

3. Azure 入口網站] 索引標籤上的 Internet Explorer 中，在功能窗格] 中按一下 [**所有服務**、 並輸入**Intune**，然後按一下都 [ **Intune**。
    
4. 如果您看到**尚未啟用尚未裝置管理**訊息**Microsoft Intune** blade 上，按一下它。在**行動裝置管理授權**blade 中，按一下 [ **Intune MDM 授權**、 及 [**選擇**。重新整理您瀏覽器] 索引標籤。
    
5. 在左側瀏覽窗格中，按一下 [群組]****。
    
6. 在**群組所有群組**blade 中，按一下 [ **+ 新群組**。
    
7. 在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入 [**受管理的 iOS 裝置使用者****成員資格類型**] 中選取 [**已指派**] 和 [**建立**。 
    
8. 關閉**群組**blade。
    
9. 在**群組所有群組**blade 中，按一下 [**新增]**。
    
10. 在**群組**blade 中，選取 [ **Office 365** **群組類型？**、 在 [**名稱**] 中輸入**受管理的 Android 裝置使用者****成員資格類型**] 中選取 [**已指派**] 和 [**建立**。
    
11. 關閉**群組所有群組**blade。
    
12. 在**Intune** blade、**快速工作**清單中，按一下 [**建立規範原則**。
    
13. 在**規範原則設定檔**blade 中，按一下 [**建立原則**。
    
14. 在**建立原則**blade，在 [**名稱**] 輸入**iOS**。在**平台**，選取**iOS**、 上**iOS 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。
    
15. 在**規範原則設定檔**blade 中，按一下 [**建立原則**。
    
16. 在**建立原則**blade，在 [**名稱**] 中，輸入**Android**。在**平台**，選取**Android**、 在**Android 規範原則**blade 中，按一下 [**確定]** 和 [**建立**。
    
17. 按一下 [**規範原則設定檔**blade、 **Android**原則名稱。
    
18. **Android-屬性**blade 的左方導覽，按一下 [**工作分派**，和 [**選取群組**。
    
19. 在 [**選取群組**blade、 [**受管理的 Android 裝置 users**群組，和 [**選取**。
    
20. 按一下 [**儲存**]，然後關閉 [ **Android-工作分派**blade。
    
21. 按一下 [**規範原則設定檔**blade、 **iOS**原則名稱。
    
22. **IOS-屬性**blade 的左方導覽，按一下 [**工作分派**，和 [**選取群組**。
    
23. 在 [**選取群組**blade、 [**受管理 iOS 裝置 users**群組，和 [**選取**。
    
24. 按一下 [**儲存**]，然後關閉 [ **iOS-工作分派**blade。
    
25. 關閉**規範原則設定檔**blade。
    
26. 在**Intune** blade 中，按一下 [在左側導覽中的**管理應用程式**。
    
27. 在**行動應用程式**blade 中，按一下 [**應用程式**。
    
28. 在 [應用程式] 清單中按一下 [ **PowerPoint** 
    
29. 在**PowerPoint 概觀 （英文)** blade 中，按一下 [**指派 > 選取群組 > 受管理的 iOS 裝置 > 選取**。在 [**類型**] 選取 [**線上**] 和 [**儲存**。
    
30. 重複步驟 29 下列應用程式：
    
    - Outlook for Android
    
    - Word for iOS
    
    - iOS 版 Excel
    
    - iOS 版 Outlook
    
    - iOS 版 Microsoft Dynamics CRM (適用於 iPad)
    
    - iOS 版 Microsoft Dynamics CRM (適用於 iPhone)
    
    - Android 版 Dynamics CRM (適用於手機)
    
    - Android 版 Dynamics CRM (適用於平板電腦)
    
    - Android 版 Excel
    
    - Android 版 Word
    
    - iOS 版的 OneNote
    
31. 關閉**行動應用程式-應用程式**blade。
    
32. 在**行動應用程式**blade 中，按一下 [**應用程式保護原則**。
    
33. 在**應用程式保護原則**blade 中，按一下 [**新增原則**。
    
34. 在 [**新增原則**blade 中，輸入**iOS**，和 [**選取所需的應用程式**。
    
35. 在**應用程式**blade、 [ **PowerPoint**、 **IPhone 上的 Microsoft Dynamics CRM**、 **Excel**、 **IPhone 上的 Microsoft Dynamics CRM**、 **Word**、 **OneNote**、 及**Outlook**] 和 [**選取**。
    
36. 按一下 [**新增原則**blade、 的 [**建立**]。
    
37. 在**應用程式保護原則**blade 中，按一下 [**新增原則**。
    
38. 在**新增原則**blade 中，輸入**Android**、 選取 [ **Android** **平台**，及 [**選取所需的應用程式**。
    
39. 在**應用程式**blade 中，按一下 [ **PowerPoint**、**平板電腦的 Dynamics CRM**、 **Excel**、 **Word**、 **Outlook**和**Dynamics CRM 電話**、 及 [**選取**。
    
40. 按一下 [**新增原則**blade、 的 [**建立**]。
    
您現在有兩個 MAM 原則，一個適用於 iOS 裝置，另一個適用於 Android 裝置，並且都已準備好對選取的應用程式使用測試設定進行試驗。 
  
## <a name="next-step"></a>下一步

探索其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能與在測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 Enterprise 測試實驗室指南](m365-enterprise-test-lab-guides.md)。
  
[在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Enterprise 行動性 + 安全性 （EMS）](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
