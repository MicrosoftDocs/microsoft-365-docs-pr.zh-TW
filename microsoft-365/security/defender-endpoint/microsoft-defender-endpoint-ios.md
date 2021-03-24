---
title: iOS 的 Microsoft Defender ATP 簡介
ms.reviewer: ''
description: 說明如何為 iOS 安裝及使用 Microsoft Defender ATP
keywords: microsoft，defender，atp，ios，綜述，安裝，部署，卸載，intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e5aae9dcb361caf9133c1270a16711fc43033bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059404"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a>用於 iOS 的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

適用于 **iOS 的 Microsoft Defender for** a，可提供網站、電子郵件及應用程式的網路釣魚和不安全網路連線防護。 所有提醒都會透過 Microsoft Defender Security Center 中的單一玻璃窗格獲得。 入口網站讓安全性小組能夠集中查看 iOS 裝置上的威脅及其他平臺。

> [!CAUTION]
> 對 iOS 執行其他協力廠商端點保護產品及 Defender for Endpoint，都可能會造成效能問題和不可預期的系統錯誤。

## <a name="pre-requisites"></a>先決條件

**使用者的**

- 指派給使用者 (s) 的 Microsoft Defender Endpoint 授權。 請參閱 [Microsoft Defender Endpoint 授權需求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- 裝置 (s) 會透過 Intune 公司入口網站應用程式進行 [註冊](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) ，以強制執行 Intune 裝置的相容性原則。 這需要將使用者指派為 Microsoft Intune 授權。
    - 您可以從 [Apple 應用程式存放區](https://apps.apple.com/us/app/intune-company-portal/id719171358)下載 Intune 公司入口網站。
    - 請注意，Apple 不允許重新導向使用者從應用程式存放區下載其他應用程式，因此必須在使用者執行此步驟後，才能上架至 Microsoft Defender for Endpoint 應用程式。

- 如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**針對系統管理員**

- 存取 Microsoft Defender Security Center 入口網站。

    > [!NOTE]
    > Microsoft Intune 是唯一支援的行動裝置管理 (MDM) 方案，可為 iOS 部署 Microsoft Defender for Endpoint。 目前只有已註冊的裝置才支援在 Intune 中強制執行 iOS 相關裝置規範原則的端點。

- 存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，將應用程式部署至組織中已註冊的使用者群組。

**系統需求**

- 執行 iOS 11.0 和更新版本的裝置 iOS。 iPad 裝置從版本 1.1.15010101 + 正式支援。

- 已使用 [Intune 公司入口網站](https://apps.apple.com/us/app/intune-company-portal/id719171358)註冊裝置。

> [!NOTE]
> **Microsoft Defender ATP (用於 iOS 的端點) 現在可用於 [Apple App Store](https://aka.ms/mdatpiosappstore)。**

## <a name="installation-instructions"></a>安裝指示

透過 Microsoft Intune (MDM) 部署 Microsoft Defender for iOS，並支援受監視和 unsupervised 裝置。
如需詳細資訊，請參閱為 [IOS 部署 Microsoft Defender For Endpoint](ios-install.md)。

## <a name="resources"></a>資源

- 請造訪我們的 [博客](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)，以及時瞭解即將推出的版本。

- 透過應用程式內的意見反應系統或透過[SecOps 入口網站](https://securitycenter.microsoft.com)提供意見反應

## <a name="next-steps"></a>後續步驟

- [為 iOS 部署 Microsoft Defender for Endpoint](ios-install.md)
- [設定 iOS 功能端點的 Microsoft Defender](ios-configure-features.md)