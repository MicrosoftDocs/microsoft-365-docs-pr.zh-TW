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
ms.openlocfilehash: d78f90e78a50d5902070f441a1d60693a5f531c8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185716"
---
# <a name="create-indicators-for-files"></a>建立檔案的指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

您可以 banning 潛在的惡意檔案或可疑惡意程式碼，以避免進一步傳播您組織中的攻擊。 如果您知道可能是惡意遷移的可執行檔 (PE) file，您可以將它封鎖。 此作業可防止在組織中的機器上讀取、寫入或執行此作業。

您可以透過兩種方式來建立檔案的指示器：
- 透過 [設定] 頁面建立指示器
- 使用 [檔案詳細資料] 頁面中的 [新增指示器] 按鈕建立上下文指示器

### <a name="before-you-begin"></a>開始之前
在建立檔案的指示器之前，請務必先瞭解下列必要條件：

- 如果您的組織使用 Windows Defender 防病毒和雲端式保護，則可以使用此功能。 如需詳細資訊，請參閱 [在 Microsoft Defender 防毒軟體中使用下一代技術（透過雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)）。
- 反惡意軟體用戶端版本必須是4.18.1901 或更新版本。
- 在 Windows 10 版本1703或更新版本、Windows server 2016 及2019上的電腦上支援。
- 若要開始封鎖檔案，您必須先在 [設定] 中 [關閉 [ **封鎖] 或 [允許** ] 功能](advanced-features.md) 。
- 這項功能的設計是為了防止可疑的惡意程式碼 (或可能的惡意檔案) 從網頁下載。 它目前支援可遷移的可執行檔 (PE) 檔案（包括 _.exe_ 和 _.dll_ 檔案）。 覆蓋範圍會隨著時間擴充。

>[!IMPORTANT]
>- 如果檔案的分類存在於 allow 或封鎖動作之前的設備快取上，則無法在檔案上執行 allow 或 block 功能 
>- 受信任的簽署檔會以不同方式處理。 已優化用於處理惡意檔的 Defender for Endpoint。 嘗試封鎖信任的簽署檔案，在某些情況下，可能會有效能的含義。

 
>[!NOTE]
>通常會在幾分鐘內強制執行檔封鎖，但可長達30分鐘。

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>從 [設定] 頁面建立檔案的指標

1. 在功能窗格中，選取 [**設定**  >  **指示器**]。  

2. 選取 [檔案 **雜湊** ] 索引標籤。

3. 選取 [ **新增指示器**]。

4. 指定下列詳細資料：
   - 標記-指定實體詳細資料並定義指示器的到期期限。
   - Action-指定要採取的動作並提供描述。
   - Scope-定義機器群組的範圍。

5. 在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>從 [檔案詳細資料] 頁面建立上下文指示器
對檔案採取 [回應動作](respond-file-alerts.md) 的其中一個選項是為檔案新增標記。 

當您為檔案新增指示器雜湊時，您可以選擇每當組織中的機器嘗試執行時，才引發警示並封鎖檔。

標記自動封鎖的檔案不會出現在檔案的動作中心，但提醒仍會顯示在 [警示] 佇列中。


## <a name="related-topics"></a>相關主題
- [建立指示器](manage-indicators.md)
- [為 IPs 和 URLs/網域建立指示器](indicator-ip-domain.md)
- [根據憑證建立指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
