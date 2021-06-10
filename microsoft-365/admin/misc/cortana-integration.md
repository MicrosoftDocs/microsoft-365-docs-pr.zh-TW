---
title: Microsoft 365 中的 Cortana
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 具有有效工作或學校帳戶的使用者可以在 Microsoft 365 體驗中取得 Cortana，以符合企業級的安全性承諾 Office 365。
ms.openlocfilehash: e4b934a8991837637869074d43df89e70b09924d
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866616"
---
# <a name="cortana-in-microsoft-365"></a>Microsoft 365 中的 Cortana

Cortana，您的個人生產能力 assistant 可提供 AI 的體驗，以節省時間，並重點關注最重要的問題。 Cortana 可協助您的使用者在工作和生命週期中提高其整個公司的個人生產力。 當您使用有效的工作或學校帳戶登入時，使用者可以在 Microsoft 365 體驗中取得 Cortana 的雲端協助服務，以滿足 Office 365 企業級隱私權、安全性和合規性承諾 ( 「Cortana enterprise 服務」 ) 。 

做為個人的生產能力小幫手，Cortana 的設計是為了提供安全且安全地處理的功能，以及與 Office 365 資料（如電子郵件、檔案、聊天等）有關的功能，以節省時間、提高效率，並增強使用者的生產力。

向前發展，我們的重點是在企業生產力上重點放入小娜。

- 與其他 Office 365 服務一致，Cortana enterprise 服務會符合相同的企業級隱私權、安全性和合規性承諾，反映在[線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products)中。

