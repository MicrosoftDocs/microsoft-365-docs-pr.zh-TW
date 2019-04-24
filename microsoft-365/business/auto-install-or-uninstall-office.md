---
title: 在 Windows 10 裝置上自動安裝或解除安裝 Office
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: '安裝或解除安裝 Office，從 Microsoft 365 商務版系統管理中心的 Windows 10 裝置上。 '
ms.openlocfilehash: fef4a543aed489202bf05dfb1e8cafbb784ca819
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277260"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="6aed0-103">在 Windows 10 裝置上自動安裝或解除安裝 Office</span><span class="sxs-lookup"><span data-stu-id="6aed0-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="6aed0-104">您可以從 Microsoft 365 商務版系統管理中心快速且輕鬆地將 Office 安裝到 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="6aed0-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="6aed0-105">若要了解如何透過這種方式安裝 Office App，請參閱[準備 Office 用戶端安裝](prepare-for-office-client-deployment.md)再開始進行。</span><span class="sxs-lookup"><span data-stu-id="6aed0-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="6aed0-106">管理 Office 部署</span><span class="sxs-lookup"><span data-stu-id="6aed0-106">Manage Office deployments</span></span>

1. <span data-ttu-id="6aed0-107">使用全域系統管理員認證登入[系統管理中心](https://aka.ms/bcsportal)。</span><span class="sxs-lookup"><span data-stu-id="6aed0-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="6aed0-108">在 [**裝置**] 卡片中，選擇 [**管理 Office 部署**]。</span><span class="sxs-lookup"><span data-stu-id="6aed0-108">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="6aed0-109">如果您沒有看見 [**裝置動作**] 卡片，在系統管理中心**主**頁面中，按一下 [**新增]** （+） 將其新增至您的系統管理首頁。</span><span class="sxs-lookup"><span data-stu-id="6aed0-109">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="6aed0-111">在開啟 [**管理 Office 部署**] 窗格中，選擇 [**加入群組**]，然後選取您想要使用的群組。</span><span class="sxs-lookup"><span data-stu-id="6aed0-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="6aed0-112">新增您要使用的群組之後從**部署動作**下拉式清單，選取 [**安裝 Office 儘速**或**解除安裝 Office**。</span><span class="sxs-lookup"><span data-stu-id="6aed0-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="6aed0-114">選擇 [**下一步**\>檢閱設定，然後選擇 [ **Confirm**。</span><span class="sxs-lookup"><span data-stu-id="6aed0-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="6aed0-115">系統會在您所用群組指定之使用者擁有的裝置中自動安裝或解除安裝 32 位元的 Office。</span><span class="sxs-lookup"><span data-stu-id="6aed0-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="6aed0-116">若要驗證，您可在要安裝 Office 的選取電腦上開啟 [工作管理員]，然後尋找 Microsoft Office 隨選即用程序。</span><span class="sxs-lookup"><span data-stu-id="6aed0-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


