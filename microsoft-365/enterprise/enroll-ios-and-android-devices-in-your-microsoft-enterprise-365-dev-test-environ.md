---
title: 註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南來註冊 Microsoft 365 測試環境中的裝置，並從遠端管理。
ms.openlocfilehash: 0d7e03d1dcc6e8f401258587c1dbc083b1237d49
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640375"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>註冊 iOS 和 Android 裝置，Microsoft 365 企業版測試環境中

藉由遵循本文中提供的指示，您將能夠註冊，並在 Microsoft 365 企業版測試環境中測試 for iOS 和 Android 裝置的基本的行動裝置管理功能。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式註冊 iOS 和 Android 裝置，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要註冊 iOS 和 Android 裝置模擬的企業中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>階段 2： 註冊 iOS 和 Android 裝置

首先，使用中的指示[安裝並登入公司入口網站應用程式](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)來自訂您的測試環境的 Microsoft Intune 公司入口網站應用程式。

接下來，使用中[設定您的公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)的指示，註冊 iOS 裝置。

接下來，使用中[註冊您的 Android 裝置，在 Intune 中](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)的指示，註冊 Android 裝置。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>階段 3： 您的 iOS 和 Android 裝置從遠端管理

Microsoft Intune 提供遠端鎖定和密碼重設功能。 如果有人遺失他們的裝置，您可以從遠端鎖定裝置。 如果有人忘記其密碼，您可以從遠端重。
  
若要從遠端鎖定 iOS 或 Android 裝置︰

1. 登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的認證。
2. 按一下 [**所有服務**]，輸入**Intune**，，然後都按一下 [ **Intune**。
3. 按一下 [**裝置 > 所有裝置**。
4. 在裝置清單中，按一下 [iOS 或 Android 裝置，，，然後按一下 [**遠端鎖定**巨集指令。

    
若要從遠端重設密碼︰

1. 如有需要登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的認證。
2. 按一下 [**所有服務**]，輸入**Intune**，，然後都按一下 [ **Intune**。
3. 按一下 [**裝置 > 所有裝置**。
4. 從裝置清單您可以管理、 按一下 iOS 或 Android 裝置，並選擇 **...]多個**。 然後選擇 [**移除密碼**裝置遠端巨集指令。

其他試驗，請參閱[可用的裝置的動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。

    
## <a name="next-step"></a>下一步

瀏覽其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能及測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)
  
[裝置合規性原則，您的 Microsoft 365 企業版測試環境](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