- 新的 Microsoft 365 體驗（如簡報電子郵件和播放我的電子郵件）將使用 Cortana enterprise 服務來啟用，並完全符合這些承諾。 這些功能目前可供全球通用 (標準多租使用者) 使用。 如需尋找使用位置的詳細資訊，請造訪 [View 的其他屬性值](../../enterprise/view-user-accounts-with-microsoft-365-powershell.md?view=o365-worldwide#view-additional-property-values-for-accounts)。

- 使用者可能會透過 Windows 10 (版本2004和更新版本) 中的 cortana，及用戶端應用程式（例如 iOS 和 Android Outlook 的使用者應用程式）連接到此處所述的 cortana enterprise 服務。 

- 現有的消費者經驗（包括 Windows 10 (版本1909和更早版本的) ，以及 iOS 和 Android 上的 cortana 應用程式）都是由[microsoft 服務合約](https://www.microsoft.com/licensing/product-licensing/products)和[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)所管理。 (，請參閱下列的「現有服務消費者」一節。 這些術語也會在使用使用者認證登入時，管理使用者提供給使用者的 Cortana 企業服務。

## <a name="what-data-is-processed-by-cortana-enterprise-services"></a>Cortana enterprise 服務處理的資料為何？ 

Cortana enterprise 服務處理來自使用者的查詢、Office 完成使用者要求所需的資料，以及 Microsoft 系統執行服務所產生的其他遙測。 「Cortana 企業服務」所收集的資料包含使用者之朗讀查詢的文字標記法 (亦即從語音辨識) 轉譯。 這項文字資料是客戶資料，而且會依照  [線上服務條款](https://www.microsoft.com/licensing/product-licensing/products)加以管理。 它只用于開發及改善與線上服務條款一致的機器教學模型。

## <a name="what-is-the-governance-model-for-customer-data-in-cortana-enterprise-services"></a>Cortana enterprise 服務中客戶資料的管理模型是什麼？

與其他 Office 365 服務一致，Cortana enterprise 服務會受到保護，並受限於[線上服務條款](https://www.microsoft.com/licensing/product-licensing/products)。 這包括保護客戶資料以防意外遺失、篡改、未經授權的披露或存取，或非法銷毀的承諾集合。 客戶資料也服從嚴格訪問限制。 Microsoft 只會使用客戶資料來供應商定的服務，以及與這些服務相容的目的。 如需詳細資訊，請參閱下表。

## <a name="how-does-microsoft-store-retain-process-and-use-customer-data-in-cortana"></a>Microsoft 如何儲存、保留、處理及使用 Cortana 中的客戶資料？

下表說明 Cortana enterprise 服務的資料處理。

| 名稱 | 描述 |
|:-----|:-----|
|**儲存**  <br/> |客戶資料儲存在 Office 365 雲端內部的 Microsoft 伺服器上。 您的資料是租使用者的一部分。 <br/><br/>不保留語音音訊。  <br/> |
|**保留在地理位置**  <br/> |客戶資料儲存于地理位置的 Office 365 雲端中的 Microsoft 伺服器上。 您的資料是租使用者的一部分。  <br/> |
|**保留原則**  <br/> |當租使用者管理員關閉或 GDPR 資料主體許可權刪除要求時，會刪除客戶資料。 <br/><br/>不保留語音音訊。  <br/> |
|**處理和機密性**  <br/> |在處理客戶資料和個人資料 (的人員) ，只會在客戶的指示上處理這類資料，而 (ii) 則可以維護這類資料的機密性和安全性，即使其合約結束也是一樣。  <br/> |
|**Usage**  <br/> |Microsoft 只會使用客戶資料來供應商定的服務，以及與這些服務相容的目的。 若要開發及改善模型，機器教學就是其中一個用途。 機器學習是在 Office 365 雲端內完成，而且不會對客戶資料進行人工查看、複查或標記。 <br/><br/>您的資料不會用來瞄準廣告。  <br/> |

## <a name="cortana-enterprise-services-in-microsoft-365-experiences"></a>Microsoft 365 體驗中的 Cortana 企業服務

### <a name="cortana-in-windows-10-version-2004-and-later"></a>Windows 10 (版本2004和更新版本中的 Cortana) 

Windows 10 中的 Cortana 應用程式可協助使用者在 Microsoft 365 中快速取得資訊，使用輸入或口述的查詢來連線人員、檢查行事曆、設定提醒等等。

Windows 中的 Cortana 可協助使用者更好地管理其排程和工作。 他們可以在 Microsoft To Do 中新增至他們的清單、查閱本機資訊、取得定義，並使用 Bing 搜尋來追蹤最新的新聞、天氣和財務資訊。

在 Windows 10 中，版本2004和更新版本的 cortana，符合對 Cortana enterprise 服務的相同企業層級隱私權、安全性和合規性承諾，如[線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products)所反映。

### <a name="how-to-opt-out-of-cortana-in-windows-10"></a>如何在 Windows 10 中選擇用小娜

系統管理員可以使用 Experience\AllowCortana MDM 原則，或透過群組原則： Computer Configuration\Administrative Templates \ Windows Components\Search\Allow cortana，在 Windows 10 中為組織設定 Cortana。

從 Windows 10 開始2004，Cortana 是通用 Windows 平臺 (UWP) 已預先安裝的應用程式應用程式，而且會定期透過 Windows 更新。 若要接收 Cortana 的最新更新，您必須[透過 Microsoft Store 啟用更新](/windows/configuration/stop-employees-from-using-microsoft-store)。

[深入瞭解 Windows 10 中的 Cortana](/windows/configuration/cortana-at-work/cortana-at-work-overview)

### <a name="cortana-voice-assistance-in-teams"></a>Teams 中的 Cortana 語音協助

> [!NOTE]
> Microsoft Teams 的行動應用程式支援 Cortana 語音協助，以供美國、英國、加拿大、印度和澳大利亞的使用者在 iOS 和 Android 和 Microsoft Teams 中顯示。  Windows 上的 Microsoft Teams 會議室只支援美國的使用者。 Cortana 語音協助目前不適用於 GCC、GCC 高、DoD、EDU 承租人。 在未來的版本中，將會發生其他語言和地區的擴充。

在 Teams 行動裝置應用程式和 Microsoft Teams 顯示裝置上的 Cortana 語音協助可讓 Microsoft 365 企業版使用者利用口述自然語言來簡化通訊、共同作業和會議相關的工作。 使用者可以透過選取位於 Teams 行動應用程式右上方的麥克風按鈕，或是說 Microsoft Teams 顯示中 &#8220;Cortana&#8221; 來對 Cortana 講話。 若要快速地與其小組直接連線，使用者可以說 &#8220;呼叫 Megan&#8221; 或 &#8220;將郵件傳送至下一個會議&#8221;。 使用者也可以說 &#8220;加入我的下一個會議&#8221; 並使用語音協助來共用檔案、檢查其行事曆等等，以加入會議。 這些語音協助體驗可使用完全符合 Office 365 隱私權、安全性和合規性承諾，在[線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products)中所反映的 Cortana 企業級服務來提供。

**系統管理控制**

預設會為承租人啟用 Cortana 語音協助。 系統管理員可以透過 (TeamsCortanaPolicy) 的原則，控制其承租人中的使用者可以使用 Cortana 語音協助 Teams。 這個原則可以設定為使用者帳戶層級或租使用者層級。 系統管理員也可以使用此原則控制中的 [CortanaVoiceInvocationMode] 欄位，判斷 Cortana 是否已停用、只使用推入按鈕 (叫用，或使用喚醒字呼叫啟用（如 Microsoft Teams 顯示) 的裝置）。 

**使用者控制項**

個別使用者可以在 Teams 行動應用程式中，按一下 [麥克風] 按鈕，以嘗試使用 Cortana 語音協助。 在 Microsoft Teams 顯示裝置上，只要口述 &#8220;Cortana，他們就可以嘗試使用 cortana 語音協助。 &#8221; 使用者也可以控制 cortana 是否回應喚醒字詞的呼叫。 

1.  開啟 Teams mobile
2.  移至設定
3.  選取 Cortana
4.  切換語音啟用切換


[深入瞭解 Teams 中的 Cortana 語音協助](/microsoftteams/cortana-in-teams)

### <a name="conversational-ai-in-outlook-for-ios-with-cortana"></a>使用 Cortana iOS Outlook 中的會話 AI

在 iOS 的 Outlook 中，Cortana 的語音導向通話體驗功能可讓使用者向其工作效率的 assistant，以排程會議、撰寫電子郵件、管理他們的行事曆和收件匣，並尋找所有類型的資訊。

使用自然語言、語音辨識、機器學習及語言的 Microsoft AI 技術，Cortana 會取得您的內容，以協助您保持井然有序、連線至對您很重要的人員和事項，以及控制您的日常。

只要使用麥克風按鈕，即可要求 Cortana 加入會議收件者，或是變更日期、時間或地點。 您也可以要求 Cortana 尋找特定的事件。 最後，您可以要求 Cortana 撰寫快速電子郵件、轉寄郵件或回復執行緒。 Cortana 的麥克風也可以協助您在 iOS 的 Outlook 中開始播放我的電子郵件，因此您可以收聽您的收件匣免提。

這項新的交談 AI 功能可在美國使用 Outlook iOS 使用 Microsoft 365 的工作帳戶，以英文使用。 若要深入瞭解，請與[您的個人生產能力 assistant 開始交談，以使用 Cortana Outlook](https://techcommunity.microsoft.com/t5/outlook-blog/start-a-conversation-with-your-personal-productivity-assistant/ba-p/2071416#:~:text=Conversational%20AI%20allows%20you%20to,time%2C%20all%20with%20your%20voice)。

### <a name="conversational-ai-with-cortana-in-outlook-with-ios-is-an-opt-in-experience"></a>具有 iOS 的 Outlook 中的 Cortana 的會話 AI 是自願參與的經驗

個別的使用者會在第一次在 iOS 上的 Outlook 中，提示他們選擇「邀請 Cortana」 mic 按鈕時，會提示您選用。

### <a name="play-my-emails"></a>播放我的電子郵件

透過) Outlook 行動裝置 (來播放我的電子郵件以語音導向的免提體驗，讓使用者透過其手機、耳機或連接的音訊裝置上的揚聲器收聽新郵件。 使用者可以要求 Cortana 高聲閱讀他們最近的電子郵件，並要求 Cortana 採取諸如旗標、封存、刪除和略過訊息等動作。 這項功能特別有助於在 commuting、多工工作或前往時追趕您的電子郵件。 當使用者在 [播放我的電子郵件] 中與 Cortana 交談時，語音音訊要求會直接移至 [Cortana enterprise 服務]。 使用者電子郵件的語音讀出文字會在 Office 365 雲端內處理。 在此程式中，不會在使用者的行動裝置上處理任何 Office 365 資料，也不會儲存電子郵件資料。 口述命令的成績單 (例如「標為已讀取」、「下一步」、「旗標」等等。 ) 可能會依照 Microsoft [Online Services 條款](https://www.microsoft.com/licensing/product-licensing/products)中的資料保護條款保留。

當電子郵件受到保護時，Cortana 會呼叫出來，並在閱讀郵件之前停頓片刻，讓使用者有足夠的時間來暫停播放或略過下一封郵件。 類似于私人電話，當使用者可能會 overheard 機密資訊的位置時，使用者應小心謹慎。 在這些情況下，當您在 Outlook 行動裝置中使用「播放我的電子郵件」時，建議您在適當的環境中，將組織的員工磨損。


### <a name="opt-out-of-play-my-emails"></a>選擇不播放我的電子郵件

使用下列步驟，個人可以選擇 [播放我的電子郵件]。

1. 開啟 Outlook mobile。

2. 移至 **設定**。
  
3. 選取 [ **播放我的電子郵件**]。

4. 在您要停用的帳戶上，將切換移至 [關閉]。

[深入瞭解玩我的電子郵件](https://support.microsoft.com/help/4558256)

### <a name="briefing-email"></a>簡報電子郵件

Cortana 會傳送個人化簡報電子郵件，其中包含您用來將其標記為 [已 **完成** ] 或 [排程焦點] 以完成工作的任務和承諾。 它也包含您一天的會議和相關檔摘要。 Cortana 會從使用者的電子郵件中提取資訊，並將其儲存在其 Exchange Online 信箱中，直到將其合併至簡報電子郵件。 在任何時間，您的 Exchange Online 信箱之外可以存取個人資料。 只有當使用者擁有包含 Exchange Online 服務方案的授權時，才會取得簡報電子郵件的存取權。

### <a name="how-to-opt-out-of-briefing-email"></a>如何選擇未用簡報電子郵件

系統管理員可以使用 Exchange Online 中的[PowerShell](/briefing/be-admin) ，設定其組織的簡報。 個人可以在郵件的頁尾選取 [ **取消訂閱** ]，以選擇不使用 Cortana 的簡報電子郵件。

[深入瞭解簡報電子郵件](https://support.microsoft.com/help/4558259)

我們將繼續引進與上述類似的經驗，協助您增加組織的生產力。

[深入瞭解 Microsoft 規範服務](/compliance/regulatory/offering-home)

## <a name="how-is-the-delivery-of-cortana-enterprise-services-different-from-the-delivery-of-other-cortana-features-i-may-have-previously-experienced"></a>Cortana 企業服務的傳遞與我先前可能經歷的其他 Cortana 功能的傳遞有何不同？

以下是兩種方式來考慮 Cortana 在企業中的運作方式：

**使用 cortana enterprise 服務之組織的新體驗**： cortana enterprise 服務的設計目的是為了符合組織的安全性和合規性需求： 

1. 這是一項新服務，在此檔中會加以討論。

2. 針對受線上服務條款制約的服務，Microsoft 是資料處理器： Microsoft 只會收集客戶所要求的線上服務，並使用客戶資料，以提供客戶所要求的線上服務。 在歐盟的一般資料保護規定 (GDPR) ，客戶是其資料的資料控制器。 請參閱 [線上服務條款](https://www.microsoft.com/licensing/product-licensing/products) ，並 [為我們的商業雲端客戶引進更多隱私權透明性](https://blogs.microsoft.com/eupolicy/2019/11/18/introducing-privacy-transparency-commercial-cloud-customers/)。

3. 舉例來說，「我的電子郵件」是您的使用者可以透過 Outlook iOS 並利用 cortana enterprise 服務的 cortana 服務。 

4. IT 系統管理員在使用 Office ProPlus 應用程式時，系統管理員一定會具有 Cortana 選用的連接體驗的控制項，類似選用的連線體驗。  

**現有的消費者服務**： Cortana 選用聯機服務主要是針對使用者經驗所設計，目前是以 Windows 10 (版本1909和更舊版本的) 和 iOS 和 Android 上的 Cortana 應用程式來提供。

1. 這些經驗可以啟用天氣、新聞及流量等功能。

2. 租使用者系統管理員可以控制是否 Windows 10 (版本1909和更舊版本) 中的 cortana，以及 iOS 和 Android 上的 cortana 應用程式是否可以允許 Cortana 連線到 Office 365 租使用者資料。

關閉 Cortana 對您組織的 Microsoft 主控資料的存取

1. 在 Microsoft 365 系統管理中心中，選取 [**設定**  >  **Org 設定**]，然後選取 [ **Cortana**]。

2. 取消選取 [**允許 Windows 10 (版本1909和更舊版本) 中的小娜] 核取方塊，以及 iOS 和 Android 上的 cortana 應用程式，以在組織中代表人員，存取 Microsoft 主控的資料**，以停用 Cortana 連線體驗。

3. 選取 **[儲存變更]**。

針對 [Microsoft 服務合約](https://go.microsoft.com/fwlink/p/?LinkId=2109174) 和 [microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)所控制的服務，microsoft 是資料控制器。 就像資料控制者一樣，Microsoft 會使用資料，依照 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)來改進產品和服務。


## <a name="related-content"></a>相關內容

[Teams (文章中的 Cortana 語音協助](/microsoftteams/cortana-in-teams)) \
[在 Windows 10 (文章中設定 Cortana](/windows/configuration/cortana-at-work/cortana-at-work-overview)) \
[您可以從 Cortana 播放我的電子郵件？](https://support.microsoft.com/help/4558256)
