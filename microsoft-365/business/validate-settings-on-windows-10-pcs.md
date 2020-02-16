---
title: 驗證 Windows 10 PC 上的 App 保護設定
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何驗證 Windows 10 裝置上的 Microsoft 365 商務版應用程式保護設定。
ms.openlocfilehash: 1762382aec00a80e006cf38b66c28d02c0c25989
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42056632"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="9bc0d-103">驗證 Windows 10 電腦上的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="9bc0d-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="9bc0d-104">請確認已設定 Windows 10 裝置原則</span><span class="sxs-lookup"><span data-stu-id="9bc0d-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="9bc0d-105">之後您[設定裝置原則](protection-settings-for-windows-10-pcs.md)，可能會佔用的原則至使用者的裝置上生效的幾個小時。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="9bc0d-106">您可以確認原則所需的效果，來查看使用者的裝置上的各種 Windows 設定畫面。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="9bc0d-107">因為使用者無法修改其 Windows 10 裝置上的 Windows 更新] 和 [Windows Defender 防毒軟體設定，有許多選項將會變為灰色。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="9bc0d-108">移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **重新啟動選項**，並確認所有設定呈現都灰色。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![重新啟動的所有選項會都變為灰色。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="9bc0d-110">移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項]** ，並確認所有設定呈現都灰色。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Advanced 更新選項所有會變為灰色。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="9bc0d-112">移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項** \> **選擇更新傳送的方式**。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="9bc0d-113">確認您可以看到的訊息 （以紅色），某些設定都是隱藏或受管理的組織，並且會變為灰色，所有選項。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![選擇 [更新傳送的方式設定都是隱藏或由組織管理] 頁面上會指示。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="9bc0d-115">若要開啟 [Windows Defender 資訊安全中心，移至 [**設定** \> **更新&amp;安全性** \> **Windows Defender** \>按一下 [**開啟 Windows defender 資訊安全中心** \> **病毒&amp;執行緒保護** \> **病毒&amp;威脅保護設定**。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="9bc0d-116">確認所有選項呈現都灰色。</span><span class="sxs-lookup"><span data-stu-id="9bc0d-116">Verify that all options are grayed out.</span></span> 
    
    ![病毒和威脅保護設定會變為灰色。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="9bc0d-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="9bc0d-118">Related Topics</span></span>

[<span data-ttu-id="9bc0d-119">Microsoft 365 商務版文件和資源</span><span class="sxs-lookup"><span data-stu-id="9bc0d-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="9bc0d-120">開始使用 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9bc0d-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="9bc0d-121">管理 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9bc0d-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="9bc0d-122">設定適用於 Windows 10 電腦的裝置設定</span><span class="sxs-lookup"><span data-stu-id="9bc0d-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

