---
title: AutoPilot 裝置錯誤疑難排解
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 瞭解如何疑難排解在使用 Microsoft 365 商務版 Premium 中的 AutoPilot 裝置檔案時，可能會看到的錯誤。
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578080"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="b8d76-103">AutoPilot 裝置錯誤疑難排解</span><span class="sxs-lookup"><span data-stu-id="b8d76-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="b8d76-104">裝置檔錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="b8d76-104">Device file error messages</span></span>

<span data-ttu-id="b8d76-105">以下是在使用 Microsoft 365 商務版 Premium 中的 AutoPilot 裝置檔案時，可能會看到的一些錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b8d76-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="b8d76-106">**錯誤碼**</span><span class="sxs-lookup"><span data-stu-id="b8d76-106">**Error code**</span></span>|<span data-ttu-id="b8d76-107">**修正以嘗試**</span><span class="sxs-lookup"><span data-stu-id="b8d76-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8d76-108">不正確要求體</span><span class="sxs-lookup"><span data-stu-id="b8d76-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="b8d76-109">這種錯誤應該很少發生，如果您看到此錯誤，請重試此作業。</span><span class="sxs-lookup"><span data-stu-id="b8d76-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="b8d76-110">裝置的硬體雜湊值不正確。</span><span class="sxs-lookup"><span data-stu-id="b8d76-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="b8d76-111">如果您看到此錯誤，表示您在 CSV 檔案中為一個裝置的硬體雜湊所提供的值不正確。</span><span class="sxs-lookup"><span data-stu-id="b8d76-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="b8d76-112">首先，請確認輸入的值正確。</span><span class="sxs-lookup"><span data-stu-id="b8d76-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="b8d76-113">如果您認為此值是正確的，但是此錯誤仍會發生，請向您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="b8d76-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b8d76-114">指派給其他租使用者的裝置</span><span class="sxs-lookup"><span data-stu-id="b8d76-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="b8d76-115">如果您看到此錯誤，表示您在 CSV 檔案中所提供的數值是一或多個裝置的序號碼或產品金鑰不正確。</span><span class="sxs-lookup"><span data-stu-id="b8d76-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="b8d76-116">首先，請確認輸入的值正確。</span><span class="sxs-lookup"><span data-stu-id="b8d76-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="b8d76-117">如果您認為此值是正確的，但是此錯誤仍會發生，請向您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="b8d76-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b8d76-118">CSV 檔案包含不正確序號碼或產品金鑰</span><span class="sxs-lookup"><span data-stu-id="b8d76-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="b8d76-119">如果您看到此錯誤，表示您嘗試註冊的裝置已由另一個組織註冊。</span><span class="sxs-lookup"><span data-stu-id="b8d76-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="b8d76-120">若要修正此錯誤，請向您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="b8d76-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b8d76-121">此裝置不支援使用 AutoPilot 設定</span><span class="sxs-lookup"><span data-stu-id="b8d76-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="b8d76-122">此錯誤表示裝置不符合 AutoPilot 部署需求。</span><span class="sxs-lookup"><span data-stu-id="b8d76-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="b8d76-123">裝置必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="b8d76-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="b8d76-124">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b8d76-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="b8d76-125">尚未透過 Windows 全新體驗的新裝置。</span><span class="sxs-lookup"><span data-stu-id="b8d76-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="b8d76-126">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="b8d76-126">Device not found</span></span>  <br/> |<span data-ttu-id="b8d76-127">此錯誤表示您的 CSV 檔案中的一或多個裝置並未註冊至您的組織。</span><span class="sxs-lookup"><span data-stu-id="b8d76-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="b8d76-128">若要修正此問題，請向您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="b8d76-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
