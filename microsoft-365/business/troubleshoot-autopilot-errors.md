---
title: 針對自動駕駛裝置錯誤進行疑難排解
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何疑難排解自動駕駛儀上裝置檔案錯誤。
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866299"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="5cfb2-103">針對自動駕駛裝置錯誤進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="5cfb2-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="5cfb2-104">裝置檔案錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="5cfb2-104">Device file error messages</span></span>

<span data-ttu-id="5cfb2-105">以下資訊之錯誤的一些您可能會看到時使用 Microsoft 365 Business 中的自動駕駛儀上裝置檔案。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="5cfb2-106">**錯誤碼**</span><span class="sxs-lookup"><span data-stu-id="5cfb2-106">**Error code**</span></span>|<span data-ttu-id="5cfb2-107">**若要嘗試修復**</span><span class="sxs-lookup"><span data-stu-id="5cfb2-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5cfb2-108">無效的要求主體</span><span class="sxs-lookup"><span data-stu-id="5cfb2-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="5cfb2-109">此錯誤發生少，如果您看到此錯誤，請嘗試操作一次。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="5cfb2-110">裝置硬體雜湊值不正確。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="5cfb2-p101">如果您看到此錯誤，就表示您提供一個裝置硬體雜湊您 CSV 檔案中的值不正確。首先，確認已正確輸入值。如果您認為的值是正確的但仍發生此錯誤，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="5cfb2-114">指派給另一個承租人的裝置</span><span class="sxs-lookup"><span data-stu-id="5cfb2-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="5cfb2-p102">如果您看到此錯誤，就表示您 CSV 檔案中提供的序號或一或多個裝置的產品金鑰的值不正確。首先，確認已正確輸入值。如果您認為的值是正確的但仍發生此錯誤，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="5cfb2-118">CSV 檔案包含無效的序號或產品金鑰</span><span class="sxs-lookup"><span data-stu-id="5cfb2-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="5cfb2-p103">如果您看到此錯誤用意是註冊 tyring 裝置已經註冊其他組織所。若要修正此問題，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="5cfb2-121">使用自動駕駛儀上安裝程式不是支援此裝置</span><span class="sxs-lookup"><span data-stu-id="5cfb2-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="5cfb2-p104">此錯誤表示裝置不符合自動駕駛儀上部署需求。裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="5cfb2-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="5cfb2-124">Windows 10 版本 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="5cfb2-125">新裝置尚未執行過 Windows 全新體驗設定。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="5cfb2-126">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="5cfb2-126">Device not found</span></span>  <br/> |<span data-ttu-id="5cfb2-p105">此錯誤表示 CSV 檔案中的一或多個裝置未註冊於您的組織。若要修正此問題，請將您的硬體廠商尋求協助。</span><span class="sxs-lookup"><span data-stu-id="5cfb2-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
