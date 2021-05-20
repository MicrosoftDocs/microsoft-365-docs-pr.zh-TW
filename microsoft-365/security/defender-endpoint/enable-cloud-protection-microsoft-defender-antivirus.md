---
title: 在 Microsoft Defender 防毒軟體中開啟雲端傳送保護
description: 開啟雲端提供的保護，以利用快速和高級的保護功能。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，cloud，第一次看到封鎖
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572054"
---
# <a name="turn-on-cloud-delivered-protection"></a>開啟雲端提供的保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞到網路和端點。 雖然它稱為雲端服務，但不只是保護儲存在雲端中的檔案;相反地，它會使用分散式資源和機器教學，以比傳統的安全性智慧更新速度更快的速率來提供對端點的保護。

Microsoft Defender 防毒軟體會使用多個偵測及防護技術來提供準確、即時和智慧的保護。 [深入瞭解 Microsoft Defender 在第二代端點的核心的高級技術](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

您可以多種方式開啟或關閉 Microsoft Defender 防毒軟體雲端提供的保護：

- Microsoft Intune
- Microsoft 端點管理員
- 群組原則
- PowerShell Cmdlet。

 您也可以在 Windows 安全性應用程式的個別用戶端中開啟或關閉該功能。

請參閱[使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)，以取得 Microsoft Defender 防毒軟體雲端提供保護的概述。

如需特定網路連線需求的詳細資訊，以確保端點能夠連線至雲端提供的保護服務，請參閱 [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> 在 Windows 10 中，本主題所述的 **基本** 和 **高級** 報告選項之間沒有任何差異。 這是傳統的區別，而且選擇任一設定會導致相同的雲端傳送層級保護。 共用的資訊類型或數量不會有任何差異。 如需我們收集之專案的詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>使用 Intune 開啟雲端傳送保護

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。

2. 在 [ **首頁** ] 窗格中，選取 [裝置設定] **> 設定檔**。

3. 選取您要設定的 **裝置限制** 配置檔案類型。 如果您需要建立新的 **裝置限制** 配置檔案類型，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。

4. 選取 [**屬性**  >  **設定：編輯**  >  **Microsoft Defender 防毒軟體**]。

5. 在 **雲端提供的保護** 參數上，選取 [ **啟用**]。

6. 在 [ **提交範例前提示使用者** ] 下拉式清單中，選取 [ **自動傳送所有資料**]。

如需 Intune 裝置設定檔的詳細資訊，包括如何建立和設定其設定，請參閱[什麼是 Microsoft Intune 裝置設定檔？](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>使用 Microsoft 端點管理員開啟雲端傳送保護

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。

2. 選擇 [ **Endpoint security**  >  **防病毒**]。

3. 選取防病毒設定檔。  (如果您尚沒有其中一個，或若您想要建立新的設定檔，請參閱[在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。

4. 選取 [ **屬性**]。 然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。

5. 展開 [ **cloud protection**]，然後在 [ **雲端提供的保護層級** ] 清單中，選取下列其中一項：
   - **High**：套用強層次的偵測。
   - **High plus**：使用 **高階** ，套用其他保護措施 (可能會影響用戶端效能) 。
   - **零容錯**：封鎖所有的未知可執行檔。

6. 選取 [ **複查 + 儲存**]，然後選擇 [ **儲存**]。

如需設定 Microsoft Endpoint Configuration Manager 的詳細資訊，請參閱 how [to create and deploy 反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>使用群組原則開啟雲端傳送保護

1. 在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

2. 在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]。

3. 選取 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 對應**

5. 連按兩下 [ **加入 MICROSOFT 地圖**]。 確定已開啟此選項，並將其設定為 [ **基本地圖** ] 或 [ **高級地圖**]。 選取 **[確定]**。

6. **需要進一步分析時，** 請按兩下 [傳送檔案範例]。 確定第一個選項設定為 [ **啟用** ]，且其他選項設定為下列其中一項：

    1.  (1) **傳送安全的範例**
    2. **將所有範例都傳送** (3) 

        >[!NOTE]
        > [ **傳送安全範例** (1) ] 選項表示將會自動傳送大部分的範例。 可能包含個人資訊的檔案仍會出現提示，需要其他確認。
        > 將此選項設定為 **Always Prompt** (0) 會降低裝置的保護狀態。 設定為 **永不傳送** (2) 表示 Microsoft Defender for Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。

7. 選取 **[確定]**。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>使用 PowerShell Cmdlet 開啟雲端傳送保護

下列 Cmdlet 可以開啟雲端提供的保護：

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。 [原則 CSP-Defender](/windows/client-management/mdm/policy-csp-defender) 也有專用於 [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)的詳細資訊。

>[!NOTE]
> 您也可以將 **SubmitSamplesConsent** 設定為 `SendSafeSamples` (預設設定) 、 `NeverSend` 或 `AlwaysPrompt` 。 此 `SendSafeSamples` 設定表示將會自動傳送大多數的範例。 可能包含個人資訊的檔案仍會出現提示，需要其他確認。

>[!WARNING]
> 設定 **-SubmitSamplesConsent** 至 `NeverSend` 或 `AlwaysPrompt` 會降低裝置的保護層級。 此外，設定為 `NeverSend` 表示 Microsoft Defender For Endpoint 的「 [區塊第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 」功能將無法運作。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>使用 Windows 管理指令 (WMI) 開啟雲端傳送保護

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/defender/set-msft-mppreference) ：

```WMI
MAPSReporting
SubmitSamplesConsent
```

如需允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>在 Windows 安全性應用程式的個別用戶端上開啟雲端提供保護

> [!NOTE]
> 如果設定為 [**將 Microsoft MAPS** 群組原則設定覆寫] 設定為 [**已停** 用]，則 Windows 設定中的 **雲端型保護** 設定會變灰並無法使用。 必須先將透過群組原則物件進行的變更部署到個別端點，才能在 Windows 設定中更新設定。

1. 在工作欄中選取盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 Windows 安全性應用程式。

2. 在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後 **& [病毒威脅防護設定** ] 標籤：

    ![Windows 安全性應用程式中的病毒與威脅防護設定標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. 確認已將 **雲端式保護** 和 **自動範例提交** 切換為 [ **開啟**]。

> [!NOTE]
> 如果已使用群組原則設定自動範例提交，則設定會變灰並無法使用。

## <a name="related-articles"></a>相關文章

- [設定雲端封鎖逾時期間](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [設定初次看到的封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [使用 Microsoft Intune] 的 Endpoint Protection 來協助保護 Windows 電腦](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Defender Cmdlet](/powershell/module/defender/)
- [在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)
- [如何建立及部署反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
