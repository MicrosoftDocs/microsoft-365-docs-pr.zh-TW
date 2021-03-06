---
title: 在系統管理中心管理增益集
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用集中式增益集，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: b888c0f329e3f1f36f5aa566df7efbab07cd1f5f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509131"
---
# <a name="manage-add-ins-in-the-admin-center"></a>在系統管理中心管理增益集

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true) (英文)。

::: moniker-end

Office 增益集可協助您個人化檔，並簡化存取網頁上資訊的方式 (請參閱 [開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。 

在管理員為組織中的使用者部署增益集後，系統管理員可以關閉或開啟增益集、編輯、刪除及管理增益集的存取。

如需從系統管理中心安裝增益集的詳細資訊，請參閱 [在系統管理中心部署增益集](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。
  
## <a name="add-in-states"></a>增益集狀態

增益集可以處於 [ **開啟** ] 或 [ **關閉** ] 狀態。
  
|**State**|**狀態如何發生**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |系統管理員上載增益集，並將其指派給使用者或群組。  <br/> |被指派增益集的使用者和群組會在相關用戶端中看見增益集。  <br/> |
|**已關閉**  <br/> |系統管理員已關閉增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> 如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。  <br/> |
|**Deleted**  <br/> |系統管理員已刪除增益集。  <br/> |被指派增益集的使用者和群組無法再存取增益集。  <br/> |
   
如果沒有人再使用增益集，請考慮刪除增益集。 例如，如果增益集只會在一年的特定時間內使用，則關閉增益集可能會有意義。

## <a name="delete-an-add-in"></a>刪除增益集

您也可以刪除已部署的增益集。

1. 在系統管理中心中，移至 [**設定**  >  **服務] & 增益集**] 頁面。

     > [!NOTE]
    > 系統管理中心已更新整合型應用程式的部署經驗。 如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [**設定**] [  >  **整合式應用程式**]。 在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。

2. 選取部署的增益集。

3. 按一下 [ **刪除] Add-In**。 移除右下角的增益集按鈕。

4. 驗證您的選擇，然後選擇 [ **移除增益集**]。

## <a name="edit-add-in-access"></a>編輯增益集存取

部署後，系統管理員也可以管理使用者對增益集的存取。

1. 在系統管理中心中，移至 [**設定**  >  **服務] & 增益集**] 頁面。

     > [!NOTE]
    > 系統管理中心已更新整合型應用程式的部署經驗。 如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [**設定**] [  >  **整合式應用程式**]。 在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。

2. 選取部署的增益集。

3. 按一下 [在 **誰可以存取**] 底下的 [**編輯**]。

4. 儲存變更。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>在 Outlook) 以外的所有用戶端上關閉 Office 存放區，以防止增益集下載 (

> [!NOTE]
> Outlook 增益集安裝是由 [不同](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)的程式管理。

做為組織，您可能想要防止從 Office Store 下載新的 Office 增益集。 這可以與集中式部署搭配使用，以確保只有組織認可的增益集部署至組織內的使用者。
  
**若要關閉增益集採集**
  
1. 在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。

     > [!NOTE]
    > 系統管理中心已更新整合型應用程式的部署經驗。 如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [**設定**] [  >  **整合式應用程式**]。 在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。
    
3. 選取 [ **使用者擁有的應用程式和服務**]。
    
4. 清除 [讓使用者存取 Office store] 選項。

這會防止所有使用者從存放區中取得下列增益集。
  
- Word、Excel 及 PowerPoint 2016 的增益集，來自：
    
  - Windows
    
  - Mac
    
  - 辦公室
    
    
- 從 **AppSource** 中開始的購置
    
- Microsoft 365 中的增益集
    
嘗試存取儲存區的使用者會看到下列訊息： **對不起，Microsoft 365 已設定為防止個別購買 Office store 增益集。**
  
下列版本提供支援關閉 Office 書店的功能：
  
- Windows： 16.0.9001-目前可供使用。
    
- Mac： 16.10.18011401-目前可供使用。
    
- iOS： 2.9.18010804-目前可供使用。
    
- 目前可用的 web。
    
這不會讓系統管理員使用集中式部署從 Office Store 指派增益集。
  
若要防止使用者使用 Microsoft 帳戶登入，您可以限制登入只使用組織帳戶。 如需詳細資訊，請參閱 [Office 2016 的身分識別、驗證及授權](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。  

> [!NOTE]
> 防止使用者存取 office 書店也會防止使用者在 [進行測試時旁載 Office 增益集](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>更多關於使用者使用增益集的體驗

部署增益集之後，您的使用者就可以開始在 Office 應用程式中使用它 (請參閱 [開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。 增益集會出現在增益集所支援的所有平臺上。
  
如果增益集支援增益集命令，命令會顯示在 Office 功能區上。 在下列範例中，會出現 **引文** 增益集的命令 **搜尋引文**。 

![具有搜尋引文的 Office 功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的增益集不支援增益集命令，或是您想要查看所有已部署的增益集，您可以透過 **My 增益集** 進行查看。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 選取 [ **插入 \> 我的增益集**]。 
    
2. 在 [Office 增益集] 視窗中，選取 [ **管理受管理** ] 索引標籤。 
    
3. 在此範例中，按兩下您先前部署的增益集 (中的 **引文** ) 。 <br/>![[Office 增益集] 頁面的 [管理受管理] 索引標籤](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在 [ **首頁** ] 功能區上，選取 [ **取得增益集**]。<br/>![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)
  
2. 選取左側導覽中的 [系統 **管理管理** ]。 

## <a name="learn-more"></a>深入了解

[在系統管理中心部署增益集](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

深入了解如何建立及建置 [Office 增益集](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)。
  
[使用集中式部署 PowerShell Cmdlet 來管理增益集](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。
  
[疑難排解：使用者未看到增益集](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Microsoft Store 中的未成年人和取得增益集](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
