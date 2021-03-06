---
title: '在 Microsoft 隱私權管理 (預覽中尋找及顯示個人資料) '
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: 深入瞭解隱私權管理中的概述和資料設定檔，以及如何深入瞭解組織 Microsoft 365 環境中的個人資料。
ms.openlocfilehash: d8ea8d3306840244aff7621a12702d0ca19062c0
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378505"
---
# <a name="find-and-visualize-personal-data-in-privacy-management-preview"></a>在隱私權管理 (預覽中尋找及顯示個人資料) 

在本文中：深入瞭解 **一覽** 和 **資料設定檔** 頁面的功能，以及如何深入瞭解您的資料。

## <a name="purpose-of-the-overview-and-data-profile"></a>概覽和資料設定檔的目的

Microsoft 365 隱私權管理可讓您在環境中尋找及顯示個人資料的功能。 此解決方案會在 Exchange、SharePoint、OneDrive 和 Teams 中自動化個人資料資產的探索，並提供儀表板，以提供資料中的主要洞察力。 您的隱私權管理員可以採取這些洞察力，以加強組織對隱私權的處理方式並降低風險。

### <a name="overview-page"></a>概觀頁面

[一覽表] 頁面是隱私權管理解決方案的整體儀表板，呈現您組織個人資料生態系統的動態洞察力。 隱私權管理員可以監視資料趨勢與活動、找出並調查個人資料的潛在風險，以及 springboard 至主要活動，例如原則管理或主體許可權要求動作。 如需詳細資訊，請參閱 [探索 [一覽表] 頁面](#explore-the-overview-page)。

### <a name="data-profile-page"></a>資料設定檔頁面面

[隱私權管理] 中的 [資料設定檔] 頁面提供您的組織在 Microsoft 365 中儲存的個人資料的快照視圖。 這可協助您直觀顯示個人資料的所在位置、組織最流行的類型，以及您的 Microsoft 365 服務中存在多少不同類型。 您也可以從這個位置探索個人資料。 若要深入瞭解，請參閱 [探索 [資料設定檔] 頁面](#explore-the-data-profile-page)。

## <a name="explore-the-overview-page"></a>探索概覽頁面

[一覽表] 頁面包含三個主要區段。 頁面頂端的麻將牌提供有關資料的重要最近更新統計資料。 《重要資訊」一節提供有關趨勢和重要關注領域的調查機會。 如需資料環境的進一步觀點，請參閱趨勢線圖表。 若要深入瞭解這些區域，請參閱下列各節。

### <a name="top-tiles"></a>上磚

#### <a name="policy-matches-over-past-7-days"></a>符合過去7天的原則

當原則在隱私權管理內設定時，您的資料將會針對可能出現隱私權風險的某些條件進行評估。 原則相符表示可能需要進一步審查或修復的資料發現。 此卡片顯示過去7天內發生的任何原則符合專案計數。 在這裡會出現「相符」原則是在測試模式中執行或執行的原則，因此您可以看到所有作用中原則的結果。 按一下此麻將牌會帶您前往隱私權管理之 [原則] 頁面的篩選視圖，顯示在過去7天內，出現相符的原則。

#### <a name="items-with-personal-data"></a>包含個人資料的專案

若要查看隱私權管理解決方案的自動探索功能，請查看包含個人資料磚的專案。 這會顯示過去7天內，組織的 Microsoft 365 環境中已發現包含個人資料的新專案數目。 按一下此麻將牌會載入找到的最新100專案的視圖。

#### <a name="subject-rights-requests"></a>主體權力要求

[一覽] 頁面的上方麻將牌包含與主體權力要求相關的兩個麻將牌。 第一個顯示過去7天建立的要求計數。 第二個麻將牌會匯總逾期的要求，而且可能需要立即注意。 按一下這些麻將牌會讓使用者具備隱私權管理的「主題權利要求」頁面的適當許可權。

### <a name="key-insights"></a>重要資訊

#### <a name="content-items-with-the-most-personal-data"></a>具有最多個人資料的內容專案

組織中包含大量個人資料的 Microsoft 365 環境中的內容，可能會帶來風險較高的風險。 您可能想要查看這些專案，以確保隱私權管理原則涵蓋這些專案。 為了協助您注意這些專案，[一覽] 頁面會提供您的內容專案中包含大部分個人資料的視圖。 您可以在這裡看到偵測到的獨特個人資料類型數目、已識別的唯一內容擁有人數量，以及已根據主體許可權要求的資料比對設定所識別的資料主體數目。

選取 [查看摘要] 以查看找到之專案的摘要視圖。 您也可以選擇探索這些調查結果，以預覽個別檔案。 此視圖顯示最多100個專案。 隱私權管理角色群組中的使用者可以選取檔案，以查看詳細資料及判斷相關性，並以 .csv 格式匯出清單以供參考。

#### <a name="policies-with-the-most-matches-in-the-last-week"></a>最後一周最符合的原則

此深入瞭解會展示哪些原則在過去7天內最常符合的原則，不論是在「On」模式或「測試」。 這有助於說明您的原則效能及現行工作的影響，因為您的隱私權管理使用者會收到訓練，而且能夠解決內容的問題並精煉其隱私權行為。

選取 [查看摘要]，以取得符合前10個原則的摘要和關聯內容的內容擁有者。 您也會看到由於這些原則相符而傳送的使用者通知數目，以及所採取的使用者動作數目。 選取 [調查]，以查看 [隱私權管理] 中的 [原則] 頁面，已篩選，以顯示摘要視圖中的原則。 此調查視圖會顯示完整的原則生命週期的統計資料。 選取它，以查看詳細資料，例如初次偵測符合專案的時間。

#### <a name="users-with-the-most-policy-matched-in-the-last-week"></a>最近一周內符合最高原則的使用者

這種洞察力也會解決「測試」或「開啟」模式中的原則的相符情況。 它可讓您在過去一周內，查看具有最符合原則的使用者摘要，以及其符合的原則。 這包括獨特內容擁有者的總數、傳送給這些使用者的通知，以及這些通知所採取的動作數目。 選取 [調查] 會帶您前往 [原則] 頁面，篩選成顯示摘要視圖中的原則。 在 [調查] 視圖中，您將找不到使用者資訊，但您可以選取原則，以查看與這些相符專案相關的原則詳細資訊。

#### <a name="items-with-the-most-data-subject-content"></a>具有最多資料主體內容的專案

這項洞察力是指來自主體權利要求中的資料比對功能，以及在 Microsoft 365 中探索的專案，這些專案包含其內容中的最多資料主體。 若要深入瞭解該設定，請參閱 [管理主體權力要求](privacy-management-subject-rights-requests.md)。

這些專案可協助確認您的資料比對設定，並協助您緩解這些專案相關的隱私權風險。 選取摘要視圖的 [查看摘要]。 選取 [探索]，以查看這些專案中最多100個專案的詳細資訊。 您可以在這裡預覽這些專案並判斷相關性，並以 .csv 格式匯出清單。

### <a name="trendline-graphs"></a>趨勢線圖形

如需組織資料中所發現趨勢的動態視覺化效果，請參閱趨勢線圖表。 您可以根據所提供資訊的相關特性來篩選這些圖形，例如資料的範圍、資料類型或資料位置。 使用提供的下拉式功能表來調整您的視圖。 在圖形中的線條上懸停，可讓您查看與該特定時間點相關的統計資訊。

與原則相關的結果會在「測試」和「開啟」模式中包含來自原則的資料。 如果沒有任何特定類型的原則為使用中，則相關的圖表將不會顯示任何結果。

#### <a name="active-policy-alerts"></a>主動原則警示

此區域顯示原則相符觸發的使用中警示的快照。 經過一段時間後，此視圖可協助您更輕鬆地偵測 abnormalities，例如大量的大量峰值。 選取 [View alerts] （查看）以流覽至隱私權管理中的原則頁面，您可以在其中進一步調查提醒並建立修復的問題。

#### <a name="personal-data-found-in-organization"></a>組織中找到的個人資料

此圖顯示在 Microsoft 365 環境中已發現的個人資料量及其所在位置的趨勢。 當隱私權管理已執行足夠的時間，且在 SharePoint、OneDrive、Teams 和/或 Exchange 內找到含個人資料的內容之後，它就會開始進行填充。

#### <a name="data-transfers-detected-in-organization"></a>組織中偵測到的資料傳輸

此圖形與資料傳送原則相關。 它會提供資料在組織內的移動方式，也就是多地理位置組織的部門之間或地區之間的移動方式。

#### <a name="unused-personal-data"></a>未使用的個人資料

此圖形與資料最小化原則相關。 它可深入瞭解您的組織如何儲存包含個人資料的內容，以及您的原則如何在一段時間後改善對此資料的處理。

#### <a name="overexposed-personal-data"></a>Overexposed 個人資料

此圖形與資料 overexposure 原則相關。 它可以協助您在組織中識別共用行為，以及可以 overexposed 具有個人資料之內容的位置（例如，以公開方式共用、與外部使用者共用，或在組織內廣泛共用）。

#### <a name="subject-rights-requests-by-regulation"></a>依規定的主體許可權要求

這種觀點可深入瞭解 prevalently 您的主體權力要求最高的規章。 此圖表的圖例顯示各種規章。 在趨勢線上懸停會顯示在選取的時間內針對該規定開啟的主體權力要求總數。

#### <a name="subject-rights-requests-by-status"></a>依狀態的主體許可權要求

此圖顯示您的組織如何完成主體權力要求、分解為主動、封閉式或逾期的要求。 這裡的結果可能會協助指出您可以從哪些方面獲得更多資源，以關閉您的要求和會議目標。

### <a name="additional-data-views"></a>其他資料檢視

#### <a name="subject-rights-requests-at-a-glance"></a>主體權力要求一覽

此視圖提供使用中主體許可權要求的高層級視圖，包括完成要求的時間（按其定義的期限）。 它會摘要說明您有多少個要求、多少作用中，以及已關閉的要求數目。 選取 [View all requests to to the subject rights requests] 頁面，您可以在其中查看進一步的詳細資料，並處理使用中的要求，以進行完成。

#### <a name="subject-rights-requests-by-residency"></a>派駐服務的主體權力要求

此地圖視圖可協助您透過資料主體的派駐所要求的主體許可權。 將滑鼠停留在氣泡上方，可找出代表居民開啟之主體權力要求的地區和總數。

## <a name="explore-the-data-profile-page"></a>探索 [資料設定檔] 頁面

### <a name="personal-data-type-instances-detected-in-microsoft-365"></a>在 Microsoft 365 中偵測到個人資料類型實例

這張卡片可協助您直觀顯示 Microsoft 365 環境中存在多少個人資料，以及如何在 Exchange、OneDrive、SharePoint 及 Teams 之間散佈資料。

柱狀圖圖表顯示在內容中找到的唯一個人資料類型實例的大致合計計數。 資料類型的範例可能包含信用卡號碼和社會保險號碼等專案。 因此，包含三個信用卡號碼和一個社會保險號碼的發現檔案，會包含兩個唯一的個人資料類型和四個實例。 這張牌的下一層會顯示每個 Microsoft 365 位置內的唯一個人資料類型。 它可讓您看到組織內容中偵測到的個人資料類型的多樣性。

### <a name="top-personal-data-types-across-your-organization"></a>組織內的主要個人資料類型

這張卡片可提供您環境中所偵測到的最上層個人資料類型的快照，以及有關包含該個人資料類型和位置之專案數的資訊。

### <a name="personal-data-by-region"></a>依地區的個人資料

在多地理位置環境中，此卡地區會根據主控此內容的地區，匯總在內容中找到的個人資料類型實例。 若為單一地區組織，這張卡片會顯示一個代表 Microsoft 365 服務位置的點。 在地圖上的點上懸停會顯示在該地區中探索的個人資料類型實例的大致計數。

### <a name="exploring-content"></a>探索內容

在任何資料設定檔卡片上選取 [ **探索** ]，即可開啟內容瀏覽器。 此時，您無法搜尋特定的內容專案，也不會在此視圖中看到 Teams 資料。 這表示內容瀏覽器內的數位可能與 [資料設定檔] 頁面上顯示的數位不符，因為 [資料設定檔] 頁面包括 Teams 內容。 想要進一步深入瞭解其隱私權資料的隱私權系統管理員可能會根據個人資料類型 (敏感資訊類型) 或位置 (Exchange、OneDrive 或 SharePoint) 來進行。
