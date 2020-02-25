---
title: 調查 Microsoft 威脅防護中的事件
description: 分析與裝置、使用者和信箱相關的事件。
keywords: 事件,電腦,裝置,使用者,身分識別,郵件,電子郵件,信箱,調查,圖形,證據
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7e0e98c94f66e2cac9300a65d0000b4447ec6d2b
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235102"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>調查 Microsoft 威脅防護中的事件

**適用於：**
- Microsoft 威脅防護




Microsoft 威脅防護可彙總各種裝置、使用者和信箱的所有相關警示、資產、調查和證據，讓您全面了解整個攻擊範圍。 

調查影響您網路的警示、了解其含義，並彙整與該事件相關聯的證據，以便設計有效的修復方案。 

## <a name="investigate-an-incident"></a>調查事件

1. 從事件佇列中選取事件。 <BR> 這會開啟側邊面板，並預覽重要資訊，例如狀態、嚴重性、類別和受影響的實體。

    ![事件側邊面板影像](../../media/incident-side-panel.png)

2. 選取**開啟事件頁面**。 <BR> 這會開啟事件頁面，您可以在此找到更多資訊事件詳細資料、註解和動作、索引標籤 (概觀、警示、裝置、使用者、調查、證據)。

3. 檢閱涉及事件的警示、裝置、使用者和其他實體。

## <a name="incident-overview"></a>事件概觀 
概觀頁面可讓您一覽無遺地了解事件的主要內容。


![事件概觀頁面影像](../../media/incidents-overview.png)


攻擊類別為您提供視覺和數字檢視，以了解這項攻擊對終止鏈的進展狀況。 如同其他 Microsoft 安全性產品，Microsoft 威脅防護保護與 [MITRE ATT&CK&trade;](https://attack.mitre.org/) 架構一致。 

範圍區段會顯示屬於此事件中影響最大的資產清單。 如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。

警示時間表可讓您先預覽警示發生的時間順序，以及這些警示與此事件相關聯的原因。

最後，證據區段提供事件中包含多少不同成品以及其修復狀態摘要，因此您可以立即識別是否需要採取任何動作。 

此概觀藉由提供您應該注意的事件主要特性深入解析，可協助對事件進行初步分級。 


## <a name="alerts"></a>警示 
您可以檢視與該事件相關的所有警示，以及與該事件相關的其他資訊，例如嚴重性、涉及警示的實體、警示來源 (Azure ATP、Microsoft Defender ATP、Office 365 ATP)，以及連結在一起的原因。 

![事件警示頁面影像](../../media/incident-alerts.png)

根據預設，警示會依時間順序排列，讓您首先檢視攻擊如何隨時間推移而進行。 按一下每個警示，就會引導您至相關警示頁面，您可以在該頁面中深入調查警示。 

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
調查已識別為指定事件一部分或與相關的信箱。 若要執行進一步調查工作，選取與郵件相關的警示，將會開啟 Office 365 進階威脅防護，便可進行修復。


![事件信箱索引標籤影像](../../media/incident-mailboxes.png)

## <a name="investigations"></a>調查
選取 [調查] **** 即可在此事件中透過警示查看所有觸發的自動化調查內容。 調查將執行修復動作或等待分析人員核准動作，具體取決於您如何設定自動化調查以在 Microsoft Defender ATP 和 Office 365 進階威脅防護中執行。

![事件調查索引標籤影像](../../media/incident-investigations.png)


選取調查以瀏覽至 [調查詳細資料] 頁面，取得調查和修復狀態的完整資訊。 如果有任何待核准的動作為調查的一部分，將顯示在 [擱置中的動作] 索引標籤中。採取動作，作為事件修復的一部分。


## <a name="evidence"></a>證據
Microsoft 威脅防護會自動調查警示中所有事件支援活動和可疑實體，為您提供重要檔案、程序、服務、電子郵件等相關自動回應與資訊。 可協助您快速偵測並封鎖事件中的潛在威脅。 

![事件證據索引標籤影像](../../media/incident-evidence.png)

系統會將每個經分析的實體標示為判定結果 (惡意、可疑、清除) 以及修復狀態。 可協助您了解整個事件的修復狀態，以及進一步修復可採取的步驟。


## <a name="related-topics"></a>相關主題
- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)
