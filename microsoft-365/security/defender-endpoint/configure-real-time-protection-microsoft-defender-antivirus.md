---
title: 啟用和設定 Microsoft Defender 防毒軟體保護功能
description: 啟用和設定 Microsoft Defender 防毒軟體即時保護功能，例如行為監控、啟發式及機器學習）
keywords: 防毒程式，即時保護，rtp，機器教學，行為監控，試探法
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275129"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>在群組原則中啟用和設定 Microsoft Defender 防毒軟體一律開啟保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Always on 防護包含即時保護、行為監控和試探法，以根據已知的可疑和惡意活動來識別惡意程式碼。

這些活動包括事件（例如，對現有檔案進行非正常變更的處理常式）、修改或建立自動啟動登錄機碼和啟動位置 (也稱為自動啟動擴充點，或 ASEPs) ，以及其他對檔案系統或檔結構所做的變更。

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>啟用並設定群組原則中的 always on 保護

您可以使用 **本機組策略編輯器**，啟用和設定 Microsoft Defender 防毒軟體 always on 防護設定。

啟用和設定 always on 保護：

1. 開啟 [ **本機群組原則編輯器**]。 若要執行這項作業：  

    1. 在 [Windows 10 的工作列] 搜尋方塊中，輸入 **gpedit.msc**。
    
    1. 在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。
    
       ![Gpedit.msc 工作列搜尋結果](images/gpedit-search.png)

2. 在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體** 的樹狀目錄。 

3. 設定 Microsoft Defender 防毒軟體的反惡意程式碼服務原則設定。 若要執行這項作業：  

    1. 在右側的 [ **Microsoft Defender 防毒軟體** 詳細資料] 窗格中，按兩下 [原則] 設定，如下表所指定：

       | 設定 | 描述 | 預設設定 |
       |-----------------------------|------------------------|-------------------------------|
       | 允許反惡意程式碼服務以一般優先順序啟動 | 您可以降低 Microsoft Defender 防毒軟體引擎的優先順序，這在您想要讓啟動程式盡可能精益的輕量部署中非常有用。 這可能會影響端點的保護。 | 啟用
       | 允許反惡意程式碼服務持續保持執行狀態 | 如果已停用保護更新，您可以將 Microsoft Defender 防毒軟體設定為仍然執行。 這會降低對端點的保護。 | 停用 |
    
    1. 設定適當的設定，然後按一下 **[確定]**。
    
    1. 針對表格中的每個設定，重複上述步驟。

