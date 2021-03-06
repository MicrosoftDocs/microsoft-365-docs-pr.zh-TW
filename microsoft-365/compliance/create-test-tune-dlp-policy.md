---
title: 建立、測試及調整 DLP 原則
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 在本文中，您將瞭解如何根據組織的需求來建立、測試及調整 DLP 原則。
ms.openlocfilehash: 3b7f74605c8a825bb03244f3a861ad3cca8f550d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572570"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>建立、測試及調整 DLP 原則

資料遺失防護 (DLP) 可協助您防止意外或意外的敏感資訊共用。

DLP 會檢查電子郵件和檔案的敏感資訊，例如信用卡號碼。 使用 DLP，您可以偵測敏感資訊，並採取下列動作：

- 記錄事件的審計目的
- 向傳送電子郵件或共用檔的使用者顯示警告
- 主動封鎖電子郵件或檔案共用發生

## <a name="permissions"></a>權限

您的規範小組中將建立 DLP 原則的成員必須具備規範中心的權限。 根據預設，您的租使用者系統管理員可以存取合規性監察官員和其他人員。 遵循下列步驟：
  
1. 在 Microsoft 365 中建立一個群組，並將法務人員新增至此群組。
    
2. 在安全性與合規性中心的 **[權限]** 頁面上建立角色群組。 

3. 建立角色群組時，請使用 [ **選擇角色** ] 區段，將下列角色新增至角色群組： [ **DLP 規範管理**]。
    
4. 使用 [選擇成員] 區段，將您建立的 Microsoft 365 群組新增至角色群組。

使用 **VIEW-ONLY Dlp 相容性管理** 角色來建立具有 DLP 原則和 dlp 報告之只供查看許可權的角色群組。

如需詳細資訊，請參閱[授與使用者存取 Office 365 合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
若要建立及套用 DLP 原則，不會強制執行原則，這些許可權是必要的。

## <a name="how-sensitive-information-is-detected-by-dlp"></a>DLP 偵測到敏感資訊的方式

DLP 會依正則運算式尋找敏感資訊 (RegEx) 模式比對，以與其他指標（如某些關鍵字接近于相符的模式）搭配。 例如，簽證的信用卡號碼具有16位數。 不過，這些數位可以以不同的方式寫入，例如1111-1111-1111-1111、1111 1111 1111 1111 或1111111111111111。

任何16位數的字串不一定是信用卡號碼，其可能是技術支援人員系統中的票證號碼，或是某一塊硬體的系列號碼。 為了說明信用卡號碼和無害的16位數位符串之間的差異，會執行 (檢查) 中的計算，以確認號碼符合各種信用卡品牌的已知模式。

如果 DLP 發現關鍵字（如 "簽證" 或 "AMEX"）、可能是信用卡到期日的接近日期值，DLP 也會使用該資料來協助其判斷字串是否為信用卡號碼。

換句話說，DLP 非常聰明，可辨識電子郵件中這兩個文字字串之間的差異：

- 「您可以定購新的可擕式電腦。 使用我的簽證號碼1111-1111-1111-1111，到期11/22，當您有時，將預估的傳遞日期傳送給我。
- 「我的膝上型電腦序號是2222-2222-2222-2222，其購買于11/2010。 順便說一來，我的旅行簽證是否已獲批准？

請參閱 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md) ，說明偵測每種資訊類型的方式。

## <a name="where-to-start-with-data-loss-prevention"></a>從資料遺失防護開始的位置

當資料洩漏風險不完全顯而易見時，就很難實際開始執行 DLP。 幸運的是，DLP 原則可以在「測試模式」中執行，這樣您就能在開啟之前估量效能和精確度。

您可以透過 Exchange 系統管理中心管理 Exchange Online 的 DLP 原則。 不過，您可以透過安全性 & 規範中心設定所有工作負載的 DLP 原則，如此一來，我們將在本文中示範。 在安全性 & 規範中心，您會在 **資料遺失防護** 原則下找到 DLP 原則  >  ****。 選擇 [建立要啟動 **的原則** ]。

Microsoft 365 提供您可以用來建立原則的[DLP 原則範本](what-the-dlp-policy-templates-include.md)範圍。 假設您是澳大利亞公司。 您可以篩選澳大利亞的範本，並選擇 [金融]、「醫療」和「健康情況」和「隱私權」。

