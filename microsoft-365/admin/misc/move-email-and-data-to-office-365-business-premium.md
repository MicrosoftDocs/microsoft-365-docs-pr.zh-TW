---
title: 將電子郵件和資料移至 Microsoft 365 商務標準
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 瞭解如何將資料移至新的商務身分識別。
ms.openlocfilehash: 03a8ff6b3cfab43d80401a10825a1c274e278ed9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399323"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>將電子郵件和資料移至 Microsoft 365 商務標準

當您升級至 Microsoft 365 商務標準時，我們會為您提供一種新的*商業身分識別*。 You get a new email account, and a separate OneDrive account for your business data. 
  
如果您想要將某些個人資料移至新的商務身分識別中，請遵循下列指示：
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **複製您的 OneDrive 資料**
1. 在您的硬碟上建立暫存資料夾，以暫時存放您要遷移至 Microsoft 365 for business 的檔案。
    
2. 移至 [https://onedrive.live.com/](https://onedrive.live.com/) 並使用您用來存取 microsoft 365 家族訂閱的 Microsoft 帳戶登入。 
    
3. 將您想要用於商務用 Microsoft 365 的檔案複製到您在步驟1中建立的本機資料夾。
    
 **將 OneDrive 檔案匯入至 Microsoft 365 for business**
1. 移至[admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) ，並使用您的 Microsoft 365 應用程式的使用者名稱和密碼登入。 
    
2. 選取左上角的**應用程式啟動器**圖示，然後選擇 [ **OneDrive**]。
  
    > [!TIP]
    > 首次開啟商務用 OneDrive 時，您必須設定 OneDrive。 如果發生這種情況，在 [**歡迎使用商務用 OneDrive** ] 頁面上，選取 **[下一步]**。 在設定 OneDrive 後，請選取**您的 OneDrive 準備就緒**。 
  
3. 您會進入空白的 OneDrive 資料夾。 如果您想要建立子資料夾，請選取 [**新增** \> **資料夾**]。

4. 選取 **[上傳**]，將檔案從您複製 OneDrive 檔案的硬碟上複製。 
  
    > [!NOTE]
    >  您可以上傳個別檔案，也可以一次上傳一組檔案 (例如特定資料夾中的所有檔案)，但您無法將資料夾複製到商務用 OneDrive。您必須改為在商務用 OneDrive 中建立需要的資料夾結構。 >  如果您想將檔案複製到步驟 4 中建立的資料夾，請在上傳檔案前開啟該資料夾，否則檔案將會上傳到根資料夾。上傳檔案之後，您也可以在商務用 OneDrive 中的資料夾之間移動檔案。 
  
## <a name="outlookemail"></a>[Outlook/電子郵件](#tab/Outlook)
  
 **將 Outlook 2013 資訊匯出成 Outlook 資料檔**
1. 建立 Outlook 資料檔 (.pst) 之前，您必須先在電腦版 Outlook 中新增要匯出 Outlook 資訊的帳戶。若要了解如何將帳戶新增到 Outlook 2013 或更新版本，請參閱[在 Windows 版 Outlook 中設定電子郵件](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)或[在 Mac 版 Outlook 2011 中設定電子郵件](https://support.microsoft.com/en-us/office/set-up-email-in-mac-os-x-mail-de372dc4-9648-4044-a76c-e8a60e178d54)。
    
2. 每個使用者都需要完成[將電子郵件、連絡人及行事曆匯出或備份為 Outlook.pst 檔案](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)中的步驟。
    
 **在 Outlook 中設定新的電子郵件帳戶**
1. 每個使用者都必須設定其新的電子郵件帳戶隨附于 Microsoft 365 for business 訂閱。 若要這麼做，他們將需要其新電子郵件帳戶的位址。 每個使用者的電子郵件帳戶與用來登入 Microsoft 365 for business 的使用者名稱相同。 它看起來會類似 sue@contoso.onmicrosoft.com 或 david@contoso.com。
    
2. 要求每個使用者在 Outlook 中新增自己的電子郵件帳戶。若要了解如何進行這項作業，請參閱[在 Windows 版 Outlook 中設定電子郵件](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)或[在 Mac 版 Outlook 2011 中設定電子郵件](https://support.microsoft.com/en-us/office/set-up-email-in-mac-os-x-mail-de372dc4-9648-4044-a76c-e8a60e178d54)。
    
 **從 Outlook 資料檔匯入資訊**
1. 這會將儲存在 PST 檔案中的電子郵件、行事曆、工作和連絡人，合併成您的商務用 Microsoft 365 電子郵件帳戶。
    
2. 若要將儲存在 PST 檔案中的資訊匯入至 Microsoft 365 的商務電子郵件帳戶，請讓每位使用者完成[從 Outlook .pst 檔案匯入電子郵件、連絡人和行事曆](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx)中的步驟。
    
---

