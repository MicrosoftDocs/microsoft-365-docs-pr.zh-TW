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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592093"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**

- Microsoft 365 Defender

Microsoft 365 Defender 會將所有相關的警示、資產、調查和證據從您的裝置、使用者和信箱集中在一起，讓您全面瞭解攻擊的整體廣度。

調查影響您網路的警示、了解其含義，並彙整與該事件相關聯的證據，以便設計有效的修復方案。

## <a name="investigate-an-incident"></a>調查事件

1. 從事件佇列中選取事件。 <BR> 側邊面板隨即開啟，並預覽重要資訊（例如狀態、嚴重性、類別及受影響的實體）。

    ![事件側邊面板影像](../../media/incident-side-panel.png)

2. 選取 **開啟事件頁面**。 <BR> 這會開啟 [事件] 頁面，您可以在其中找到詳細資訊事件詳細資料、批註和動作、索引標籤 (總覽、警示、裝置、使用者、調查、證據) 。

3. 檢閱涉及事件的警示、裝置、使用者和其他實體。

## <a name="incident-overview"></a>事件概觀

概觀頁面可讓您一覽無遺地了解事件的主要內容。

![事件概觀頁面影像](../../media/incidents-overview.png)

「攻擊類別」可讓您直觀和數值的方式，顯示攻擊如何對 kill 鏈進行的進展。 與其他 Microsoft 安全性產品一樣，Microsoft 365 Defender 會對應至[MITRE ATT&CK &trade; ](https://attack.mitre.org/) framework。

範圍區段會顯示屬於此事件中影響最大的資產清單。 如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。

警示時間表可讓您先預覽警示發生的時間順序，以及這些警示與此事件相關聯的原因。

最後，證據區段提供事件中包含多少不同成品以及其修復狀態摘要，因此您可以立即識別是否需要採取任何動作。

此概觀藉由提供您應該注意的事件主要特性深入解析，可協助對事件進行初步分級。

## <a name="alerts"></a>警示

您可以查看與該事件相關的所有警示及其他相關資訊，例如警示中所涉及的嚴重性、實體、 (Microsoft Defender for Identity、Microsoft Defender for Endpoint、microsoft defender for Office 365) ，以及連結在一起的原因。

![事件警示頁面影像](../../media/incident-alerts.png)

根據預設，警示會依時間順序排列，讓您首先檢視攻擊如何隨時間推移而進行。 按一下每個警示會產生相關的警示頁面，您可以在其中對該警示進行深入調查。 瞭解如何在[調查提醒](investigate-alerts.md)中使用警示頁面和整合提醒佇列

## <a name="devices"></a>裝置

裝置索引標籤會列出所有顯示事件相關警示的裝置。

按一下執行攻擊的電腦名稱，引導您至其 [電腦] 頁面，您可以其中查看觸發的警示，以及提供的相關事件，以便輕鬆調查。

![事件機器索引標籤影像](../../media/incident-machines.png)

選取 [時間表] 索引標籤可讓您捲動電腦時程表，並以時間順序檢視電腦上觀測到的所有活動和行為，以及散布其中的警示。

> [!TIP]
> 您可以在裝置頁面上執行手動掃描。 在 Microsoft 365 的 [安全性中心] 中，選擇 [ **設備清查**]。 選取具有警示的裝置，然後執行防病毒掃描。 在 [ **裝置庫存** ] 頁面上追蹤並顯示的動作（例如防病毒掃描）。 若要深入瞭解，請參閱 [在裝置上執行 Microsoft Defender 防病毒掃描](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。


## <a name="users"></a>使用者

查看已識別為指定事件一部分或與相關的使用者。

按一下使用者名稱以引導您至使用者的雲端 App 安全性頁面，可在頁面中執行進一步的調查。

![事件使用者索引標籤影像](../../media/incident-users.png)

## <a name="mailboxes"></a>信箱

調查已識別為指定事件一部分或與相關的信箱。 若要進行進一步的調查工作，選取郵件相關的警示會開啟 Microsoft Defender for Office 365，您可以採取修正動作。

![事件信箱索引標籤影像](../../media/incident-mailboxes.png)

## <a name="investigations"></a>調查

選取 [ **調查** ]，以查看此事件中的警示所觸發的所有自動調查。 調查會執行修正動作，或等候分析員的動作批准，視您如何設定自動調查以在 Microsoft Defender for Endpoint 和 Defender for Office 365 中執行。

![事件調查索引標籤影像](../../media/incident-investigations.png)

選取調查以瀏覽至 [調查詳細資料] 頁面，取得調查和修復狀態的完整資訊。 如果有任何動作出于調查的一部分而待核准，它們就會出現在 [擱置的動作] 索引標籤中。採取動作做為事件修復的一部分。

## <a name="evidence"></a>證據

Microsoft 365 Defender 會自動調查警示中的所有事件支援事件和可疑實體，以提供 autoresponse 及重要檔案、程式、服務、電子郵件等相關資訊。 可協助您快速偵測並封鎖事件中的潛在威脅。

![事件證據索引標籤影像](../../media/incident-evidence.png)

系統會將每個經分析的實體標示為判定結果 (惡意、可疑、清除) 以及修復狀態。 可協助您了解整個事件的修復狀態，以及進一步修復可採取的步驟。

## <a name="related-topics"></a>相關主題

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [管理事件](manage-incidents.md)

