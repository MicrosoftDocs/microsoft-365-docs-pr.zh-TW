---
title: 查看和組織 Microsoft Defender for Endpoint devices 清單
description: 深入瞭解您可以從 [裝置] 清單中使用的功能，例如排序、篩選和匯出清單，以加強調查。
keywords: 排序、篩選、匯出、csv、裝置名稱、網域、最後一次查看的內部 IP、健康狀態、作用中警示、作用中的惡意程式碼偵測、威脅類別、審閱警示、網路、連線、惡意程式碼、一般惡意程式碼、stealer、勒索軟體、攻擊、威脅、一般惡意程式碼、不需要的軟體
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
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861572"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>查看和組織 Microsoft Defender for Endpoint Devices 清單

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


[ **裝置] 清單** 會顯示您網路中產生警示的裝置清單。 依預設，佇列會顯示過去30天內看到的裝置。  

您將會看到諸如網域、風險層級、作業系統平臺及其他詳細資訊等資訊，以便更輕鬆地識別最具風險的裝置。

您可以選擇從多個選項自訂 [裝置] 清單視圖。 您可以在上方導覽上進行下列作業：

- 新增或移除欄
- 以 CSV 格式匯出整個清單
- 選取每頁顯示的專案數
- 套用篩選

在上架過程中， **裝置清單** 會隨著裝置開始報告感應器資料而逐漸填滿。 使用此視圖在線上時追蹤架端點，或下載完整的端點清單做為 CSV 檔案以供離線分析使用。

>[!NOTE]
> 如果您匯出的是裝置清單，它會包含您組織中的每一部裝置。 視您的組織規模而定，可能需要很長的時間才能下載。 以 CSV 格式匯出清單會以未篩選的方式顯示資料。 CSV 檔案會包含組織中的所有裝置，不論該視圖本身所套用的篩選。

![具有裝置清單的裝置清單影像](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>排序及篩選裝置清單

您可以套用下列篩選器來限制警示清單，並取得更具焦點的視圖。

### <a name="risk-level"></a>風險層級

風險層級會根據因素的組合，反映裝置的整體風險評估，包括裝置上作用中警示的類型和嚴重性。 解決作用中的警示、核准修復活動，以及抑制後續的警示，可降低風險等級。

### <a name="exposure-level"></a>公開層級

暴露層級會根據未決安全性建議的累計影響，反映裝置目前的公開情況。 可能的層級為低、中和高。 危險性低表示您的裝置不易受到攻擊。

如果暴露層級說「沒有可用的資料」，這可能是因為這種情況的原因：

- 裝置停止報告超過30天–在此情況下，它會被視為非使用中，而且不會計算曝光
- 不支援裝置作業系統-請參閱 [Microsoft Defender For Endpoint 的基本需求](minimum-requirements.md)
- 具有陳舊代理程式的裝置 (很少) 

### <a name="os-platform"></a>作業系統平臺

僅選取您想要調查的作業系統平臺。

### <a name="health-state"></a>健康狀態

依下列裝置健康狀態進行篩選：

- 使用 **中–對服務主動報告** 感應器資料的裝置。
- **非** 使用中–已完全停止傳送信號的裝置超過7天。
- 未 **正確**–與服務通訊或無法傳送感應器資料的裝置。 設定錯誤的裝置可進一步分類為：
  - 無感應器資料
  - 受損的通訊

  如需如何解決誤設定之裝置之問題的詳細資訊，請參閱， [修正狀況不良的感應器](fix-unhealthy-sensors.md)。

### <a name="antivirus-status"></a>防病毒狀態

依防病毒狀態篩選裝置。 僅適用于使用中 Windows 10 裝置。

- **Disabled** -已關閉病毒 & 威脅防護。
- **不報告** -病毒 & 威脅防護不會報告。
- **未更新** -病毒 & 威脅防護不是最新的。

如需詳細資訊，請參閱 [View The 威脅 & 弱點管理儀表板](tvm-dashboard-insights.md)。

### <a name="threat-mitigation-status"></a>威脅緩解狀態

若要查看可能受到特定威脅影響的裝置，請從下拉式功能表中選取威脅，然後選取需要緩解的弱點方位。

若要深入瞭解特定威脅，請參閱 [威脅分析](threat-analytics.md)。 如需緩解資訊，請參閱 [威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)。

### <a name="windows-10-version"></a>Windows 10 版本

僅選取您想要調查的 Windows 10 版本。

### <a name="tags--groups"></a>& 群組的標記

根據您已新增至個別裝置的分組及標記，篩選清單。 請參閱 [建立及管理裝置標記](machine-tags.md) ，以及 [建立和管理裝置群組](machine-groups.md)。

## <a name="related-topics"></a>相關主題

- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
