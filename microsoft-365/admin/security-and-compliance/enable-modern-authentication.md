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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 瞭解如何設定登錄機號，以針對已安裝 Microsoft Office 2013 的裝置啟用新式驗證。
ms.openlocfilehash: 34078291fa237b63c391a7e90ba06ea0085c37cb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926555"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="b4012-103">為 Windows 裝置上的 Office 2013 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="b4012-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="b4012-104">若要為已安裝 Office 2013 的任何 Windows 裝置啟用新式驗證，您必須先設定專用登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="b4012-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="b4012-105">為 Office 2013 用戶端啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="b4012-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="b4012-106">Office 2016 用戶端已啟用新式驗證，您無需為 Office 2016 設定登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="b4012-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="b4012-p101">若要針對已安裝 Microsoft Office 2013、且執行 Windows 的任何裝置啟用新式驗證 (比如膝上型電腦和平板電腦)，您必須先設定下列登錄機碼。您必須在每部要啟用新式驗證的裝置上設定機碼：</span><span class="sxs-lookup"><span data-stu-id="b4012-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="b4012-109">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="b4012-109">**Registry key**</span></span>|<span data-ttu-id="b4012-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4012-110">**Type**</span></span>|<span data-ttu-id="b4012-111">**Value**</span><span class="sxs-lookup"><span data-stu-id="b4012-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="b4012-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="b4012-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="b4012-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="b4012-113">REG_DWORD</span></span>  |<span data-ttu-id="b4012-114">1 </span><span class="sxs-lookup"><span data-stu-id="b4012-114">1</span></span>  |
|<span data-ttu-id="b4012-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="b4012-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="b4012-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="b4012-116">REG_DWORD</span></span> |<span data-ttu-id="b4012-117">1 </span><span class="sxs-lookup"><span data-stu-id="b4012-117">1</span></span> |
   
<span data-ttu-id="b4012-118">設定好登錄機鍵後，您可以設定 Office 2013 裝置 App 使用多重要素驗證 [ (MFA ](set-up-multi-factor-authentication.md)) Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b4012-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="b4012-p102">如果您目前使用任何用戶端 App 登入，您就必須在登出後再次登入，變更才會生效。否則，在 ADAL 識別建立之前，您將無法使用 MRU 和漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="b4012-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="b4012-121">停用裝置上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="b4012-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="b4012-122">若要停用裝置上的新式驗證，請在裝置上設定下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="b4012-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="b4012-123">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="b4012-123">**Registry key**</span></span>|<span data-ttu-id="b4012-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="b4012-124">**Type**</span></span>|<span data-ttu-id="b4012-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="b4012-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="b4012-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="b4012-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="b4012-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="b4012-127">REG_DWORD</span></span>|<span data-ttu-id="b4012-128">0</span><span class="sxs-lookup"><span data-stu-id="b4012-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="b4012-129">相關文章</span><span class="sxs-lookup"><span data-stu-id="b4012-129">Related articles</span></span>
[<span data-ttu-id="b4012-130">使用第二種驗證方式登入 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b4012-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

