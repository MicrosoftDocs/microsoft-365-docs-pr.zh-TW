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
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fc952ceec7d26d853e39cab0a803daace62a4767
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345882"
---
# <a name="enable-attack-surface-reduction-rules"></a>啟用受攻擊面縮小規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[攻擊面減少規則](attack-surface-reduction.md) (ASR 規則) 協助防止惡意程式碼經常濫用裝置和網路遭到侵入的動作。

**需求** 您可以針對執行下列任何版本與 Windows 的裝置，設定攻擊面減少規則：

- Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

雖然攻擊面降減規則不需要[Windows E5 授權](/windows/deployment/deploy-enterprise-licenses)，但如果您有 Windows E5，就會取得高級管理功能。 這些功能只能在 Windows E5 中包含用於[端點的](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)監控、分析和工作流程，以及[Microsoft 365 安全性中心](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)的報表和設定功能。 Windows Professional 或 Windows E3 授權無法使用這些高級功能;不過，如果您有這些授權，您可以使用「事件檢視器」和 Microsoft Defender 防毒軟體記錄檔，以查看攻擊面減少規則事件。

每個 ASR 規則都包含四個設定的其中一項：

- **未設定**：停用 ASR 規則
- **封鎖**：啟用 ASR 規則
- **Audit**：評估 ASR 規則在啟用時會如何影響您的組織
- **警告**：啟用 ASR 規則，但是允許使用者略過封鎖

