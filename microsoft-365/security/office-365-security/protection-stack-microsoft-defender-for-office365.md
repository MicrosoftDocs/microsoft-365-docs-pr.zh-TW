---
title: Microsoft Defender 的 Office 365 逐步威脅防護堆疊
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: 在 Microsoft Defender 的威脅篩選堆疊中，追蹤傳入郵件的路徑，以取得 Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1113d04cabdabe2925242cb18dde78daf9ef6e2c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194802"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender 中的逐步威脅防護

適用于 Office 365 保護或篩選堆疊的 Microsoft Defender 可分為四個階段，如本文所述。 一般說來，傳入郵件會在傳遞之前透過所有這些階段進行傳遞，但是實際的電子郵件會受到組織的 Office 365 設定的 Defender 的制約。

> [!TIP]
> 請密切關注本文結尾的所有4個階段的 *整合* 圖形，以取得 Office 365 保護！

## <a name="phase-1---edge-protection"></a>階段 1-Edge Protection

不幸的是，已過 *嚴重* 的 Edge 區塊現在相對簡單，無法克服不良的演員。 經過一段時間後，就不會在這裡封鎖流量，但它仍是堆疊的重要部分。  

Edge 區塊是設計為自動。 在誤報的情況下，寄件者會收到通知，並告知如何解決他們的問題。 來自具有有限信譽的信任合作夥伴的連接器，可確保在上架新端點時，deliverability 或暫時覆寫可就地保留。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Office 365 的 Defender 中篩選的階段1為 Edge Protection。":::

1. **網路節流** 會限制一組特定基礎結構可提交的郵件數目，以保護 Office 365 基礎結構和客戶免受拒絕服務 (DOS) 攻擊。

2. **IP 信譽及節流** 會封鎖從已知的錯誤連接 IP 位址傳送的郵件。 如果特定 IP 會在短時間內傳送許多郵件，將會受到限制。

3. **網域信譽** 會封鎖所有從已知的錯誤網域傳送的郵件。

4. **目錄型 edge 篩選** 封鎖會嘗試透過 SMTP 來收集組織的目錄資訊。

