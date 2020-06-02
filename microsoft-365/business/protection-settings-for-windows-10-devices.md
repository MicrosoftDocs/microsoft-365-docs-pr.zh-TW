---
title: 設定 Windows 10 裝置的應用程式保護設定
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 瞭解如何建立應用程式管理原則，以及保護使用者個人 Windows 10 裝置上的工作檔案。
ms.openlocfilehash: df10470c6bd7aad2f35700a267c4d24d949f569c
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470860"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="74603-103">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="74603-103">Set application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="74603-104">本文適用于 Microsoft 365 商務版 Premium。</span><span class="sxs-lookup"><span data-stu-id="74603-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="74603-105">建立適用於 Windows 10 的應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="74603-105">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="74603-106">如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。</span><span class="sxs-lookup"><span data-stu-id="74603-106">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="74603-107">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="74603-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="74603-108">在左側導覽中，選擇 [**裝置** \> **原則**] [ \> **新增**]。</span><span class="sxs-lookup"><span data-stu-id="74603-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="74603-109">在 [**新增原則**] 窗格中，輸入這個原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="74603-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="74603-110">在 [**原則類型**] 底下，選擇 [ **Windows 10 的應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="74603-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="74603-111">在 [**裝置類型**] 底下，選擇 [**個人**或**公司擁有**]。</span><span class="sxs-lookup"><span data-stu-id="74603-111">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="74603-112">**加密工作**檔案會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="74603-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="74603-113">如果您不想讓使用者將工作檔案儲存在其**電腦上**，請將 [**防止使用者將公司資料複製到個人檔案]，並強制使用者將工作檔案儲存至 OneDrive 的商務**檔案。</span><span class="sxs-lookup"><span data-stu-id="74603-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="74603-114">**在 Windows 裝置上展開復原資料**。</span><span class="sxs-lookup"><span data-stu-id="74603-114">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="74603-115">我們建議您**將其開啟**。</span><span class="sxs-lookup"><span data-stu-id="74603-115">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="74603-116">您必須先建立資料修復代理憑證，才能瀏覽至其位置。</span><span class="sxs-lookup"><span data-stu-id="74603-116">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="74603-117">如需相關指示，請參閱[建立及驗證加密檔案系統（EFS）資料復原代理程式（DRA）憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="74603-117">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="74603-118">根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。</span><span class="sxs-lookup"><span data-stu-id="74603-118">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="74603-119">只有該使用者可以開啟並解密該檔案。</span><span class="sxs-lookup"><span data-stu-id="74603-119">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="74603-120">不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。</span><span class="sxs-lookup"><span data-stu-id="74603-120">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="74603-121">系統管理員可以使用資料復原代理程式（DRA）憑證來解密檔案。</span><span class="sxs-lookup"><span data-stu-id="74603-121">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="74603-123">如果您想要新增其他網域或 SharePoint 線上位置，請展開 [**保護其他網路和雲端位置**]，以確保所有列出之應用程式中的檔案受到保護。</span><span class="sxs-lookup"><span data-stu-id="74603-123">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="74603-124">如果您需要為任何欄位輸入多個項目，請在每個項目之間插入分號 (;)。</span><span class="sxs-lookup"><span data-stu-id="74603-124">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="74603-126">下一步決定**誰將取得這些設定？**</span><span class="sxs-lookup"><span data-stu-id="74603-126">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="74603-127">如果您不想要使用預設的 [**所有使用者**] 安全性群組，請選擇 [**變更**]，然後選取將取得這些設定的安全性群組 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="74603-127">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="74603-128">最後，選擇 [**新增**] 以儲存原則，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="74603-128">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
