---
title: Android 上適用於端點的 Microsoft Defender
ms.reviewer: ''
description: 說明如何在 Android 上安裝及使用 Microsoft Defender for Endpoint
keywords: microsoft、defender、Microsoft Defender for Endpoint、android、安裝、部署、卸載、intune
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
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844715"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 上適用於端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題說明如何在 Android 上安裝、設定、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 在 Android 上執行其他協力廠商端點防護產品及 Defender for Endpoint 時，可能會造成效能問題和不可預期的系統錯誤。


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上安裝 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必要條件

-   **使用者的**

    -   指派給使用者 (s) 的 Microsoft Defender Endpoint 授權。 請參閱 [Microsoft Defender 的 Endpoint 授權需求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune 公司入口網站應用程式可以從[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)下載，並可在 Android 裝置上使用。

        -   此外，裝置 (s) 可以透過 Intune 公司入口網站應用程式進行[註冊](/mem/intune/user-help/enroll-device-android-company-portal)，以強制執行 Intune 裝置的相容性原則。 這需要 Microsoft Intune 授權指派給使用者。

    -   如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。
        

-   **針對系統管理員**

    -   存取 Microsoft Defender 資訊安全中心入口網站。

        > [!NOTE]
        > Microsoft Intune 是唯一支援的行動裝置管理 (MDM) 方案，可在 Android 上部署 Microsoft Defender for Endpoint。 目前只有已註冊的裝置才支援在 Intune 中強制執行 Android 相關裝置相容性原則上的端點。 

    -   Access [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，將應用程式部署至組織中已註冊的使用者群組。
        
### <a name="network-requirements"></a>網路需求

- 若要在連接至網路時，Android 上的 Microsoft Defender for Endpoint 可以運作，則需要將防火牆/proxy 設定為可 [存取 Microsoft defender For Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

### <a name="system-requirements"></a>系統需求

-   執行 Android 6.0 和更新版本的 android 裝置。
-   Intune 公司入口網站應用程式從[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)和安裝下載。 需要有裝置註冊，才能強制執行 Intune 裝置合規性原則。

### <a name="installation-instructions"></a>安裝指示

在 Android 上的 Microsoft Defender for Endpoint 支援在已註冊裝置的兩種模式上安裝-傳統裝置管理員和 Android Enterprise 模式。
**目前，在 Android Enterprise 中支援具有工作設定檔的個人擁有的裝置及公司所擁有的完整管理使用者裝置註冊。在準備好時，將會宣佈對其他 Android Enterprise 模式的支援。**

在 Android 上部署 Microsoft Defender for Endpoint 是透過 Microsoft Intune (MDM) 。
如需詳細資訊，請參閱[在 Android 上使用 Microsoft Intune 部署 Microsoft Defender For Endpoint](android-intune.md)。


> [!NOTE]
> **在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 上現在可以使用 Android 上的 Microsoft Defender for Endpoint。** <br> 您可以從 Intune 連線到 Google，以部署 Microsoft Defender for Endpoint 應用程式、跨裝置管理員和 Android Enterprise entrollment 模式。 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上設定 Microsoft Defender for Endpoint

設定 android 功能上的 [microsoft](android-configure.md)defender for endpoint，可取得如何針對 android 功能設定 microsoft Defender for endpoint 功能的指導方針。



## <a name="related-topics"></a>相關主題
- [在 Android 上使用 Microsoft Intune 部署適用於端點的 Microsoft Defender](android-intune.md)
- [在 Android 上設定適用於端點的 Microsoft Defender 功能](android-configure.md)

