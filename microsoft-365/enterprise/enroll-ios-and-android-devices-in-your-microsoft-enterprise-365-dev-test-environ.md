---
title: 在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置
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
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南，可在 Microsoft 365 測試環境中註冊裝置，並以遠端方式管理這些裝置。
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686007"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

遵循本文所提供的指示，您可以在 Microsoft 365 for enterprise 測試環境中，為 iOS 和 Android 裝置登錄並測試基本行動裝置管理功能。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式登記 iOS 和 Android 裝置，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中登記 iOS 和 Android 裝置，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>階段2：註冊您的 iOS 和 Android 裝置

首先，使用 [安裝和登入公司入口網站](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 中的指示，為您的測試環境自訂 Microsoft Intune 公司入口網站應用程式。

接下來，使用 [設定您公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 來註冊 iOS 裝置。

接下來，使用在 [Intune 中註冊您的 android 裝置](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 中的指示來註冊 android 裝置。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>階段3：從遠端系統管理您的 iOS 和 Android 裝置

Microsoft Intune 提供遠端鎖定和密碼重設功能。 如果有人遺失他們的裝置，您可以從遠端鎖定裝置。 如果有人忘記其密碼，您可以遠端重設密碼。
  
若要從遠端鎖定 iOS 或 Android 裝置：

1. [https://portal.azure.com](https://portal.azure.com)使用全域系統管理員帳戶的認證登入 Azure 入口網站。
2. 在瀏覽器的 [Azure 入口網站] 索引標籤上，在搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。
3. 按一下 [ **裝置 > 所有裝置**]。
4. 在裝置清單中，按一下 [iOS] 或 [Android] 裝置，然後按一下 [ **遠端鎖定** ] 動作。

    
若要從遠端重設密碼︰

1. 如有需要，以 [https://portal.azure.com](https://portal.azure.com) 全域系統管理員帳戶的認證登入 Azure 入口網站。
2. 在瀏覽器的 [Azure 入口網站] 索引標籤上，在搜尋方塊中輸入 **Intune** ，然後按一下 [ **intune**]。
3. 按一下 [ **裝置 > 所有裝置**]。
4. 從您管理的裝置清單中，按一下 [iOS] 或 [Android] 裝置，然後選擇 [...]。 **其他**。 然後選擇 [ **移除密碼** 裝置遠端] 動作。

如需其他實驗，請參閱 [可用的裝置動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。

    
## <a name="next-step"></a>下一步

在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)
  
[適用于 Microsoft 365 企業版測試環境的裝置合規性原則](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 企業版概觀](microsoft-365-overview.md)

