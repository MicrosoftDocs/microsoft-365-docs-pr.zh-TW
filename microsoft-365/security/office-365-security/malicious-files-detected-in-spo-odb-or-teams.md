---
title: 檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: 了解要移至檢視中 SharePoint、 OneDrive 或小組，偵測到的惡意檔案的相關資訊，以及如何對這些檔案採取動作。
ms.openlocfilehash: b16ba88cd4984754f92fac2917f0f2b393600692
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078126"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="92f7f-103">檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="92f7f-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="92f7f-104">[適用於 SharePoint、 OneDrive 及 Microsoft Teams 的 office 365 ATP](atp-for-spo-odb-and-teams.md)會保護您的組織在文件庫和小組網站中的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="92f7f-105">偵測到惡意檔案時，該檔案被封鎖，讓任何人可以開啟、 複製、 移動或共用直到由組織的安全性小組會採取進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="92f7f-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="92f7f-106">閱讀本篇文章以了解如何檢視關於偵測到檔案的資訊以及要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="92f7f-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="92f7f-107">若要執行本文所述的工作，您必須具有所需之[Office 365 安全性的權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="92f7f-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="92f7f-108">檢視報告與偵測到檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="92f7f-108">View reports with information about detected files</span></span>

<span data-ttu-id="92f7f-109">若要檢視狀態和偵測到由 Office 365 ATP 的檔案的詳細的資訊，您可以使用威脅保護狀態報表。</span><span class="sxs-lookup"><span data-stu-id="92f7f-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="92f7f-110">在[Office 365 安全性&amp;合規性中心](https://protection.office.com)，選擇 [**報告**] \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="92f7f-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="92f7f-111">在報表的右上角，選擇 [**檢視詳細資料] 表格**。</span><span class="sxs-lookup"><span data-stu-id="92f7f-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="92f7f-112">檢視報表中偵測到的檔案的清單。</span><span class="sxs-lookup"><span data-stu-id="92f7f-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="92f7f-113">若要檢視的詳細的資訊，包括採取的動作、 檔案名稱、 檔案路徑，以及更多在清單中選取項目。</span><span class="sxs-lookup"><span data-stu-id="92f7f-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="92f7f-114">選擇 [**進階分析**] 索引標籤來檢視資訊，例如觀察到的行為與分析詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="92f7f-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="92f7f-115">檢視並採取檔案中的巨集指令，在隔離區中</span><span class="sxs-lookup"><span data-stu-id="92f7f-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="92f7f-116">在 Office 365 安全性&amp;合規性中心，選擇 [**威脅管理** \> **檢閱** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="92f7f-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="92f7f-117">在左上角，變更篩選從**電子郵件**到**內容**。</span><span class="sxs-lookup"><span data-stu-id="92f7f-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="92f7f-118">若要檢視的詳細的資訊，包括之檔案的 URL 清單中選取項目。</span><span class="sxs-lookup"><span data-stu-id="92f7f-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="92f7f-119">選擇 [可用的動作。</span><span class="sxs-lookup"><span data-stu-id="92f7f-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="92f7f-120">選擇 [**版本&amp;報表**解除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="92f7f-121">選取 [**傳送報告給 Microsoft**向 Microsoft 報告為誤判的檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="92f7f-122">選擇 [**檔案下載**調查進一步的檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="92f7f-123">選擇 [**刪除**] 以從隔離的項目清單中移除檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-123">Choose **Delete** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="92f7f-124">如果您選擇此選項，您也必須針對商務或 Microsoft Teams 刪除從其各自的文件庫中 SharePoint Online、 OneDrive 檔案。</span><span class="sxs-lookup"><span data-stu-id="92f7f-124">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="92f7f-125">此選項不會解除封鎖正在將檔案開啟或共用。</span><span class="sxs-lookup"><span data-stu-id="92f7f-125">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="92f7f-126">選擇 [**關閉**] 以關閉 [選取的項目詳細資料。</span><span class="sxs-lookup"><span data-stu-id="92f7f-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  

