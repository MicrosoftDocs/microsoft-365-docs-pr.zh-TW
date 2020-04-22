---
title: 檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
description: 深入瞭解在 SharePoint、OneDrive 或小組中偵測到之惡意檔案的相關資訊，以及如何對這些檔案採取動作。
ms.openlocfilehash: 95f497c5be16d1ba1d4fa9fc57f0dd9650450414
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635397"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="e33ba-103">檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊</span><span class="sxs-lookup"><span data-stu-id="e33ba-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="e33ba-104">[SharePoint、OneDrive 和 Microsoft 團隊的 Office 365 ATP](atp-for-spo-odb-and-teams.md) ，可保護您的組織，避免文件庫和小組網站中的惡意檔。</span><span class="sxs-lookup"><span data-stu-id="e33ba-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="e33ba-105">偵測到惡意檔案時，該檔案會遭到封鎖，因此在組織的安全性小組採取進一步動作之前，任何人都無法開啟、複製、移動或共用該檔案。</span><span class="sxs-lookup"><span data-stu-id="e33ba-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="e33ba-106">請閱讀本文以瞭解如何查看偵測到檔案的相關資訊，以及要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="e33ba-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="e33ba-107">為了執行本文所述的工作，您必須具備[安全性&amp;與合規性中心](permissions-in-the-security-and-compliance-center.md)的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="e33ba-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="e33ba-108">以偵測到的檔案的相關資訊來查看報告</span><span class="sxs-lookup"><span data-stu-id="e33ba-108">View reports with information about detected files</span></span>

<span data-ttu-id="e33ba-109">若要查看 Office 365 ATP 所偵測到之檔案的狀態和詳細資訊，您可以使用威脅防護狀態報表。</span><span class="sxs-lookup"><span data-stu-id="e33ba-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="e33ba-110">在 [[安全性&amp;與合規性中心](https://protection.office.com)] 中，選擇 [**報告** \> ]**儀表板** \> **威脅防護狀態**。</span><span class="sxs-lookup"><span data-stu-id="e33ba-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="e33ba-111">在報表的右上角，選擇 [ **View details table**]。</span><span class="sxs-lookup"><span data-stu-id="e33ba-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="e33ba-112">查看報告中偵測到的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="e33ba-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="e33ba-113">選取清單中的專案，以查看詳細資訊，包括採取的動作、檔案名、檔路徑等等。</span><span class="sxs-lookup"><span data-stu-id="e33ba-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="e33ba-114">選擇 [**高級分析**] 索引標籤，以查看資訊，例如觀察行為和分析詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e33ba-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="e33ba-115">針對隔離區中的檔案，查看並採取動作</span><span class="sxs-lookup"><span data-stu-id="e33ba-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="e33ba-116">在 [安全性&amp;與合規性中心] 中，選擇 [**威脅管理** \> **檢查** \> **隔離區**]。</span><span class="sxs-lookup"><span data-stu-id="e33ba-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="e33ba-117">（您也可以直接前往[https://protection.office.com/quarantine](https://protection.office.com/quarantine)。）</span><span class="sxs-lookup"><span data-stu-id="e33ba-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="e33ba-118">在左上角，將**電子郵件**的下拉式功能表**變更為檔案**。</span><span class="sxs-lookup"><span data-stu-id="e33ba-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="e33ba-119">如果結果清單中包含太多專案，請使用**篩選**功能縮小選取範圍。</span><span class="sxs-lookup"><span data-stu-id="e33ba-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="e33ba-120">選取清單中的專案，以查看詳細資訊，包括檔案的 URL。</span><span class="sxs-lookup"><span data-stu-id="e33ba-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="e33ba-121">選擇可用的動作。</span><span class="sxs-lookup"><span data-stu-id="e33ba-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="e33ba-122">選擇 [**發行**檔案] 以解除封鎖檔。</span><span class="sxs-lookup"><span data-stu-id="e33ba-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="e33ba-123">選取 [**傳送報告給 microsoft** ]，將檔案報告為對 microsoft 的 false 陽性。</span><span class="sxs-lookup"><span data-stu-id="e33ba-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="e33ba-124">選擇 [**下載**檔案] 以進一步調查檔案。</span><span class="sxs-lookup"><span data-stu-id="e33ba-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="e33ba-125">選擇 [**從隔離區移除**]，以從隔離的專案清單中移除檔案。</span><span class="sxs-lookup"><span data-stu-id="e33ba-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="e33ba-126">如果您選擇此選項，您也必須在 SharePoint Online、商務用 OneDrive 或 Microsoft 小組中，從各自的文件庫中刪除檔案。</span><span class="sxs-lookup"><span data-stu-id="e33ba-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e33ba-127">此選項不會解除封鎖檔的開啟或共用。</span><span class="sxs-lookup"><span data-stu-id="e33ba-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="e33ba-128">選擇 [**關閉**]，關閉所選取專案的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e33ba-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

