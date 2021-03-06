---
title: 建立檔案的指示器
ms.reviewer: ''
description: 為定義實體的偵測、預防和排除的檔案雜湊，建立指示器。
keywords: file，hash，manage，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256912"
---
# <a name="create-indicators-for-files"></a>建立檔案的指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Banning 潛在的惡意檔案或可疑惡意程式碼，以防止進一步傳播您組織中的攻擊。 如果您知道可能是惡意遷移的可執行檔 (PE) file，您可以將它封鎖。 此作業可防止在組織中的裝置上讀取、寫入或執行此作業。

您可以透過三種方式來建立檔案的指示器：

- 透過 [設定] 頁面建立指示器
- 使用 [檔案詳細資料] 頁面中的 [新增指示器] 按鈕建立上下文指示器
- 透過[指示器 API](ti-indicator.md)建立指示器

## <a name="before-you-begin"></a>開始之前

在建立檔案的指示器之前，請務必先瞭解下列必要條件：

- 如果您的組織使用 **Microsoft Defender 防毒軟體 (使用中) 模式**，且 **已啟用雲端型防護**，則可以使用此功能。 如需詳細資訊，請參閱 [管理以雲端為基礎的保護](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。

- 反惡意軟體用戶端版本必須是4.18.1901 或更新版本。 請參閱 [每月平臺和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- 在具有 Windows 10 版本1703或更新版本的裝置上支援 Windows Server 2016 和2019。

- 若要開始封鎖檔，您必須先在設定中 [開啟「封鎖或允許」功能](advanced-features.md)。

這項功能的設計是為了防止可疑的惡意程式碼 (或可能的惡意檔案) 從網頁下載。 它目前支援可遷移的可執行檔 (PE) 檔案（包括 .exe 和 .dll 檔案）。 覆蓋範圍會隨著時間擴充。

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>從 [設定] 頁面建立檔案的指標

1. 在功能窗格中，選取 [ **設定 >** 指標]。

2. 選取 [檔案 **雜湊**] 索引標籤   。

3. 選取 [ **新增指示器**]。

4. 指定下列詳細資料：
    - 標記-指定實體詳細資料並定義指示器的到期期限。
    - Action-指定要採取的動作並提供描述。
    - Scope-定義裝置群組的範圍。

5. 在 [摘要] 索引標籤中查看詳細資料，然後選取 [ **儲存**]。

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>從 [檔案詳細資料] 頁面建立上下文指示器

對檔案採取 [回應動作](respond-file-alerts.md)的其中一個選項   是為檔案新增標記。 當您為檔案新增指示器雜湊時，您可以選擇每當組織中的設備嘗試執行時，就會引發警示並封鎖檔案。

標記自動封鎖的檔案不會出現在檔案的動作中心，但提醒仍會顯示在 [警示] 佇列中。

>[!IMPORTANT]
>- 通常會在幾分鐘內強制執行並移除檔區塊，但可長達30分鐘。
> 
>- 如果有相同的強制類型和目標的衝突檔案 IoC 原則，則會套用更安全的雜湊原則。 SHA-256 檔案雜湊 IoC 原則會透過 SHA-1 檔案雜湊 IoC 原則進行贏取，如果雜湊類型定義同一個檔案，該原則將會贏取 MD5 的檔案雜湊 IoC 原則。 不論裝置群組為何，此值都是如此。 
>   在所有其他情況下，如果與相同強制目標的衝突檔案 IoC 原則套用至所有裝置和裝置群組，則裝置群組中的原則會獲勝。 
>   
>- 如果停用 EnableFileHashComputation 群組原則，則會降低檔 IoC 的封鎖精確度。 不過，啟用 `EnableFileHashComputation` 可能會影響裝置效能。 例如，將網路共用中的大型檔案複製到您的本機裝置（特別是透過 VPN 連線）時，可能會對裝置效能產生影響。
>
>   如需 EnableFileHashComputation 群組原則的詳細資訊，請參閱 [DEFENDER CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>原則衝突處理  

Cert 和檔案 IoC 原則處理衝突會依照下列順序進行：

- 如果 Windows Defender 應用程式控制和 AppLocker 強制執行模式原則/原則不允許檔案，則 **封鎖**

- 否則，如果 Microsoft Defender 防毒軟體的排除允許檔案，則 **允許**

- 否則，如果檔遭到封鎖或警告檔或 IoC，則封鎖 **/警告**

- 否則，如果 allow file IoC 原則允許檔案，則 **允許**

- 如果是由 ASR 規則、共同體、AV、SmartScreen 封鎖檔案，則為 Else，然後 **封鎖**  

- 否則 **(** Windows Defender 應用程式控制 & AppLocker 原則，則不會對其套用 IoC 規則) 

如果有相同的強制類型和目標的相互衝突的檔 IoC 原則，則更安全 (的原則會套用較長) 雜湊。 例如，如果兩個雜湊類型都定義相同的檔案，SHA-256 檔案雜湊 IoC 原則會在 MD5 檔案雜湊 IoC 原則上贏取。

威脅和弱點管理的封鎖漏洞應用程式功能會使用檔案 IoCs 進行強制執行，並遵循上述衝突處理順序。

### <a name="examples"></a>範例

|元件 |元件強制執行 |檔標記動作 |結果
|--|--|--|--|
|攻擊面減少檔路徑排除 |允許 |封鎖 |封鎖
|攻擊面減少規則 |封鎖 |允許 |允許
|Windows Defender 應用程式控制 |允許 |封鎖 |允許 |
|Windows Defender 應用程式控制 |封鎖 |允許 |封鎖
|Microsoft Defender 防毒軟體排除 |允許 |封鎖 |允許

## <a name="see-also"></a>另請參閱

- [建立指示器](manage-indicators.md)
- [建立 IP 和 URL/網域的指示器](indicator-ip-domain.md)
- [根據憑證建立指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
