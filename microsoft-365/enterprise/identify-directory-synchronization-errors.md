---
title: 在 Microsoft 365 中查看目錄同步處理錯誤
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: 瞭解如何在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤及可能的修正。
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907501"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="c65fb-103">在 Microsoft 365 中查看目錄同步處理錯誤</span><span class="sxs-lookup"><span data-stu-id="c65fb-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="c65fb-104">您可以在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="c65fb-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c65fb-105">只會顯示使用者物件錯誤。</span><span class="sxs-lookup"><span data-stu-id="c65fb-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="c65fb-106">若要使用 PowerShell 查看錯誤，請參閱 [使用 DirSyncProvisioningErrors 識別物件](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)。</span><span class="sxs-lookup"><span data-stu-id="c65fb-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c65fb-107">在 Microsoft 365 系統管理中心中查看目錄同步處理錯誤</span><span class="sxs-lookup"><span data-stu-id="c65fb-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="c65fb-108">若要在 Microsoft 365 系統管理中心中查看任何錯誤：</span><span class="sxs-lookup"><span data-stu-id="c65fb-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="c65fb-109">使用全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="c65fb-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="c65fb-110">在 **首頁** 上，您會看到 [ **使用者管理** 卡]。</span><span class="sxs-lookup"><span data-stu-id="c65fb-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Microsoft 365 系統管理中心中的使用者管理卡](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="c65fb-112">在卡片上，選擇 [ **AZURE AD Connect]** 底下的 [**同步處理錯誤**]，以查看 [**目錄同步處理錯誤**] 頁面上的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c65fb-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![「目錄同步處理錯誤」頁面的範例](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="c65fb-114">選擇任何錯誤以顯示詳細資料窗格，顯示有關錯誤的資訊，以及如何修正該錯誤的秘訣。</span><span class="sxs-lookup"><span data-stu-id="c65fb-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![目錄同步處理錯誤詳細資料的範例](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="c65fb-116">查看之後，請參閱 [修正 Microsoft 365 目錄同步處理的問題](fix-problems-with-directory-synchronization.md) ，修正任何已識別的問題。</span><span class="sxs-lookup"><span data-stu-id="c65fb-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>