---
title: 設定 Windows 10 裝置的應用程式保護設定
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何建立的應用程式管理原則，以及保護 Windows 10 裝置上的工作檔案。
ms.openlocfilehash: 670184a2e81721fb5cc063e854822e9b271164d9
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074603"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="5d829-103">設定 Windows 10 裝置的應用程式保護設定</span><span class="sxs-lookup"><span data-stu-id="5d829-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="5d829-104">建立適用於 Windows 10 的應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="5d829-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="5d829-105">如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。</span><span class="sxs-lookup"><span data-stu-id="5d829-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="5d829-106">移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="5d829-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="5d829-107">在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。</span><span class="sxs-lookup"><span data-stu-id="5d829-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="5d829-108">在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="5d829-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="5d829-109">[**原則類型**] 下選擇 [**用於 Windows 10 應用程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="5d829-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="5d829-110">[**裝置類型**] 下選擇 [**個人**或**公司所擁有**]。</span><span class="sxs-lookup"><span data-stu-id="5d829-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="5d829-111">**加密工作檔案**會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="5d829-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="5d829-112">**防止使用者複製到個人檔案的公司資料並強制他們將工作將檔案儲存到商務用 OneDrive**如果設定為**在**您不想要在其電腦上的工作檔案儲存的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d829-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="5d829-113">依序展開 [**修復 Windows 裝置上的資料**，並建議，您將它**開啟**。</span><span class="sxs-lookup"><span data-stu-id="5d829-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="5d829-p101">您必須先建立資料修復代理憑證，才能瀏覽至其位置。如需相關指示，請參閱[建立並驗證加密檔案系統 (EFS) 資料修復代理 (DRA) 憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。</span><span class="sxs-lookup"><span data-stu-id="5d829-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="5d829-p102">根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。只有該使用者可以開啟並解密該檔案。不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。系統管理員可以使用資料修復代理程式 (DRA) 憑證來解密該檔案。</span><span class="sxs-lookup"><span data-stu-id="5d829-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="5d829-121">如果您想要新增其他網域或 SharePoint Online 的位置，以確保所有列出的應用程式中的檔案會受到保護，請展開 [**保護其他網路及雲端位置**]。</span><span class="sxs-lookup"><span data-stu-id="5d829-121">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected.</span></span> <span data-ttu-id="5d829-122">如果您需要為任何欄位輸入多個項目，請在每個項目之間插入分號 (;)。</span><span class="sxs-lookup"><span data-stu-id="5d829-122">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="5d829-124">下一步] 決定**人員會收到這些設定？**</span><span class="sxs-lookup"><span data-stu-id="5d829-124">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="5d829-125">如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。</span><span class="sxs-lookup"><span data-stu-id="5d829-125">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="5d829-126">最後，選擇 [**新增]** 以儲存原則，並將它指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="5d829-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 