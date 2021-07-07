---
title: 非 Windows 平台版適用於端點的 Microsoft Defender
description: 瞭解適用于非 Windows 平臺的 Microsoft Defender for Endpoint 功能
keywords: 非 windows，mac，macos，linux，android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4793f3c84ddda0db7f4d67ac96cb31a6e2108c57
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326996"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>非 Windows 平台版適用於端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft 已在 Windows 和 Windows Server 之外擴充其業界領先的端點安全性功能，以 macOS、Linux、Android 及 iOS。

組織面臨不同平臺和裝置的威脅。 我們的小組致力於建立並非 microsoft *的* 安全性解決方案，但 *在* microsoft 也致力於讓客戶能夠保護和保護其異構環境。 我們正在聆聽客戶的意見反應，並與我們的客戶密切合作，以建立符合其需求的解決方案。

透過 Microsoft Defender for Endpoint，客戶可以從 Microsoft Defender 資訊安全中心、跨 Windows 和非 Windows 平臺的所有威脅和警示統一的觀點中受益，讓他們能取得環境中發生什麼事的完整畫面，讓他們能夠更快速地評估及回應威脅。

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS 上適用於端點的 Microsoft Defender 

macOS 上的 Microsoft Defender for endpoint 提供了防毒軟體、端點偵測和回應 (EDR) 及弱點管理的最新發行版本本功能。 客戶可以透過 Microsoft 端點管理員和 Jamf 來部署及管理解決方案。 就像 macOS 上的 Microsoft Office 應用程式一樣，microsoft 自動更新是用來管理 Mac 更新上的 microsoft Defender for Endpoint。 如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。

如需如何開始的詳細資訊，請造訪 macOS [檔](microsoft-defender-endpoint-mac.md)上的 Defender for Endpoint。

>[!NOTE]
>MacOS 端點上目前不支援下列功能：
>- 資料外洩防護
>- 即時回應
>- SIEM


## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 上適用於端點的 Microsoft Defender

linux 上的 Microsoft Defender for endpoint 會提供預防性 (AV) 、端點偵測和回應 (EDR) ，以及 Linux 伺服器的弱點管理功能。 這包括完整的命令列體驗，可供您設定及管理代理程式、起始掃描及管理威脅。 我們支援最常見的六個舊版 Linux 伺服器發行： RHEL 7.2 +、CentOS Linux 7.2 +、Ubuntu 16 LTS 或更高 LTS、SLES 12 +、Debian 9 + 及 Oracle Linux 7.2。 您可以使用 Puppet、Ansible 或使用現有的 Linux 設定管理工具，部署及設定 Linux 上的 Microsoft Defender for Endpoint。 如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。

如需如何開始的詳細資訊，請流覽 Linux [檔](microsoft-defender-endpoint-linux.md)上的 Microsoft Defender for Endpoint。

>[!NOTE]
>在 Linux 端點上目前不支援下列功能：
>- 資料外洩防護
>- 即時回應
>- SIEM



## <a name="microsoft-defender-for-endpoint-on-android"></a>Android 上適用於端點的 Microsoft Defender

Android 上的 Microsoft Defender for Endpoint 是我們的行動威脅防護解決方案，適用于執行 Android 6.0 和更高版本的裝置。 同時支援 Android Enterprise (的工作設定檔) 和裝置管理員模式。 在 Android 上，我們提供 web 保護，包括反網路釣魚、封鎖不安全的連線，以及自訂指示器的設定。 解決方案會將惡意程式碼和潛在有害的應用程式掃描 (PUA) ，並透過與 Microsoft 端點管理員和條件式存取的整合，提供額外的侵犯防護功能。 如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。

如需如何開始的詳細資訊，請流覽 Android [檔](microsoft-defender-endpoint-android.md)上的 Microsoft Defender for Endpoint。

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 上適用於端點的 Microsoft Defender

IOS 的 Microsoft Defender for Endpoint 是我們的行動威脅防護解決方案，適用于執行 iOS 11.0 和更高版本的裝置。 支援受監視和 Unsupervised 裝置。 在 iOS 上，我們提供 web 保護，包括反網路釣魚、封鎖不安全的連線，以及設定自訂指示器。 如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。 

如需如何開始的詳細資訊，請流覽 iOS [檔](microsoft-defender-endpoint-ios.md)上的 Microsoft Defender for Endpoint。

## <a name="licensing-requirements"></a>授權需求 

合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。 Microsoft Defender for Endpoint 也可從雲端解決方案提供者 (CSP) 購買。

客戶可以透過獨立 microsoft defender for endpoint 授權，在 macOS 取得 microsoft defender for endpoint，也可以在 Microsoft 365 A5/E5 或 Microsoft 365 安全性] 中取得。

在 Android 和 iOS 上的 Microsoft Defender for Endpoint 的最近宣告功能，包含在適用于合格授權使用者之五個合格裝置的一部分中。

您可以透過適用于商業及教育版客戶的 Defender for Endpoint Server SKU，取得 Linux 上的 defender for Endpoint。

如需定價及其他資格需求，請與您的帳戶小組或 CSP 聯繫。
