---
title: AutoPilot 裝置錯誤疑難排解
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何針對自動駕駛裝置檔案錯誤進行疑難排解。
ms.openlocfilehash: 88b59ec20ddda401c1dac45ff729ac38497a767e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074353"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="fb1ec-103">AutoPilot 裝置錯誤疑難排解</span><span class="sxs-lookup"><span data-stu-id="fb1ec-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="fb1ec-104">裝置檔案錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="fb1ec-104">Device file error messages</span></span>

<span data-ttu-id="fb1ec-105">在某些錯誤的以下資訊您可能會看到時使用 Microsoft 365 商務版中的自動駕駛裝置檔案。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="fb1ec-106">**錯誤碼**</span><span class="sxs-lookup"><span data-stu-id="fb1ec-106">**Error code**</span></span>|<span data-ttu-id="fb1ec-107">**若要嘗試修正**</span><span class="sxs-lookup"><span data-stu-id="fb1ec-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb1ec-108">無效的要求本體</span><span class="sxs-lookup"><span data-stu-id="fb1ec-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="fb1ec-109">應該很少，會發生此錯誤如果您看到這項錯誤，請再操作一次。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="fb1ec-110">裝置硬體雜湊值不正確。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="fb1ec-111">如果您看到這項錯誤，就表示您提供的一部裝置硬體雜湊 CSV 檔案中的值不正確。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="fb1ec-112">首先，確認已正確輸入值。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="fb1ec-113">如果您認為的值正確，但仍然發生此錯誤，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="fb1ec-114">指派給另一個租用戶的裝置</span><span class="sxs-lookup"><span data-stu-id="fb1ec-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="fb1ec-115">如果您看到這項錯誤，就表示您所提供的序號或產品金鑰的一或多個裝置 CSV 檔案中的值不正確。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="fb1ec-116">首先，確認已正確輸入值。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="fb1ec-117">如果您認為的值正確，但仍然發生此錯誤，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="fb1ec-118">CSV 檔案包含無效的序號或產品金鑰</span><span class="sxs-lookup"><span data-stu-id="fb1ec-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="fb1ec-119">如果您看到此錯誤表示是 tyring 註冊裝置已登錄的其他組織。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-119">If you see this error it means that the device you are tyring to register is already registered by an other organization.</span></span> <span data-ttu-id="fb1ec-120">若要修正此問題，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-120">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="fb1ec-121">使用 AutoPilot 設定不是支援此裝置</span><span class="sxs-lookup"><span data-stu-id="fb1ec-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="fb1ec-122">這個錯誤表示裝置不符合 AutoPilot 部署需求。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-122">This error means the device does not meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="fb1ec-123">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="fb1ec-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="fb1ec-124">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="fb1ec-125">新裝置尚未執行過 Windows 全新體驗設定。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="fb1ec-126">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="fb1ec-126">Device not found</span></span>  <br/> |<span data-ttu-id="fb1ec-127">這個錯誤表示，在您的 CSV 檔案中的一或多個裝置未登錄至您的組織。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-127">This error means that one or more devices in your CSV file is not registered to your organization.</span></span> <span data-ttu-id="fb1ec-128">若要修正此問題，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="fb1ec-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
