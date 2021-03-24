---
title: '適用于 Mac 的 Microsoft Defender ATP-系統擴充 (預覽) '
description: 本文包含如何試用 Microsoft Defender ATP for Mac 之系統擴充功能的指示。 這項功能目前是公開預覽。
keywords: microsoft，defender，atp，mac，內核，系統，分機，catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 8b644e27c5a36d2175ab18ae92424e7c70f39d0f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057376"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a>適用于 Mac 的 Microsoft Defender for Mac-系統擴充公開預覽) 

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

隨著 macOS 演變，我們準備好使用系統擴充（而非核心擴充）的 Defender for Mac 更新。 此更新只會套用至 macOS Catalina (10.15.4) 和更新版本的 macOS。

這項功能目前是公開預覽。 本文說明如何在您的裝置上啟用此功能。 您可以在您自己的裝置上本機嘗試此功能，或透過管理工具來遠端設定此功能。

這些步驟假設您已在裝置上執行的是 Defender for Endpoint。 如需詳細資訊，請參閱[此頁面](microsoft-defender-endpoint-mac.md)。

## <a name="known-issues"></a>已知問題

- 我們收到干擾使用 Apple SSO Kerberos 擴充的網路分機報告。
- 目前版本的產品仍然會安裝內核擴充。 內核副檔名只會做為回退機制使用，並會在此功能到達公開預覽之前移除。
- 我們仍在 macOS 11 大的 Sur 上部署並運作的產品版本。

## <a name="deployment-prerequisites"></a>部署必要條件

- 最低 macOS 作業系統版本： **10.15.4**
- 產品版本下限： **101.03.73**
- 您的裝置必須在「 **內幕 Fast 更新」通道** 中。 您可以使用下列命令來檢查更新通道：

  ```bash
  mdatp health --field release_ring
  ```

  如果您的裝置還沒有在「有問必答 Fast 更新」通道中，請從終端執行下列命令。 通道更新會在下一次產品開始時 (會在安裝下一個產品更新時或重新開機裝置) 時生效。

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  或者，如果您處在受管理的環境 (JAMF 或 Intune) 中，您可以從遠端設定更新通道。 如需詳細資訊，請參閱 [部署 Microsoft DEFENDER ATP For Mac 的更新：設定通道名稱](mac-updates.md#set-the-channel-name)。

## <a name="deployment-steps"></a>部署步驟

遵循與您的環境對應的部署步驟，以及您嘗試此功能的慣用方法。

### <a name="manual-deployment"></a>手動部署

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a>核准系統擴充和啟用網路分機

1. 在所有部署必要條件都符合後，請重新開機裝置以啟動系統分機核准和啟用程式。

   您將會看到一系列的系統提示，以核准用於端點系統擴充的 Defender。 您必須核准該數列的 **所有** 提示，因為 macOS 需要明確核准每個副檔名（適用于 Mac 的 Endpoint for Mac 在裝置上安裝）。
   
   針對每個核准，選取 [ **開啟安全性喜好** 設定]，然後選取 [ **允許** 系統分機] 以執行。

   > [!IMPORTANT]
   > 您必須先關閉並重新開啟 **系統偏好** 設定  >  **安全性 & 隱私權** 視窗的後續核准。 否則，macOS 不會顯示下一個核准。

   > [!IMPORTANT]
   > 在產品回到內核擴充之前有一分鐘的超時。 這可確保裝置受到保護。
   >
   > 如果經歷超過一分鐘，請重新開機此裝置或使用 `sudo killall -9 wdavdaemon` 以重新觸發核准流程以重新開機守護程式。

   ![系統分機核准快顯視窗](images/mac-system-extension-approval.png)

   ![系統延伸核准視窗](images/mac-system-extension-pref.png)

1. 批准系統擴充後，macOS 會提示您核准是否允許篩選網路流量。 按一下 [ **允許**]。

   ![網路分機核准快顯視窗](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a>授與對端點安全性系統擴充的完整磁片存取權

開啟 [**系統喜好** 設定  >  **安全性 & 隱私權**  >  **隱私權**] 索引標籤，並授與 **Microsoft Defender 端點安全性分機** 的 **完整磁片存取權**。

![針對端點安全性系統擴充的完整磁片存取權](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a>重新開機裝置

為了使變更生效，您必須重新開機裝置。

#### <a name="verify-that-the-system-extensions-are-running"></a>確認系統擴充模組正在執行中

從終端執行下列命令：

```bash
mdatp health --field real_time_protection_subsystem
```

終端輸出 `endpoint_security_extension` 指出產品使用的是系統擴充功能。

### <a name="managed-deployment"></a>受管理的部署

請參閱 [新的設定設定檔，以取得 MacOS Catalina 和更新版本的 macOS： JAMF](mac-sysext-policies.md#jamf) 的新設定設定檔，您必須為此新功能部署。

除了這些設定檔之外，請務必將目標裝置設定為「內幕人士快速更新」通道（如 [部署必要條件](#deployment-prerequisites)中所述）。

在符合所有必要條件且已部署新設定設定檔的裝置上，執行下列命令：

```bash
$ mdatp health --field real_time_protection_subsystem
```

如果此命令會列印出來 `endpoint_security_extension` ，表示產品使用的是系統擴充功能。

## <a name="validate-basic-scenarios"></a>驗證基本案例

1. 針對電腦防病毒研究 (EICAR.TXT) 偵測測試歐洲研究所。 在終端視窗中，執行下列命令：

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   確認 EICAR.TXT 檔案已隔離。 您可以使用下列命令，在使用者介面中的 [保護史] 頁面上，或從命令列驗證檔案的狀態：

    ```bash
    mdatp threat list
    ```

2. 測試 (EDR) DIY 案例的端點偵測和回應。 在終端視窗中，執行下列命令：

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   在 EICAR.TXT 和 EDR DIY 案例的 [機器] 頁面上，驗證入口網站上是否彈出兩個警示。

## <a name="frequently-asked-questions"></a>常見問題集

- 問：為什麼我 `kernel_extension` 在執行時仍然會看到 `mdatp health --field real_time_protection_subsystem` ？

    A：請參閱「 [部署先決條件](#deployment-prerequisites) 」一節，並仔細檢查是否符合所有必要條件。 若所有先決條件皆已符合，請重新開機裝置，然後再檢查一次。

- 問：何時 macOS 11 大的 Sur 是受支援的？

    A：我們積極致力於為 macOS 11 新增支援。 我們將會在 [ [新功能](mac-whatsnew.md) ] 頁面上發佈其他資訊。
