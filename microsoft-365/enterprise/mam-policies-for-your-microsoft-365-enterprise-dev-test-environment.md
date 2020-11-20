---
title: 適用于 Microsoft 365 企業版測試環境的裝置合規性原則
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，將 Intune 裝置相容性原則新增至您的 Microsoft 365 企業版測試環境。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367092"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>適用于 Microsoft 365 企業版測試環境的裝置合規性原則

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

本文說明如何將 Windows 10 裝置和 Microsoft 365 應用程式的 Intune 裝置遵循原則，新增至 Microsoft 365 for enterprise test 環境。

新增 Intune 裝置規範原則包括兩個階段：
- [階段1：組建您的 Microsoft 365 企業版測試環境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：建立 Windows 10 裝置的裝置合規性原則](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您想要以最小需求的輕量方式設定 MAM 原則，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定 MAM 原則，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>階段2：建立 Windows 10 裝置的裝置合規性原則

在此階段中，您會為 Windows 10 裝置建立裝置符合性原則。 此階段使用 Microsoft Intune 和 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431) 管理員系統管理中心新增群組，並建立符合性原則。

1. 移至 [microsoft 365 系統管理中心](https://admin.microsoft.com)，並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。 選取 **端點** 管理員管理中心。 [端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)隨即開啟。

    如果已顯示類似 **您未啟用 [裝置管理** ] 的郵件，請選取 [Intune] 做為 MDM 授權。 如需特定步驟，請參閱 [Set the mobile device management 機關](/mem/intune/fundamentals/mdm-authority-set)。

    端點管理員管理中心著重于裝置管理和應用程式管理。 如需此系統管理中心的教程，請參閱「 [教程：演練 Intune 中的 Microsoft 端點管理員](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)」。

2. 在 **[群組**] 中，使用 **指派** 的成員資格類型，新增名為「**受管理的 Windows 10 裝置使用者**」的新 **Microsoft 365** 或 **安全** 組。 在後續步驟中，您會將您的相容性原則指派給此群組。 

    如需特定步驟，以及 **Microsoft 365** 或 **安全** 組的詳細資訊，請參閱 [新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

3. 在 [ **裝置**] 中，建立 Windows 10 合規性原則。 將此原則指派給您建立的 **受管理 Windows 10 裝置使用者** 群組。

    在您的原則中，您可以封鎖簡單密碼、需要防火牆、需要執行 Microsoft Defender 反惡意程式碼服務，等等。 規範原則通常會包含基本設定或每個裝置應該具備的最低基本設定。

    如需特定步驟，以及您可以設定之可用之相容性設定的資訊，請參閱 [Use 合規性原則設定您管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。

完成後，您會在 **受管理的 Windows 10 裝置使用者** 群組中，測試成員的裝置合規性原則。
  
## <a name="next-step"></a>後續步驟

在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。

## <a name="see-also"></a>另請參閱

[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
