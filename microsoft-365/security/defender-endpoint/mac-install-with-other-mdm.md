---
title: 使用不同的行動裝置管理來部署 (MDM) 系統（適用于 Mac 的 Microsoft Defender ATP）
description: 在其他管理解決方案上安裝適用于 Mac 的 Microsoft Defender ATP。
keywords: microsoft，defender，atp，mac，安裝，deploy，macos，catalina，mojave，high 塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 28e57f1749ea9dce22e1a8a210f73cc3c7993738
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059683"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a>使用不同的行動裝置管理來進行部署 (MDM) 系統（適用于 Mac 的 Microsoft Defender for Endpoint）

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>必要條件和系統需求

開始之前，請參閱 [《 Microsoft Defender For Mac 的主要端點」頁面](microsoft-defender-endpoint-mac.md) ，以取得目前軟體版本之必要條件和系統需求的描述。

## <a name="approach"></a>方法

> [!CAUTION]
> 目前，Microsoft oficially 只支援 Intune 和 JAMF，以進行 Microsoft Defender for Mac 的部署和管理。 Microsoft 對本所提供的資訊不提供任何明示或默示的保證。

如果您的組織使用的行動裝置管理 (未正式支援的 MDM) 解決方案，這並不表示您無法為 Mac 部署或執行 Microsoft Defender for Endpoint。

適用于 Mac 的 Microsoft Defender 不取決於任何廠商特有的功能。 它可搭配任何支援下列功能的 MDM 解決方案使用：

- 將 pkg macOS 部署到受管理的裝置。
- 將 macOS 系統設定檔部署到受管理的裝置。
- 在受管理的裝置上執行任何系統管理員設定的工具/腳本。

大多數新式的 MDM 解決方案都包含這些功能，但它們可能會以不同的方式呼叫這些功能。

您可以從前述清單的最後一個必要條件，部署 Defender，但不具備下列各項：

- 您將無法以集中式方式收集狀態
- 如果您決定卸載 Defender，您必須以系統管理員身分登入用戶端裝置。

## <a name="deployment"></a>部署

大部分的 MDM 解決方案都使用相同的模型來管理 macOS 裝置，具有類似的術語。 使用以 [JAMF 為基礎的部署](mac-install-with-jamf.md) 做為範本。

### <a name="package"></a>套件

設定 [必要應用程式套件](mac-install-with-jamf.md)的部署，安裝套件 (wdav pkg) 從 [Microsoft Defender Security Center](mac-install-with-jamf.md)下載。

若要將套件部署至您的企業，請使用 MDM 解決方案相關聯的指示。

### <a name="license-settings"></a>授權設定

設定 [系統設定檔](mac-install-with-jamf.md)。 您的 MDM 解決方案可能會呼叫它像是「自訂設定設定檔」，因為 Mac 版端點的 Microsoft Defender 不是 macOS 的一部分。

使用 [屬性] 清單中的 jamf/WindowsDefenderATPOnboarding plist，可從 [Microsoft Defender 安全中心](mac-install-with-jamf.md)下載的上架套件中解壓縮。
您的系統可能支援 XML 格式的任意屬性清單。 在該情況下，您可以上傳 jamf/WindowsDefenderATPOnboarding plist 檔案。
或者，您可能需要先將屬性清單轉換成不同的格式。

通常，您的自訂設定檔具有識別碼、name 或 domain 屬性。 您必須嚴格使用此值的 "wdav"。
MDM 使用它將設定檔案部署至用戶端裝置上的 **/Library/Managed 偏好設定 wdav** ，而 Defender 使用此檔案載入上架資訊。

### <a name="kernel-extension-policy"></a>內核擴充原則

設定 KEXT 或內核擴充原則。 使用小組識別碼 **UBF8T346G9** ，允許 Microsoft 提供的內核擴充。

### <a name="system-extension-policy"></a>系統擴充原則

設定系統擴充原則。 使用小組識別碼 **UBF8T346G9** 及核准下列的束識別碼：

- wdav epsext
- wdav netext

### <a name="full-disk-access-policy"></a>完整磁片存取原則

授與下列元件的完整磁片存取權：

- 適用於端點的 Microsoft Defender
    - 識別碼： `com.microsoft.wdav`
    - 識別碼類型：束識別碼
    - 程式碼需求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender for Endpoint 安全性擴充
    - 識別碼： `com.microsoft.wdav.epsext`
    - 識別碼類型：束識別碼
    - 程式碼需求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>網路擴充原則

做為端點偵測和回應功能的一部分，Mac 版端點的 Microsoft Defender 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。 下列原則允許網路分機執行這項功能。

- 篩選類型：外掛程式
- 外掛程式捆綁識別碼： `com.microsoft.wdav`
- 篩選資料提供者束識別碼： `com.microsoft.wdav.netext`
- 篩選資料提供者指定的需求： `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- 篩選通訊端： `true`

## <a name="check-installation-status"></a>檢查安裝狀態

在用戶端裝置上執行 [Microsoft Defender For Endpoint](mac-install-with-jamf.md) 以檢查上架狀態。