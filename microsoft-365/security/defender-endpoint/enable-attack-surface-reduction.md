---
title: 啟用受攻擊面縮小規則
description: 啟用攻擊面減少 (ASR) 規則，保護您的裝置免受使用宏、腳本及一般插入技術的攻擊。
keywords: 攻擊面降減，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，啟用，開啟
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
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570945"
---
# <a name="enable-attack-surface-reduction-rules"></a>啟用受攻擊面縮小規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[攻擊面減少規則](attack-surface-reduction.md) (ASR 規則) 協助防止惡意程式碼經常濫用裝置和網路遭到侵入的動作。 您可以為執行下列任何版本的 Windows 裝置設定 ASR 規則：
- Windows 10 專業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本
- Windows 10 企業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本
- Windows Server， [版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 或更新版本
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

每個 ASR 規則都包含三個設定的其中一項：

- 未設定：停用 ASR 規則
- 封鎖：啟用 ASR 規則
- Audit：評估 ASR 規則在啟用時會如何影響您的組織

強烈建議您搭配 Windows E5 授權 (或類似授權 SKU) 使用 ASR 規則，以利用 [Microsoft defender for](https://docs.microsoft.com/windows/security/threat-protection) Endpoint (Defender for endpoint) 中可用的高級監控和報告功能。 不過，如果是其他授權（如 Windows Professional 或 E3）無法存取高級監控和報告功能，您可以在觸發 ASR 規則時，在每個端點上建立您自己的監控和報告工具，以在觸發 ASR 規則時產生 (例如，事件轉送) 。

> [!TIP]
> 若要深入瞭解 Windows 授權，請參閱 [windows 10 授權](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 並取得 [Windows 10 的大量授權指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

您可以使用下列任何一種方法來啟用攻擊面減少規則：

- [Microsoft Intune](#intune)
- [移動裝置管理 (MDM) ](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [群組原則](#group-policy)
- [PowerShell](#powershell)

建議使用企業層級管理（如 Intune 或 Microsoft 端點管理員）。 企業級管理將覆寫任何衝突的群組原則或啟動時 PowerShell 設定。

## <a name="exclude-files-and-folders-from-asr-rules"></a>從 ASR 規則中排除檔案和資料夾

您可以將檔案和資料夾排除在大多數攻擊面降低規則之外進行評估。 這表示即使 ASR 規則判斷的檔案或資料夾包含惡意行為，也不會封鎖該檔案執行。 這可能會允許不安全的檔案執行並感染您的裝置。

您也可以透過允許指定的 Defender for Endpoint file 和憑證指示器，排除從觸發憑證和檔案雜湊的 ASR 規則。  (請參閱 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。 ) 

> [!IMPORTANT]
> 排除檔案或資料夾可能會大大降低 ASR 規則所提供的保護。 將會允許執行排除的檔案，而且不會記錄任何報表或事件。
> 如果 ASR 規則偵測到您認為不應該偵測到的檔案，您應該 [先使用審計模式來測試規則](evaluate-attack-surface-reduction.md)。


您可以指定個別的檔案或資料夾 (使用資料夾路徑或完全限定資源名稱) ，但您無法指定要套用排除的規則。 只有在已排除的應用程式或服務啟動時，才會套用排除。 例如，如果您為已在執行的更新服務新增排除，更新服務會繼續觸發事件，直到停止並重新啟動服務為止。

ASR 規則支援環境變數和萬用字元。 如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。

下列啟用 ASR 規則的套裝程式括如何排除檔案和資料夾的指示。

## <a name="intune"></a>Intune

1. 選取 [**裝置** 設定  >  **設定檔**]。 選擇現有的 endpoint protection 設定檔，或建立一個新的 endpoint protection 設定檔。 若要建立新的設定檔，請選取 [ **建立設定檔** ]，然後輸入此設定檔的資訊。 在 [ **配置檔案類型**] 中，選取 [ **Endpoint protection**]。 如果您已選取現有的設定檔，請選取 [ **屬性** ]，然後選取 [ **設定**]。

2. 在 [ **Endpoint protection** ] 窗格中，選取 [ **Windows Defender 利用防護**]，然後選取 [ **攻擊面減少**]。 針對每個 ASR 規則選取所需的設定。

3. 在 [ **攻擊面減少例外** 狀況] 底下，輸入個別的檔案和資料夾。 您也可以選取 [匯入 **]，匯** 入包含要從 ASR 規則排除的檔案和資料夾的 CSV 檔案。 CSV 檔案中的每一行都應該格式化如下：

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 在三個設定窗格上選取 **[確定]** 。 如果您要建立新的 endpoint protection 檔案，請選取 [ **建立** ]，如果您要編輯現有的 endpoint protection 檔案，請選取 [ **儲存** ]。

## <a name="mdm"></a>Mdm

使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service PROVIDER (CSP) 以個別啟用和設定每個規則的模式。

下列為參考資料範例，其使用 [的是 ASR 規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

在稽核模式中啟用、停用或啟用的值包括：

- 停用 = 0
- 封鎖 (啟用 ASR 規則) = 1
- Audit = 2

使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。

範例：

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 請務必輸入不含空格的 OMA URI 值。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在 Microsoft 端點 Configuration Manager 中，移至 [**資產和合規性**  >  **端點防護**] 「  >  **Windows Defender 利用防護**」。

2. 選取 [**首頁**  >  **建立 Exploit Guard 原則**]。

3. 輸入名稱和描述，選取 [ **攻擊面減少**]，然後選取 **[下一步]**。

4. 選擇會封鎖或審核動作的規則，然後選取 **[下一步]**。

5. 複查設定，然後選取 **[下一步]** 建立原則。

6. 建立原則之後， **關閉**。

## <a name="group-policy"></a>群組原則

> [!WARNING]
> 如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體將會覆寫啟動時的任何衝突的群組原則設定。

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統****管理範本**]。

3. 將樹狀目錄展開為 **Windows 元件**  >  **microsoft defender 防病毒**  >  **microsoft defender 利用防護防護**  >  **攻擊面降減**。

4. 選取 [ **設定攻擊面減少規則** ]，然後選取 [ **啟用**]。 然後，您可以在 [選項] 區段中，為每個規則設定個別的狀態。

   選取 [ **顯示 ...** ]，然後在 [值 **名稱** ] 欄中輸入規則識別碼，並在 [ **值** ] 欄中輸入您選擇的狀態，如下所示：

   - 停用 = 0
   - 封鎖 (啟用 ASR 規則) = 1
   - Audit = 2

   ![群組原則設定會顯示空白攻擊面降減規則識別碼及值1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. 若要從 ASR 規則中排除檔案和資料夾，請選取 [ **從攻擊面減少規則排除檔案和路徑** ] 設定，並將此選項設定為 [ **啟用**]。 選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。 在 [**值**] 欄中，為每個專案輸入 **0** 。

> [!WARNING]
> 請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。

## <a name="powershell"></a>PowerShell

> [!WARNING]
> 如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體會在啟動時覆寫所有衝突的 PowerShell 設定。 若要讓使用者使用 PowerShell 定義值，請在管理平臺中使用規則的「使用者定義」選項。

1. 在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [ **以系統管理員身分執行**]。

2. 輸入下列 Cmdlet：

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    若要在稽核模式中啟用 ASR 規則，請使用下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    若要關閉 ASR 規則，請使用下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > 您必須個別指定每個規則的狀態，但是您可以將規則和狀態組合成以逗號分隔的清單。
    >
    > 在下列範例中，會啟用前兩個規則，將會停用第三個規則，且會在審計模式中啟用第四個規則：
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    您也可以使用 `Add-MpPreference` PowerShell 謂詞將新的規則新增至現有清單。

    > [!WARNING]
    > `Set-MpPreference` 永遠會覆寫現有的規則集。 如果您想要新增至現有的集合，則應該改為使用 `Add-MpPreference` 。
    > 您可以使用來取得規則及其目前狀態的清單 `Get-MpPreference` 。

3. 若要從 ASR 規則中排除檔案和資料夾，請使用下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    繼續使用將 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 更多檔案和資料夾新增至清單。

    > [!IMPORTANT]
    > 用於 `Add-MpPreference` 附加或新增應用程式至清單。 使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。

## <a name="related-articles"></a>相關文章

- [使用攻擊面減少規則來減少攻擊面](attack-surface-reduction.md)

- [評估攻擊面減少](evaluate-attack-surface-reduction.md)

- [受攻擊面縮小常見問題集](attack-surface-reduction.md)
