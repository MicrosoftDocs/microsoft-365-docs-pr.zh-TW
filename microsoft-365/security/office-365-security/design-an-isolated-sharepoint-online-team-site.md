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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 設計獨立 SharePoint Online 小組網站，包括決定許可權等級、將許可權指派給具有存取群組的使用者，以及嵌套的 Azure AD 群組。
ms.openlocfilehash: 821e15a05bc80e3795f9e18d4457416baf7145b7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209508"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>設計獨立的 SharePoint Online 小組網站

 **摘要：** 逐步執行獨立 SharePoint Online 小組網站的設計程式。
  
本文將引導您完成建立隔離的 SharePoint Online 小組網站之前必須進行的主要設計決策。
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>階段1：判斷您的 SharePoint 群組和許可權等級

預設會使用下列 SharePoint 群組建立每個 SharePoint Online 小組網站：
  
- \<網站名稱> 成員
    
- \<網站名稱> 訪客
    
- \<網站名稱> 擁有者
    
這些群組是與 Microsoft 365 和 Azure Active Directory （AD）群組分開的，也是指派網站資源之許可權的基礎。
  
一組特定許可權，可決定 SharePoint 群組的成員可在網站中執行的動作為許可權等級。 SharePoint Online 小組網站的預設許可權等級有三個： Edit、Read 及 Full control。 下表顯示 SharePoint 群組的預設關聯，以及指派的許可權等級：
  
|**SharePoint 群組**|**權限等級**|
|:-----|:-----|
|\<網站名稱> 成員  <br/> |編輯  <br/> |
|\<網站名稱> 訪客  <br/> |讀取  <br/> |
|\<網站名稱> 擁有者  <br/> |完全控制  <br/> |
   
 **最佳作法：** 您可以建立額外的 SharePoint 群組和許可權層級。 不過，我們建議您針對隔離的 SharePoint Online 網站使用預設的 SharePoint 群組和許可權層級。
  
以下是預設的 SharePoint 群組和許可權層級。
  