![選擇國家或地區的選項](../media/DLP-create-test-tune-choose-country.png)

在本次示範中，我會選擇澳大利亞個人身分識別資訊 (PII) 資料，其中包含 (TFN) 和駕駛執照號碼的澳大利亞稅收檔編號資訊類型。

![選擇原則範本的選項](../media/DLP-create-test-tune-choose-policy-template.png)

請將新的 DLP 原則命名為 [名稱]。 預設名稱會符合 DLP 原則範本，但您應選擇更具描述性的名稱，因為您可以從同一個範本建立多個原則。

![用於命名原則的選項](../media/DLP-create-test-tune-name-policy.png)

選擇原則將套用的位置。 DLP 原則可以套用到 Exchange Online、SharePoint 線上及商務用 OneDrive。 我要將此原則設定為套用至所有位置。

![選擇所有位置的選項](../media/DLP-create-test-tune-choose-locations.png)

在第一個 **原則設定** 步驟，只要接受預設值即可。 您可以自訂 DLP 原則，但預設值是一個不錯的開始位置。

![自訂要保護的內容類型的選項](../media/DLP-create-test-tune-default-customization-settings.png)

按 [下一步] 之後，您將會看到一個更具 **原則設定**] 頁面上，具有更多自訂選項。 針對您剛測試的原則，您可以在這裡開始進行一些調整。

- 現在已經關閉原則提示，這是在您只測試專案，而不想要向使用者顯示任何專案時採取的合理步驟。 原則提示會向使用者顯示警告，告知您其即將違反 DLP 原則。 例如，Outlook 使用者會看到一則警告，指出其所附加的檔案包含信用卡號碼，並將拒絕其電子郵件。 原則秘訣的目標是先停止不相容的行為，再進行此操作。
- 我也減少了從10到1的實例數目，所以這個原則會偵測所有的澳大利亞 PII 資料共用，而不只是大量的資料共用。
- 我也將另一位收件者新增至附隨報告電子郵件。

![其他原則設定](../media/DLP-create-test-tune-more-policy-settings.png)

最後，我已設定此原則最初在測試模式中執行。 請注意，在 [測試模式] 中也有一個用於停用原則提示的選項。 這可讓您彈性啟用原則中的原則提示，但接著決定是否要在測試期間顯示或隱藏它們。

![先測試原則的選項](../media/DLP-create-test-tune-test-mode.png)

在最後的審閱畫面上，按一下 [ **建立** ] 以完成建立原則。

## <a name="test-a-dlp-policy"></a>測試 DLP 原則

新的 DLP 原則會在大約1小時內開始生效。 您可以坐下來，等待一般的使用者活動觸發，否則您也可以嘗試自行觸發。 舊版 I 連結至 [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)，可提供有關如何觸發 DLP 相符的資訊。

舉例來說，我為本文建立的 DLP 原則會偵測到 (TFN) 的澳大利亞稅收檔案編號。 根據檔，符合下列準則為基礎。

