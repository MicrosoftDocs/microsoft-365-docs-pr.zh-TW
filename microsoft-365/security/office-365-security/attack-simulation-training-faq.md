---
title: 攻擊模擬訓練部署考慮和常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 組織中有關攻擊模擬和訓練的部署考慮和常見問題。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57252252d8a22ade4b8e1a18f42d7fdce91324e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454711"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>攻擊模擬訓練部署考慮和常見問題

現已 [提供](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)攻擊模擬訓練。 攻擊模擬訓練可讓 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 組織，可讓您建立及管理以實際執行 weaponized 網路釣魚詐騙為供電的網路釣魚模擬模擬，以衡量及管理社交工程風險。 在合作與 Terranova 安全性中提供的超目標訓練，可協助改善知識並變更員工行為。

如需如何開始使用攻擊模擬訓練的詳細資訊，請參閱 [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)。

當整個類比建立及排程體驗設計為自由流動和 frictionless 時，在企業規模中執行模擬通常需要規劃。 本文可協助解決客戶在自己的環境中執行模擬時所看到的特定難題。

## <a name="issues-with-end-user-experiences"></a>使用者體驗方面的問題

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Google Safe 流覽封鎖 URLs 網路釣魚類比

URL 信譽服務可能會識別攻擊模擬訓練所使用的一或多個 URLs 為不安全。 Google Chrome 中的 google Safe 流覽會封鎖某些模擬的網路釣魚 URLs 與 **欺騙性網站** 一起使用的郵件。 當我們與許多 URL 信譽廠商合作，以無條件允許類比 URLs，我們不一定會有完整的覆蓋範圍。

![Google Chrome 中的欺騙性網站先行警告](../../media/attack-sim-chrome-deceptive-site-message.png)

請注意，此問題不會影響 Microsoft Edge。

