---
title: Microsoft Defender for Endpoint 的基本需求
description: 瞭解上架裝置對服務的授權需求和需求
keywords: 最低需求、授權、比較表
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1b203a29083aaa4a1f86abcd7e2c7b24bd63f186
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445741"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的基本需求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


對服務上架裝置的一些基本需求。 深入瞭解授權、硬體和軟體需求，以及對服務的板載裝置的其他設定。

> [!TIP]
> - 深入瞭解 endpoint for endpoint the defender 的最新增強功能： [defender For Endpoint 社區](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。
> - 在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。 Read： [來自 MITRE ATT 的 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

## <a name="licensing-requirements"></a>授權需求
Microsoft Defender for Endpoint 需要下列其中一個 Microsoft 大量授權服務：

- Windows 10 企業版 E5
- Windows 10 教育版 A5
- Microsoft 365 E5 (M365 E5) 包含 Windows 10 企業版 E5
- Microsoft 365 A5 (M365 A5) 
- Microsoft 365 E5 安全性
- Microsoft 365 A5 安全性
- 適用於端點的 Microsoft Defender

> [!NOTE]
> 合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。
> Microsoft Defender for Endpoint 也可從雲端解決方案供應商購買 (CSP) 。
> RDSH Vm 不需要個別的 Defender for Endpoint 授權。

伺服器的 Microsoft Defender 端點需要下列其中一個授權選項：

- [啟用 Azure Defender 的 azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender for Server (每個伺服器) 一個伺服器的端點

> [!NOTE]
> 如果伺服器具有至少一或多個下列使用者授權的最低50授權，則每個伺服器的伺服器作業系統環境都可取得伺服器授權 ( (OSE) ) 的 Microsoft Defender for server。
>
> * 適用於端點的 Microsoft Defender
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 安全性

如需詳細的授權資訊，請參閱 [產品條款網站](https://www.microsoft.com/licensing/terms/) ，與您的帳戶小組合作以深入瞭解條款與條件。

如需 Windows 10 版中功能陣列的詳細資訊，請參閱 [比較 Windows 10 edition](https://www.microsoft.com/windowsforbusiness/compare)。

如需 Windows 10 商業版比較的詳細比較表，請參閱 [比較 PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)。

## <a name="browser-requirements"></a>瀏覽器需求
您可以透過瀏覽器來存取端點，以支援下列瀏覽器：

- Microsoft Edge
- Google Chrome

> [!NOTE]
> 雖然其他瀏覽器可能會運作，但上述瀏覽器也是支援的瀏覽器。


## <a name="hardware-and-software-requirements"></a>硬體及軟體需求

### <a name="supported-windows-versions"></a>支援的 Windows 版本
- Windows 7 SP1 Enterprise ([需要 ESU 以取得支援服務](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。 ) 
- Windows 7 SP1 Pro ([需要 ESU 以取得支援服務](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。 ) 
- Windows 8.1 企業版
- Windows 8.1 專業版
- Windows 10 企業版
- [Windows 10 企業版 LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 教育版
- Windows 10 專業版
- Windows 10 專業教育版
- Windows server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server，版本1803或更新版本
  - Windows Server 2019
- Windows 虛擬桌面

您的網路上的裝置必須執行下列其中一個版本。

針對支援的版本，裝置上之 Endpoint 的 Defender 的硬體需求是相同的。

> [!NOTE]
> 不支援執行行動 Windows mobile 版本 Windows 的機器 (例如 Windows CE 和 Windows 10 行動) 。
>
> 執行 Windows 10 企業版 2016 LTSB 的虛擬機器在非 Microsoft 虛擬化平臺上執行時，可能會遇到效能問題。
>
> 在虛擬環境中，我們建議使用 Windows 10 Enterprise LTSC 2019 或更新版本。


### <a name="other-supported-operating-systems"></a>其他支援的作業系統
- Android
- iOS
- Linux
- macOS

> [!NOTE]
> 您必須確認 Linux 的發行和版本的 Android、iOS 和 macOS 與您的電腦上的 Defender for Endpoint 相容，以供整合運作。



### <a name="network-and-data-storage-and-configuration-requirements"></a>網路和資料儲存區及設定需求
當您第一次執行 [上架] 嚮導時，必須選擇 Microsoft Defender 用於端點相關資訊的儲存位置：在歐盟、英國或美國資料中心。

> [!NOTE]
> - 您無法在第一次設定之後變更資料儲存位置。
> - 請參閱 [Microsoft Defender For Endpoint data storage and 隱私權](data-storage-privacy.md) ，以取得 microsoft 儲存資料的地點和方式的詳細資訊。


### <a name="diagnostic-data-settings"></a>診斷資料設定

> [!NOTE]
> 只要啟用，則 Microsoft Defender for Endpoint 不需要任何特定的診斷層級。

確定您組織中的所有裝置都已啟用診斷資料服務。
依預設，會啟用此服務。 請務必確認您會從這些位置取得感應器資料。

**使用命令列來檢查 Windows 10 診斷資料服務啟動類型**：

1. 在裝置上開啟已提升許可權的命令列提示：

   1.  轉至 **[開始]** 並鍵入 **「cmd」**。

   1.  以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

2. 輸入下列命令，然後按 **enter**：

   ```console
   sc qc diagtrack
   ```

   如果已啟用服務，結果應該如下列螢幕擷取畫面所示：

   ![Diagtrack 的 sc 查詢命令的結果](images/windefatp-sc-qc-diagtrack.png)


如果 **START_TYPE** 未設定為 **AUTO_START**，您必須將服務設定為自動啟動。


**使用命令列將 Windows 10 診斷資料服務設定為自動啟動：**

1.  在端點上開啟已提升許可權的命令列提示：

    1. 轉至 **[開始]** 並鍵入 **「cmd」**。

    1. 以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

2.  輸入下列命令，然後按 **enter**：

    ```console
    sc config diagtrack start=auto
    ```

3.  隨即顯示一則成功訊息。 輸入下列命令，然後按 **enter**，以確認變更：

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>網際網路連線能力
必須直接或透過 proxy，在裝置上的網際網路連線。

「！使用條款」的 Defender for Endpoint 感應器可以使用每日平均頻寬為 5 MB，以與 Endpoint 雲端服務和報告網路資料的 Defender 進行通訊。 在此每日平均頻寬中不會包含一項一次性活動，例如檔案上傳和調查套件集合。

如需其他 proxy 設定設定的詳細資訊，請參閱 [Configure device proxy And Internet connectivity settings](configure-proxy-internet.md)。

在您的板載裝置之前，必須先啟用診斷資料服務。 Windows 10 中預設會啟用此服務。


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender 防病毒設定需求
端點代理程式的 Defender 取決於 Microsoft Defender 防病毒掃描檔案的能力，並提供這些檔案的相關資訊。

在 Defender for Endpoint 裝置上設定安全性智慧更新，是否 Microsoft Defender 防病毒是使用中的反惡意程式碼。 如需詳細資訊，請參閱 [管理 Microsoft Defender 防病毒更新及套用基準](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

當 Microsoft Defender 防毒程式不是您組織中使用的反惡意程式碼，且您使用 Defender for Endpoint service 時，Microsoft Defender 防毒程式會進入被動模式。

如果您的組織已透過群組原則或其他方法關閉 Microsoft Defender 防病毒，則必須從此群組原則排除架裝置。

如果您是上架伺服器，而 Microsoft Defender 防毒軟體不是伺服器上使用中的反惡意程式碼，則 Microsoft Defender 防毒軟體必須設定為進入被動模式或已卸載。 設定取決於伺服器版本。 如需詳細資訊，請參閱 [Microsoft Defender 防毒程式相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。

> [!NOTE]
> 您的一般群組原則不會套用到防篡改保護，當防篡改保護開啟時，將會忽略對 Microsoft Defender 防病毒設定所做的變更。


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender 防病毒及早啟動反惡意程式碼 (ELAM) 驅動程式已啟用
如果您是在裝置上執行 Microsoft Defender 防毒軟體做為主要的反惡意軟體產品，端點代理程式的 Defender 代理程式就會順利地板載。

如果您正在執行協力廠商反惡意程式碼用戶端，並使用行動裝置管理解決方案或 Microsoft 端點管理員 (目前的分支) ，您必須確定已啟用 Microsoft Defender 防病毒 ELAM 驅動程式。 如需詳細資訊，請參閱 [確定原則未停用 Microsoft Defender 防病毒](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。


## <a name="related-topics"></a>相關主題
- [設定 Microsoft Defender for Endpoint 部署](production-deployment.md)
- [板載裝置](onboard-configure.md)