![澳大利亞稅收檔案編號的檔](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
為了以緊密的方式示範 TFN 偵測，具有 "稅收 file number" 一詞的電子郵件和近距離的九位數位符串都是 sail，不會有任何問題。 不會觸發 DLP 原則的原因是，九位數位符串必須傳遞校驗和，表示它是有效的 TFN，而不只是無害的數位字串。

![未通過檢查的澳大利亞稅收檔編號](../media/DLP-create-test-tune-email-test1.png)

相比之下，具有 "稅收檔號碼" 字樣的電子郵件和傳遞校驗和的有效 TFN 會觸發原則。 在這裡的記錄中，所使用的 TFN 是從網站產生，但不是正版，TFNs。 這類網站非常有用，因為測試 DLP 原則時最常見的錯誤之一是使用不正確虛假號碼，而且不會傳遞校驗和 (，因此不會觸發原則) 。

![傳遞校驗和的澳大利亞稅收檔編號](../media/DLP-create-test-tune-email-test2.png)

附隨報告電子郵件包括所偵測到的敏感資訊類型、偵測到多少個實例，以及偵測的信賴等級。

![顯示繳稅檔編號的附隨報告](../media/DLP-create-test-tune-email-incident-report.png)

如果您在測試模式中保留 DLP 原則，並分析附隨報告電子郵件，您可以開始進行 DLP 原則的準確性，以及強制執行它的有效性。 除了附隨報告之外，您還可以 [使用 DLP 報告](view-the-dlp-reports.md) 來查看整個租使用者中原則相符專案的匯總視圖。

## <a name="tune-a-dlp-policy"></a>調整 DLP 原則

當您分析原則點擊時，您可能會想要對原則的行為方式進行一些調整。 簡單的範例是，您可能會判斷電子郵件中的某個 TFN 不是問題 (我認為它仍是，但為了示範) ，我們會告訴它，但有兩個以上的實例是問題。 多個實例可能是一種危險案例，例如員工使用從人力資源資料庫到外部方的 CSV 匯出電子郵件，例如外部會計服務。 絕對您想要偵測和封鎖的內容。

在 [規範中心] 中，您可以編輯現有的原則來調整行為。

![編輯原則的選項](../media/DLP-create-test-tune-edit-policy.png)
 
您可以調整位置設定，讓原則僅套用至特定工作負載，或套用至特定的網站和帳戶。

![選擇特定位置的選項](../media/DLP-create-test-tune-edit-locations.png)

您也可以調整原則設定，並編輯規則，以更符合您的需求。

![編輯規則的選項](../media/DLP-create-test-tune-edit-rule.png)

在 DLP 原則中編輯規則時，您可以變更：

- 條件，包含會觸發規則的敏感性資料實例類型和數目。
- 採取的動作，例如限制存取內容。
- 使用者通知：這是在電子郵件客戶程式或網頁瀏覽器中向使用者顯示的原則提示。
- 使用者覆寫會決定使用者是否可以選擇繼續進行電子郵件或檔案共用。
- 附隨報告，以通知系統管理員。

![編輯規則部分的選項](../media/DLP-create-test-tune-editing-options.png)

在本次示範中，我已將使用者通知新增至原則 (請小心執行這項操作，而不需要有足夠的使用者認知訓練) ，而且允許使用者以業務理由覆蓋原則，或將其標記為誤報。 您也可以自訂 [電子郵件] 和 [原則提示] 文字，如果您想要包含組織原則的任何其他資訊，或提示使用者如有任何問題，請使用者聯繫支援人員。

![使用者通知和覆寫的選項](../media/DLP-create-test-tune-user-notifications.png)

原則包含兩個處理大量磁片或低容量的規則，因此請務必使用您想要的動作進行編輯。 這是視案例的特性而異的機會。 例如，您可以允許覆寫磁片容量低的情況，但不允許對高磁片區違規的覆寫。

![適用于低容量的高容量和一個規則的一個規則](../media/DLP-create-test-tune-two-rules.png)

此外，如果您想要實際封鎖或限制存取違反原則的內容，您必須設定規則上的動作來執行此動作。

![可限制存取內容的選項](../media/DLP-create-test-tune-restrict-access-action.png)

將變更儲存至原則設定後，我也需要回到原則的 [主要設定] 頁面，並啟用此選項，以在原則處於測試模式時，向使用者顯示原則提示。 這是將 DLP 原則引入使用者的有效方式，並進行使用者知曉訓練，但不會冒出影響其生產力的誤報數。

![在測試模式中顯示原則提示的選項](../media/DLP-create-test-tune-show-policy-tips.png)

在 [伺服器端 (] 或 [雲端端] 如果您想要) ，變更可能不會立即生效，因為不同的處理間隔。 如果您要進行 DLP 原則變更，以向使用者顯示新的原則提示，使用者可能看不到 Outlook 用戶端中所做的變更會立即生效，這會檢查每24小時執行的原則變更。 如果您想要加快測試速度，您可以使用此註冊表修正程式， [從 PolicyNudges 機碼清除上次下載時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。 Outlook 會在下一次重新開機時下載最新的原則資訊，並開始撰寫電子郵件訊息。

如果您已啟用原則提示，使用者就會開始查看 Outlook 中的秘訣，並在發生時向您報告錯誤的陽性。

![具有報告 false 正值選項的原則提示](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>調查誤報

DLP 原則範本並不完全直接離開盒。 您很可能會發現環境中有一些誤報的情況，這就是為什麼讓您輕鬆地進行 DLP 部署變得如此重要的原因，請花些時間來充分測試及調整原則。

以下是誤報的範例。 這封電子郵件相當無害。 使用者向某人提供其行動電話號碼，並包含他們的電子郵件簽名。

![顯示誤報正值資訊的電子郵件](../media/DLP-create-test-tune-false-positive-email.png)
 
不過，使用者會看到一個原則提示，告知他們電子郵件包含機密資訊（特別是澳大利亞駕駛執照號碼）。

![在原則提示中報告 false 陽性的選項](../media/DLP-create-test-tune-policy-tip-closeup.png)

使用者可以報告誤報，而且系統管理員可以深入瞭解發生的原因。 在 [附隨報告] 電子郵件中，會將電子郵件標記為誤報。

![顯示誤報的附隨報告](../media/DLP-create-test-tune-false-positive-incident-report.png)

此駕駛執照案例是深入瞭解的一個很好的範例。 這種誤報的原因是，「澳大利亞駕駛執照」類型會由任何9位數位符串 (所觸發，甚至是10位數位符串) 的一部分，在300個字元接近關鍵字 "悉尼 nsw" (不區分大小寫的) 。 因此，它會因電話號碼和電子郵件簽章而觸發，只是因為使用者碰巧在悉尼。


其中一個選項是移除來自原則的澳大利亞駕駛執照資訊類型。 因為它是 DLP 原則範本的一部分，但不會強制您使用它。 如果您只對稅收檔編號（而不是驅動程式的授權）感興趣，您可以將它移除。 例如，您可以從原則中的低容量規則中移除它，但將它保留在高容量規則中，以便仍偵測到多個驅動程式授權清單。
 
另一個選項是增加實例計數，所以只有在多個實例時，才會偵測到低數量的驅動程式授權。

![編輯實例計數的選項](../media/DLP-create-test-tune-edit-instance-count.png)

除了變更實例計數之外，您也可以調整 (或信賴等級) 的相符精確性。 如果您的敏感資訊類型有多種模式，您可以調整規則中的相符準確度，使規則只符合特定模式。 例如，若要協助減少誤報，您可以設定規則的符合準確度，使其只符合具有最高信賴度的模式。 如需信賴層級的詳細資訊，請參閱 how [to use 信賴層級來調整您的規則](data-loss-prevention-policies.md#match-accuracy)。

最後，如果您想要更進一步的掌握，您可以自訂任何敏感資訊類型，例如，您可以從 [澳大利亞駕駛執照號碼](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)的關鍵字清單中移除「悉尼 NSW」，以消除上述假的誤報。 若要瞭解如何使用 XML 和 PowerShell 執行這項操作，請參閱 [自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)。

## <a name="turn-on-a-dlp-policy"></a>開啟 DLP 原則

當您很樂意您的 DLP 原則正確且有效地偵測敏感資訊類型，而且使用者準備好處理已就地原則的原則之後，即可啟用該原則。

![開啟原則的選項](../media/DLP-create-test-tune-turn-on-policy.png)
 
如果您想要查看原則何時生效，請[連線安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) ，並執行[Get-DlpCompliancePolicy Cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) ，以查看 DistributionStatus。

![在 PowerShell 中執行 Cmdlet](../media/DLP-create-test-tune-PowerShell.png)

開啟 DLP 原則之後，您應該先執行您自己的一些最終測試，以確保發生預期的原則動作。 如果您嘗試測試像是信用卡資料之類的內容，則會有網站線上，提供如何產生範例信用卡或其他個人資訊的資訊，這些資訊會透過校驗和觸發您的原則。

允許使用者覆寫的原則會將該選項呈現給使用者，成為原則提示的一部分。

![允許使用者覆寫的原則提示](../media/DLP-create-test-tune-override-option.png)

限制內容的原則會在原則提示的一部分向使用者呈現警告，並防止他們傳送電子郵件。

![內容受限制的原則提示](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>摘要

資料遺失防護原則對於所有類型的組織都很有用。 測試某些 DLP 原則是低風險的動作，因為您的控制原則提示、使用者覆寫和附隨報告等專案。 您可以不知不覺地測試部分 DLP 原則，以查看組織中已發生的違規類型，然後使用低的誤報速率來製作原則，並對使用者提供允許和不允許的專案，然後將 DLP 原則推廣至組織。