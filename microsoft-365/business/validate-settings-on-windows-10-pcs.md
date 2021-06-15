---
title: 驗證 Windows 10 電腦的應用程式保護設定
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 瞭解如何驗證商務應用程式保護設定的 Microsoft 365 是否會在使用者的 Windows 10 裝置上生效。
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925252"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="66da2-103">驗證 Windows 10 電腦的裝置保護設定</span><span class="sxs-lookup"><span data-stu-id="66da2-103">Validate device protection settings for Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="66da2-104">確認已設定 Windows 10 裝置原則</span><span class="sxs-lookup"><span data-stu-id="66da2-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="66da2-105">[設定裝置原則](protection-settings-for-windows-10-pcs.md)之後，可能需要數小時的時間，才能讓原則在使用者的裝置上生效。</span><span class="sxs-lookup"><span data-stu-id="66da2-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="66da2-106">您可以在使用者的裝置上查看各種 Windows 設定螢幕，以確認原則是否生效。</span><span class="sxs-lookup"><span data-stu-id="66da2-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="66da2-107">因為使用者無法修改其 Windows 10 裝置上的 Windows 更新及 Windows Defender 防毒軟體設定，所以許多選項會變暗。</span><span class="sxs-lookup"><span data-stu-id="66da2-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="66da2-108">移至 **設定** \> **更新 &amp; 安全性** \> **Windows 更新** \> **重新開機選項**，並確認所有設定均呈現灰色。</span><span class="sxs-lookup"><span data-stu-id="66da2-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![所有重新開機選項都是灰色的。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="66da2-110">移至 **設定** \> **更新 &amp; 安全性** \> **Windows 更新** \> **高級選項**，並確認所有設定均呈現灰色。</span><span class="sxs-lookup"><span data-stu-id="66da2-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows[高級更新] 選項都是灰色的。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="66da2-112">移至 **設定** \> **更新 &amp; 安全性** \> **Windows 更新** \> [**高級選項**] \> **選擇如何傳送更新**。</span><span class="sxs-lookup"><span data-stu-id="66da2-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="66da2-113">請確認您可以看到郵件 (以紅色) 某些設定已隱藏或由您的組織管理，而且所有選項均呈現灰色。</span><span class="sxs-lookup"><span data-stu-id="66da2-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![選擇如何傳送更新頁面表示設定已隱藏或由您的組織管理。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="66da2-115">若要開啟 Windows Defender 的安全性中心，請移至 **設定** \> **更新 &amp; 安全性** \> **Windows Defender** \> 按一下 [**開啟 Windows Defender 安全性中心** \> **病毒 &amp; 執行緒防護** \> **病毒 &amp; 防護設定**]。</span><span class="sxs-lookup"><span data-stu-id="66da2-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="66da2-116">確認所有選項均呈現灰色。</span><span class="sxs-lookup"><span data-stu-id="66da2-116">Verify that all options are grayed out.</span></span> 
    
    ![[病毒和威脅防護] 設定會變暗。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="66da2-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="66da2-118">Related Topics</span></span>

[<span data-ttu-id="66da2-119">商務檔和資源的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="66da2-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="66da2-120">開始使用商務 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="66da2-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="66da2-121">管理商務 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="66da2-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="66da2-122">設定適用於 Windows 10 電腦的裝置設定</span><span class="sxs-lookup"><span data-stu-id="66da2-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
