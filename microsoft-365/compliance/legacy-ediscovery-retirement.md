---
title: 舊版電子文件探索工具淘汰
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Exchange Online 中的 In-Place eDiscovery 和 In-Place 保留（以及對應的 PowerShell Cmdlet）會在2020的上半年內淘汰。 Search-Mailbox Cmdlet 及 Advanced eDiscovery 1.0 1.0 也會在相同的時段內淘汰。
ms.openlocfilehash: 48dbbd86071f8b07fa3dbf3a699f0d7e085fd50b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943342"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>舊版電子文件探索工具淘汰

> [!IMPORTANT]
> Microsoft 已評估公開健康情況，我們瞭解這對客戶造成的影響。 我們想要成為強大的合作夥伴和負責的全球公民。 為了簡化您面臨的眾多工作之一，我們會將本文所述之舊版 eDiscovery 工具的計畫停用延遲為三個月。 **更新後的退休日期會反映在下方。**

在幾年中，Microsoft 提供了 eDiscovery 工具，可讓您從 Exchange Online 搜尋、預覽及匯出電子郵件內容。 不過，這些工具不再提供有效的方式，可在其他 Microsoft 365 服務中搜尋非 Exchange 內容，例如 SharePoint 線上和 Microsoft 365 群組。 為了解決此情況，Microsoft 提供了其他 eDiscovery 工具，可協助您搜尋各種各樣的 Microsoft 365 內容。 而且我們致力於在[Microsoft 365 規範中心](https://compliance.microsoft.com)內整合最新和功能強大的 eDiscovery 功能。 這可讓組織對許多 Microsoft 365 服務（包括 Exchange Online）的內容，回應法律、內部及其他檔要求。

由於 Microsoft 365 規範中心的這項新的和改善的 eDiscovery 功能，我們即將淘汰下列與電子檔內容在 Exchange Online 和 Microsoft 365 中搜尋相關的 eDiscovery 相關功能：

- 在 Exchange 系統管理中心中[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[In-Place 存放](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- Exchange Online PowerShell Cmdlet，支援 In-Place eDiscovery 和 In-Place 保留（這些 Cmdlet 共同識別為 **-get-mailboxsearch 程式*Cmdlet）。 這包括下列 Cmdlet：

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > 當其他 * *-MailboxSearch * * * * * 指令程式已停用之後，就可以使用[Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)和[Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) Cmdlet，這樣您就可以使用這些 Cmdlet 來協助您轉換至其他 eDiscovery 和保留工具。 不過，在特定日期（如下所示）之後，Microsoft 支援將不再支援這兩個 Cmdlet。

- Exchange Online PowerShell 中的[Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) Cmdlet。

- Exchange Web 服務 API 中的下列作業：

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced ediscovery 1.0](office-365-advanced-ediscovery.md)版，也就是透過 Office 365 安全性 & 合規性中心的核心 eDiscovery 案例所存取的第一個版本。 停用高級 eDiscovery 1.0 版不會影響您建立及管理核心 eDiscovery 案例的能力。

> [!NOTE]
> 即將淘汰的 eDiscovery 功能僅適用于雲端式版本的 Microsoft 365 和 Office 365。 在內部部署 Exchange 和 SharePoint 版本中的 eDiscovery 功能仍會受到支援，直到進一步通知為止。

本文中的下列各節提供每個已撤銷的功能的指導方針。 此資訊包含時程表和您可以使用的替代工具，而不是退休工具。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>在 Exchange 系統管理中心中 In-Place eDiscovery 和 In-Place 存放 

根據原始宣告于2017年7月1日，在 Exchange 系統管理中心（EAC）中的 In-Place eDiscovery & 保留功能即將淘汰。 EAC 中 In-Place eDiscovery & 保留頁面可讓您搜尋、保留及匯出 Exchange Online 中的內容。 In-Place eDiscovery 也可讓您將搜尋結果複製到探索信箱，讓您或其他 eDiscovery 管理員可以查看內容，並將其提供給法律、法規及公開的要求。

由於所有這些功能（除了將搜尋結果複製到探索信箱之外）現在可在[Microsoft 365 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)的內容搜尋、Ediscovery 和高級 ediscovery 工具中取得，因此我們建議您儘快開始使用這些工具（改進功能、可靠性和365支援）。 為了協助您轉換至這些其他 eDiscovery 工具，下表列出您可以使用的工具，而不是 In-Place eDiscovery 和 In-Place 保留。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業組織

- Office 365 和 Microsoft 365 教育組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD

- Office 365 德國

### <a name="timeline-for-retirement"></a>退休的時程表

- 2020年7月1日：您將無法建立新的搜尋和保留，但是您仍然可以自行承擔執行、編輯和刪除現有的搜尋。 Microsoft 支援將不會再 In-Place EAC 中的 eDiscovery & 保留。

- 2020年10月1日： In-Place eDiscovery & 保留 EAC 中的功能將置於唯讀模式。 這表示您只可以移除現有的搜尋和保留。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>註解</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出於法律目的進行搜尋、匯出和保留</td>
<td>Microsoft 365 規範中心內的核心 eDiscovery 案例 </td>
<td><p>使用核心 eDiscovery 案例的功能，可提供功能性同位，以 In-Place eDiscovery 和 In-Place 保留。 其中包括下列項目：</p>
<ul>
<li>
<p>搜尋可擴展至數百萬位置</p>
</li>
<li>
<p>更高的可靠性用於搜尋、匯出及放置內容保留</p>
</li>
<li>
<p>在 Exchange Online 中搜尋內容、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊、Yammer 群組、Microsoft 365 群組，以及其他儲存在 Office 365 應用程式中的內容</p></li></ul>
<p>如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">管理 Office 365 的法律調查</a>。</td>
</tr>
<tr class="even">
<td>保留以供保留用途</td>
<td>Microsoft 365 規範中心內的保留原則</td>
<td><p>您可以使用保留原則來保留內容，如有需要，請在保留期間到期之後加以刪除。 其他功能包括：</p>
<ul>
<li>
<p>將原則套用至整個組織 </p>
</li><li>
<p>將原則套用至特定的內容位置，例如 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 團隊和 Office 365 群組</p></li>
<li>
<p>將原則套用至特定使用者</p></li></ul>
<p>如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">保留原則一覽</a>。</td>
</tr>
<tr class="odd">
<td>將電子郵件搜尋結果複製到探索信箱以供審閱</td><td>在高級 eDiscovery 2.0 中複查集</td>
<td><p>在 Microsoft 365 中審閱內容的工作並不容易。 「複查集」具有許多強大的功能，可協助您減少所需的查看時間和資料量，包括：</p>
<ul>
<li><p>執行 fast search 查詢及篩選審閱集中的內容</p></li>
<li><p>分析審閱集中的內容;這包括電子郵件執行緒、接近重複偵測、主題分析和預測編碼</p></li>
<li><p>標記檢閱集中的文件</p></li>
<li><p>標記建議，以協助識別律師用戶端許可權內容</p></li></ul>
<p>如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的進階電子文件探索解決方案概觀</a>。</p>
<p>
<p>或者，您可以將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 365 匯入服務將 Pst 匯入探索信箱。 如需逐步指示，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用網路上傳將 PST 檔案匯入 Office 365</a>。
</tr>
<tr class=even>
  <td>將郵件從一個信箱複製到不同的信箱</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
  <td>若要讓人員能夠存取另一個使用者的電子郵件（例如，當員工離開您的組織，而您需要讓其他人存取先前員工的電子郵件），建議您指派該人員存取先前員工的信箱。 因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</td>
  
  </tr>
<tr class="odd">
<td>從 [可復原的專案] 資料夾還原專案</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>您可以還原信箱中永久刪除的專案（也稱為虛<i>刪除的</i>專案），只要專案的刪除專案保留期間尚未過期。 如需詳細資訊，請參閱<a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中</a>的 [可復原的專案] 資料夾。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>有關 In-Place eDiscovery 和 In-Place 保留的 FAQs

**我使用 In-Place eDiscovery & 的「副本搜尋結果」功能，將搜尋結果複製到探索信箱，以供律師審閱。我現在有哪些選項？**

目前有兩種方法可以複製這項功能。 第一個用途是使用[高級 eDiscovery 2.0 版中的複查集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。 「審閱」集中的功能，您可以在傳統的回顧工具中看到許多相同的功能，例如快速搜尋檔、標記、電子郵件執行緒、接近重複群組、主題分析和預測編碼。 如果您仍然想要使用探索信箱進行審閱，第二個選項是將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 規範中心的 [Pst 匯入][功能](use-network-upload-to-import-pst-files.md)，將 pst 檔案匯入到探索信箱。

**如何控制 eDiscovery 管理員可使用新工具進行搜尋的內容位置（例如信箱或網站）？**

Microsoft 365 規範中心也會使用[規範界限](set-up-compliance-boundaries.md)來控制 eDiscovery 管理員可搜尋的內容位置。 規範界限可用於政府機構內，但必須保持在代理商界限或具備地理位置 boarders 的多國公司。

**如何將目前的搜尋和保留移動至 Microsoft 365 規範中心？**

您可以使用 PowerShell 從 EAC 遷移 In-Place eDiscovery 搜尋和保留。 如需相關指示，請參閱將[搜尋和保留從 EAC 遷移至 Microsoft 365 規範中心](https://go.microsoft.com/fwlink/?linkid=2114224)。

## <a name="-mailboxsearch-cmdlets"></a>\*-Get-mailboxsearch 程式 Cmdlet

根據在 Exchange 系統管理中心的2017年7月1日宣佈的原始宣告，In-Place eDiscovery & 保留功能和對應** \*的 get-mailboxsearch 程式**Cmdlet 即將停用。 這些 Cmdlet 可讓使用者搜尋、保留及匯出法律、法規及公開要求的信箱內容。

由於這些功能現在可在[<span class="underline">Microsoft 365 規範中心</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)和 Office 365 安全性 & 合規性中心 PowerShell 取得，提高效能與擴充性，所以您應該使用這些改進的 Cmdlet。 這些 Cmdlet 包括[<span class="underline"> \*-get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase)、 [<span class="underline"> \*-new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)、 [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)、 [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)及[<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業組織

- Office 365 和 Microsoft 365 教育組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD

- Office 365 德國

### <a name="timeline"></a>時間表

- 2020年7月1日：您將無法使用**New-MailboxSearch**來建立新的 In-Place eDiscovery 搜尋和 In-Place 保留，但是您仍然可以使用 Cmdlet 來執行、編輯和刪除現有的搜尋，並以您自己的風險進行。 Microsoft 支援人員將不再為這些類型的搜尋和保留提供協助。

- 2020年10月1日：如先前所述，將 EAC 中的 In-Place eDiscovery & 保留功能會置於唯讀模式。 這也表示您將無法使用**New-MailboxSearch**、 **Start-MailboxSearch**或**Set-MailboxSearch** Cmdlet。 您只可以取得及移除現有的搜尋和保留。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>註解</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜尋和匯出</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。 您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。 然後，您可以使用<strong>New-ComplianceSearchAction</strong> Cmdlet 來匯出搜尋結果。 您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</p>
<p>
<p><strong>附注：</strong>如果您使用這些 Cmdlet 來建立未與核心 eDiscovery 案例相關聯的搜尋，則這些搜尋會位於 Microsoft 365 規範中心的 [<strong>內容搜尋</strong>] 頁面上。</p></td>
</tr>
<tr class="even">
<td>保留信箱中的內容</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">*-New-caseholdrule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 規範中心的封存必須與 Get-compliancecase 相關聯。 首先，建立規範案例，然後建立 CaseHoldPolicy 及 New-caseholdrule。</p>
<p><strong>附注：</strong>建立沒有建立 New-caseholdrule 的 CaseHoldPolicy，會在建立 New-caseholdrule 並與 CaseHoldPolicy 關聯之前，使保留無法運作。 如需詳細資訊，請參閱 Cmdlet 檔。</p></td>
</tr>
<tr class="odd">
<td>將搜尋結果複製到探索信箱</td>
<td>無</td>
<td>這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。 請參閱下列常見問題，以取得其他解決方案。</td>
</tr>
  <tr class=even>
  <td>將郵件從一個信箱複製到不同的信箱</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
  <td>若要讓人員能夠存取另一個使用者的電子郵件（例如，當員工離開您的組織，而您需要讓其他人存取先前員工的電子郵件），建議您指派該人員存取先前員工的信箱。 因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FAQs 關於 ***-get-mailboxsearch 程式**Cmdlet

**我們使用「複製搜尋」來匯出電子郵件訊息或立即訊息，以供其他 eDiscovery 和法律調查之用。停用這些 Cmdlet 後，還有哪些其他選項？**

[<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph)提供許多方法，可讓您提取資料，以進行分析，以及與使用** \*-get-mailboxsearch 程式**指令程式相比更具彈性性及可擴充性的其他目的。

**如何將搜尋遷移並保留至 Microsoft 365 規範中心？**

使用 PowerShell 腳本，可以從 Exchange 系統管理中心遷移 In-Place eDiscovery 搜尋和保留。 如需詳細資訊，請參閱將[舊版 eDiscovery 搜尋和保留遷移至 Microsoft 365 規範中心](migrate-legacy-eDiscovery-searches-and-holds.md)。

**在終止 Cmdlet 後，是否仍然可以移除或取回搜尋？**

是的，雖然我們正在移除建立及修改搜尋的能力，但您仍然可以使用**Get-MailboxSearch**和**Remove-MailboxSearch** ，直到進一步通知。 不過，在退休日期之後使用這些 Cmdlet 會有您自己的風險，而且 Microsoft 支援將不再能夠提供協助。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox Cmdlet

Exchange Online PowerShell 中的**Search-Mailbox** Cmdlet 會在 [正在撤銷] 中，于最初宣告的指令中的指令，于2018中從後傳回的指令。 **Search-Mailbox** Cmdlet 最初是用來搜尋使用者的信箱，並清除惡意內容。 建議您開始使用 Office 365 安全性 & 規範中心 PowerShell 的**New-ComplianceSearch**和**New-ComplianceSearchAction** Cmdlet，以搜尋及清除內容。 針對內建的安全性體驗， [<span class="underline">microsoft 365 的安全性功能</span>](https://docs.microsoft.com/microsoft-365/security/)可為電子郵件和許多其他 Microsoft 服務提供強健的威脅防護。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業組織

- Office 365 和 Microsoft 365 教育組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD

- Office 365 德國

### <a name="timeline"></a>時間表

-  2020年7月1日：將無法再使用**Search-Mailbox** Cmdlet，Microsoft 支援人員將不再提供協助。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>註解</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜尋信箱</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></a></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。 您可以使用<strong>新的-</strong>、 <strong>Get</strong>及<strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。 然後，您可以使用<strong>New-ComplianceSearchAction 匯出</strong>命令匯出搜尋結果。 您仍然需要使用 Microsoft 365 規範中心內的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</p></p>
</td>
</tr>
<tr class="even">
<td>清除信箱中的郵件</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋及清除內容。 您可以使用<strong>New-ComplianceSearch</strong>和<strong>New-ComplianceSearch</strong> Cmdlet 來建立和執行搜尋，然後您可以使用<strong>New-ComplianceSearchAction-Purge PurgeType</strong>命令來清除內容。 如需詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜尋並刪除郵件</span></a>。</p>
</td>
</tr>
<tr class="odd">
<td>從信箱刪除大量電子郵件</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">設定信箱的封存與刪除原則</span></a></p>
<p></p></td>
<td><p>系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</p>
</td>
</tr>
<tr class="even">
<td>將搜尋結果複製到探索信箱</td>
<td> </td>
<td>這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。 如需其他解決方案，請參閱<strong>*-MailboxSearch Cmdlet</strong>區段中的 FAQs。 </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web 服務 API 作業

Exchange 系統管理中心的 In-Place eDiscovery & 保留功能，以及 exchange Online PowerShell 中的對應** \*get-mailboxsearch 程式**Cmdlet 使用 exchange Web 服務 API 中的這些作業。 當您淘汰其他舊版 eDiscovery 工具時，也會將其淘汰。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業組織

- Office 365 和 Microsoft 365 教育組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC High 和 DoD

- Office 365 德國

### <a name="timeline"></a>時間表

- 2020年7月1日：將不再提供 GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 作業，而且 Microsoft 支援將不再提供協助。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v 1。0

Advanced ediscovery 1.0 版，也就是在核心 eDiscovery 案例中，您可以按一下 [**切換至高級 ediscovery**]，將會停用此版本的高級 ediscovery。 其功能已由 Microsoft 365 規範中心內的新「[高級 eDiscovery」解決方案](https://aka.ms/edisco)所取代。

若要判斷您的組織是否使用 Advanced eDiscovery 1.0 版：

1. 移至[Office 365 的安全性 & 規範中心](https://protection.office.com)。

2. 在安全性 & 規範中心的左功能窗格中，按一下 [ **ediscovery > ediscovery**，然後開啟核心 eDiscovery 案例。

3. 如果您看到 [**切換至「高級 ediscovery** 」按鈕，請按一下此按鈕將會帶您的1.0 版本的高級 ediscovery （即將淘汰）。 在核心 eDiscovery 中建立及管理案例的功能將不會受到影響。 只有在高級 eDiscovery 1.0 （按一下 [**切換成 Advanced eDiscovery**]）中新增及分析案例資料的功能，才會停用。

Microsoft 365 （也稱為「 *Advanced ediscovery 2.0 2.0*」）中新的 [ediscovery 解決方案] 提供了原始解決方案的所有功能，但現在包含以保管人為基礎的方法，可識別其他 Microsoft 365 服務中的內容、收集該內容，然後將其新增至審閱集，以供檢閱者使用 fast search 查詢、標記和分析功能，協助挑選相關的檔。 「高級 eDiscovery」現在包括 Microsoft 和非 Microsoft 檔案類型的增強的處理和原生檢視器、[這裡](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)是檔案類型的完整清單，以及支援的元資料欄位在[這裡](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。 此外，新的高級 eDiscovery 解決方案提供功能強大的保管人功能，可讓您將保留套用至不同服務中的內容、通知使用者保留，以及追蹤保管人回應，全部都是在高級 eDiscovery 案例內。

存取高級 eDiscovery 2.0：

1. 移至[Microsoft 365 規範中心](https://compliance.microsoft.com)。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Advanced**]。

此時，我們建議您開始將 eDiscovery 工作流程轉換為新的高級 eDiscovery 功能。 雖然您仍然可以存取現有案例中的 Advanced eDiscovery 1.0 版，但 Microsoft 支援不會在2020年10月1日之後提供支援。 如需詳細資訊，請參閱下列時程表。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業組織

- Office 365 和 Microsoft 365 教育組織

- Office 365 德國

### <a name="timeline"></a>時間表

- 2020年7月1日：您將無法建立新的高級 eDiscovery 1.0 案例。

- 2020年10月1日：您將無法在任何情況下新增資料（為高級 eDiscovery 準備搜尋結果）。 您將能夠繼續使用現有案例中的資料，必須自行承擔。 Microsoft 支援將不再提供協助。 

### <a name="alternative-tools"></a>替代工具

Microsoft 365 規範中心的[高級 eDiscovery 解決方案](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。