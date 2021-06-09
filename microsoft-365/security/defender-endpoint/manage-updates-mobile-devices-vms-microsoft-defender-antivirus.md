---
title: 定義移動裝置的更新方式 Microsoft Defender 防毒軟體
description: 管理行動裝置（例如膝上機）應如何更新 Microsoft Defender 防毒軟體保護更新。
keywords: 更新，保護，排程更新，電池，行動裝置，膝上型電腦，筆記本，自願加入，microsoft update，wsus，覆寫
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269537"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>管理行動裝置和虛擬機器 (VM) 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

行動裝置和 Vm 可能需要更多設定，以確保更新不會影響效能。

這些裝置有兩個可用的設定：

- 在未使用 WSUS 連線的情況下，在行動電腦上加入宣告 Microsoft 更新
- 在使用電池電源時防止安全性智慧更新

下列文章在下列情況中也會很有用：
- [設定排程和追趕掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [虛擬桌面基礎結構 (VDI) 環境中 Microsoft Defender 防毒軟體的部署指南](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>在未使用 WSUS 連線的情況下，在行動電腦上加入宣告 Microsoft 更新

當行動裝置未連接到公司網路或沒有 WSUS 連線時，您可以使用 Microsoft Update，將其上的安全性智慧保持在最新狀態的移動 Microsoft Defender 防毒軟體裝置上。 

這表示即使您已將 WSUS 設定為覆寫 Microsoft Update，也可以透過 Microsoft Update) 將保護更新傳送至裝置 (。

您可以採用下列其中一種方式，選擇參加行動裝置上的 Microsoft 更新：

- 使用群組原則變更設定。
- 使用 VBScript 建立腳本，然後在網路中的每一部電腦上執行。
- 透過 **設定** 功能表，在網路上的每一部電腦上手動選擇。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>使用群組原則加入宣告 Microsoft 更新

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 選取 [ **原則** ]，然後選取 [ **管理範本**]。

4. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **簽名更新**。

5. 將 [ **允許 Microsoft 更新的安全性智慧更新** ] 設定為 [ **啟用**]，然後選取  **[確定]**。


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>使用 VBScript 加入宣告 Microsoft Update

1. 使用 MSDN 文章 [加入宣告 Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 中的指示來建立 VBScript。

2. 在您的網路中的每一部電腦上執行您所建立的 VBScript。

### <a name="manually-opt-in-to-microsoft-update"></a>手動加入宣告 Microsoft Update

1. 在您想要加入的電腦上，在 [**更新 & 安全性** 設定] 中開啟 **Windows 更新**。

2. 選取 [ **高級** 選項]。

3. 選取在 **更新 Windows 時，提供其他 Microsoft 產品更新** 的核取方塊。

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>在使用電池電源時防止安全性智慧更新

您可以設定 Microsoft Defender 防毒軟體，只在電腦連線至有線電源時，才下載保護更新。 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>使用群組原則防止在電池電源上進行安全性情報更新

1.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，選擇您要設定的群組原則物件，然後開啟以供編輯。

2.  在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3.  選取 [ **原則** ]，然後選取 [ **管理範本**]。

4.  展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體** 簽章  >  **更新**，然後設定 **在使用電池供電時**（停用）為 **停用** 時，允許安全性智慧更新。 然後選取 **[確定]**。 

當電腦使用電池電源時，此動作可防止下載保護更新。

## <a name="related-articles"></a>相關文章

- [管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [更新和管理 Windows 10 中的 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)