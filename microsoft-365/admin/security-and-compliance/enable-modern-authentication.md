---
title: 為 Windows 裝置上的 Office 2013 啟用新式驗證
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 瞭解如何設定登錄機碼，以便為已安裝 Microsoft Office 2013 的裝置啟用新式驗證。
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779962"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="6d953-103">為 Windows 裝置上的 Office 2013 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="6d953-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="6d953-104">若要為已安裝 Office 2013 的任何 Windows 裝置啟用新式驗證，您必須先設定專用登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="6d953-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="6d953-105">為 Office 2013 用戶端啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="6d953-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="6d953-106">Office 2016 用戶端已啟用新式驗證，您無需為 Office 2016 設定登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="6d953-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="6d953-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span><span class="sxs-lookup"><span data-stu-id="6d953-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span></span> <span data-ttu-id="6d953-108">The keys have to be set on each device that you want to enable for modern authentication:</span><span class="sxs-lookup"><span data-stu-id="6d953-108">The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="6d953-109">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="6d953-109">**Registry key**</span></span>|<span data-ttu-id="6d953-110">**類型**</span><span class="sxs-lookup"><span data-stu-id="6d953-110">**Type**</span></span>|<span data-ttu-id="6d953-111">**Value**</span><span class="sxs-lookup"><span data-stu-id="6d953-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="6d953-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="6d953-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="6d953-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="6d953-113">REG_DWORD</span></span>  |<span data-ttu-id="6d953-114">1 </span><span class="sxs-lookup"><span data-stu-id="6d953-114">1</span></span>  |
|<span data-ttu-id="6d953-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="6d953-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="6d953-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="6d953-116">REG_DWORD</span></span> |<span data-ttu-id="6d953-117">1 </span><span class="sxs-lookup"><span data-stu-id="6d953-117">1</span></span> |
   
<span data-ttu-id="6d953-118">設定登錄機碼之後，您可以將 Office 2013 裝置應用程式設定為使用[多重要素驗證（MFA）](set-up-multi-factor-authentication.md)與 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6d953-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="6d953-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span><span class="sxs-lookup"><span data-stu-id="6d953-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span></span> <span data-ttu-id="6d953-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span><span class="sxs-lookup"><span data-stu-id="6d953-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="6d953-121">停用裝置上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="6d953-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="6d953-122">若要停用裝置上的新式驗證，請在裝置上設定下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="6d953-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="6d953-123">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="6d953-123">**Registry key**</span></span>|<span data-ttu-id="6d953-124">**類型**</span><span class="sxs-lookup"><span data-stu-id="6d953-124">**Type**</span></span>|<span data-ttu-id="6d953-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="6d953-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="6d953-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="6d953-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="6d953-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="6d953-127">REG_DWORD</span></span>|<span data-ttu-id="6d953-128">0</span><span class="sxs-lookup"><span data-stu-id="6d953-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="6d953-129">相關文章</span><span class="sxs-lookup"><span data-stu-id="6d953-129">Related articles</span></span>
[<span data-ttu-id="6d953-130">使用第二種驗證方式登入 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6d953-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

