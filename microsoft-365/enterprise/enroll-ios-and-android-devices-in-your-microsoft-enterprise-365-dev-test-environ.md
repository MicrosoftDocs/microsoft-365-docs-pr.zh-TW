---
title: 在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南註冊 Microsoft 365 測試環境中的裝置並從遠端管理它們。
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866256"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>在您的 Microsoft 365 企業版測試環境中註冊 iOS 和 Android 裝置

遵循本文中提供的指示，您將能夠註冊並在 Microsoft 365 企業版測試環境中測試 iOS 及 Android 裝置的基本的行動裝置管理功能。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要註冊 iOS 及 Android 裝置輕量型的方式的最低需求，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要註冊 iOS 及 Android 裝置模擬 enterprise 中的，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>階段 2： 註冊 iOS 及 Android 裝置

首先，使用中的指示[安裝並登入的公司入口網站應用程式](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)自訂您的測試環境的 Microsoft Intune 的公司入口網站應用程式。

接下來，使用中[設定您的公司資源的存取權](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)的指示以註冊 iOS 裝置。

接下來，用於指示中[註冊您的 Intune 的 Android 裝置](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)註冊 Android 裝置。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>階段 3： IOS 及 Android 裝置從遠端管理

Microsoft Intune 提供遠端鎖定及密碼重設功能。如果某人失去使用者的裝置，您可以從遠端鎖定裝置。如果有人忘記其密碼，您可以從遠端重。
  
若要從遠端鎖定 iOS 或 Android 裝置：

1. 在 Azure 入口網站登入[https://portal.azure.com](https://portal.azure.com)以全域管理員帳戶的認證。
2. 按一下 [**所有服務**，並輸入**Intune**，然後按一下都 [ **Intune**。
3. 按一下 [**裝置 > 所有裝置**。
4. 在裝置的清單中，按一下 iOS 或 Android 裝置和 [**遠端鎖定**巨集指令。

    
若要從遠端重設密碼︰

1. 必要時，在 Azure 的入口網站登入[https://portal.azure.com](https://portal.azure.com)以全域管理員帳戶的認證。
2. 按一下 [**所有服務**，並輸入**Intune**，然後按一下都 [ **Intune**。
3. 按一下 [**裝置 > 所有裝置**。
4. 從裝置清單您可以管理、 按一下 iOS 或 Android 裝置，並選擇 **...]更多**。然後選擇 [**移除密碼**裝置遠端巨集指令。

如其他試驗，請參閱[可用的裝置動作](https://docs.microsoft.com/intune/device-management#available-device-actions)。

    
## <a name="next-step"></a>下一步

探索其他[行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)功能與在測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 企業版的裝置規範遵守原則測試環境](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Enterprise 行動性 + 安全性 （EMS）](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
