---
title: 開啟網路保護
description: 使用「群組原則」、「PowerShell」或「行動裝置管理」及 Configuration Manager 來啟用網路保護。
keywords: ANetwork protection，乘虛攻擊，惡意網站，ip，網域，網域，啟用，開啟
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a513013c4b5f41cf95b876648882cb56ba818b32
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570993"
---
# <a name="turn-on-network-protection"></a>開啟網路保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[網路保護](network-protection.md) 可協助防止員工使用任何應用程式存取可能會在網際網路上主控網路釣魚詐騙、入侵和其他惡意內容的危險網域。 您可以在測試環境中 [審核網路保護](evaluate-network-protection.md) ，以查看在啟用之前將封鎖哪些應用程式。

[深入瞭解網路篩選設定選項](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>檢查是否已啟用網路保護

使用登錄編輯程式檢查是否已在本機裝置上啟用網路保護。

1. 選取工作列中的 [ **開始** ] 按鈕，然後輸入 **regedit** 開啟登錄編輯程式
1. 選擇側邊功能表中的 [ **HKEY_LOCAL_MACHINE**
1. 流覽嵌套的功能表至 **軟體**  >  **原則**  >  **Microsoft**  >  **Windows defender**  >  **windows defender 利用防護**  >  **網路保護**
1. 選取 [ **EnableNetworkProtection** ]，以查看裝置上目前的網路保護狀態。

    * 0或 **關閉**
    * 1或 **開啟**
    * 2或 **審計** 模式
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>啟用網路保護

使用下列任何一種方法來啟用網路保護：

* [PowerShell](#powershell)
* [移動裝置管理 (MDM) ](#mobile-device-management-mdm)
* [Microsoft 端點管理員/Intune](#microsoft-endpoint-manager-formerly-intune)
* [群組原則](#group-policy)

### <a name="powershell"></a>PowerShell

1. 在 [開始] 功能表中輸入 **powershell** ，以滑鼠右鍵按一下 [ **Windows PowerShell** ，然後選取 [以 **系統管理員身分執行**]
2. 輸入下列 Cmdlet：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. 選用：使用下列 Cmdlet 在稽核模式中啟用此功能：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    使用 `Disabled` 代替 `AuditMode` 或 `Enabled` 關閉功能。

### <a name="mobile-device-management-mdm"></a>移動裝置管理 (MDM) 

使用 [/Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service PROVIDER (CSP) 以啟用或停用網路保護或啟用稽核模式。

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft 端點管理員 (先前的 Intune) 

1. 登入 Microsoft 端點管理員管理中心 (https://endpoint.microsoft.com)

2. 建立或編輯 [endpoint protection 設定檔](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)

3. 在設定檔流程中的「設定設定」下，移至 **Microsoft Defender 利用防護**  >  **網路篩選**  >  **網路保護**  >  **啟用** 或 **僅限審核**

### <a name="group-policy"></a>群組原則

使用下列程式可在已加入網域的電腦或獨立電腦上啟用網路保護。

1. 在單機電腦上，移至 [ **開始** ]，然後輸入並選取 [ **編輯群組原則**]。

    *或*

    在已加入網域的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統****管理範本**]。

3. 將樹狀目錄展開為 **windows 元件**  >  **Microsoft defender 防病毒**  >  **Windows defender 利用防護**  >  **網路防護**。

> [!NOTE]
> 在舊版 Windows 上，群組原則路徑可以說「Windows Defender 防毒程式」，而不是「Microsoft Defender 防毒程式」。

4. 按兩下 [ **防止使用者和應用程式存取危險的網站** ] 設定，並將此選項設定為 [ **啟用**]。 在 [選項] 區段中，您必須指定下列其中一個選項：
    * **封鎖** -使用者無法存取惡意的 IP 位址和網域
    * **停用 (預設)** -網路保護功能將無法運作。 使用者不會被封鎖存取惡意網域
    * **稽核模式** -如果使用者要走訪惡意的 IP 位址或網域，將會在 Windows 事件記錄檔中記錄事件。 不過，使用者不會被封鎖訪問位址。

> [!IMPORTANT]
> 若要完全啟用網路保護，您必須將群組原則選項設定為 [ **啟用** ]，然後在 [選項] 下拉式功能表中選取 [ **封鎖** ]。

使用登錄編輯程式確認已在本機電腦上啟用網路保護：

1. 選取 [ **啟動** ] 並輸入 **Regedit** 以開啟 **登錄編輯程式**。

2. 流覽至 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**

3. 選取 **EnableNetworkProtection** 並確認值：
   * 0 = 關閉
   * 1 = 開啟
   * 2 = 審計

## <a name="see-also"></a>另請參閱

* [網路保護](network-protection.md)
* [評估網路保護](evaluate-network-protection.md)
* [疑難排解網路保護](troubleshoot-np.md)
