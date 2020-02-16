---
title: 設計獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 摘要： 逐步執行獨立的 SharePoint Online 小組網站的設計程序。
ms.openlocfilehash: f03df1f99650f458dd9df2c9e561decf491c3011
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083203"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>設計獨立的 SharePoint Online 小組網站

 **摘要：** 獨立的 SharePoint Online 小組網站的設計程序步驟。
  
本文會引導您完成建立隔離的 SharePoint Online 小組網站之前，您必須進行的關鍵設計決策。
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>階段 1： 判斷您的 SharePoint 群組和權限等級

使用下列 SharePoint 群組建立預設每個 SharePoint Online 小組網站：
  
- \<站台名稱 # C0 成員
    
- \<站台名稱 # C0 訪客
    
- \<站台名稱 # C0 擁有者
    
這些群組不同 Office 365 和 Azure Active Directory (AD) 群組，並會指派的資源之網站的權限的基準。
  
會決定 SharePoint 群組的成員可以執行網站中的特定權限集合是權限等級。 根據預設，適用於 SharePoint Online 小組網站有三個權限層級： 編輯 」、 「 讀取和 「 完全控制。 下表顯示預設相互關聯的 SharePoint 群組和指派的權限等級：
  
|**SharePoint 群組**|**權限等級**|
|:-----|:-----|
|\<站台名稱 # C0 成員  <br/> |編輯  <br/> |
|\<站台名稱 # C0 訪客  <br/> |讀取  <br/> |
|\<站台名稱 # C0 擁有者  <br/> |完全控制  <br/> |
   
 **最佳作法：** 您可以建立其他的 SharePoint 群組和權限等級。 不過，建議使用的預設 SharePoint 群組和權限層級的隔離 SharePoint Online 網站。
  
以下是預設 SharePoint 群組和權限等級。
  
