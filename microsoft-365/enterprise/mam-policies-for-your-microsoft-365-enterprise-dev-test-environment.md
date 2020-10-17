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
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487409"
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

在這個階段中，為 Windows 10 裝置建立裝置符合性原則。
  
1. 移至 [microsoft 365 系統管理中心](https://admin.microsoft.com) ，並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。
1. 在您的瀏覽器的新索引標籤上，開啟 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。
1. 在 Azure 入口網站的 [搜尋] 方塊中，輸入 **intune**，然後選取 [ **intune**]。
1. 如果您看到 [ **Microsoft Intune** ] 窗格中**沒有啟用 [裝置管理**] 資訊，請選取它。 在 [行動 **裝置管理授權** ] 窗格中，選取 [ **Intune MDM 核證機關**]，然後選取 **[選擇**]。
1. 重新整理瀏覽器索引標籤。
1. 在左功能窗格中，選取 [ **群組**]。
1. 在 [ **群組-所有群組** ] 窗格中，選取 [ **+ 新增群組**]。
1. 在 [**群組**] 窗格中，選取 [ **Microsoft 365** ] 或 [**群組類型**的**安全性**？]，在 [**名稱**] 中輸入**受管理的 Windows 10 裝置使用者** **，選取 [** 在**成員資格類型**中**指派**]，然後選取 [
1. 選取 [ **Microsoft Intune**]。
1. 在 [ **Microsoft Intune** ] 窗格的 [ **快速作業** ] 清單中，選取 [ **建立符合性原則**]。
1. 在 [ **合規性原則設定檔** ] 窗格中，選取 [ **建立原則**]。
1. 在 [ **建立原則** ] 窗格的 [ **名稱**] 中，輸入 **Windows 10**。 在 [**平臺**] 中，選取 [windows **10 和更新版本**]，在 [ **windows 10 規範原則**] 窗格中選取 **[確定]** ，然後選取 [**建立**]。
1. 選取 [ **相容性原則設定檔**]，然後選取 **Windows 10** 原則名稱。
1. 在 [ **Windows 10** ] 窗格中，選取 [ **指派**]，然後選取 [ **選取要包含的群組**]。
1. 在 [ **選取要包含的群組** ] 窗格中，選取 [ **受管理的 Windows 10 裝置使用者** ] 群組，然後選取 [ **選取**]。
1. 選取 [ **儲存**]，選取 **[Microsoft Intune-簡介**]，然後選取左側導覽中的 [ **用戶端應用程式** ]。
1. 在 [ **用戶端應用程式** ] 窗格中，選取 [ **應用程式**]，然後選取 [ **新增**]。
1. 在 [**新增應用程式**] 窗格中，選取 [**應用程式類型**]，然後選取 [ **Microsoft 365 套件**] 底下的**Windows 10** 。
1. 在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件資訊**]。
1. 在 [**應用程式套件資訊**] 窗格中，輸入 [適用于**套件名稱**和套件中的**Microsoft 365 應用程式**]**說明**，然後選取 **[確定]**。
1. 在 [ **新增應用程式** ] 窗格中，選取 [ **設定應用程式套件**]，然後選取 **[確定]**。
1. 在 [ **新增應用程式** ] 窗格中，選取 [ **應用程式套件設定**]。
1. 在 [ **更新通道**] 中，選取 [ **半年 Enterprise**]，然後選取 **[確定]**。
1. 在 [ **新增應用程式** ] 窗格中，選取 [ **新增**]。

現在，您已具備裝置符合性原則，可用於測試 **Windows 10** 裝置合規性原則中所選取的應用程式，以及 **受管理的 Windows 10 裝置使用者** 群組的成員。 請注意，選取 [ **Microsoft 365** ] 做為「群組類型」會建立其他資源。
  
## <a name="next-step"></a>下一步

在您的測試環境中探索其他行動 [裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 功能和功能。

## <a name="see-also"></a>另請參閱

[適用于企業測試實驗室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 for enterprise test 環境中登記 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