在規劃階段中，請務必先檢查支援的網頁瀏覽器中的 URL 可用性，再使用網路釣魚活動中的 URL。 如果 URLs 被 Google 安全流覽封鎖，請遵循 Google 的 [指導](https://support.google.com/chrome/a/answer/7532419) 以允許存取 URLs。

請參閱如何 [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md) ，以取得受攻擊模擬訓練的目前使用 URLs 清單。

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>網路 proxy 解決方案及篩選器驅動程式封鎖網路釣魚類比和系統管理員 URLs

網路釣魚模擬 URLs 和系統管理 URLs 可能會被您的中間安全性裝置或篩選器封鎖或丟棄。 例如：

- 防火牆
- WAF) 解決方案的 Web 應用程式防火牆 (
- 協力廠商篩選器驅動程式 (例如，核心模式篩選) 

當我們看到少數客戶在此階層遭到封鎖時，就會發生這種情況。 如果您遇到問題，請考慮設定下列 URLs，以略過您的安全性裝置或篩選器（如有必要）：

- 模擬網路釣魚 URLs，如 [開始使用進攻類比訓練](attack-simulation-training-get-started.md)中所述。
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>類比訊息未傳遞給所有目標使用者

實際接收模擬電子郵件的使用者人數可能會小於類比所針對的使用者數目的數目。 下列類型的使用者將會排除為目標驗證的一部分：

- 不正確收件者電子郵件地址。
- 來賓使用者。
- 在 Azure Active Directory (Azure AD) 中不再使用中的使用者。

模擬中只會包含有效的非來賓使用者，具有有效的信箱。 如果您使用通訊群組或擁有郵件功能的安全性群組來為使用者設定目標，您可以使用[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中的[Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) Cmdlet，以查看和驗證通訊群組成員。

## <a name="issues-with-attack-simulation-training-reporting"></a>攻擊模擬的訓練報告問題

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>攻擊模擬訓練報告不含任何活動詳細資料

攻擊模擬訓練包含豐富的可操作性見解，可讓您獲悉員工的威脅準備進度。 如果攻擊模擬訓練報告未填入資料，請確認已在組織中開啟「審計記錄搜尋」 () 預設為開啟。

攻擊模擬訓練會要求進行審計記錄搜尋，讓事件可以捕獲、記錄和回讀。 關閉「審計記錄檔搜尋」時，攻擊模擬訓練會產生下列後果：

- 報告資料無法在所有報告中使用。 報告會顯示空白。
- 因為無法使用資料，所以訓練指派遭到封鎖。

若要開啟審計記錄搜尋，請參閱 [開啟或關閉審計記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

> [!NOTE]
> 不會將任何 E5 授權指派給使用者，也可能會造成空白的活動詳細資料。 請確認至少有一個 E5 授權指派給作用中的使用者，以確保捕獲和記錄報告事件。

### <a name="simulation-reports-are-not-updated-immediately"></a>不會立即更新類比報告

在您啟動市場活動之後，就不會立即更新詳細的類比報告。 別擔心;這是預期行為。

每個類比活動都有生命週期。 第一次建立時，類比即為 **排程** 狀態。 當類比開始時，它會轉變為 **進行中** 狀態。 完成時，類比會轉換成 **已完成** 的狀態。

當類比處於 **排程** 狀態時，類比報告基本上會是空的。 在此階段中，模擬引擎正在解析目標使用者電子郵件地址、展開通訊群組、從清單中移除來賓使用者等等：

![排程狀態中的報告](../../media/attack-sim-empty-reporting.png)

類比進入 **進行中** 階段後，您會注意到資訊開始細流到報告：

![在進行中的狀態報表](../../media/attack-sim-in-progress.png)

您最多可能需要30分鐘的時間，才能將個別的類比報告更新為 [ **進行中** ] 狀態。 報告資料會繼續建立，直到類比達到 **完成** 狀態為止。 報告更新的執行間隔如下：

- 在前60分鐘內，每10分鐘一次。
- 60分鐘之後每隔15分鐘直到2天。
- 在2天之後的30分鐘之後，直到7天。
- 7天后，每隔60分鐘。

[ **一覽** ] 頁面上的小元件可提供組織隨時間的類比基礎安全性狀況快速快照。 因為這些小小程式會反映您的整體安全性狀況和旅程，所以在完成每個類比活動之後，就會更新。

> [!NOTE]
> 您可以在各種報告頁面上使用 [ **匯出** ] 選項，以提取資料。

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>使用者報告為網路釣魚的郵件未出現在類比報告中

攻擊模擬器訓練中的類比報告可提供使用者活動的詳細資料。 例如：

- 在郵件中按一下連結的使用者。
- 提供其認證的使用者。
- 將郵件報告為網路釣魚的使用者。

如果使用者報告為網路釣魚的郵件不會在攻擊模擬訓練類比報告中取得，則可能會有 Exchange 郵件流程規則 (也稱為傳輸規則) 會封鎖所報告的郵件傳遞至 Microsoft。 確認任何郵件流程規則不會封鎖傳遞至下列電子郵件地址：

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- 非 \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>其他常見問題

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>問：針對類比活動的使用者，建議使用哪種方法？

A：目標使用者可以使用數種選項：

- 包含目前可供低於40000使用者之組織使用的所有使用者 () 。
- 選擇 [特定使用者]。
- 從 CSV 檔案中選取 [使用者]。
- Azure AD 群組為基礎的目標。

我們發現市場活動中，Azure AD 群組識別目標使用者通常會比較容易管理。

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>問：從 CSV 或新增使用者進行匯入時，是否要針對使用者提供任何限制？

A：從 CSV 檔案匯入收件者或將個別收件者新增至類比的限制是40000。

收件者可以是個別的使用者或群組。 群組可能包含成百上千個收件者，因此實際的限制不會放在個別使用者的數量上。

管理大型 CSV 檔案或新增許多個人的收件者可能會很麻煩。 使用 Azure AD 群組可簡化類比的整體管理。

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>問： Microsoft 是否提供其他語言的負載？

A：目前有5個當地語系化的負載可用。 已注意到，現有負載的任何直接或機器翻譯翻譯為其他語言的通知，會導致不准確並降低相關性。

也就是說，您可以使用自訂的負載製作體驗，以您選擇的語言來建立您自己的負載。 我們也強烈建議您收集用來將特定地理位置的使用者作為目標的現有負載。 換句話說，讓攻擊者為您當地語系化內容。

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>問：我該如何切換其他語言以取得系統管理員入口網站及訓練體驗？

A：在 Microsoft 365 或 Office 365 中，語言設定為每個使用者帳戶的特定及集中式。 如需如何變更語言設定的指示，請參閱 [在 Microsoft 365 For Business 中變更您的顯示語言和](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)時區。

請注意，設定變更可能需要30分鐘的時間，才能同步處理所有服務。

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>問：我是否可以觸發測試模擬，以瞭解在啟動完整的活動之前所要看到的功能？

A：可以是。 在嚮導中 [最近一次的 **檢查類比** ] 頁面上，建立新的類比，有一個選項可以 **傳送測試**。 此選項會將範例網路釣魚模擬郵件傳送給目前登入的使用者。 在您在 [收件匣] 中驗證網路釣魚郵件之後，您可以提交模擬。

![在 [檢查類比] 頁面上傳送測試按鈕](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>問：我是否可以將屬於其他租使用者的使用者設定為相同類比活動的一部分？

答：否。 目前不支援跨租使用者模擬。 確認您的所有目標使用者都位於相同的承租人。 任何跨承租人使用者或來賓使用者將會從類比活動中排除。

### <a name="q-how-does-region-aware-delivery-work"></a>問：地區識別傳遞的運作方式如何？

A：地區感知傳遞使用目標使用者信箱的 TimeZone 屬性和「非 before」邏輯來決定何時傳遞郵件。 例如，請考量下列情境：

- 在太平洋時區中的 7:00 AM (UTC-8) ，系統管理員會建立和排程市場活動，以在同一天的 9:00 AM 開始。
- UserA 位於東部時區 (UTC-5) 。
- UserB 也位於太平洋時區。

在同一天的 9:00 AM，類比郵件會傳送至 UserB。 透過地區感知傳遞，郵件不會在同一天傳送至 UserA，因為 9:00 AM 太平洋時間是東部時間 12:00 PM。 相反地，郵件會在下一天的 9:00 AM 東部時間傳送至 UserA。

因此，在初次執行具有地區感知傳遞功能的活動時，可能會出現類比訊息只傳送給特定時區中的使用者。 不過，隨著時間傳遞和更多使用者進入範圍中，目標使用者將會增加。
