---
title: 裝置合規性原則，您的 Microsoft 365 企業版測試環境
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
description: 使用此測試實驗室指南來新增 Intune 裝置合規性原則，以您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 8a746f99e16444527c44267eddbaec9f5e5156eb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801628"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>裝置合規性原則，您的 Microsoft 365 企業版測試環境

*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*

透過本文中的指示，您可以新增 Windows 10 裝置和 Office 365 專業增強版的 Intune 裝置合規性原則至 Microsoft 365 企業版測試環境。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式設定 MAM 原則，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中設定的 MAM 原則，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>階段 2： 建立 Windows 10 裝置的裝置合規性原則

在這個階段，您會建立 Windows 10 裝置的裝置合規性原則。
  
1. 移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並登入您的 Office 365 測試實驗室訂閱，以全域管理員帳戶。
    
2. 在瀏覽器的新] 索引標籤上開啟 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)。

3. 從 Azure 入口網站] 索引標籤瀏覽器中，在 [搜尋] 方塊中，輸入**Intune** ，然後按一下 [ **Intune**。
    
4. 如果您看到**您尚未啟用尚未裝置管理**訊息在**Microsoft Intune** ] 窗格中的，按一下它。 在 [**行動裝置管理授權**] 窗格中，按一下 [ **Intune MDM 授權單位**，，然後按一下 [**選擇**。 重新整理您的瀏覽器索引標籤。
    
5. 在左側瀏覽窗格中，按一下 [群組]****。
    
6. 在 [**群組-所有群組**] 窗格中，按一下 [ **+ 新增群組**]。
    
7. 在 [**群組**] 窗格中，選取 [ **Office 365**或**安全性****群組類型？**，在 [**名稱**] 中，輸入**受管理的 Windows 10 裝置使用者**在 [**成員資格類型**] 中，選取 [**已指派**，然後按一下 [**建立**。 
    
8. 按一下 [ **Microsoft Intune**]。 在**Microsoft Intune** ] 窗格中，在 [**快速工作**] 清單中，按一下 [**建立合規性政策**]。
    
9. 在 [**合規性政策設定檔**] 窗格中，按一下 [**建立原則**]。
    
10. 在 [**建立原則**] 窗格中，在 [**名稱**] 中，輸入**Windows 10**。 在 [**平台**，選取 [ **Windows 10 和更新版本**在**Windows 10 合規性原則**] 窗格中，按一下 [**確定]** ，然後按一下 [**建立**。 
    
11. 按一下**合規性政策設定檔**、，然後按一下 [ **Windows 10**原則名稱。
    
12. 在**Windows 10** ] 窗格中，按一下 [**工作分派**，，然後按一下 [**選取要包含的群組**。
    
13. 在 [**選取要加入群組**] 窗格中，按一下 [**管理 Windows 10 裝置使用者**] 群組中，，然後按一下 [**選取**。
    
14. 按一下 [**儲存**]，請按一下 [ **Microsoft Intune 概觀**，和 [**用戶端應用程式**在左側導覽窗格中。
    
15. 在**用戶端應用程式**] 窗格中，按一下 [**應用程式**，，然後按一下 [**新增]**。 

16. 在 [**新增應用程式**] 窗格中，選取**應用程式類型**]，然後選取 [ **Office 365 套件**] 下的**Windows 10** 。

17. 在 [**新增應用程式**] 窗格中，選取 [**應用程式套件資訊**。
 
18. 在 [**應用程式套件資訊**] 窗格中，輸入**Office 365 專業增強版**在**套件名稱**] 和 [**套件描述**。
按一下 [確定]。

19. 在 [**新增應用程式**] 窗格中，選取 [**設定應用程式套件**，，然後按一下 [**確定]**。

20. 在 [**新增應用程式**] 窗格中，選取 [**應用程式套件設定**。

21. **更新通道**，選取**半年**，然後再按一下 [**確定]**。

22. 在 [**新增應用程式**] 窗格中，按一下 [**新增**]。

您現在可以在**Windows 10**裝置合規性原則中進行測試選取的應用程式和**受管理的 Windows 10 裝置的使用者**群組的成員裝置合規性原則。 請注意，選取 [Office 365，因為群組類型會建立額外的資源。 
  
## <a name="next-step"></a>下一步

瀏覽其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能及測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。
  
[註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
