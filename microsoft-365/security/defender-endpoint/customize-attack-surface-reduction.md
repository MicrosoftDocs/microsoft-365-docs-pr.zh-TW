---
title: 自訂受攻擊面縮小規則
description: 個別設定審核、封鎖或已停用模式中的規則，以及新增應從攻擊面減少規則排除的檔案和資料夾
keywords: 攻擊面減少，hips，主機入侵防護系統，保護規則，反惡意攻擊，antiexploit，exploit，感染防護，自訂，設定，排除
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6d2770dec270e2d1c1b9750387a0f07f82b357f9
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177090"
---
# <a name="customize-attack-surface-reduction-rules"></a>自訂受攻擊面縮小規則

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

[攻擊面減少規則](enable-attack-surface-reduction.md) 可協助避免經常濫用的軟體行為，損害您的裝置或網路。 例如，攻擊者可能會嘗試從 USB 磁片磁碟機關閉未簽署的腳本，或是 Office 檔中的宏直接撥打 WIN32 API。 攻擊面減少規則可限制這些類型的危險行為，並改善組織的防禦性狀況。

瞭解如何自訂攻擊面減少規則，方法是 [排除檔案和資料夾](#exclude-files-and-folders) ，或 [將自訂文字新增至](#customize-the-notification) 使用者電腦上出現的通知警示。

您可以針對執行下列任何版本和版本的裝置，設定攻擊面減少規則 Windows：

- Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

您可以使用「群組原則」、「PowerShell」和「行動裝置管理」 (MDM) 設定服務提供者 (CSP) 來設定這些設定。

如需支援的作業系統及其他需求資訊的相關資訊，請參閱「啟用攻擊面降低規則」一文中的 [需求](enable-attack-surface-reduction.md#requirements) 。

## <a name="exclude-files-and-folders"></a>排除檔案和資料夾

您可以選擇排除受攻擊面降低規則所評估的檔案和資料夾。 排除時，即使攻擊面降低規則會偵測到檔案包含惡意行為，檔案也不會執行封鎖。

例如，您會考慮勒索軟體的以下規則：

勒索軟體的原則是專門設計用來協助企業客戶降低勒索軟體攻擊的風險，同時確保商務持續性。 根據預設，勒索軟體規則會在警告一側發生錯誤，並防止尚未具備足夠信譽和信任的檔案。 若要 reemphasize，勒索軟體規則只會觸發未獲得足夠肯定信譽和流行的檔案，根據數百萬客戶的使用量計量。 通常，區塊會自行解決，因為每個檔案的「信譽和信任」值會隨著非問題的使用量而逐漸升級。

在未及時解決區塊問題的情況下，客戶 _可以自行解決問題：使用_ 自助服務機制或損害指示器 (IOC) 型「允許清單」功能，自行解除封鎖檔。  

> [!WARNING]
> 排除或取消阻止檔案或資料夾可能會允許不安全的檔案執行並感染您的裝置。 排除檔案或資料夾可能會嚴重降低受攻擊面縮小規則所提供的保護。 會允許執行已被規則封鎖的檔案，而且不會記錄任何報表或事件。

排除會套用到允許排除的所有規則。 您可以指定個別的檔案、資料夾路徑或資源的完整功能變數名稱。 不過，您無法限制特定規則的排除。

只有在已排除的應用程式或服務啟動時，才會套用排除。 例如，如果您為已在執行的更新服務新增排除，更新服務會繼續觸發事件，直到停止並重新啟動服務為止。

攻擊面減少支援環境變數和萬用字元。 如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。
如果您遇到的錯誤偵測不應該偵測到的檔案，請 [使用稽核模式來測試規則](evaluate-attack-surface-reduction.md)。

| 規則說明 | GUID |
|:----|:----|
| 封鎖濫用的漏洞簽章驅動程式 | `56a863a9-875e-4185-98a7-b882c64b5ce5` |
| 封鎖 Adobe Reader，以建立子流程 | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| 封鎖所有 Office 的應用程式建立子流程 | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| 封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取)  | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| 從電子郵件客戶程式和 web 郵件封鎖可執行檔內容 | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| 封鎖可執行檔，除非符合流行、age 或受信任的清單準則 | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| 封鎖可能混淆的腳本執行 | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| 從啟動下載的可執行內容封鎖 JavaScript 或 VBScript | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| 封鎖 Office 應用程式建立可執行檔內容 | `3B576869-A4EC-4529-8536-B80A7769E899` |
| 封鎖 Office 的應用程式將程式碼注入其他進程 | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| 封鎖 Office 的通訊應用程式以建立子流程 | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| 透過 WMI 事件訂閱封鎖持久性 | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |
| 封鎖來自 PSExec 和 WMI 命令的進程建立 | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| 封鎖從 USB 執行的不受信任和未簽署程式 | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| 從 Office 宏封鎖 WIN32 API 呼叫 | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| 使用勒索軟體的高級防護 | `c1db55ab-c21a-4637-bb3f-a12568109d35` |

如需每個規則的詳細資訊，請參閱 [攻擊面減少](attack-surface-reduction.md) 主題。

### <a name="use-group-policy-to-exclude-files-and-folders"></a>使用群組原則排除檔案和資料夾

1. 在您的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。

2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Microsoft Defender 惡意探索防護**  >  **攻擊面降減**。

4. 按兩下 [排除檔案 **和攻擊面減規則的路徑** ] 設定，並將選項設定為 [ **啟用**]。 選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。 在 [**值**] 欄中，為每個專案輸入 **0** 。

> [!WARNING]
> 請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。

### <a name="use-powershell-to-exclude-files-and-folders"></a>使用 PowerShell 排除檔案和資料夾

1. 在 [開始] 功能表中輸入 **powershell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [以 **系統管理員身分執行**]
2. 輸入下列 Cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

繼續使用將 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 更多資料夾新增至清單。

> [!IMPORTANT]
> 用於 `Add-MpPreference` 附加或新增應用程式至清單。 使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>使用 MDM Csp 排除檔案和資料夾

使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。

## <a name="customize-the-notification"></a>自訂通知

您可以自訂觸發規則的通知，並封鎖應用程式或檔案。 請參閱[Windows 安全性](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。

## <a name="related-topics"></a>相關主題

- [使用攻擊面減少規則來減少攻擊面](attack-surface-reduction.md)
- [啟用受攻擊面縮小規則](enable-attack-surface-reduction.md)
- [評估受攻擊面縮小規則](evaluate-attack-surface-reduction.md)
- [受攻擊面縮小常見問題集](attack-surface-reduction.md)
