---
title: 獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 瞭解獨立的 SharePoint Online 小組網站，包括使用、需求以及可以搭配使用的功能。
ms.openlocfilehash: f88be4b16d7f3a65ba624f7bf4c490b0173883c8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036701"
---
# <a name="isolated-sharepoint-online-team-sites"></a>獨立的 SharePoint Online 小組網站

 **摘要：** 了解獨立的 Sharepoint 小組網站的用途。
  
SharePoint Online 小組網站是為 Microsoft Office 365 中的記事、文件、文章、行事曆及其他資源快速建立共同作業空間的簡易方式。SharePoint Online 小組網站是以 Microsoft 365 群組為基礎，具有簡化的系統管理模型，可以允許具有私人群組成員集合或整個組織的開發共同作業。預設 SharePoint Online 小組網站可讓 Microsoft 365 群組的成員邀請其他使用者並且控制權限設定。
  
不過，在某些情況下，您會想要為網站權限是透過群組成員資格和 SharePoint Online 權限等級 (只能由 SharePoint 系統管理員進行管理) 進行更嚴密控制的共同作業建立 SharePoint Online 小組網站。我們將它稱為獨立的網站，它獨立於共用作業、檢視其內容或管理網站的使用者集合。針對下列項目，您可能需要獨立的網站：
  
- 組織中的秘密專案。
    
- 組織的高度敏感或貴重智慧財產權的位置。
    
- 組織採取的法律行動資源，或其受限所在的資源。
    
- 為了在某些地方重疊，但是大部分來說是個別商務實體的多個組織之間共用 Microsoft 365 訂閱。
    
以下是獨立網站的需求：
  
- 只有 SharePoint Online 系統管理員可以執行網站系統管理，包括可以存取網站的群組成員資格以及設定自訂權限。
    
- 網站的成員無法邀請其他成員加入小組網站。
    
- 不是獨立網站成員的使用者無法要求網站的存取權。當他們嘗試存取與網站相關聯的任何 URL 時，會進入存取遭拒網頁。
    
SharePoint Online 系統管理員要求集中式存取控制和自訂權限的代價是網站經過一段時間後仍然是獨立的。舉例來說，目前成員無論有意或無意，都無法對不應該是網站成員的 Microsoft 365 訂閱內其他使用者進行邀請或設定自訂權限。
  
獨立的網站可以與其他功能搭配使用，例如：
  
- 資訊版權管理，以便確定網站上的資源保持加密，即使它們是在本機下載並且上傳至可供整個組織使用的其他網站。
    
- 資料外洩防護，以便防止使用者以電子郵件傳送網站的資源，例如檔案。
    
## <a name="next-steps"></a>後續步驟

若要在試用訂閱中嘗試獨立的 SharePoint Online 小組網站，請參閱＜[獨立的 SharePoint Online 小組網站開發/測試環境](isolated-sharepoint-online-team-site-dev-test-environment.md)＞中的逐步指示
  
當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。
  
## <a name="see-also"></a>另請參閱

[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)


