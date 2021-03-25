---
title: 適用于 Android 的 Microsoft Defender ATP
ms.reviewer: ''
description: 說明如何安裝和使用適用于 Android 的 Microsoft Defender ATP
keywords: microsoft、defender、atp、android、安裝、部署、卸載、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187610"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>適用于 Android 的 Microsoft Defender Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題說明如何針對 Android 安裝、設定、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 針對 Android 的 Endpoint for Endpoint 執行其他協力廠商端點保護產品可能會造成效能問題和不可預期的系統錯誤。


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>如何為 Android 安裝 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必要條件

-   **使用者的**

    -   指派給使用者 (s) 的 Microsoft Defender Endpoint 授權。 請參閱 [Microsoft Defender 的 Endpoint 授權需求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune 公司入口網站應用程式可從 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下載，且可用於 Android 裝置。

        -   此外，裝置 (s) 可以透過 Intune 公司入口網站進行 [註冊](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) ，以強制執行 intune 裝置相容性原則。 這需要將使用者指派為 Microsoft Intune 授權。

    -   如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。
        

-   **針對系統管理員**

    -   存取 Microsoft Defender Security Center 入口網站。

        > [!NOTE]
        > Microsoft Intune 是唯一支援的行動裝置管理 (MDM) 解決方案，可為 Android 部署 Microsoft Defender for Endpoint。 目前只有已註冊的裝置才支援在 Intune 中強制執行 Android 相關裝置相容性原則的端點。 

    -   存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，將應用程式部署至組織中已註冊的使用者群組。

### <a name="system-requirements"></a>系統需求

-   執行 Android 6.0 和更新版本的 android 裝置。
-   Intune 公司入口網站應用程式從 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 和安裝中下載。 需要有裝置註冊，才能強制執行 Intune 裝置合規性原則。

### <a name="installation-instructions"></a>安裝指示

適用于 Android 的 Microsoft Defender Endpoint 支援在已註冊裝置的兩種模式上安裝-傳統裝置管理員和 Android 企業模式。
**目前，在 Android Enterprise 中支援具有工作設定檔及公司所擁有的完整管理使用者裝置 enrolments 的個人擁有裝置。在準備好時，將會宣佈對其他 Android 企業模式的支援。**

Microsoft Intune for Android 的部署是透過 Microsoft Intune (MDM) 進行部署。
如需詳細資訊，請參閱 [使用 Microsoft Intune 部署適用于 Android 的 Microsoft Defender For Endpoint](android-intune.md)。


> [!NOTE]
> **[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)現在已提供適用于 Android 的 Microsoft Defender 端點。** <br> 您可以從 Intune 連線到 Google，以部署 Microsoft Defender for Endpoint 應用程式、跨裝置管理員和 Android Enterprise entrollment 模式。 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>如何設定適用于 Android 的 Microsoft Defender for Endpoint

設定適用于 android 功能的 [microsoft](android-configure.md)defender for endpoint 功能的指導方針。



## <a name="related-topics"></a>相關主題
- [使用 Microsoft Intune 部署 Microsoft Defender for Endpoint](android-intune.md)
- [針對 Android 功能設定 Microsoft Defender for Endpoint 功能](android-configure.md)

