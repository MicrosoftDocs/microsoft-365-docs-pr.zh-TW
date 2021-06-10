---
title: 調查 Microsoft Defender 的端點檔案
description: 使用調查選項可取得與警示、行為或事件相關聯之檔案的詳細資料。
keywords: 調查、調查、檔、惡意活動、攻擊動機、深入分析、深入分析報告
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186062"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>調查與 Microsoft Defender for Endpoint alert 相關聯的檔案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

調查與特定警示、行為或事件相關聯之檔案的詳細資料，以協助判斷該檔案是否展示惡意活動、識別攻擊動機，以及瞭解遭到破壞的潛在範圍。

有許多方式可以存取特定檔案的詳細設定檔頁面面。 例如，您可以使用「搜尋」功能，按一下 **警示處理樹狀目錄**、 **事件曲線圖**、 **專案時程表** 中的連結，或選取 **裝置時程表** 中所列的事件。

在 [詳細設定檔] 頁面上，您可以透過 [切換新的檔案] **頁面**，在新的和舊的頁面配置之間切換。 本文的其餘部分將說明較新的頁面配置。

您可以從下列 [檔案] 視圖中的區段取得資訊：

- 檔案詳細資料、惡意程式碼偵測、檔傳播
- 深入分析
- 警示
- 組織中的觀測
- 深入分析
- 檔案名稱

您也可以從這個頁面對檔案採取動作。

## <a name="file-actions"></a>檔動作

在 [設定檔] 頁面上，沿著檔資訊卡片上方。 您可以在這裡執行的動作包括：

- 停止和隔離
- 新增/編輯指示器
- 下載檔案
- 諮詢威脅專家
- 控制中心

如需這些動作的詳細資訊，請參閱 [在檔案上採取回應動作](respond-file-alerts.md)。

## <a name="file-details-malware-detection-and-file-prevalence"></a>檔案詳細資料、惡意程式碼偵測和檔傳播

檔案詳細資料、事件、惡意程式碼偵測和檔案流行卡會顯示檔案的各種屬性。

您會看到詳細資料，例如檔案的 MD5、病毒的偵測比率，以及 Microsoft Defender AV 偵測（若有的話），以及檔案的流行情況。

檔傳播卡片顯示在組織中的裝置及全球範圍內，看到該檔案的位置。 

> [!NOTE] 
> 不同的使用者可能會在檔傳播卡片的 [ *組織中的裝置* ] 區段中看到不同的值。 這是因為名片會根據使用者所擁有的 RBAC 範圍來顯示資訊。 也就是說，如果使用者已被授與特定裝置集，只會看到這些裝置上的檔組織傳播。

![檔資訊影像](images/atp-file-information.png)

## <a name="alerts"></a>警示

[ **警示** ] 索引標籤提供與檔案相關聯的警示清單。 此清單涵蓋許多與警示佇列相同的資訊，但裝置群組（如果有的話）屬於，則受影響裝置除外。 您可以從欄標題上方的工具列中，選取 [ **自訂資料行** ]，以選擇要顯示的資訊類型。

![與檔案區段相關的警示圖像](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a>組織中的觀測

[ **在組織中看到** 的] 索引標籤可讓您指定日期範圍，以查看哪些裝置已對檔案進行觀測。

>[!NOTE]
>此索引標籤會顯示100裝置的數目上限。 若要查看檔案中的 _所有_ 裝置，請從索引標籤欄上方的 [動作] 功能表中，選取 [ **匯出** ]，將索引標籤匯出至 CSV 檔案。

![具有檔案的最近觀測裝置的影像](images/atp-observed-machines.png)

使用滑塊或範圍選取器，快速指定您要檢查與檔案相關之事件的時段。 您可以指定小至一天的時間範圍。 這可讓您在該時間只看到與該 IP 位址通訊的檔案，以大幅減少不必要的滾動和搜尋。

## <a name="deep-analysis"></a>深入分析

[ **深入分析** ] 索引標籤可讓您 [提交檔案進行深入分析](respond-file-alerts.md#deep-analysis)，以找出檔案行為的詳細資訊，以及組織內所用的影響。 在您提交檔案之後，[詳細分析] 報告會在此索引標籤中出現一次可用結果。 如果深入分析沒有找到任何專案，則報告將會是空的，而且結果空間也會保留空白。

![深入分析索引標籤的影像](images/submit-file.png)

## <a name="file-names"></a>檔案名稱

[檔案 **名稱** ] 索引標籤會列出已在組織中觀測出的所有檔案名。

![[檔案名] 索引標籤的影像](images/atp-file-names.png)

## <a name="related-topics"></a>相關主題

- [查看和組織 Microsoft Defender for Endpoint 佇列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
- [調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址](investigate-ip.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
- [調查 Microsoft Defender for Endpoint 中的使用者帳戶](investigate-user.md)
- [對檔案採取回應動作](respond-file-alerts.md)
