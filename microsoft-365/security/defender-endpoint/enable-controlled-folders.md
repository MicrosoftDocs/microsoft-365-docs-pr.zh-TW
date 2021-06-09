---
title: 啟用受控資料夾存取權
keywords: 可控資料夾存取、windows 10、windows defender、勒索軟體、保護、檔案、資料夾、啟用、開啟、使用
description: 瞭解如何透過啟用「控制資料夾存取」來保護您的重要檔案
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841975"
---
# <a name="enable-controlled-folder-access"></a>啟用受控資料夾存取權

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[受控制的資料夾存取](controlled-folders.md) 可協助您保護寶貴的資料，避免惡意應用程式和威脅（如勒索軟體）。 [受管理的資料夾存取] 包含在 Windows 10 和 Windows Server 2019。

您可以使用下列任何一種方法來啟用受控資料夾存取：

* [Windows 安全性應用程式](#windows-security-app)
* [Microsoft Intune](#intune)
* [移動裝置管理 (MDM) ](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [群組原則](#group-policy)
* [PowerShell](#powershell)

[稽核模式](evaluate-controlled-folder-access.md) 可讓您測試功能 (和審閱事件) 的運作方式，而不會影響裝置的正常使用。

停用本機管理員清單合併的群組原則設定會覆寫「控制的資料夾存取」設定。 它們也會覆寫受保護的資料夾，以及由本機系統管理員透過「可控資料夾存取」所設定的應用程式。 這些原則包括：

* Microsoft Defender 防毒軟體 **設定清單的本機系統管理員合併行為**
* System Center Endpoint Protection **允許使用者新增排除和覆寫**

如需停用本機清單合併的詳細資訊，請參閱 [防止或允許使用者從本機修改 Microsoft DEFENDER AV 原則設定](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)。

## <a name="windows-security-app"></a>Windows 安全性應用程式

1. 選取工作列中的盾牌圖示，以開啟 Windows 安全性應用程式。 您也可以搜尋 **Defender** 的 [開始] 功能表。

2. 在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [ **勒索軟體防護**]。

3. 將「 **受控資料夾存取** 」的參數設為 [ **開啟**]。

> [!NOTE]
> 如果已使用群組原則、PowerShell 或 MDM csp 設定受管理的資料夾存取，則在重新開機裝置後，該狀態會在 Windows 安全性應用程式中變更。
> 如果使用任何工具將功能設定為 [**審計模式]** ，Windows 安全性應用程式會顯示狀態為 [**關閉**]。
> 如果您要保護使用者設定檔資料，建議使用者設定檔應位於預設的 Windows 安裝磁片磁碟機上。

## <a name="intune"></a>Intune

1. 登入 [Azure 入口網站](https://portal.azure.com) 並開啟 Intune。

2. 移至 **裝置配置**  >  **檔**  >  **建立設定檔**。

3. 命名設定檔，選擇 [ **Windows 10 和更新版本**] 和 [ **Endpoint protection**]。 <br/> ![建立 endpoint protection 設定檔](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. 移至 **設定**  >  **Windows Defender Exploit Guard**  >  **控制的資料夾存取**  >  **啟用**。

5. 輸入可存取受保護資料夾之每個應用程式的路徑，以及任何需要保護之其他資料夾的路徑。 選取 ****[新增]。<br/> ![啟用 Intune 中的可控資料夾存取](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard 支援應用程式，但不適用於資料夾。 子資料夾不受保護。 允許的應用程式會繼續觸發事件，直到重新開機為止。

6. 選取 **[確定]** 以儲存每個開啟的刀片式伺服器並 **建立**。

7. 選取設定檔 **指派**，並指派給 **所有使用者 & 所有裝置** 及 **儲存**]。

## <a name="mobile-device-management-mdm"></a>移動裝置管理 (MDM) 

使用 [/Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在 Microsoft Endpoint Configuration Manager 中，移至 **資產及規範**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**。

2. 選取 [**首頁**  >  **建立 Exploit Guard 原則**]。

3. 輸入名稱和描述，選取 [ **受管理的資料夾存取**]，然後選取 **[下一步]**。

4. 選擇封鎖或審核變更、允許其他應用程式或新增其他資料夾，然後選取 **[下一步]**。
   > [!NOTE]
   > Wilcard 支援應用程式，但不適用於資料夾。 子資料夾不受保護。 允許的應用程式會繼續觸發事件，直到重新開機為止。

5. 複查設定，然後選取 **[下一步]** 建立原則。

6. 建立原則之後， **關閉**。

## <a name="group-policy"></a>群組原則

1. 在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。

3. 展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體 > Windows Defender Exploit Guard > 受控制的資料夾存取**。

4. 按兩下 [ **設定受控資料夾存取** 設定]，並將選項設定為 [ **啟用**]。 在 [選項] 區段中，您必須指定下列其中一個選項：
    * **Enable** -不允許惡意和可疑應用程式對受保護資料夾中的檔案進行變更。 在 Windows 事件記錄檔中會提供通知。
    * **停用 (預設)** -「受管理的資料夾存取」功能將無法運作。 所有應用程式都可對受保護資料夾中的檔案進行變更。
    * 「**審計模式**」-如果惡意或可疑應用程式嘗試對受保護資料夾中的檔案進行變更，便允許變更。 不過，它會記錄在 Windows 事件記錄檔中，您可以在其中評估對組織的影響。
    * **僅封鎖磁片修改**：在 Windows 事件記錄檔中，會記錄不受信任應用程式對磁片區的嘗試。 在 [**應用程式及服務記錄**] 中，可以找到這些記錄檔 > Microsoft > Windows > Windows Defender > 作業 > ID 1123。
    * **僅限審核磁片修改只** 會在 [**應用程式及服務 Windows 記錄** 檔] 下的 [Windows 事件記錄 (中記錄寫入受保護的磁片磁區，  >    >    >  **Windows Defender**  >  **運作**  >  **識別碼 1124**) 。 不會記錄在 [受保護的資料夾] 中修改或刪除檔的嘗試。

      ![已啟用群組原則選項的螢幕擷取畫面和下拉式清單中選取的審計模式](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> 若要完全啟用可控資料夾存取，您必須將群組原則選項設定為 [ **啟用** ]，然後在 [選項] 下拉式功能表中選取 [ **封鎖** ]。

## <a name="powershell"></a>PowerShell

1. 在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [以 **系統管理員身分執行**]。

2. 輸入下列 Cmdlet：

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

您可以指定代替來啟用 [審計模式] 中的功能 `AuditMode` `Enabled` 。

用 `Disabled` 來關閉功能。

## <a name="see-also"></a>另請參閱

* [使用受控資料夾存取權來保護重要資料夾](controlled-folders.md)
* [自訂受控資料夾存取權](customize-controlled-folders.md)
* [評估適用於端點的 Microsoft Defender](evaluate-mde.md)
