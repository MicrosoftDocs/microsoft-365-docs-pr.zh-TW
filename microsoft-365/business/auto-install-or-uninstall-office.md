---
title: 在 Windows 10 裝置上自動安裝或解除安裝 Office
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: '安裝或解除安裝 Office 從 Microsoft 365 商務系統管理中心的 Windows 10 裝置上。 '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866547"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="a3fbb-103">在 Windows 10 裝置上自動安裝或解除安裝 Office</span><span class="sxs-lookup"><span data-stu-id="a3fbb-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="a3fbb-104">您可以從 Microsoft 365 商務版系統管理中心快速且輕鬆地將 Office 安裝到 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="a3fbb-105">若要了解如何透過這種方式安裝 Office App，請參閱[準備 Office 用戶端安裝](prepare-for-office-client-deployment.md)再開始進行。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="a3fbb-106">管理 Office 部署</span><span class="sxs-lookup"><span data-stu-id="a3fbb-106">Manage Office deployments</span></span>

1. <span data-ttu-id="a3fbb-107">使用全域系統管理員認證登入[系統管理中心](https://aka.ms/bcsportal)。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="a3fbb-p101">在**裝置**卡片、 選擇 [**管理 Office 的部署**。   如果沒有看到**裝置動作**卡片、 在 admin center**首頁**] 頁面上，按一下 [**新增]** （+） 將它新增至您的系統管理首頁。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-p101">On the **Devices** card, choose **Manage Office Deployment**.    If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="a3fbb-111">在開啟 [**管理 Office 部署**] 窗格中，選擇 [**新增群組**]，然後選取您要使用的群組。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="a3fbb-112">新增您要使用的群組身分後從**部署後動作**下拉式清單，選取 [**盡安裝 Office**或**解除安裝 Office**。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="a3fbb-114">選擇 [**下一步**\>檢閱設定，然後選擇 [**確認**。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="a3fbb-115">系統會在您所用群組指定之使用者擁有的裝置中自動安裝或解除安裝 32 位元的 Office。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="a3fbb-116">若要驗證，您可在要安裝 Office 的選取電腦上開啟 [工作管理員]，然後尋找 Microsoft Office 隨選即用程序。</span><span class="sxs-lookup"><span data-stu-id="a3fbb-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


