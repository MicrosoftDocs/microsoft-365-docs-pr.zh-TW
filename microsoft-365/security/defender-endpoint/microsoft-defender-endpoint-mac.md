---
title: Mac 版 Microsoft Defender ATP
ms.reviewer: ''
description: 瞭解如何針對 Mac 安裝、設定、更新及使用 Microsoft Defender for Endpoint。
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 3e96cf09fd13a4d99546a1c18f9c61f40c362bf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057056"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a>Mac 版端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題說明如何安裝、設定、更新和使用適用于 Mac 的端點的 Defender。

> [!CAUTION]
> 執行其他協力廠商的 endpoint protection 產品及 Defender for Mac 的 Endpoint，都可能會導致效能問題和不可預期的副作用。 若非 Microsoft endpoint protection 是您環境中的絕對需求，則您仍然可以在將 Mac 防病毒功能設定為以 [被動式模式](mac-preferences.md#enable--disable-passive-mode)執行之前，放心地利用 MDATP FOR mac EDR 功能。

## <a name="whats-new-in-the-latest-release"></a>最新版本中的新功能

[Microsoft Defender for Endpoint 中的新功能](whats-new-in-microsoft-defender-atp.md)

[Mac 版端點的 Microsoft Defender 新增功能](mac-whatsnew.md)

> [!TIP]
> 如果您有任何想要分享的意見反應，請在您的裝置上開啟 Microsoft Defender for Mac 的端點，然後流覽以 **協助**  >  **傳送意見** 反應，以提交。

若要取得最新的功能，包括預覽功能 (例如 Mac 裝置的端點偵測和回應) ，請將執行 Microsoft Defender for Endpoint 的 macOS 裝置設定為「有問必答」裝置。

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a>如何針對 Mac 安裝 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必要條件

- 用於端點訂閱和 Microsoft Defender Security Center 入口網站存取權的 Defender
- macOS 和 BASH 腳本中的初級層級體驗
- 當手動部署時，裝置上的系統管理許可權 () 

### <a name="installation-instructions"></a>安裝指示

您可以使用數種方法和部署工具，為 Mac 安裝和設定 Defender。

- 協力廠商管理工具：
    - [以 Microsoft Intune 為基礎的部署](mac-install-with-intune.md)
    - [以 JAMF 為基礎的部署](mac-install-with-jamf.md)
    - [其他 MDM 產品](mac-install-with-other-mdm.md)

- 命令列工具：
    - [手動部署](mac-install-manually.md)

### <a name="system-requirements"></a>系統需求

這三個最新的 macOS 主要版本都支援。

> [!IMPORTANT]
> 在 macOS 11 (Big Sur) 上，Microsoft Defender for Endpoint 需要其他設定設定檔。 如果您是現有的客戶從舊版的 macOS 升級，請務必在 [MacOS Catalina 及更新版本的 macOS](mac-sysext-policies.md)上部署所列于新設定設定檔的其他設定檔。

> [!IMPORTANT]
> 10.13 年2月 15 2021 日 macOS， (高階) 的支援將會終止。

- 11 (大型 Sur) ，10.15 (Catalina) ，10.14 (Mojave) ，10.13 (高塞拉里昂) 
- 磁碟空間：1GB

不支援 Beta 版本的 macOS。

在您啟用服務之後，您可能需要設定網路或防火牆，以允許它和您的端點之間的輸出連線。

### <a name="licensing-requirements"></a>授權需求

適用于 Mac 的 microsoft Defender 端點需要下列其中一項 Microsoft 大量授權服務：

- Microsoft 365 E5 (M365 E5) 
- Microsoft 365 E5 安全性
- Microsoft 365 A5 (M365 A5) 

> [!NOTE]
> 合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。
> Microsoft Defender for Endpoint 也可從雲端解決方案供應商購買 (CSP) 。 透過 CSP 購買時，不需要列出 Microsoft 大量授權提供者。

### <a name="network-connections"></a>網路連線

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取，否則您可能需要為他們建立一個 *允許* 規則。



|**網域清單的試算表**|**描述**|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | 服務位置、地理位置和作業系統的特定 DNS 記錄試算表。 <br><br>在這裡下載試算表： [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)。

Microsoft Defender for Endpoint 可使用下列探索方法探索 proxy 伺服器：
- Proxy 自動設定 (PAC) 
- Web Proxy 自動探索通訊協定 (WPAD) 
- 手動靜態 proxy 設定

如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。

> [!WARNING]
> 不支援已驗證的 proxy。 確定只使用 PAC、WPAD 或靜態 proxy。
>
> 出於安全性原因，也不支援 SSL 檢查和截取 proxy。 設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接將 Microsoft Defender for Mac 的資料傳遞至相關的 URLs，而不需要截獲。 將您的截取憑證新增至全域存放區將不允許截取。

若要測試連接未封鎖，請 [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) 在瀏覽器中開啟和。

如果您傾向使用命令列，您也可以在終端中執行下列命令，以檢查連線：

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

此命令的輸出應類似下列所示：

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> 建議您在用戶端裝置上啟用 [系統完整性保護](https://support.apple.com/en-us/HT204899) (SIP) 。 SIP 是內建的 macOS 安全性功能，可防止對作業系統的低層級篡改，且預設為啟用。

安裝 Microsoft Defender for Endpoint 後，可在 Terminal 中執行下列命令來驗證連線：
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a>如何更新 Mac 版的 Microsoft Defender 端點

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。 若要更新 Microsoft Defender for Mac 的端點，使用名為 Microsoft AutoUpdate (MAU) 的程式。 若要深入瞭解，請參閱 [Deploy Microsoft Defender For Mac For Endpoint 的更新](mac-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a>如何針對 Mac 設定 Microsoft Defender for Endpoint

有關如何在企業環境中設定產品的指引，可在 [設定 Microsoft Defender For Mac 的首選項中取得](mac-preferences.md)。

## <a name="macos-kernel-and-system-extensions"></a>macOS 內核和系統擴充

隨著 macOS 演變，我們準備好 Microsoft Defender for Mac 更新，以利用系統擴充，而不是核心擴充。 如需相關的詳細資訊，請參閱 [Microsoft Defender For Mac 的新功能](mac-whatsnew.md)。

## <a name="resources"></a>資源

- 如需有關記錄、卸載或其他主題的詳細資訊，請參閱適用于 [Mac 的 Microsoft Defender 端點資源](mac-resources.md)。

- 適用于[Mac 的 Microsoft Defender 端點隱私權](mac-privacy.md)。