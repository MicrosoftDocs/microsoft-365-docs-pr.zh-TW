---
title: 利用威脅和弱點管理修正弱點
description: 修正透過安全性建議所發現的安全性弱點，視需要在威脅和弱點管理中建立例外狀況。
keywords: Microsoft Defender for Endpoint tvm 修復，Microsoft Defender for Endpoint tvm，威脅和弱點管理，威脅 & 漏洞管理，威脅 & 漏洞管理修正，tvm 修復 intune，tvm 修正 sccm
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
ms.openlocfilehash: 56b6c809e31285bbfae47a5fdcc0446890919e8b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934066"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>利用威脅和弱點管理修正弱點

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>要求修正

Microsoft Defender for Endpoint 中的威脅和弱點管理功能會透過修正要求工作流程，在安全性與 IT 系統管理員之間取得橋樑。 安全性管理員贊您可要求 IT 管理員從 Intune 的 **安全性建議** 頁面修復弱點。

### <a name="enable-microsoft-intune-connection"></a>啟用 Microsoft Intune 連線

若要使用此功能，請啟用您的 Microsoft Intune 連線。 在 Microsoft Defender Security Center 中，流覽至 [**設定**]  >  **[一般**  >  **高級功能**]。 向左下向和尋找 **Microsoft Intune** 連線。 預設會關閉切換功能。 開啟您 **的** **Microsoft Intune** 連線切換功能。

**附注**：如果您已啟用 intune 連線，您可以在建立修復要求時，取得建立 intune 安全性工作的選項。 如果未設定 connection，則不會顯示此選項。

請參閱 [使用 Intune 修復 Microsoft Defender For Endpoint 所識別的漏洞](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) 以取得詳細資訊。

### <a name="remediation-request-steps"></a>修正要求步驟

1. 移至 Microsoft Defender Security Center 中的 [威脅與弱點管理] 流覽功能表，然後選取 [ [**安全性建議**](tvm-security-recommendation.md)]。

2. 選取您要要求修復的安全性建議，然後選取 [ **修正選項**]。

3. 填寫表單，包含您要求修正的專案、適用的裝置群組、優先順序、到期日及選用的附注。
    1. 如果您選擇「需要注意」修正選項，由於沒有特定動作，所以無法使用選取到期日。

4. 選取 [ **提交要求**]。 送出修正要求會在威脅和弱點管理中建立修復活動專案，以用於監視此建議的修正進度。 這不會觸發修復或將任何變更套用到裝置。

5. 通知 IT 管理員有關新要求的資訊，讓他們登入 Intune，以核准或拒絕要求，然後啟動套件部署。

6. 移至 [ [**修復**](tvm-remediation.md) ] 頁面，以查看修正要求的狀態。

如果您想要檢查票證在 Intune 中的顯示方式，請參閱 [使用 Intune 修復 Microsoft Defender For Endpoint 所識別的漏洞](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) 以取得詳細資訊。

>[!NOTE]
>如果您的要求需要修正超過10000台裝置，我們只能將10000裝置傳送至 Intune 的修正裝置。

識別組織的 cybersecurity 弱點並對應至可操作的 [安全性建議](tvm-security-recommendation.md)後，開始建立安全性工作。 您可以透過與 Microsoft Intune 整合的方式建立工作，以建立修復票證。

降低組織面臨的隱患，並修正安全性建議，以提升安全性設定。

## <a name="view-your-remediation-activities"></a>查看您的修復活動

當您從 [安全性建議] 頁面提交修正要求時，它會停用修復活動。 建立可在威脅和弱點管理 **修正** 頁面中追蹤的安全性任務，並在 Microsoft Intune 中建立修正憑證。

如果您選擇「注意必要」修復選項，則不會有任何進度列、票證狀態或到期日，因為我們沒有任何實際的動作可供監視。

在 [修復] 頁面上，選取您要查看的修復活動。 您可以依照修復步驟、追蹤進度、查看相關的建議、匯出至 CSV 或標記為完成。
![「修復」頁面的範例，其中包含選取的修復活動，以及該活動的快顯視窗，列出描述、IT 服務和裝置管理工具，以及裝置修正進度。](images/remediation_flyouteolsw.png)

>[!NOTE]
> 完成修復活動的保留期間為180天。 若要讓修正頁面的執行效果優化，修復活動會在完成後6個月內移除。

### <a name="completed-by-column"></a>已完成（按欄）

在 [修正] 頁面上追蹤「完成者」欄中關閉修復活動的人員。

- **電子郵件地址**：手動完成工作之人員的電子郵件
- **系統確認**：任務已自動完成 (所有已修正的裝置) 
- **N/A**：無法使用資訊，因為我們不知道此舊工作的完成方式

![由具有兩列的資料行建立及完成。 已完成的一列：電子郵件的範例，另一個資料列會顯示系統確認。](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>儀表板中的主要修復活動

在「[威脅與弱點管理」儀表板](tvm-dashboard-insights.md)中查看 **主要修復活動**。 選取任何專案，以移至 [ **修復** ] 頁面。 您可以在 IT 系統管理員小組 remediates 任務之後，將修復活動標示為已完成。

![主要修復活動卡的範例，其中會列出由安全性建議所產生之主要活動的表格。](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>相關文章

- [威脅和弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [儀表板](tvm-dashboard-insights.md)
- [安全性建議](tvm-security-recommendation.md)