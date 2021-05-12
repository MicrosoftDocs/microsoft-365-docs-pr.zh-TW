---
title: 自訂受控資料夾存取權
description: 新增其他應受「受控制的資料夾存取」保護的資料夾，或是允許未正確封鎖對重要檔案所做變更的應用程式。
keywords: 可控資料夾存取，windows 10，windows defender，勒索軟體，保護，檔案，資料夾，自訂，新增資料夾，新增應用程式，允許，新增可執行檔
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326522"
---
# <a name="customize-controlled-folder-access"></a>自訂受控資料夾存取權

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

受控制的資料夾存取可協助您保護寶貴的資料，避免惡意應用程式和威脅（如勒索軟體）。 Windows Server 2019 和 Windows 10 用戶端支援受控資料夾存取。 本文說明如何自訂受管理的資料夾存取功能，並包含下列各節：

- [保護其他資料夾](#protect-additional-folders)
- [新增應允許存取受保護的資料夾的應用程式](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [允許簽署的可執行檔存取受保護的資料夾](#allow-signed-executable-files-to-access-protected-folders)
- [自訂通知](#customize-the-notification)

> [!IMPORTANT]
> 受管理的資料夾存取可監控偵測為惡意之活動的應用程式。 有時候會封鎖合法應用程式對您的檔案進行變更。 如果受控資料夾存取影響組織的生產力，您可以考慮在 [稽核模式](audit-windows-defender.md) 中執行這項功能，以完全評估影響。

## <a name="protect-additional-folders"></a>保護其他資料夾

「受管理的資料夾存取」會套用至許多系統資料夾及預設位置，包括 **檔**、 **圖片** 和 **影片** 等資料夾。 您可以新增其他受保護的資料夾，但您無法移除預設清單中的預設資料夾。

將其他資料夾新增至 [受管理的資料夾存取] 在您未將檔案儲存在預設的 Windows 文件庫中時，或已變更文件庫的預設位置時，可能會很有説明。

您也可以指定網路共用和對應的磁片磁碟機。 支援環境變數和萬用字元。 如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

您可以使用 Windows 安全性應用程式、群組原則、PowerShell Cmdlet 或行動裝置管理設定服務提供者來新增及移除受保護的資料夾。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>使用 Windows 安全性應用程式來保護其他資料夾

1. 在工作列上選取盾牌圖示，或是在 [開始] 功能表中搜尋 *安全性*，以開啟 Windows 安全性應用程式。

2. 選取 [ **病毒 & 威脅防護**]，然後向下滾動至 [ **勒索軟體防護** ] 區段。

3. 選取 [ **管理勒索軟體防護** ] 以開啟 [ **勒索軟體防護** ] 窗格。

4. 在 [ **受管理的資料夾存取** ] 區段中，選取 [ **受保護的資料夾**]。

5. 在 [**使用者存取控制** 提示] 上選擇 [**是]** 。 [ **受保護的資料夾** ] 窗格隨即顯示。

6. 選取 [ **新增受保護的資料夾** ]，然後依照提示新增資料夾。

### <a name="use-group-policy-to-protect-additional-folders"></a>使用群組原則來保護其他資料夾

1. 在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)。 

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 在您的 **群組原則管理編輯器** 中，移至 [**電腦** 設定原則] 「  >    >  **管理範本**」。

4. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender Exploit Guard**  >  **控制的資料夾存取**。 <br/>**附注**：在舊版的 Windows 中，您可能會看到 **Windows Defender 防毒軟體** 而非 **Microsoft Defender 防毒軟體**。

5. 按兩下 [ **已設定受保護的資料夾**]，然後將選項設定為 [ **啟用**]。 選取 [ **顯示**]，然後指定每個要保護的資料夾。

6. 像往常一樣部署您的群組原則物件。

### <a name="use-powershell-to-protect-additional-folders"></a>使用 PowerShell 來保護其他資料夾

1. 在 [開始] 功能表中輸入 **PowerShell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [以 **系統管理員身分執行**]

2. 輸入下列 PowerShell Cmdlet， `<the folder to be protected>` 並以資料夾路徑取代 (`"c:\apps\"`) ：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 針對每個要保護的資料夾重複步驟2。 受保護的資料夾在 Windows 安全性應用程式中是可見的。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="顯示 Cmdlet 的 PowerShell 視窗":::

> [!IMPORTANT]
> 用於 `Add-MpPreference` 在清單中附加或新增應用程式 `Set-MpPreference` 。 使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>使用 MDM Csp 來保護其他資料夾

使用 [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>允許特定的應用程式變更受管理的資料夾

您可以指定某些應用程式是否一定會被視為安全，並對受保護的資料夾中的檔案提供寫入存取權。 如果您知道和信任的特定應用程式被受控資料夾存取功能封鎖，則允許應用程式會非常有用。

> [!IMPORTANT]
> 根據預設，Windows 會將視為友好的應用程式新增至允許的清單。 這類應用程式會自動新增，不會記錄在 Windows 安全性應用程式或使用相關 PowerShell Cmdlet 所顯示的清單中。 您不需要新增大多數的應用程式。 僅新增應用程式（若已被封鎖，您可以驗證其可信度）。

當您新增應用程式時，您必須指定應用程式的位置。 只有該位置中的應用程式才能存取受保護的資料夾。 如果使用相同名稱的應用程式 () 位於不同的位置，則不會將它新增至 allowlist，也不會被受控資料夾存取權封鎖。

在啟動後，允許的應用程式或服務只具有受管理的資料夾的寫入權限。 例如，更新服務會在允許事件後繼續觸發事件，直到它停止並重新啟動為止。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>使用 Windows Defender 的安全性應用程式來允許特定的應用程式

1. 在 [**安全性**] 的 [開始] 功能表上搜尋，以開啟 Windows 安全性應用程式。

2. 在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [ **管理勒索軟體防護**]。

3. 在 [**受管理的資料夾存取**] 區段中，選取 [**允許透過可控資料夾存取的應用程式**]。

4. 選取 [ **新增允許的應用程式** ]，然後依照提示新增應用程式。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="[新增允許的應用程式] 按鈕":::

### <a name="use-group-policy-to-allow-specific-apps"></a>使用群組原則允許特定的應用程式

1. 在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。

3. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender Exploit Guard**  >  **控制的資料夾存取**。

4. 按兩下 [ **設定允許的應用程式** ] 設定，並將選項設定為 [ **啟用**]。 選取 [ **顯示** ]，然後輸入每個應用程式。

### <a name="use-powershell-to-allow-specific-apps"></a>使用 PowerShell 允許特定的應用程式

1. 在 [開始] 功能表中輸入 **PowerShell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [以 **系統管理員身分執行**]
2. 輸入下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    例如，若要新增位於 *C:\apps* 資料夾中的可執行 *test.exe* ，此 Cmdlet 如下所示：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   繼續使用將 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 更多應用程式新增至清單。 使用此 Cmdlet 新增的應用程式會出現在 Windows 安全性應用程式中。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="允許應用程式的 PowerShell Cmdlet":::

> [!IMPORTANT]
> 用於 `Add-MpPreference` 附加或新增應用程式至清單。 使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>使用 MDM Csp 以允許特定的應用程式

使用 [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>允許簽署的可執行檔存取受保護的資料夾

Microsoft Defender for Endpoint 憑證和檔指示器可允許簽署的可執行檔存取受保護的資料夾。 如需有關執行的詳細資訊，請參閱 [建立以憑證為基礎的指示器](indicator-certificates.md)。

> [!Note]
> 這不會套用至腳本掃描引擎，包括 Powershell

## <a name="customize-the-notification"></a>自訂通知

如需在觸發規則時自訂通知並封鎖應用程式或檔案的詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中設定警示通知](configure-email-notifications.md)。

## <a name="see-also"></a>請參閱

- [使用受控資料夾存取權來保護重要資料夾](controlled-folders.md)
- [啟用受控資料夾存取權](enable-controlled-folders.md)
- [評估受攻擊面縮小規則](evaluate-attack-surface-reduction.md)
