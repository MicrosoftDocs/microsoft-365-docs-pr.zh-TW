---
title: 為 Windows 裝置上的 Office 2013 啟用新式驗證
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 瞭解如何設定登錄機碼，以便為已安裝 Microsoft Office 2013 的裝置啟用新式驗證。
ms.openlocfilehash: 8bfe515fefed9d58f140a67e53ce0d078457aa72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393652"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="ae0ed-103">為 Windows 裝置上的 Office 2013 啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="ae0ed-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="ae0ed-104">若要為已安裝 Office 2013 的任何 Windows 裝置啟用新式驗證，您必須先設定專用登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ae0ed-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="ae0ed-105">為 Office 2013 用戶端啟用新式驗證</span><span class="sxs-lookup"><span data-stu-id="ae0ed-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="ae0ed-106">Office 2016 用戶端已啟用新式驗證，您無需為 Office 2016 設定登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ae0ed-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="ae0ed-p101">若要針對已安裝 Microsoft Office 2013、且執行 Windows 的任何裝置啟用新式驗證 (比如膝上型電腦和平板電腦)，您必須先設定下列登錄機碼。您必須在每部要啟用新式驗證的裝置上設定機碼：</span><span class="sxs-lookup"><span data-stu-id="ae0ed-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="ae0ed-109">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-109">**Registry key**</span></span>|<span data-ttu-id="ae0ed-110">**類型**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-110">**Type**</span></span>|<span data-ttu-id="ae0ed-111">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="ae0ed-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="ae0ed-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="ae0ed-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ae0ed-113">REG_DWORD</span></span>  |<span data-ttu-id="ae0ed-114">1 </span><span class="sxs-lookup"><span data-stu-id="ae0ed-114">1</span></span>  |
|<span data-ttu-id="ae0ed-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="ae0ed-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="ae0ed-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ae0ed-116">REG_DWORD</span></span> |<span data-ttu-id="ae0ed-117">1 </span><span class="sxs-lookup"><span data-stu-id="ae0ed-117">1</span></span> |
   
<span data-ttu-id="ae0ed-118">設定登錄機碼之後，您可以設定 Office 2013 裝置應用程式使用[多重要素驗證 (MFA) ](set-up-multi-factor-authentication.md)搭配 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ae0ed-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="ae0ed-p102">如果您目前使用任何用戶端 App 登入，您就必須在登出後再次登入，變更才會生效。否則，在 ADAL 識別建立之前，您將無法使用 MRU 和漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="ae0ed-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="ae0ed-121">停用裝置上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="ae0ed-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="ae0ed-122">若要停用裝置上的新式驗證，請在裝置上設定下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="ae0ed-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="ae0ed-123">**登錄機碼**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-123">**Registry key**</span></span>|<span data-ttu-id="ae0ed-124">**類型**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-124">**Type**</span></span>|<span data-ttu-id="ae0ed-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae0ed-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="ae0ed-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="ae0ed-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="ae0ed-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ae0ed-127">REG_DWORD</span></span>|<span data-ttu-id="ae0ed-128">0</span><span class="sxs-lookup"><span data-stu-id="ae0ed-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="ae0ed-129">相關內容</span><span class="sxs-lookup"><span data-stu-id="ae0ed-129">Related content</span></span>

<span data-ttu-id="ae0ed-130">[使用第二個驗證方法登入 Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (文章) </span><span class="sxs-lookup"><span data-stu-id="ae0ed-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>\
<span data-ttu-id="ae0ed-131">[Outlook 提示密碼，但不使用新式驗證連線至 Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (文章) </span><span class="sxs-lookup"><span data-stu-id="ae0ed-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

