---
title: 在 Microsoft 365 for enterprise test 環境中登記 iOS/iPadOS 和 Android 裝置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此測試實驗室指南，可在 Microsoft 365 測試環境中註冊裝置，並以遠端方式管理這些裝置。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367080"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

本文說明如何在 Microsoft 365 for enterprise 測試環境中，為 iOS/iPadOS 和 Android 裝置登錄和測試基本行動裝置管理功能。

在測試環境中登記 iOS/iPadOS 和 Android 裝置包含三個階段：
- [階段1：組建您的 Microsoft 365 企業版測試環境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：註冊您的 iOS/iPadOS 和 Android 裝置](#phase-2-enroll-your-ios-and-android-devices)
- [階段3：從遠端系統管理您的 iOS/iPadOS 和 Android 裝置](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

若要以輕量的方式登記 iOS/iPadOS 和 Android 裝置，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中登記 iOS/iPadOS 和 Android 裝置，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 它會以選項形式提供，以便您可以測試自動授權和群組成員資格，也可以在代表一般組織的環境中進行試驗。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>階段2：註冊您的 iOS 和 Android 裝置

如果您正在考慮行動裝置管理 (MDM) 解決方案來管理裝置，您可以使用 Microsoft Intune。 使用任何 MDM 提供者（包括 Intune）時，裝置會「已註冊」。 當註冊時，他們會收到您設定的功能和設定。 

在 Intune 中，有幾種方式可以註冊您的 iOS/iPadOS 和 Android 裝置。 您可以選擇最適合您組織的註冊選項。 如需詳細資訊和指導，請參閱下列文章：

- [部署指南：在 Microsoft Intune 中註冊 iOS 和 iPadOS 裝置](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [部署指南：在 Microsoft Intune 中註冊 Android 裝置](/mem/intune/fundamentals/deployment-guide-enrollment-android)

如果您已準備好使用 Intune 進行裝置管理，且想要提供一些指引，下列資訊可能會有所説明：

- [裝置管理概述](/mem/intune/fundamentals/what-is-device-management)
- [Microsoft 端點管理員中的教學課程：演練 Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [部署指南：設定或移至 Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>階段3：從遠端系統管理您的 iOS 和 Android 裝置

Microsoft Intune 提供遠端鎖定和密碼重設功能。 如果有人喪失其裝置，您可以遠端鎖定裝置。 如果有人忘記其密碼，您可以從遠端重設密碼。

- 若要遠端鎖定 iOS/iPadOS 或 Android 裝置，請參閱 [使用 Intune 遠端鎖定裝置](/mem/intune/remote-actions/device-remote-lock)。
- 若要遠端重設密碼，請參閱 [reset or remove device 密碼 In Intune](/mem/intune/remote-actions/device-passcode-reset)。

如需其他可遠端執行的工作，請參閱 [可用的裝置動作](/mem/intune/remote-actions/device-management#available-device-actions)。
    
## <a name="next-step"></a>後續步驟

在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)
  
[適用于 Microsoft 365 企業版測試環境的裝置合規性原則](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 企業版概觀](microsoft-365-overview.md)
