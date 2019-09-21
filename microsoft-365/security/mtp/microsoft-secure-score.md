---
title: Microsoft 安全分數
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及哪些安全性系統管理員可以預期使用它。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 17d2decc7374d9022c68cbe2f2d58da959f44a7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078357"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

>[!IMPORTANT]
>一些資訊和有關搶鮮產品，可能會在正式發行之前大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

與 Microsoft 安全分數 Microsoft 365 安全中心內，您可以增加可見性，並控制貴組織的安全性狀態。 從集中式的儀表板中，您可以監視並改善 Microsoft 365 的身分識別、 資料、 應用程式、 裝置及基礎結構的安全性。

Microsoft 安全分數會提供健全的視覺效果，與其他 Microsoft 產品] 的整合您與其他公司，篩選類別，以及執行更多功能的分數的比較。 工具]，您可以在組織內完成安全性改進動作與追蹤您的分數的歷程記錄。 分數也可反映協力廠商解決方案時解決建議的改進動作。  

## <a name="how-it-works"></a>運作方式

您所設定的特定點建議的安全性功能，執行與安全性相關的工作 （例如檢視報表），或解決與協力廠商應用程式或軟體的改進巨集指令。 某些動作，就會獲得的部分完成時，例如啟用使用者的多重要素驗證 (MFA)。 安全性應該一律平衡與可用性，並不是每個建議適用於您的環境。

## <a name="required-permissions"></a>必要的權限

目前，若要檢視 Microsoft 安全分數，您必須獲指派其中一個 Azure Active Directory 中的下列角色：

* 全域管理員
* 安全性系統管理員
* 安全性讀取者

## <a name="rich-experiences--additional-security-recommendations"></a>豐富體驗 & 額外的安全性建議

Microsoft 安全分數，我們新增了建議從 Azure AD，Intune 和雲端 App 安全性，建議從 Azure 資訊安全中心和 Microsoft Defender ATP 即將推出。 我們也已新增更多 Office 365 安全性建議。 與其他的見解和更多的可見性廣泛的 Microsoft 產品和服務，您可以信心最管理有關貴組織的安全性狀況報告。 您也可以取得您使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)的分數。

為了協助您更快速地需要的資訊，Microsoft 建議會組織成群組：

* 身分識別 （Azure AD 帳戶和角色的保護狀態）
* 資料 （Office 365 文件的保護狀態）
* 裝置的裝置; （保護狀態Microsoft Defender ATP 改進動作即將推出）
* 應用程式 （保護狀態的電子郵件部署與雲端應用程式）
* 基礎結構 （您 Azure 的資源的保護狀態; 即將推出）

在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。 [概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。 您可以使用此資料可採取行動，以您的安全性狀態的重大差異。  

![M365 首頁](../media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*

## <a name="take-action-to-improve-your-score"></a>採取動作來改善您的分數

改進動作] 索引標籤列出所有的安全性建議適用於您的租用戶 （完成、 沒有完成、 解析透過協力廠商，而且會略過） 及其狀態。 您可以搜尋、 篩選和群組的所有控制項。  排名根據 Microsoft 評估安全性值和努力來完成。

標示為 [不計分] 動作並不會追蹤由 Microsoft 安全分數。 您仍然可以採取的動作，但完成它們不會影響您的分數。 如果巨集指令會變成在未來追蹤由 Microsoft 安全分數，而且您已經完成它，您的安全分數會自動反映出變更。

當您按一下改進巨集指令時，會出現飛入]。 若要完成此動作，您有幾個選項：

1. 選取 [**檢視設定**回到 [設定] 畫面，並進行變更。 然後，您將取得動作是值得，顯示出飛出視窗頂端的點。點可能需要 24 小時的時間來更新。

2. 因為由協力廠商應用程式或軟體已處理過的改進巨集指令，請選取 [**解決透過協力廠商**]。 讓您安全分數更妥善地反映您的整體安全性狀態，您將能夠值得了巨集指令的點。 如果協力廠商不再涵蓋控制項，您可以將標示為未完成的改進巨集指令。 請記住，Microsoft 就會有任何可見性是否分數需求已符合如果改進巨集指令會標示為透過協力廠商解決。

3. 因為您已決定要接受的風險，並不制訂的改進巨集指令，請選取 [**略過**]。 一旦您略過改進巨集指令，總數安全分數點就能得到將會降低。 您可以檢視歷程記錄中的此巨集指令或復原在任何時間。

4. 因為改進巨集指令會要求您定期檢閱您的環境以取得，並保留點的一部分，請選取 [**檢閱**]。 例如，信箱轉寄規則應檢閱以確定資料尚未進行挾帶出去，從您的網路以每週為基礎。 您不需要進行任何變更，但需要要執行巨集指令。 若您定期檢閱規則時，您會收到資料點。 如果不是，將會降低分數。

![M365 首頁](../media/secure-score/secure-score1x450.png) ![M365 首頁](../media/secure-score/secure-score2x450.png)

*圖表 2 & 3： 改進巨集指令延伸顯示*

## <a name="monitor-improvements-over-time"></a>經過一段時間的監視器增強功能

經過一段時間在 [**歷程記錄**] 索引標籤中，您可以檢視您組織的分數的圖形。此檢視包含全域平均產業平均，類似的基座計數，以及所有選取的時間範圍內所採取的動作。 您也可以依類別自訂日期範圍與篩選器。

分數的計算一次每日 (大約 1:00 AM PST)。 如果您變更測量的巨集指令，分數會自動更新的下一天。 務必也請注意，某些其他入口網站會顯示 Microsoft 安全分數部分 （例如 Microsoft defender 資訊安全中心）。 如果您完成改進巨集指令，以及分數會增加這些入口網站，可能需要 24 小時的時間的更新分數 」 來顯示在 Microsoft 365 安全中心。  

## <a name="how-improvement-actions-are-scored"></a>如何改進動作，就會獲得

二進位的方式，就會獲得最-如果您實作改進的動作，例如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。 其他改進的動作，點都指定的百分比的總組態。 例如，如果改進巨集指令會指出是否您保護您的所有使用者以多重要素驗證，您只需要 5 的 100 個受保護的總使用者，您會收到 30 點，您會提供部分分數的大約 2 點 (受保護的 5 / 100 總 * 30 的最大點數 = 2 點數部分分數）。

## <a name="risk-awareness"></a>風險認知

Microsoft 安全分數是您的安全性狀態的數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值;它不是絕對的度量單位的方式可能會破壞您的系統或資料。 相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。 沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。

## <a name="we-want-to-hear-from-you"></a>我們想要從您聽到

如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。 我們正在監視社群，並將提供的說明。