5. **退信攻擊偵測** 可防止 NDRs) 的無效未傳遞回報 (攻擊組織。

6. **針對連接器的增強篩選功能** 會保留驗證資訊，即使流量透過另一個裝置進入 Office 365 為止也是一樣。 這可提升篩選堆疊的精確度，包括啟發式叢集、反欺騙和反網路釣魚機器教學模型，即使在複雜或混合式路由案例中也是一樣。

## <a name="phase-2---sender-intelligence"></a>階段 2-寄件者情報

寄件者智慧中的功能對於捕捉垃圾郵件、大量、模仿和未經授權的欺騙性郵件很重要，也會考慮網路釣魚偵測。 大多數的功能都是可個別設定的。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Office 365 的 Defender 篩選階段2是寄件者智慧。":::

1. 當帳戶具有反常行為時，會產生「**帳戶洩漏偵測**」和「警示」。 在某些情況下，使用者帳戶會遭到封鎖，並避免傳送任何後續的電子郵件訊息，直到組織的安全性運作小組解決問題為止。

2. **電子郵件驗證** 會包含客戶設定的方法和方法在雲端中設定的方法，其目的是為了確保寄件者獲得授權、可信的郵件。 這些方法會抵禦哄騙。
    - **SPF** 可以根據 DNS TXT 記錄來拒絕郵件，這些記錄會列出可代表組織傳送郵件的 IP 位址和伺服器。
    - **DKIM** 提供可驗證寄件者的加密簽名。
    - **DMARC** 可讓系統管理員在其網域中以必要的方式標示 SPF 和 DKIM，並強制執行這兩項技術的結果。
    - **弧線** 不是由客戶設定，但是會在 DMARC 上建立，以在記錄驗證鏈時，與郵寄清單中的轉寄一起使用。

3. **欺騙性智慧** 可將允許其篩選為「哄騙」的 (，也就是代表另一個帳戶傳送郵件，或從模仿組織或已知外部網域的惡意寄件者) 郵寄清單的轉送。 它會將合法的「代表」郵件分開，以欺騙傳送垃圾郵件和網路釣魚郵件的寄件者。

    組織內的 **欺騙智慧** 偵測並封鎖來自組織內網域的欺騙嘗試。

4. **跨網域的欺騙智慧** 偵測並封鎖來自組織外部網域的欺騙嘗試。

5. **大量篩選** 可讓系統管理員設定大量信賴層級 (BCL) 指出郵件是否從大量寄件者傳送。 系統管理員可以使用反垃圾郵件原則中的大量滑塊，決定將大宗郵件視為垃圾郵件的層級。

6. **信箱智慧** 從標準使用者電子郵件行為。 它會利用使用者的通訊圖來偵測寄件者，其是否只顯示為使用者通常會與其通訊，但實際上為惡意的人。 此方法會偵測模擬。

7. **信箱智慧** 模擬會根據每個使用者的個人寄件者地圖，啟用或停用增強的模仿結果。 啟用此功能時，會協助識別模擬。

8. **使用者** 模擬可讓系統管理員建立可能模仿的高價值目標清單。 如果郵件到達的位置，寄件者的名稱和位址似乎與受保護的高價值帳戶相同，則會標記或標記郵件。  (例如，trα *tracye@contoso.com*) 的 *cye@contoso .com* 。

9. **網域** 模擬會偵測與收件者網域類似的網域，並嘗試看起來像是內部網域。 例如，此類比 tracye@liw *tracye@litware.com* 的 *αre* 。

## <a name="phase-3---content-filtering"></a>階段 3-內容篩選

在這個階段中，篩選堆疊會開始處理郵件的特定內容，包括其超連結和附件。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO 中篩選的階段3是內容篩選。":::

1. **傳輸規則** (也稱為郵件流程規則或 Exchange 傳輸規則，) 可讓系統管理員在郵件符合相同範圍的情況時採取大量的動作。 所有流經您組織的郵件都會針對已啟用的郵件流程規則/傳輸規則進行評估。

2. **Microsoft Defender 防毒軟體** 和兩個 *協力廠商防病毒引擎* 都是用來偵測附件中的所有已知惡意程式碼。

3. 防病毒 (AV) 引擎也可用於 true 輸入所有附件，所以 **類型封鎖** 可以封鎖 admin 所指定類型的所有附件。

4. 每當 Microsoft Defender Office 365 偵測到惡意附件時，檔案的雜湊及其作用中內容的雜湊會新增至 Exchange Online Protection (EOP) 信譽。 **附件信譽封鎖** 會透過 MSAV 雲端通話，封鎖所有 Office 365 和端點上的檔案。

5. **啟發式** 叢集可根據傳遞試探法判斷檔案是否可疑。 當發現可疑附件時，整個活動會暫停，而且檔案會進行沙箱化。 若發現有惡意的檔案，則會封鎖整個活動。

6. **Machine 教學模型** 會作用於標頭、正文內容及郵件 URLs，以偵測網路釣魚企圖。

7. Microsoft 使用 URL 沙箱中的信譽，以及 **url 信譽封鎖** 中協力廠商摘要的 url 聲譽，以封鎖任何具有已知惡意 URL 的郵件。

8. **內容試探法** 可使用機器學習模型，根據郵件本文內的結構和字頻率，偵測可疑的郵件。

9. **保管庫附件** 會沙箱 Office 365 客戶的所有適用于 Defender 的附件，使用動態分析來偵測出永不出現威脅。

10. **連結的內容引爆** 會將電子郵件中的每個 URL 連結到一個附件，並在傳遞時以非同步方式沙箱處理該檔案。

11. 當上游反網路釣魚技術發現郵件或 URL 可疑時，便會發生 **URL 引爆**。 URL 引爆會在傳遞時，沙箱訊息中的 URLs。

## <a name="phase-4---post-delivery-protection"></a>階段 4-投遞後保護

最後一個階段是在郵件或檔傳遞時，作用於位於各種信箱和檔案中的郵件，以及出現在用戶端（如 Microsoft Teams）中的連結。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Office 365 中，篩選的階段4是傳遞後的保護。":::

1. **保管庫連結** 是 Office 365 的時間保護的 Defender。 每封郵件中的每個 URL 都會換行，以指向 Microsoft 保管庫連結伺服器。 當按一下 URL 時，會將使用者重新導向至目標網站之前，檢查其最新的信譽。 URL 會以非同步方式沙箱化，以更新其信譽。

2. **以零小時自動清除 (ZAP) 網路釣魚** retroactively 會偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚郵件。

3. retroactively **惡意** 代碼會偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意惡意程式碼郵件。

4. **網路釣魚** retroactively 的 ZAP 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意垃圾郵件。

5. [**活動] 視圖** 可讓系統管理員看到重要的攻擊、更快速且更徹底的攻擊，而不是任何小組都可以進行「自動化」。 Microsoft 利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼，協助識別市場活動，然後讓系統管理員可以從開始到結尾（包括目標、影響和流程）進行調查，也可以在可下載的活動中使用。

6. **報告郵件增益集** 可讓使用者輕鬆報告誤報 (良好的電子郵件、誤標示為 *壞*) 或 false 不利 (錯誤電子郵件標示為 *良好* 的 Microsoft 進行進一步分析) 。

7. **Office 用戶端的保管庫連結** 提供相同的保管庫連結時間內保護，本機，在 Office 用戶端（如 Word、PowerPoint 和 Excel）內。

8. **OneDrive、SharePoint 及 Teams 的保護功能** 可為您提供相同保管庫的附件防護，以防範惡意檔、本機、OneDrive、SharePoint 和 Microsoft Teams。

9. 當選取指向檔案的 URL 後，傳遞傳遞時， **連結的內容引爆** 會顯示警告頁面，直到檔案的沙箱處理完成，並且找到安全的 url 為止。

## <a name="the-filtering-stack-diagram"></a>篩選堆疊圖表

最後的圖表 (，與組成它之圖表的所有部分) *在產品成長及開發時可能會有所變更*。 在此頁面上加上書簽，如果您需要在更新後要求，請使用您在底部所看到的 **意見** 反應選項。 針對您的記錄，這是以順序顯示所有階段的堆疊：

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Office 365 依順序從1到4的所有篩選階段。":::

## <a name="more-information"></a>其他資訊

您 **現在** 是否需要為 Office 365 * 設定 Microsoft Defender？ 使用此堆疊（_now * [）逐步開始](protect-against-threats.md) 保護您的組織。

*特別感謝從 MSFTTracyP 及檔撰寫小組到此內容的 Giulian Garruba*。
