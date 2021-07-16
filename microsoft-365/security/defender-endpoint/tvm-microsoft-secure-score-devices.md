---
title: 裝置用 Microsoft 安全分數
description: 您的裝置得分會顯示跨應用程式、作業系統、網路、帳戶及安全性控制裝置的集合安全性設定狀態。
keywords: 適用于裝置的 microsoft 安全分數、microsoft Defender for 裝置的端點 microsoft 安全評分、安全分數、設定分數、威脅與弱點管理、安全性控制、改進機遇、安全性設定分數，一段時間，安全性狀況，基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13307d3205818d41e7b2219b4e3a4ed6e9f2d5bb
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454777"
---
# <a name="microsoft-secure-score-for-devices"></a>裝置用 Microsoft 安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> 設定分數現在是裝置威脅與弱點管理的一部分，成為裝置的 Microsoft 安全分數。

您的裝置得分會顯示在 Microsoft 365 Defender 入口網站的[威脅與弱點管理儀表板](tvm-dashboard-insights.md)中。 針對裝置的 Microsoft 安全分數較高表示您的端點對 cybersecurity 威脅攻擊的彈性程度較高。 它會反映各類裝置的集合安全性設定狀態，其方式如下：

- 應用程式
- 作業系統
- 網路
- 帳戶
- 安全性控制項

選取類別以移至 [ [**安全性建議**](tvm-security-recommendation.md) ] 頁面，然後查看相關的建議。

## <a name="turn-on-the-microsoft-secure-score-connector"></a>開啟 Microsoft Secure 得分連接器

轉寄 Microsoft Defender for Endpoint 信號，讓 Microsoft 安全分數能夠看到裝置安全狀況。 轉寄的資料會與您的 Microsoft 安全分數資料儲存在相同的位置。

變更可能需要數小時的時間，才能在儀表板中反映。

1. 在功能窗格中，移至 **設定**  >  **端點**  >  **一般**  >  **高級功能** 

2. 向左下往 **Microsoft 安全分數** ，將設定切換為 [ **開啟**]。

3. 選取 [ **儲存喜好** 設定]。

## <a name="how-it-works"></a>運作方式

>[!NOTE]
> 目前裝置的 Microsoft 安全評分支援透過「群組原則」設定的設定。 由於目前的部分 Intune 支援，可能已透過 Intune 設定的設定會因設定錯誤而顯示。 當您的組織使用 Intune 進行安全設定管理時，請與您的 IT 系統管理員聯繫，以確認實際的設定狀態。

[裝置的 Microsoft 安全計分] 中的資料是 meticulous 和日常弱點探索程式的產品。 它會以持續進行的設定探索評估進行匯總：

- 比較收集的基準與收集的基準，以發現配置錯誤的資產
- 將設定對應至可修正或部分修正的漏洞 (風險降低) 
- 收集及維護最佳作法設定基準 (廠商、安全性摘要、內部研究小組) 
- 從所有資產收集及監視安全性控制設定狀態的變更

## <a name="improve-your-security-configuration"></a>提升您的安全性設定

修正安全性建議清單中的問題，以改善安全性設定。 當您這麼做時，裝置的 Microsoft 安全評分會提升，而且您的組織會變得更具彈性，以防禦 cybersecurity 威脅和弱點。

1. 從威脅與弱點管理儀表板中的 [裝置卡片] 的 [Microsoft 安全計分]，選取其中一個類別。 您將會看到與該類別相關的建議清單。 將會帶您前往 [ [**安全性建議**](tvm-security-recommendation.md) ] 頁面。 如果您想要查看所有安全性建議，只要您到達 [安全性建議] 頁面，就會清除 [搜尋] 欄位。

2. 選取清單中的專案。 隨即會開啟彈出面板，其中會顯示與建議相關的詳細資料。 選取 [ **修復選項**]。

   :::image type="content" alt-text="安全性控制相關的安全性建議。" source="images/security-controls.png":::

3. 閱讀描述以瞭解問題的內容及下一步的工作。 選取 [到期日]、[新增附注]，然後選取 [將 **所有修復活動資料匯出至 CSV** ]，以便將其附加至電子郵件進行後續工作。

4. **提交要求**。 您會看到一則確認訊息，表明已建立修復工作。

   :::image type="content" alt-text="修正任務建立確認。" source="images/remediation-task-created.png":::

5. 儲存 CSV 檔案。

   :::image type="content" alt-text="儲存 csv 檔案。" source="images/tvm_save_csv_file.png":::

6. 傳送追蹤電子郵件給您的 IT 系統管理員，並允許您為修正所分派的時間傳播至系統。

7. 再次檢查儀表板上的 [ **裝置的 Microsoft 安全計分** ] 卡片。 安全性控制建議的數目會減少。 當您選取 [ **安全性控制** 措施回到 **安全性建議** ] 頁面時，您所寄出的專案將不再列出。 您的裝置的 Microsoft 安全評分應該會增加。

>[!IMPORTANT]
>若要提升您的漏洞評估偵測率，請下載下列強制執行的安全性更新，並在您的網路中加以部署：
>- 19H1 客戶 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- RS5 客戶 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- RS4 客戶 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- RS3 客戶 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>若要下載安全性更新：
>1. 移至 [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx)。
>2. 在您需要下載的安全性更新 KB 編號中，按一下 [機碼]，然後按一下 [ **搜尋**]。  

## <a name="related-topics"></a>相關主題

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [儀表板](tvm-dashboard-insights.md)
- [暴險分數](tvm-exposure-score.md)
- [安全性建議](tvm-security-recommendation.md)
