---
title: 使用 Azure 資訊保護來保護 SharePoint Online 檔案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：套用 Azure 資訊保護來保護高度機密 SharePoint Online 小組網站中的檔案。
ms.openlocfilehash: 8d3a49297d13d8565d3e01cb7391d79645442128
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077807"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a>使用 Azure 資訊保護來保護 SharePoint Online 檔案

 **摘要：** 套用 Azure 資訊保護來保護高度機密 SharePoint Online 小組網站中的檔案。
  
使用本文中的步驟來設定 Azure 資訊保護，為檔案提供加密和權限。這些檔案可新增至針對高度機密保護所設定的 SharePoint 文件庫。或者，您可以直接從網站開啟檔案，並使用 Azure 資訊保護用戶端來新增加密。此加密和權限保護會與檔案一起移動，即使是從網站下載檔案也一樣。 

這些步驟是屬於較大的解決方案，用於設定 SharePoint 網站和這些網站中檔案的高度機密保護。如需詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)。 

不建議針對所有的客戶在 SharePoint Online 中的檔案使用 Azure 資訊保護，但可供需要此檔案子集合保護層級的客戶選擇使用。

這套解決方案的一些相關重要注意事項：
- 將 Azure 資訊保護加密套用至儲存於 Office 365 中的檔案時，服務會無法處理這些檔案的內容。共同撰寫、電子文件探索、搜尋、Delve 和其他共同作業功能無法運作。此外，資料外洩防護 (DLP) 原則只可用於中繼資料 (包括 Office 365 標籤)，但無法用於這些檔案的內容 (例如檔案中的信用卡號碼)。

- 此解決方案需要使用者選取標籤，適用 Azure 資訊保護所提供的保護。如果您需要自動加密，以及 SharePoint 編製索引並檢查檔案的功能，請考慮使用 SharePoint Online 中的資訊版權管理 (IRM)。當您設定 IRM 的 SharePoint 文件庫時，下載檔案以進行編輯時，會自動進行加密。SharePoint IRM 包含可能會影響決策的限制。如需詳細資訊，請參閱[在 SharePoint 系統管理中心中設定資訊版權管理 (IRM)](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)。

## <a name="admin-setup"></a>系統管理員設定
首先，針對您的 Office 365 訂閱，使用[如何從 Microsoft 365 系統管理中心啟用 Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的指示。
  
接著，為 Azure 資訊保護設定新的限域原則和子標籤，為高度機密 SharePoint Online 小組網站提供保護與權限。
  
1. 使用具有安全性系統管理員或公司系統管理員角色的帳戶登入系統管理中心。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在您瀏覽器的個別索引標籤中，移至 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com))。
    
3. 如果這是您第一次設定 Azure 資訊保護，請參閱這些[指示](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time)。

4. 在清單窗格中，按一下 [所有服務]****，輸入**資訊**，然後按一下 [Azure 資訊保護]****。

5. 按一下 [標籤]****。
    
6. 以滑鼠右鍵按一下 [高度機密]**** 標籤，然後再按一下 [新增子標籤]****。
    
7. 在 [名稱]**** 中鍵入子標籤的名稱，並在 [描述]**** 中輸入子標籤的描述。
    
8. 在 [為包含此標籤的文件與電子郵件設定權限]**** 中，按一下 [保護]****。
    
9. 在 [保護]**** 區段中，按一下 [Azure (雲端金鑰)]****。
    
10. 在 [保護]**** 刀鋒視窗中，按一下 [保護設定]**** 下的 [新增權限]****。
    
11. 在 [新增權限]**** 刀鋒視窗中，按一下 [指定使用者與群組]**** 下的 [瀏覽目錄]****。
    
12. 在 [AAD 使用者與群組]**** 窗格中，選取您高度機密 SharePoint Online 小組網站的網站成員存取群組，然後按一下 [選取]****。
    
13. 在 [選擇預設的權限，或設定自訂]**** 下，按一下 [自訂]****，然後選取 [檢視權限]****、[編輯內容]****、[儲存]****、[回覆]****、[全部回覆]**** 核取方塊。
    
14. 按兩次 [確定]****。
    
15. 在 [子標籤]**** 刀鋒視窗中，按一下 [儲存]****，然後按一下 [確定]****。

16. 在 [Azure 資訊保護]**** 刀鋒視窗中，按一下 [原則] > [+ 新增原則]****。
    
17. 在 [原則名稱]**** 中輸入新原則的名稱，並在 [描述]**** 中輸入描述。
    
18. 按一下 [選取取得此原則的使用者或群組] > [使用者/群組]****，然後選取極機密 SharePoint Online 小組網站的網站成員存取群組。
    
19. 按一下 [選取] > [確定]****。

20. 按一下 [新增或移除標籤]****。在 [原則: 新增或移除標籤]**** 窗格中，按一下新子標籤的名稱，然後按一下 [確定]****。   

21. 按一下 [儲存]****，然後按一下 [確定]****。
 
## <a name="client-setup"></a>用戶端設定
現在您已可開始建立文件，並利用 Azure 資訊保護和新標籤進行保護。
  
您必須在自己的裝置或以 Windows 為基礎的電腦上[安裝 Azure 資訊保護用戶端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)。您可以編寫指令碼並自動化安裝，使用者也可以手動安裝用戶端。請參閱下列資源：
  
- [Azure 資訊保護的用戶端](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [安裝 Azure 資訊保護用戶端](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [手動安裝的下載頁面](https://www.microsoft.com/download/details.aspx?id=53018)
    
安裝之後，您的使用者會加以執行，然後使用其 Office 365 帳戶從 Office 應用程式登入 (例如 Microsoft Word)。新的 [資訊保護]**** 列可讓使用者選取新的標籤。請確定您的使用者知道 SharePoint Online 小組網站以及要使用哪個標籤來保護其高度機密檔案。
  
> [!NOTE]
> 如果您有多個極機密 SharePoint Online 小組網站，應利用上述設定來建立多個 Azure 資訊保護限域原則，並設定子標籤，再將每個子標籤的權限設為特定 SharePoint Online 小組網站的網站成員存取群組。 
  
## <a name="adding-permissions-for-external-users"></a>新增外部使用者的權限
您可以使用兩種方式，將 Azure 資訊保護所保護的檔案存取權授與外部使用者。在這兩種情況下，外部使用者皆必須擁有 Azure AD 帳戶。如果外部使用者不屬於使用 Azure AD 的組織成員，則可以使用下列註冊頁面以個人身分取得 Azure AD 帳戶：[https://aka.ms/aip-signup](https://aka.ms/aip-signup)。

 - 將外部使用者新增至用來為標籤設定保護的 Azure AD 群組。 您必須先將帳戶新增為目錄中的 B2B 使用者。 當 [Azure Rights Management 進行群組成員資格的快取](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)時，可能需要數小時的時間。  
 - 將外部使用者直接新增至標籤保護。您可以從組織 (例如 Fabrikam.com)、Azure AD 群組 (例如組織內的財務部門) 或使用者，新增所有使用者。例如，您可以將外部的監理人員小組新增至標籤保護。

## <a name="see-also"></a>另請參閱

[保護 SharePoint Online 網站與檔案](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
