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
description: In-Place eDiscovery 和 In-Place 暫止 (，) 中的對應 PowerShell Cmdlet 會在2020的上半年內淘汰。 Search-Mailbox Cmdlet 和 Advanced eDiscovery 的1.0 也會在相同的時段內淘汰。
ms.openlocfilehash: 77a7daf36c86cd302f774e5a4b934148d3dfd5a7
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340993"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>舊版電子文件探索工具淘汰

> [!IMPORTANT]
> 本文所述之舊版 eDiscovery 工具的功能已從 Microsoft 365 服務中移除，或仍可使用，但已不再支援。 任何仍可使用的功能都可以移除，恕不另行通知。 如果您仍在使用任何舊版工具，請考慮遷移至 Microsoft 365 合規性中心中所述的 eDiscovery 工具，或本文所述的其中一個替代工具。

在幾年中，Microsoft 提供了 eDiscovery 工具，可讓您從 Exchange Online 搜尋、預覽及匯出電子郵件內容。 不過，這些工具不再提供有效的方式，可在其他 Microsoft 365 服務中搜尋非 Exchange 內容，例如 SharePoint 線上及 Microsoft 365 群組。 為了解決此情況，Microsoft 提供了其他 eDiscovery 工具，可協助您搜尋各種各樣的 Microsoft 365 內容。 而且我們已致力於在[Microsoft 365 合規性中心](https://compliance.microsoft.com)中整合最新和功能強大的 eDiscovery 功能。 這可讓組織對許多 Microsoft 365 服務中的內容（包括 Exchange Online 在內）進行法律、內部及其他檔要求。

隨著 Microsoft 365 合規性中心中這項新增及改良的 ediscovery 功能的結果，我們會在 Exchange Online 和 Microsoft 365 中，淘汰下列與搜尋電子郵件內容相關的 eDiscovery 相關功能：

- Exchange 系統管理中心中[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[In-Place 保留](/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- Exchange Online PowerShell 指令程式支援 In-Place eDiscovery 及 In-Place 保留， (這些指令程式共同識別為 **-get-mailboxsearch 程式* Cmdlet) 。 這包括下列 Cmdlet：

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > 當其他 * *-MailboxSearch * * * * * 指令程式已停用之後，就可以使用 [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) 和 [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) Cmdlet，這樣您就可以使用這些 Cmdlet 來協助您轉換至其他 eDiscovery 和保留工具。 不過，在下列 (所提及的特定日期之後) Microsoft 支援將不再支援這兩種 Cmdlet。

- Exchange Online PowerShell 中的[Search-Mailbox](/powershell/module/exchange/search-mailbox) Cmdlet。

- Exchange Web 服務 API 中的下列作業：

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 進階電子檔探索 1.0](./overview-ediscovery-20.md)版，也就是透過 Office 365 安全性 & 規範中心內的核心 eDiscovery 案例所存取 Advanced eDiscovery 的第一個版本。 停用 Advanced eDiscovery v 1.0 並不會影響您建立及管理核心 eDiscovery 案例的能力。

> [!NOTE]
> 即將淘汰的 eDiscovery 功能僅適用于雲端型版本的 Microsoft 365 和 Office 365。 在內部部署版本的 Exchange 和 SharePoint 中的 eDiscovery 功能仍會受到支援，直到進一步通知。

本文中的下列各節提供每個已撤銷的功能的指導方針。 此資訊包含時程表和您可以使用的替代工具，而不是退休工具。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Exchange 系統管理中心中 In-Place eDiscovery 和 In-Place 存放 

根據2017年7月1日的原始宣告，Exchange 系統管理員中心的 In-Place eDiscovery & 保留功能 (EAC) 即將停用。 EAC 中 In-Place eDiscovery & 保留頁面允許您從 Exchange Online 搜尋、保留及匯出內容。 In-Place eDiscovery 也可讓您將搜尋結果複製到探索信箱，讓您或其他 eDiscovery 管理員可以查看內容，並將其提供給法律、法規及公開的要求。

由於所有這些功能 (，但除了將搜尋結果複製到探索信箱) 之外， [Microsoft 365 合規性中心](./microsoft-365-compliance-center.md) (中的內容搜尋、eDiscovery 和 Advanced eDiscovery 工具皆可使用這些功能，但改進的功能、可靠性和支援範圍廣泛的 Microsoft 365 服務) ，我們建議您儘快開始使用這些工具。 為了協助您轉換至這些其他 eDiscovery 工具，下表列出您可以使用的工具，而不是 In-Place eDiscovery 和 In-Place 保留。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業版組織

- Office 365 和 Microsoft 365 教育版組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>退休的時程表

- 2020年7月1日：您將無法建立新的搜尋和保留，但是您仍然可以自行承擔執行、編輯和刪除現有的搜尋。 Microsoft 支援將不會再 In-Place EAC 中的 eDiscovery & 保留。

- 2020年10月1日： In-Place eDiscovery & 保留 EAC 中的功能將置於唯讀模式。 這表示您只可以移除現有的搜尋和保留。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出於法律目的進行搜尋、匯出和保留</td>
<td>Microsoft 365 合規性中心中的核心 eDiscovery 案例 </td>
<td><p>使用核心 eDiscovery 案例的功能，可提供功能性同位，以 In-Place eDiscovery 和 In-Place 保留。 其中包括下列項目：</p>
<ul>
<li>
<p>搜尋可擴展至數百萬位置</p>
</li>
<li>
<p>更高的可靠性用於搜尋、匯出及放置內容保留</p>
</li>
<li>
<p>在 Exchange Online 中搜尋內容、SharePoint 線上、商務用 OneDrive、商務用 Skype、Microsoft Teams、Yammer 群組、Microsoft 365 群組，以及儲存在 Office 365 應用程式中的其他內容</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保留以供保留用途</td>
<td>Microsoft 365 合規性中心中的保留原則</td>
<td><p>您可以使用保留原則來保留內容，如有需要，請在保留期間到期之後加以刪除。 其他功能包括：</p>
<ul>
<li>
<p>將原則套用至整個組織 </p>
</li><li>
<p>將原則套用至特定的內容位置，例如 Exchange Online、SharePoint 線上、商務用 OneDrive、商務用 Skype、Microsoft Teams 和 Office 365 群組</p></li>
<li>
<p>將原則套用至特定使用者</p></li></ul>
<p>如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/retention-policies"> 瞭解保留原則和保留標籤</a>。</td>
</tr>
<tr class="odd">
<td>將電子郵件搜尋結果複製到探索信箱以供審閱</td><td>在 Advanced eDiscovery v 2.0 中檢查集合</td>
<td><p>在 Microsoft 365 中審閱內容的工作變得不容易。 「複查集」具有許多強大的功能，可協助您減少所需的查看時間和資料量，包括：</p>
<ul>
<li><p>執行 fast search 查詢及篩選審閱集中的內容</p></li>
<li><p>分析審閱集中的內容;這包括電子郵件執行緒、接近重複偵測、主題分析和預測編碼</p></li>
<li><p>標記檢閱集中的文件</p></li>
<li><p>標記建議，以協助識別律師用戶端許可權內容</p></li></ul>
<p>如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的進階電子文件探索解決方案概觀</a>。</p>
<p>
<p>或者，您可以將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 365 匯入服務，將 pst 匯入探索信箱。 如需逐步指示，請參閱<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用網路上傳將 PST 檔案匯入至 Office 365</a>。
</tr>
<tr class=even>
  <td>將郵件從一個信箱複製到不同的信箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
  <td>若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。 因此，請將存取來源信箱所需的許可權指派給使用者，而不是將信箱專案複製到另一個使用者信箱或共用信箱。</td>
  
  </tr>
<tr class="odd">
<td>從 [可復原的專案] 資料夾還原專案</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>您可以還原永久刪除的專案 (也稱為虛 <i>刪除的</i> 專案) 在信箱中，只要專案的刪除專案保留期間尚未過期。 如需詳細資訊，請參閱<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的 [可復原的專案] 資料夾</a>。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>有關 In-Place eDiscovery 和 In-Place 保留的 FAQs

**我使用 In-Place eDiscovery & 的「副本搜尋結果」功能，將搜尋結果複製到探索信箱，以供律師審閱。我現在有哪些選項？**

目前有兩種方法可以複製這項功能。 第一個用途是使用[Advanced eDiscovery v 2.0 中的審閱集](./view-documents-in-review-set.md)。 「審閱」集中的功能，您可以在傳統的回顧工具中看到許多相同的功能，例如快速搜尋檔、標記、電子郵件執行緒、接近重複群組、主題分析和預測編碼。 如果您仍然想要使用探索信箱進行審閱，第二個選項是將搜尋結果匯出至 PST 檔案，然後使用 Microsoft 規範中心的 [Pst 匯入] [功能](use-network-upload-to-import-pst-files.md) ，將 pst 檔案匯入到探索信箱。

**如何控制哪些內容位置 (例如可 eDiscovery 管理員可以使用新工具搜尋的信箱或網站) ？**

Microsoft 365 合規性中心也會使用[規範界限](set-up-compliance-boundaries.md)來控制 eDiscovery 管理員可搜尋的內容位置。 規範界限可用於政府機構內，但必須保持在代理商界限或具備地理位置 boarders 的多國公司。

**如何將目前的搜尋和保留移至 Microsoft 365 合規性中心？**

您可以使用 PowerShell 從 EAC 遷移 In-Place eDiscovery 搜尋和保留。 如需相關指示，請參閱將[搜尋和保留從 EAC 遷移至 Microsoft 365 合規性中心](./migrate-legacy-ediscovery-searches-and-holds.md)。

## <a name="-mailboxsearch-cmdlets"></a>\*-Get-mailboxsearch 程式 Cmdlet

根據在 Exchange 系統管理中心的2017年7月1日宣佈的原始宣告，In-Place eDiscovery & 保留功能和對應的 **\* get-mailboxsearch 程式** Cmdlet 即將停用。 這些 Cmdlet 可讓使用者搜尋、保留及匯出法律、法規及公開要求的信箱內容。

因為這些功能現在可在[<span class="underline">Microsoft 365 合規性中心</span>](./microsoft-365-compliance-center.md)和 Office 365 安全性 & 規範中心 PowerShell 提高效能與擴充性，所以您應該使用這些改進的 Cmdlet。 這些 Cmdlet 包括[<span class="underline"> \* -get-compliancecase</span>](/powershell/module/exchange/get-compliancecase)、 [<span class="underline"> \* -new-compliancesearch</span>](/powershell/module/exchange/get-compliancesearch)、 [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy)、 [<span class="underline"> \* -new-caseholdrule</span>](/powershell/module/exchange/get-caseholdrule)及[<span class="underline"> \* -new-compliancesearchaction</span>](/powershell/module/exchange/get-compliancesearchaction)。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業版組織

- Office 365 和 Microsoft 365 教育版組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD

- Office 365 Germany

### <a name="timeline"></a>時間表

- 2020年7月1日：您將無法使用 **New-MailboxSearch** 來建立新的 In-Place eDiscovery 搜尋和 In-Place 保留，但是您仍然可以使用 Cmdlet 來執行、編輯和刪除現有的搜尋，並以您自己的風險進行。 Microsoft 支援人員將不再為這些類型的搜尋和保留提供協助。

- 2020年10月1日：如先前所述，將 EAC 中的 In-Place eDiscovery & 保留功能會置於唯讀模式。 這也表示您將無法使用 **New-MailboxSearch**、 **Start-MailboxSearch** 或 **Set-MailboxSearch** Cmdlet。 您只可以取得及移除現有的搜尋和保留。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜尋和匯出</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。 您可以使用 <strong>新的-</strong>、 <strong>Get</strong>及 <strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。 然後，您可以使用 <strong>New-ComplianceSearchAction</strong> Cmdlet 來匯出搜尋結果。 您仍然需要使用 Microsoft 365 合規性中心中的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</p>
<p>
<p><strong>附注：</strong>如果您使用這些 Cmdlet 來建立未與核心 eDiscovery 案例相關聯的搜尋，則這些搜尋會位於 Microsoft 365 合規性中心的「<strong>內容搜尋</strong>」頁面上。</p></td>
</tr>
<tr class="even">
<td>保留信箱中的內容</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-New-caseholdrule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>在 Microsoft 365 合規性中心中的保留必須與 get-compliancecase 相關聯。 首先，建立規範案例，然後建立 CaseHoldPolicy 及 New-caseholdrule。</p>
<p><strong>附注：</strong> 建立沒有建立 New-caseholdrule 的 CaseHoldPolicy，會在建立 New-caseholdrule 並與 CaseHoldPolicy 關聯之前，使保留無法運作。 如需詳細資訊，請參閱 Cmdlet 檔。</p></td>
</tr>
<tr class="odd">
<td>將搜尋結果複製到探索信箱</td>
<td>無</td>
<td>這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。 請參閱下列常見問題，以取得其他解決方案。</td>
</tr>
  <tr class=even>
  <td>將郵件從一個信箱複製到不同的信箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
  <td>若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。 因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FAQs 關於 ***-get-mailboxsearch 程式** Cmdlet

**我們使用「複製搜尋」來匯出電子郵件訊息或立即訊息，以供其他 eDiscovery 和法律調查之用。停用這些 Cmdlet 後，還有哪些其他選項？**

[<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph)提供許多方法，可讓您提取資料，以進行分析，以及與使用 **\* -get-mailboxsearch 程式** 指令程式相比更具彈性性及可擴充性的其他目的。

**如何將搜尋遷移並保留至 Microsoft 365 合規性中心？**

您可以使用 PowerShell 腳本，從 Exchange 系統管理中心遷移 In-Place eDiscovery 搜尋和保留。 如需詳細資訊，請參閱[遷移舊版 eDiscovery 搜尋並保留至 Microsoft 365 合規性中心](migrate-legacy-eDiscovery-searches-and-holds.md)。

**在終止 Cmdlet 後，是否仍然可以移除或取回搜尋？**

是的，雖然我們正在移除建立及修改搜尋的能力，但您仍然可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch** ，直到進一步通知。 不過，在退休日期之後使用這些 Cmdlet 會有您自己的風險，而且 Microsoft 支援將不再能夠提供協助。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox Cmdlet

Exchange Online PowerShell 中的 **Search-Mailbox** Cmdlet 已于最初宣告時，在指令指令的指令中從2018開始傳回的警告。 **Search-Mailbox** Cmdlet 最初是用來搜尋使用者的信箱，並清除惡意內容。 建議您開始使用 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** Cmdlet Office 365 安全性 & 規範中心 PowerShell 來搜尋及清除內容。 針對內建的安全性體驗，Microsoft 365 的[<span class="underline">安全性功能</span>](../security/index.yml)會為電子郵件和許多其他 Microsoft 服務提供強健的威脅防護。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業版組織

- Office 365 和 Microsoft 365 教育版組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD

- Office 365 Germany

### <a name="timeline"></a>時間表

-  2020年7月1日：將無法再使用 **Search-Mailbox** Cmdlet，Microsoft 支援人員將不再提供協助。

### <a name="alternative-tools"></a>替代工具

下表說明您可以用來取代即將淘汰之現有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜尋信箱</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></a></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋和匯出內容。 您可以使用 <strong>新的-</strong>、 <strong>Get</strong>及 <strong>Start-ComplianceSearch</strong> Cmdlet 來建立新的搜尋並查看搜尋預估。 然後，您可以使用 <strong>New-ComplianceSearchAction 匯出</strong> 命令匯出搜尋結果。 您仍然需要使用 Microsoft 365 合規性中心中的核心 eDiscovery 工具，將這些搜尋結果下載至您的本機電腦。</p></p>
</td>
</tr>
<tr class="even">
<td>從信箱刪除大量電子郵件</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">設定信箱的封存與刪除原則</span></a></p>
<p></p></td>
<td><p>系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</p>
</td>
</tr>
<tr class="even">
<td>將搜尋結果複製到探索信箱</td>
<td> </td>
<td>這種功能沒有直接取代，因為它沒有提供所有 Microsoft 365 服務的存取權。 如需其他解決方案，請參閱 <strong>*-MailboxSearch Cmdlet</strong> 區段中的 FAQs。 </td>
</tr>
<tr class=odd>
  <td>將郵件從一個信箱複製到不同的信箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
  <td>若要讓人員可以存取另一個使用者的電子郵件 (例如，當員工離開您的組織，且您需要讓另一個人存取先前員工的電子郵件) 時，建議您指派該人員存取離職員工的信箱。 因此，不要將信箱專案複製到另一個使用者信箱或共用信箱，只需指派使用者的許可權即可存取來源信箱。</td>
</tr>
<tr class=even>
  <td>清除信箱中的郵件</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction 指令程式可以搭配使用，以協助您搜尋及清除內容。 您可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> Cmdlet 來建立和執行搜尋，然後您可以使用 <strong>New-ComplianceSearchAction-Purge PurgeType</strong> 命令來清除內容。 如需詳細資訊，請參閱 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜尋並刪除郵件</span></a>。</p>
</td>
</tr>
<tr class="odd"> 
<td>清除信箱中的郵件</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">指派許可權給信箱</a></td>
<td>若要清除信箱中的郵件，請指派管理員許可權來存取該員工的信箱。 您可以在必要時刪除和回收郵件，以利用 Outlook 內建的搜尋和觀賞功能。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>ExchangeWeb 服務 API 作業

Exchange Web 服務 API 中的這些作業是由 Exchange 系統管理中心中的 In-Place eDiscovery & 保留功能，以及 Exchange Online PowerShell 中的對應 **\* get-mailboxsearch 程式** Cmdlet 使用。 當您淘汰其他舊版 eDiscovery 工具時，也會將其淘汰。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業版組織

- Office 365 和 Microsoft 365 教育版組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD

- Office 365 Germany

### <a name="timeline"></a>時間表

- 2020年7月1日：將不再提供 GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 作業，而且 Microsoft 支援將不再提供協助。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v 1。0

Advanced eDiscovery 1.0 版，也就是在核心 eDiscovery 案例中，按一下 [**切換至 Advanced eDiscovery**]，就會停用 Advanced eDiscovery 的版本。 其功能已由 Microsoft 365 合規性中心中的新[Advanced eDiscovery 方案](./ediscovery.md)所取代。

若要判斷您的組織是否使用 Advanced eDiscovery 1.0 版：

1. 移至 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。

2. 在 [規範中心] 的左功能窗格中，按一下 [ **eDiscovery > core**]，然後開啟核心 eDiscovery 案例。

3. 如果您看到 [**切換至 Advanced eDiscovery** ] 按鈕，按一下該按鈕將會帶您的1.0 版 Advanced eDiscovery （即將淘汰）。 在核心 eDiscovery 中建立及管理案例的功能將不會受到影響。 只有透過按一下 [**切換至 Advanced eDiscovery** ]) 才能在 Advanced eDiscovery 的 1.0 (中新增及分析大小寫資料的功能會被停用。

Microsoft 365 中的新 Advanced eDiscovery 方案 (也稱為 *Advanced eDiscovery v 2.0*) 提供原始解決方案的所有功能，但現在包含以保管人為基礎的方法，可識別其他 Microsoft 365 服務中的內容、收集該內容，然後將其新增至審閱集，讓檢閱者可以利用 fast search 查詢、標記和分析功能，以挑選相關的檔。 Advanced eDiscovery 現在包括 Microsoft 和非 Microsoft 檔案類型的增強處理和原生檢視器，[這裡](./supported-filetypes-ediscovery20.md)有檔案類型的完整清單和支援的元資料欄位在[這裡](./document-metadata-fields-in-advanced-ediscovery.md)。 此外，新的 Advanced eDiscovery 解決方案提供功能強大的保管人保留功能，可讓您將保留套用至不同服務中的內容、通知使用者保留，以及追蹤保管人回應，全部都是在 Advanced eDiscovery 案例內。

若要存取進階電子文件探索 v2.0：

1. 移至 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。

2. 在 Microsoft 365 合規性中心的左功能窗格中，按一下 ****[顯示全部]，然後按一下 ****[電子文件探索] > [進階]。

此時，我們建議您開始將 eDiscovery 工作流程轉換為新的 Advanced eDiscovery 功能。 如有需要，您可以匯出內容並將其儲存在離線狀態，封存 Advanced eDiscovery 1.0 案例。 雖然您仍然可以在現有案例中存取 Advanced eDiscovery 的1.0，直到2020年12月31日為止，Microsoft 支援服務不會在 2020 10 月1日之後提供支援。 如需詳細資訊，請參閱下列時程表。

### <a name="scope-of-affected-organizations"></a>受影響組織的範圍

- Office 365 和 Microsoft 365 企業版組織

- Office 365 和 Microsoft 365 教育版組織

- Office 365 和 Microsoft 365 政府組織;這包括 GCC、GCC 高及 DoD

- Office 365 Germany

### <a name="timeline"></a>時間表

- 2020年7月1日：您將無法建立新的 Advanced eDiscovery 1.0 案例。

- 2020年10月1日：您將無法新增資料 (針對 Advanced eDiscovery) 的任何案例準備搜尋結果。 您將能夠繼續使用現有案例中的資料，必須自行承擔。 Microsoft 支援將不再提供協助。 

- 2020年12月31日：您將無法存取 Advanced eDiscovery 的1.0 案例。

### <a name="alternative-tools"></a>替代工具

Microsoft 365 合規性中心中的[Advanced eDiscovery 解決方案](./overview-ediscovery-20.md)。