> [!IMPORTANT]
> 目前，當您在 Microsoft 端點管理員 (MEM) 中設定 asr 規則時，不支援三種 asr 規則的警告模式。 若要深入瞭解，請參閱 [不支援警告模式的案例](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。

強烈建議您使用具有 Windows E5 授權 (或類似授權 SKU) 的 ASR 規則，以利用[Microsoft Defender for](https://docs.microsoft.com/windows/security/threat-protection) endpoint (Defender for endpoint) 中提供的高級監控和報告功能。 不過，針對 Windows Professional 或 E3 等其他授權，如未存取高級監控和報告功能，您可以在觸發 ASR 規則時，在每個端點上建立您自己的監控和報告工具，以在觸發 ASR 規則時產生， (例如事件轉送) 。

> [!TIP]
> 若要深入瞭解 Windows 授權，請參閱[Windows 10 授權](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)並取得[Windows 10 的大量授權指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

您可以使用下列任何一種方法來啟用攻擊面減少規則：

- [Microsoft Intune](#intune)
- [移動裝置管理 (MDM) ](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [群組原則](#group-policy)
- [PowerShell](#powershell)

建議使用 Enterprise 層級管理（如 Intune 或 Microsoft 端點管理員）。 Enterprise 層級管理將覆寫任何衝突的群組原則或啟動時 PowerShell 設定。

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

1. 選取 [**裝置** 設定  >  **設定檔**]。 選擇現有的 endpoint protection 設定檔，或建立一個新的 endpoint protection 設定檔。 若要建立新的設定檔，請選取 [ **建立設定檔** ]，然後輸入此設定檔的資訊。 在 [ **配置檔案類型**] 中，選取 [ **Endpoint protection**]。 如果您已選取現有的設定檔，請選取 [**屬性**]，然後選取 [**設定**]。

2. 在 [ **Endpoint protection** ] 窗格中，選取 [ **Windows Defender Exploit Guard**]，然後選取 [**攻擊面減少**]。 針對每個 ASR 規則選取所需的設定。

3. 在 [ **攻擊面減少例外** 狀況] 底下，輸入個別的檔案和資料夾。 您也可以選取 [匯入 **]，匯** 入包含要從 ASR 規則排除的檔案和資料夾的 CSV 檔案。 CSV 檔案中的每一行都應該格式化如下：

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 在三個設定窗格上選取 **[確定]** 。 如果您要建立新的 endpoint protection 檔案，請選取 [ **建立** ]，如果您要編輯現有的 endpoint protection 檔案，請選取 [ **儲存** ]。

## <a name="mdm"></a>Mdm

使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service PROVIDER (CSP) 以個別啟用和設定每個規則的模式。

下列為參考資料範例，其使用 [的是 ASR 規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

在稽核模式中，啟用 (區塊) 、停用、警告或啟用的值包括：

- 0：停用 (停用 ASR 規則) 
- 1：封鎖 (啟用 ASR 規則) 
- 2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) 
- 6：警告 (啟用 ASR 規則，但是允許使用者略過區塊) 。 警告模式現在可用於大部分的 ASR 規則。

使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。

範例：

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 請務必輸入不含空格的 OMA URI 值。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在 Microsoft Endpoint Configuration Manager 中，移至 **資產及規範**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**。

2. 選取 [**首頁**  >  **建立 Exploit Guard 原則**]。

3. 輸入名稱和描述，選取 [ **攻擊面減少**]，然後選取 **[下一步]**。

4. 選擇會封鎖或審核動作的規則，然後選取 **[下一步]**。

5. 複查設定，然後選取 **[下一步]** 建立原則。

6. 建立原則之後， **關閉**。

## <a name="group-policy"></a>群組原則

> [!WARNING]
> 如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體將會覆寫啟動時的任何衝突的群組原則設定。

1. 在您的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。

2. 在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。

3. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Microsoft Defender 惡意探索防護**  >  **攻擊面降減**。

4. 選取 [ **設定攻擊面減少規則** ]，然後選取 [ **啟用**]。 然後，您可以在 [選項] 區段中，為每個規則設定個別的狀態。

   選取 [ **顯示 ...** ]，然後在 [值 **名稱** ] 欄中輸入規則識別碼，並在 [ **值** ] 欄中輸入您選擇的狀態，如下所示：

   - 0：停用 (停用 ASR 規則) 
   - 1：封鎖 (啟用 ASR 規則) 
   - 2：審計 (評估 ASR 規則在啟用時會如何影響您的組織) 
   - 6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) 

   :::image type="content" source="images/asr-rules-gp.png" alt-text="群組原則中的 ASR 規則":::

5. 若要從 ASR 規則中排除檔案和資料夾，請選取 [ **從攻擊面減少規則排除檔案和路徑** ] 設定，並將此選項設定為 [ **啟用**]。 選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。 在 [**值**] 欄中，為每個專案輸入 **0** 。

   > [!WARNING]
   > 請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。

## <a name="microsoft-endpoint-manager-custom-procedure"></a>Microsoft 端點管理員自訂程式

您可以使用 Microsoft 端點管理員 (MEM) 系統管理中心來設定自訂的 ASR 規則。

1. 開啟 Microsoft 端點管理員 (MEM) 系統管理中心。 在 [ **主** ] 功能表中，按一下 [  **裝置**]，選取 [ **設定檔**]，然後按一下 [ **建立設定檔**]。

   ![MEM 建立設定檔](images/mem01-create-profile.png)

2. 在 [ **建立設定檔**] 的下列兩個下拉式清單中，選取下列各項：

   - 在 [**平臺**] 中，選取 [ **Windows 10 和更新版本**]
   - 在 [ **配置檔案類型**] 中，選取 **範本**

   選取 [ **自訂**]，然後按一下 [ **建立**]。

   ![MEM 規則配置檔案屬性](images/mem02-profile-attributes.png)

3. 自訂範本工具隨即開啟至步驟 **1 基礎**。 在 [ **1 基礎**] 的 [ **名稱**] 中，輸入範本的名稱，然後在 [ **描述** ] 中輸入 (選用 ) 的描述。

   ![MEM 基本屬性](images/mem03-1-basics.png)

4. 按 [下一步]。 步驟 **2 設定設定** 隨即開啟。 若為 OMA-URI 設定，請按一下 [**新增**]。 現在會顯示兩個選項： [ **新增** ] 和 [ **匯出**]。

   ![記憶體配置設定](images/mem04-2-configuration-settings.png)

5. 再按一下 [ **新增** ]。 [**新增列 OMA URI] 設定** 隨即開啟。 在 [ **新增列**] 中，執行下列動作：

   - 在 [ **名稱**] 中，輸入規則的名稱。
   - 在 [ **描述**] 中，輸入簡短描述。
   - 在 **OMA uri** 中，輸入或貼上所要新增之規則的特定 oma-uri 連結。
   - 在 [ **資料類型**] 中，選取 **字串**。
   - 在 [ **值**] 中，輸入或貼上 guid 值， \= 不含空格的 sign 和 State 值 (_GUID = StateValue_) 。 其中： {0：停用 (停用 ASR rule) }，{1：封鎖 (啟用 ASR 規則) }，{2： Audit (評估 ASR 規則會如何影響您的組織如果已啟用) }，{6：警告 (啟用 ASR 規則，但是允許使用者略過封鎖) }

   ![MEM 的 OMA URI 設定](images/mem05-add-row-oma-uri.png)

6. 按一下 [儲存]。 **新增列** 關閉。 在 [ **自訂** **] 按 [下一步]**。 在步驟 **3 範圍標記** 中，範圍標記是選用的。 執行下列其中一項：

   - 按一下 [ **選取範圍** 標籤]，選取 [範圍] 標籤 (選用) 然後按 **[下一步]**。
   - 或按 **[下一步]**

7. 在 [步驟 **4 指派**] 中，在 [ **包含的群組** ] 中，對您想要套用此規則的群組進行-從下列選項中選取：

   - **新增群組**
   - **新增所有使用者**
   - **新增所有裝置**

   ![MEM 指派](images/mem06-4-assignments.png)

8. 在 [ **排除的群組**] 中，選取您要從此規則中排除的任何群組，然後按 **[下一步]**。

9. 在 [步驟5下列設定的 **適用性規則** ] 中，執行下列動作：

   - 在 [**規則**] 中，選取 [**指派設定檔為**]，或 [**不指派設定檔**]
   - 在 [ **屬性**] 中，選取您要套用此規則的屬性
   - 在 [ **值**] 中，輸入適用的值或值範圍

   ![MEM 適用性規則](images/mem07-5-applicability-rules.png)

10. 按 [下一步]。 在步驟 **6 中，複查 + 建立**、複查您已選取並輸入的設定和資訊，然後按一下 [ **建立**]。

   ![記憶審閱和建立](images/mem08-6-review-create.png)

>[!NOTE]
> 規則會在幾分鐘內生效和即時。

>[!NOTE]
> 衝突處理：如果指派裝置兩個不同的 ASR 原則，處理衝突的方式就是已指派不同狀態的規則，不會就地進行衝突管理，且結果為錯誤。
> 非衝突的規則不會導致錯誤，而且會正確套用規則。 結果是套用第一個規則，後續的非衝突規則會合並到原則中。

## <a name="powershell"></a>PowerShell

> [!WARNING]
> 如果您使用 Intune、Configuration Manager 或其他企業級管理平臺來管理電腦和裝置，管理軟體會在啟動時覆寫所有衝突的 PowerShell 設定。 若要讓使用者使用 PowerShell 定義值，請在管理平臺中使用規則的「使用者定義」選項。

1. 在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [以 **系統管理員身分執行**]。

2. 輸入下列 Cmdlet：

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    若要在稽核模式中啟用 ASR 規則，請使用下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    若要在警告模式中啟用 ASR 規則，請使用下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    若要啟用利用漏洞簽名驅動程式的 ASR 封鎖濫用，請使用下列 Cmdlet：

   ```PowerShell
   "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled"}
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
    > `Set-MpPreference` 永遠會覆寫現有的規則集。 如果您想要新增至現有的集，請 `Add-MpPreference` 改用。
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