![預設 SharePoint 群組和權限層級的 SharePoint Online 網站。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>階段 2： 使用存取群組將權限指派給使用者

您可以藉由新增使用者帳戶或使用者帳戶為 SharePoint 群組的成員的 Office 365 或 Azure AD 群組來指派給使用者的權限。 新增後，Office 365 使用者帳戶，或是直接或間接透過 Office 365 或 Azure AD 群組的成員資格，指派相關聯的 SharePoint 群組的權限等級。
  
使用預設 SharePoint 群組做為範例：
  
- 屬於**\<網站名稱> 成員**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派的**編輯**權限層級
    
- 屬於**\<網站名稱> 訪客**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派**讀取**權限等級
    
- 屬於**\<網站名稱> 擁有者**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派 [**完全控制**」 權限等級
    
 **最佳作法：** 雖然您可以管理透過個別使用者帳戶的權限，我們建議您使用單一 Azure AD 群組，而是稱為存取群組。 這可簡化透過在 [存取] 群組的成員資格的權限管理，而不是管理清單中的使用者帳戶為每個 SharePoint 群組。
  
Azure AD 群組的 Office 365 是不同於 Office 365 群組。 Azure AD 群組出現在其**類型**設為 [**安全性**與 Microsoft 365 系統管理中心中，而且不具有電子郵件地址。 您可以管理 azure AD 群組內：
  
- Active Directory Domain Services (AD DS)
    
    這些是您內部部署中已建立的群組 AD DS 基礎結構和同步處理至 Office 365 訂閱。 在 Microsoft 365 系統管理中心中，這些群組會有**與 active directory Synched****狀態**。
    
- Office 365
    
    以下是使用 Microsoft 365 系統管理中心，在 Azure 入口網站或 Microsoft PowerShell 已建立的群組。 在 Microsoft 365 系統管理中心中，這些群組會有**雲端**的**狀態**。
    
 **最佳作法：** 如果您是使用 AD DS 內部，並且同步處理與您的 Office 365 訂閱，執行您的使用者和群組管理與 AD DS。
  
隔離的 SharePoint Online 小組網站，建議的群組結構看起來像這樣：
  
|**SharePoint 群組**|**Azure AD 為基礎的存取群組**|**權限等級**|
|:-----|:-----|:-----|
|\<站台名稱 # C0 成員  <br/> |\<站台名稱 # C0 成員  <br/> |編輯  <br/> |
|\<站台名稱 # C0 訪客  <br/> |\<站台名稱 # C0 檢視者  <br/> |讀取  <br/> |
|\<站台名稱 # C0 擁有者  <br/> |\<站台名稱 # C0 系統管理員  <br/> |完全控制  <br/> |
   
 **最佳作法：** 雖然您可以使用 Office 365 或 Azure AD 群組作為 SharePoint 群組的成員，我們建議您使用 Azure AD 群組。 Azure AD 群組、 管理透過 AD DS 或 Office 365，讓您更多彈性，可使用巢狀的群組指派權限。
  
以下是預設設定為使用 Azure AD 為基礎的存取群組的 SharePoint 群組。
  
![使用存取群組作為預設 SharePoint Online 網站群組的成員。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
在設計時三個存取群組，請謹記下列事項：
  
- 應該只有幾個成員中的**\<網站名稱> Admins**存取群組，對應至數目更少的 SharePoint Online 系統管理員負責管理小組網站。
    
- 大部分的網站成員位於**\<網站名稱> 成員**或**\<網站名稱> Viewer**存取群組。 因為網站中的成員**\<網站名稱> 成員**存取群組已刪除或修改網站中的資源，請仔細考慮其成員資格的能力。 有疑問，新增至網站成員**\<網站名稱> Viewer**存取群組。
    
以下是範例為名為 ProjectX 隔離網站的存取群組與 SharePoint 群組。
  
![SharePoint Online 網站使用存取群組的範例會為名為 ProjectX。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>階段 3： 使用巢狀 Azure AD 群組

受限於數目更少的人員的專案，Azure AD 為基礎的存取群組新增至 SharePoint 群組網站的單一層級可容納大部分的案例。 不過，如果您有大量的人員和那些人員已經成員建立 Azure AD 群組，您可以更輕鬆地指派 SharePoint 權限使用巢狀的群組或包含其他群組作為成員的群組。
  
例如，您要建立隔離的 SharePoint online 小組網站的高階主管的銷售、 行銷、 工程、 法律的共同作業與支援部門與那些部門已經自己的群組，以高階主管的使用者帳戶成員資格。 而不是新的網站成員建立新的群組，並將放中，所有的個別高階主管的使用者帳戶會置於新群組中每個部門的現有高階主管群組。
  
 如果您要共用的多個組織之間的 Office 365 訂用帳戶，單一層級的隔離的網站，為組織的群組成員資格可能變得很難管理由於使用者帳戶的真正數目。 在此情況下，您可以使用每個組織的 Azure AD 群組包含要管理權限的群組在其組織內的巢狀。
  
若要使用巢狀 Azure AD 群組：
  
1. 識別或建立 Azure AD 群組，包含使用者帳戶，並將適當的使用者帳戶新增為成員。
    
2. 建立容器 Azure AD 為基礎的存取群組，包含其他 Azure AD 群組，並將這些群組新增為成員。
    
3.  適當層級的存取容器存取群組，找出對應的權限等級與 SharePoint 群組。
    
> [!NOTE]
> 您無法使用巢狀的 Office 365 群組。 
  
以下是 [ProjectX 成員存取群組的範例中的巢狀的 Azure AD 安全性群組。
  
![針對 ProjectX 網站成員存取群組使用巢狀的存取群組的範例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
因為所有的參考資料、 工程和專案中的使用者帳戶時會導致 teams 旨在為網站成員，很容易將其 Azure AD 群組新增至 ProjectX 成員存取群組。
  
## <a name="next-step"></a>下一步

當您準備好要建立及設定隔離的網站在生產環境中時，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