![SharePoint Online 網站的預設 SharePoint 群組和許可權層級。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>階段2：將許可權指派給具有存取群組的使用者

您可以將許可權指派給使用者，方法是將其使用者帳戶或使用者帳戶所屬的 Microsoft 365 或 Azure AD 群組新增至 SharePoint 群組。 一旦新增，使用者帳戶（透過 Microsoft 365 或 Azure AD 群組中的成員資格直接或間接）會被指派與 SharePoint 群組相關聯的許可權等級。
  
使用預設的 SharePoint 群組為範例：
  
- 可包含使用者帳戶和群組的** \< 網站名稱> 成員**SharePoint 群組的成員會被指派 [**編輯**] 許可權等級。
    
- ** \< 網站名稱的成員> 訪客**SharePoint 群組，其中可以包含使用者帳戶和群組，都已獲指派「**讀取**」許可權等級。
    
- ** \< 網站名稱> 擁有**者 SharePoint 群組的成員，可包含使用者帳戶和群組，都已獲指派「**完全控制**」許可權層級。
    
 **最佳作法：** 雖然您可以透過個別使用者帳戶管理許可權，但建議您改用單一 Azure AD 群組（稱為存取群組）。 這可簡化透過存取群組成員資格的版權管理，而不是管理每個 SharePoint 群組的使用者帳戶清單。
  
Microsoft 365 的 Azure AD 群組不同于 Microsoft 365 群組。 Azure AD 群組會顯示在 Microsoft 365 系統管理中心中，其**類型**設為 [**安全性**]，而且沒有電子郵件地址。 Azure AD 群組可在下列專案中管理：
  
- Active Directory Domain Services (AD DS)
    
    這些是在您的內部部署 AD DS 基礎結構中建立並同步處理至您的 Microsoft 365 訂閱的群組。 在 Microsoft 365 系統管理中心中，這些群組的**狀態**為 [已**與 active directory 同步處理**]。
    
- Office 365
    
    這些是使用 Microsoft 365 系統管理中心、Azure 入口網站或 Microsoft PowerShell 建立的群組。 在 Microsoft 365 系統管理中心中，這些群組的**狀態**為**雲端**。
    
 **最佳作法：** 如果您使用的是 AD DS 內部部署並與 Microsoft 365 訂閱進行同步處理，請使用 AD DS 執行您的使用者和群組管理。
  
針對隔離 SharePoint 線上小組網站，建議的群組結構如下所示：
  
|**SharePoint 群組**|**Azure AD 型訪問群組**|**權限等級**|
|:-----|:-----|:-----|
|\<網站名稱> 成員  <br/> |\<網站名稱> 成員  <br/> |編輯  <br/> |
|\<網站名稱> 訪客  <br/> |\<網站名稱> 檢視器  <br/> |讀取  <br/> |
|\<網站名稱> 擁有者  <br/> |\<網站名稱> 系統管理員  <br/> |完全控制  <br/> |
   
 **最佳作法：** 雖然您可以使用 Microsoft 365 或 Azure AD 群組做為 SharePoint 群組的成員，我們還是建議您使用 Azure AD 群組。 Azure AD 群組（透過 AD DS 或 Microsoft 365 管理）可讓您更靈活地使用嵌套群組來指派許可權。
  
以下是設定為使用 Azure AD 型存取群組的預設 SharePoint 群組。
  
![使用訪問群組做為預設 SharePoint 線上網站群組的成員。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
當您設計三個訪問群組時，請記住下列事項：
  
- 在 [ ** \< 網站名稱]> Admins** access 群組中應該只有少數幾個成員，對應于管理小組網站的少數 SharePoint Online 系統管理員。
    
- 您的網站成員大部分位於** \< 網站名稱> 成員**或** \< 網站名稱> 查看**器存取群組。 因為** \< 網站名稱> 成員**存取群組中的網站成員具備刪除或修改網站中資源的能力，所以請謹慎考慮其成員資格。 若有疑問，請將網站成員新增至** \< 網站名稱> 查看**器存取群組。
    
以下是名為 ProjectX 之隔離網站的 SharePoint 群組和存取群組的範例。
  
![使用名為 ProjectX SharePoint Online 網站的存取群組的範例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>階段3：使用嵌套 Azure AD 群組

對於僅限少數人員的專案，新增至網站 SharePoint 群組的單一層級 Azure AD 訪問群組會適合大多數案例。 不過，如果您有大量人員，而這些人已經是已建立的 Azure AD 群組的成員，您可以使用嵌套群組或包含其他群組的群組做為成員，更輕鬆地指派 SharePoint 許可權。
  
例如，您想要建立一個隔離的 SharePoint 線上小組網站，以共同共同作業的銷售、行銷、工程、法律和支援部門的主管，以及那些部門已經擁有 executive 使用者帳戶成員資格的群組。 不需要為新的網站成員建立新的群組，並將所有個人的執行使用者帳戶放在新的群組中，將每個部門的現有 executive 群組放在新群組中。
  
 如果您在多個組織之間共用 Microsoft 365 訂閱，則組織的隔離網站的單一群組成員資格可能會因為使用者帳戶的數量非常困難而難於管理。 在此情況下，您可以針對包含組織內群組的每個組織，使用嵌套 Azure AD 群組來管理許可權。
  
若要使用嵌套 Azure AD 群組：
  
1. 識別或建立 Azure AD 群組，其中會包含使用者帳戶，並將適當的使用者帳戶新增為成員。
    
2. 建立將包含其他 Azure AD 群組的容器 Azure AD 型訪問群組，並將這些群組新增為成員。
    
3.  若要取得容器存取群組的適當存取層級，請找出 SharePoint 群組和對應的許可權等級。
    
> [!NOTE]
> 您無法使用嵌套的 Microsoft 365 群組。 
  
以下是 ProjectX 成員存取群組的嵌套 Azure AD 群組範例。
  
![在 ProjectX 網站的成員存取群組中使用嵌套存取群組的範例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
因為「調研」、「工程」和「專案負責人」小組中的所有使用者帳戶都是網站成員，所以將其 Azure AD 群組新增至 ProjectX 成員存取群組會比較容易。
  
## <a name="next-step"></a>後續步驟

當您準備好在實際執行中建立和設定隔離的網站時，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