4. 設定 Microsoft Defender 防毒軟體即時保護原則設定。 若要執行這項作業：

    1. 在 [ **Microsoft Defender 防毒軟體** 詳細資料] 窗格中，按兩下 [**即時保護**]。 或者，在左窗格的 **Microsoft Defender 防毒軟體** 樹狀目錄中，按一下 [**即時保護**]。
    
    1. 在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下下表所指定的原則設定：  

       | 設定 | 描述 | 預設設定 |
       |-----------------------------|------------------------|-------------------------------|
       | 開啟行為監控 | AV 引擎會監視檔案處理常式、檔案和登錄變更，以及終結點上的其他事件，以取得可疑和已知的惡意活動。 | 啟用 |
       | 掃描所有已下載的檔案和附件 | 會自動掃描下載的檔案和附件。 這項作業除了 Windows Defender SmartScreen 篩選之外，它會在下載之前和下載期間掃描檔案。 | 啟用 |
       | 監視電腦上的檔案和程式活動 | Microsoft Defender 防毒軟體引擎會記下所 (做的任何檔案變更，例如移動、副本或) 修改， (已開啟或執行的一般程式活動，以及導致其他程式執行) 的程式。 | 啟用 |
       | 開啟原始大量寫入通知 | 有關原始磁片區寫入的資訊會透過行為監控進行分析。 | 啟用 |
       | 在啟用即時保護時開啟處理常式掃描 | 您可以個別啟用 Microsoft Defender 防毒軟體引擎，以掃描正在執行的程式，以進行可疑的修改或行為。 如果您暫時停用即時保護，且想要自動掃描已停用的處理常式，這會很有用。 | 啟用 |
       | 定義要掃描的下載檔案和附件大小上限 | 您可以定義大小（以 kb 為單位）。 | 啟用 |
       | 設定本機設定超越開啟行為監控 | 設定本機覆寫以設定行為監控的設定。 此設定只可由「群組原則」設定。 如果您啟用此設定，則本機偏好設定會優先于「群組原則」。 如果您停用或未設定此設定，群組原則將優先于本機偏好設定。| 啟用 |
       | 設定本機設定覆寫以掃描所有已下載的檔案和附件 | 設定本機覆寫以設定掃描所有已下載檔案和附件的設定。 此設定只可由「群組原則」設定。 如果您啟用此設定，則本機偏好設定會優先于「群組原則」。 如果您停用或未設定此設定，群組原則將優先于本機偏好設定。| 啟用 |
       | 設定本機設定覆寫以監控電腦上的檔案和程式活動 | 設定本機覆寫，以監視電腦上的檔案和程式活動。 此設定只可由「群組原則」設定。 如果您啟用此設定，則本機偏好設定會優先于「群組原則」。 如果您停用或未設定此設定，群組原則將優先于本機偏好設定。| 啟用 |
       | 設定本機設定覆寫以開啟即時保護 | 設定本機覆寫設定，以開啟即時保護。 此設定只可由「群組原則」設定。 如果您啟用此設定，則本機偏好設定會優先于「群組原則」。 如果您停用或未設定此設定，群組原則將優先于本機偏好設定。| 啟用 |
       | 設定針對內送和外寄檔案活動進行監視的本機設定覆寫 | 設定本機覆寫，以監視傳入和傳出檔案活動的監視。 此設定只可由「群組原則」設定。 如果您啟用此設定，則本機偏好設定會優先于「群組原則」。 如果您停用或未設定此設定，群組原則將優先于本機偏好設定。 | 啟用 |
       | 設定對內送和外寄檔案和程式活動的監控 | 指定監視是否應該發生在內送、撥出、兩者或兩者的方向。 這適用于您已定義特定伺服器或伺服器角色的 Windows 伺服器安裝，只會在一個方向上看到大量的檔案變更，且您想要提升網路效能。 完全更新的端點 (和伺服器) 在網路上，不論檔變更的數目或方向，都只會對效能造成影響。 | 已啟用兩個方向 ()  |

    1. 設定適當的設定，然後按一下 **[確定]**。
    
    1. 針對表格中的每個設定，重複上述步驟。

5. 設定 Microsoft Defender 防毒軟體掃描原則設定。 若要執行這項作業：  

    1. 在左窗格的 [ **Microsoft Defender 防毒軟體**] 樹狀目錄中，按一下 [**掃描**]。
    
       ![Microsoft Defender 防毒軟體掃描選項](images/gpedit-windows-defender-antivirus-scan.png)

    1. 在右側的 [ **掃描** 詳細資料] 窗格中，按兩下下清單格所指定的原則設定：

       | 設定 | 描述 | 預設設定 |
       |-----------------------------|------------------------|-------------------------------|    
       | 開啟試探法 | 啟發式防護會在要求 Microsoft Defender 防毒軟體引擎偵測活動之前停用或封鎖可疑活動。 | 啟用 |

    1. 設定適當的設定，然後按一下 **[確定]**。
    
6. 關閉 [ **本機群組原則編輯器**]。


## <a name="disable-real-time-protection-in-group-policy"></a>停用群組原則中的即時保護

> [!WARNING]
> 停用即時保護可大幅減少對端點的保護，所以不建議您這樣做。

預設會啟用主要即時保護功能，但您可以使用 [ **本機組策略編輯器**] 加以停用。

若要停用群組原則中的即時保護：

1. 開啟 [ **本機群組原則編輯器**]。

   1. 在 [Windows 10 的工作列] 搜尋方塊中，輸入 **gpedit.msc**。
   
   1. 在 [ **最佳相符**] 底下，按一下 [ **編輯群組原則** ] 以啟動 **本機組策略編輯器**。

2.  在 [**本機群組原則編輯器**] 的左窗格中，展開 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **即時保護** 的樹狀目錄。

3. 在 [ **即時保護** 詳細資料] 窗格的 [許可權] 中，按兩下 [ **關閉即時保護**]。

   ![關閉即時保護](images/gpedit-turn-off-real-time-protection.png)

4. 在 [ **關閉即時保護** 設定] 視窗中，將選項設定為 [ **啟用**]。

   ![關閉即時保護啟用](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. 按一下 ****[確定]。

6. 關閉 [ **本機群組原則編輯器**]。

## <a name="related-articles"></a>相關文章

- [設定行為、啟發學習法和即時保護](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)