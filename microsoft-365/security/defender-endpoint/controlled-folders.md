---
title: 保護來自勒索軟體的重要資料夾，使其無法使用可控資料夾存取權加密您的檔案
description: 您可以防止惡意應用程式變更預設資料夾中的檔案。 防止勒索軟體加密您的檔案。
keywords: 受控制的資料夾存取、windows 10、windows defender、勒索軟體、保護、檔案、資料夾
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ae50d53fbc9bf01d4cd16b939461eecc9ec1a568
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165174"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>使用受控資料夾存取權來保護重要資料夾

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>何謂受控制的資料夾存取？

控制的資料夾存取可協助保護您的重要資料免受惡意應用程式和威脅（例如勒索軟體）的威脅。 「受管理的資料夾存取」會透過已知的受信任應用程式清單來檢查應用程式，以保護您的資料。 在 Windows Server 2019 和 Windows 10 用戶端上受支援，可使用受管理裝置的 Windows 安全性 App、Microsoft 端點設定管理員或 Intune (，開啟受控資料夾存取權) 。 

> [!NOTE]
> 腳本引擎是不受信任的，您無法允許他們存取受控制的受保護資料夾。  例如，即使您允許使用 [憑證及檔指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)，「受控資料夾存取」也不會信任 PowerShell。 

「受管理的資料夾存取」最適合使用 [Microsoft Defender For Endpoint](microsoft-defender-advanced-threat-protection.md)」，可讓您在一般 [警示調查案例](investigate-alerts.md)中深入報告，以進行受控資料夾存取事件和區塊。

> [!TIP]
> [受管理的資料夾存取封鎖] 不會在 [ [警示] 佇列](alerts-queue.md)中產生警示。 不過，您可以在 [裝置時程表視圖](investigate-machines.md)中，使用 [高級搜尋](advanced-hunting-overview.md)或 [自訂偵測規則](custom-detection-rules.md)，查看受控資料夾存取模組的相關資訊。

## <a name="how-does-controlled-folder-access-work"></a>控制資料夾存取的運作方式？

「受管理的資料夾存取」的運作方式只有允許信任的應用程式存取受保護的資料夾。 設定受控制的資料夾存取權時，會指定受保護的資料夾。 通常使用的資料夾（如用於檔、圖片、下載專案等的資料夾）會包含在受管理的資料夾清單中。 

「受管理的資料夾存取」可與受信任的應用程式清單搭配使用。 受信任軟體清單中包含的應用程式如預期般運作。 未包含在清單中的應用程式，無法對受保護的資料夾內的檔案進行任何變更。 

根據使用者的流行和聲譽，將應用程式新增至清單。 您整個組織中高度流行且從未顯示任何視為惡意行為的應用程式，都會視為可信。 這些應用程式會自動新增至清單。

您也可以使用 Configuration Manager 或 Intune，將應用程式手動新增至信任清單。 您可以從 [安全性中心] 主控台執行其他動作（例如新增應用程式 [的檔案指標](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) ）。

## <a name="why-controlled-folder-access-is-important"></a>控制資料夾存取很重要的原因

在協助保護您的 [勒索軟體](https://www.microsoft.com/wdsi/threats/ransomware)中的檔和資訊時，可控制的資料夾存取特別有用。 在勒索軟體攻擊中，您的檔案可能會被加密並保留 hostage。 在就地進行「可控資料夾存取」時，會在應用程式嘗試對受保護資料夾中的檔案進行變更的電腦上顯示通知。 您可以 [自訂](customize-attack-surface-reduction.md#customize-the-notification) 您公司詳細資料和連絡人資訊的通知。 您也可以個別啟用規則，以自訂功能所監視的技巧。

[ [受保護的資料夾](#review-controlled-folder-access-events-in-windows-event-viewer) ] 包括常見的系統資料夾， (包括「開機磁區」) ，而且您可以 [新增更多資料夾](customize-controlled-folders.md#protect-additional-folders)。 您也可以 [讓應用程式](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 能夠存取受保護的資料夾。

您可以使用 [審計模式](audit-windows-defender.md) ，評估當組織啟用時，受控資料夾存取會如何影響您的組織。 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 參觀 Windows Defender Test 基礎網站，確認該功能是否正常運作，並查看其運作方式。

下列 Windows 版本支援受控制的資料夾存取：
- [Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 和更新版本
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>預設會保護 Windows 系統資料夾

Windows 系統資料夾預設會受到保護，另外還有其他一些資料夾： 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> 您可以將其他資料夾設定為受保護，但您無法移除預設會受保護的 Windows 系統資料夾。

## <a name="requirements-for-controlled-folder-access"></a>受控資料夾存取的需求

受控制的資料夾存取需要啟用 [Microsoft Defender 防病毒即時保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>在 Microsoft Defender 安全中心檢查受控資料夾存取事件

當事件和區塊成為其 [警示調查案例](investigate-alerts.md)的一部分時，它會提供端點的詳細報告。

您可以使用 [ [高級搜尋](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)] 查詢 Microsoft Defender 的端點資料。 如果您使用的是「 [審核」模式](audit-windows-defender.md)，您可以使用 [高級搜尋](advanced-hunting-overview.md) 查看受控制的資料夾存取設定如何影響環境（如果已啟用）。

例如查詢：

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中檢查受控資料夾存取事件

您可以查看 Windows 事件記錄檔，以查看當控制的資料夾存取封鎖 (或) 應用程式進行審核時所建立的事件：

1. 下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。
2. 在 [開始] 功能表中輸入 **事件檢視器** ，以開啟 Windows 事件檢視器。
3. 在左窗格的 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。
4. 流覽至解壓縮 *cfa-events.xml* 的位置，然後選取。 或者， [直接複製 XML](event-views.md)。
5. 選取 [確定]。

下表顯示與受控資料夾存取相關的事件：

|事件識別碼 | 描述 |
|:---|:---|
|5007 | 設定變更時的事件 |
|1124 | 已審核的受管理資料夾存取事件 | 
|1123 | 封鎖的受管理資料夾存取事件 |

## <a name="view-or-change-the-list-of-protected-folders"></a>查看或變更受保護的資料夾清單

您可以使用 Windows 安全性應用程式來查看受控制的資料夾存取所保護的資料夾清單。 

1. 在您的 Windows 10 裝置上，開啟 [Windows 安全性應用程式]。
2. 選取 [ **病毒 & 威脅防護**]。
3. 在 [ **勒索軟體防護**] 底下，選取 [ **管理勒索軟體防護**]。
4. 如果已關閉受管理的資料夾存取，您必須將其開啟。 選取 [ **受保護的資料夾**]。
5. 請執行下列其中一個步驟：
   - 若要新增資料夾，請選取 [ **+ 新增受保護的資料夾**]。
   - 若要移除資料夾，請選取它，然後選取 [ **移除**]。 

> [!NOTE]
> [Windows 系統資料夾](#windows-system-folders-are-protected-by-default) 預設會受到保護，您無法將其從清單中移除。

## <a name="see-also"></a>另請參閱

- [評估受控資料夾存取權](evaluate-controlled-folder-access.md)
- [自訂受控資料夾存取](customize-controlled-folders.md)
- [保護更多資料夾](customize-controlled-folders.md#protect-additional-folders)
