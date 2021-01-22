---
title: 調查 Microsoft 365 Defender 中的事件
description: 分析與裝置、使用者和信箱相關的事件。
keywords: 事件,電腦,裝置,使用者,身分識別,郵件,電子郵件,信箱,調查,圖形,證據
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926891"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**

- Microsoft 365 Defender

Microsoft 365 Defender 會匯總所有來自您裝置、使用者和信箱的相關警示、資產、調查與證據，以全面瞭解整起攻擊事件。

調查影響您網路的警示、了解其含義，並彙整與該事件相關聯的證據，以便設計有效的修復方案。

## <a name="investigate-an-incident"></a>調查事件

1. 從事件佇列中選取事件。 <BR> 側邊面板隨即開啟，並預覽重要資訊，例如狀態、嚴重性、類別及受影響實體。

    ![事件側邊面板影像](../../media/incident-side-panel.png)

2. 選取 **開啟事件頁面**。 <BR> 這會開啟事件頁面，您可以在其中找到事件詳細資料、批註和動作、 (、警示、裝置、使用者、調查、證據和) 。

3. 檢閱涉及事件的警示、裝置、使用者和其他實體。

## <a name="incident-overview"></a>事件概觀

概觀頁面可讓您一覽無遺地了解事件的主要內容。

![事件概觀頁面影像](../../media/incidents-overview.png)

攻擊類別提供您一個視覺化和數值的視圖，瞭解攻擊在威脅鏈中的進步進度。 與其他 Microsoft 安全性產品一樣，Microsoft 365 Defender 會與[MITRE ATT&&trade; CK](https://attack.mitre.org/)架構對齊。

範圍區段會顯示屬於此事件中影響最大的資產清單。 如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。

警示時間表可讓您先預覽警示發生的時間順序，以及這些警示與此事件相關聯的原因。

最後，證據區段提供事件中包含多少不同成品以及其修復狀態摘要，因此您可以立即識別是否需要採取任何動作。

此概觀藉由提供您應該注意的事件主要特性深入解析，可協助對事件進行初步分級。

## <a name="alerts"></a>警示

您可以查看與事件相關的所有警示及其他相關資訊，例如嚴重性、參與警示的實體、警示的來源 (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365) ，以及它們連結的原因。

![事件警示頁面影像](../../media/incident-alerts.png)

根據預設，警示會依時間順序排列，讓您首先檢視攻擊如何隨時間推移而進行。 按一下每個警示，將您引導至相關的警示頁面，您可以在此深入調查該警示。

## <a name="devices"></a>裝置

裝置索引標籤會列出所有顯示事件相關警示的裝置。

按一下執行攻擊的電腦名稱，引導您至其 [電腦] 頁面，您可以其中查看觸發的警示，以及提供的相關事件，以便輕鬆調查。

![事件機器索引標籤影像](../../media/incident-machines.png)

選取 [時間表] 索引標籤可讓您捲動電腦時程表，並以時間順序檢視電腦上觀測到的所有活動和行為，以及散布其中的警示。

## <a name="users"></a>使用者

查看已識別為指定事件一部分或與相關的使用者。

按一下使用者名稱以引導您至使用者的雲端 App 安全性頁面，可在頁面中執行進一步的調查。

![事件使用者索引標籤影像](../../media/incident-users.png)

## <a name="mailboxes"></a>信箱

調查已識別為指定事件一部分或與相關的信箱。 若要進一步進行工作，選取郵件相關警示會開啟 Office 365 的 Microsoft Defender，您可以在其中採取補救動作。

![事件信箱索引標籤影像](../../media/incident-mailboxes.png)

## <a name="investigations"></a>調查

選取 **調查** 以查看此事件警示所觸發的所有自動化調查。 視您如何將自動化調查在 Microsoft Defender for Endpoint 和 Defender for Office 365 中執行，調查將會執行補救動作，或等待分析師核准動作。

![事件調查索引標籤影像](../../media/incident-investigations.png)

選取調查以瀏覽至 [調查詳細資料] 頁面，取得調查和修復狀態的完整資訊。 如果調查期間有任何等待核准的動作，這些動作會顯示在擱置中動作的 Tab。在事件補救中採取行動。

## <a name="evidence"></a>證據

Microsoft 365 Defender 會自動調查警示中所有事件支援的事件和可疑實體，為您提供自動控制以及重要檔案、程式、服務、電子郵件等相關資訊。 可協助您快速偵測並封鎖事件中的潛在威脅。

![事件證據索引標籤影像](../../media/incident-evidence.png)

系統會將每個經分析的實體標示為判定結果 (惡意、可疑、清除) 以及修復狀態。 可協助您了解整個事件的修復狀態，以及進一步修復可採取的步驟。

## <a name="related-topics"></a>相關主題

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)

