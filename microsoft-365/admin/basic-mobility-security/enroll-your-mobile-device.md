---
title: 使用基本行動性和安全性註冊行動裝置
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- MET150
description: 在您可以將 Microsoft 365 服務與裝置搭配使用之前，您可能需要先在 Microsoft 365 的基本行動和安全性中註冊。
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430117"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="f01a1-103">使用基本行動性和安全性註冊行動裝置</span><span class="sxs-lookup"><span data-stu-id="f01a1-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="f01a1-104">使用您的電話、平板電腦及其他行動裝置進行工作是一種很好的方式，可讓您在離開辦公室時及時瞭解及處理商務專案。</span><span class="sxs-lookup"><span data-stu-id="f01a1-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="f01a1-105">您可能需要先使用 microsoft Intune 公司入口網站，在 Microsoft 365 的基本行動性和安全性中註冊，您才能使用 Microsoft 365 服務與您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f01a1-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="f01a1-106">組織選擇基本行動性和安全性，讓員工可以使用其行動裝置，在企業安全地存取工作電子郵件、行事曆及檔時，保證重要資料的安全性，並符合法規遵從性需求。</span><span class="sxs-lookup"><span data-stu-id="f01a1-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="f01a1-107">若要深入瞭解，請參閱 [Microsoft 365 的基本行動及安全性概述](overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="f01a1-108">如需詳細資訊，請參閱我的 [組織可以在註冊裝置時看到哪些資訊？](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="f01a1-109">當您在 Microsoft 365 的基本行動及安全性註冊裝置時，您可能需要設定密碼，並允許您的工作組織使用此選項來清除裝置。</span><span class="sxs-lookup"><span data-stu-id="f01a1-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="f01a1-110">裝置擦除可以從 Microsoft 365 系統管理中心執行，例如，如果密碼輸入錯誤的次數不正確或使用期限中斷，則移除裝置中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="f01a1-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="f01a1-111">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="f01a1-111">Supported devices</span></span>

<span data-ttu-id="f01a1-112">由 Intune 服務主控的 Microsoft 365 基本行動性和安全性，適用于大部分（但非全部）行動裝置。</span><span class="sxs-lookup"><span data-stu-id="f01a1-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="f01a1-113">基本行動性和安全性可支援下列專案：</span><span class="sxs-lookup"><span data-stu-id="f01a1-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="f01a1-114">iOS 10.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f01a1-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="f01a1-115">Android 4.4 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f01a1-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="f01a1-116">Windows 8.1 和 Windows 10 (電話和電腦) </span><span class="sxs-lookup"><span data-stu-id="f01a1-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="f01a1-117">如果您的裝置並未列出，而且您需要使用基本行動性和安全性，請與您的公司或學校系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="f01a1-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="f01a1-118">如果您在註冊裝置時發生問題，請參閱 [疑難排解基本行動性和安全性](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="f01a1-119">設定具有 Intune 和基本行動性及安全性的行動裝置</span><span class="sxs-lookup"><span data-stu-id="f01a1-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="f01a1-120">Intune 公司入口網站可透過 Microsoft 365 和基本行動性及安全性來管理裝置。</span><span class="sxs-lookup"><span data-stu-id="f01a1-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="f01a1-121">iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="f01a1-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="f01a1-122">在您完成此步驟之前，您將無法傳送及接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f01a1-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="f01a1-123">移至 Apple 應用程式存放區，並下載及安裝 Intune 公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="f01a1-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="f01a1-124">若要使用公司入口網站將您的 iOS 電話或平板電腦連線至 Office 365，請參閱 [設定公司資源的 iOS 裝置存取權](https://go.microsoft.com/fwlink/?linkid=875316)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="f01a1-125">Android 手機或平板電腦</span><span class="sxs-lookup"><span data-stu-id="f01a1-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="f01a1-126">在您完成此步驟之前，您將無法傳送及接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f01a1-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="f01a1-127">移至 Google Play 商店，然後下載並安裝 Intune 公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="f01a1-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="f01a1-128">若要使用公司入口網站將您的 Android 手機或平板電腦連線至 Microsoft 365，請參閱向 [公司入口網站註冊您的裝置](https://go.microsoft.com/fwlink/?linkid=875317)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="f01a1-129">Windows 8.1 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="f01a1-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="f01a1-130">移至 Microsoft Store，並下載及安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="f01a1-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="f01a1-131">若要使用公司入口網站，將您的 Windows phone 或電腦設定為 Microsoft 365，請參閱 [在 Intune 公司入口網站中的 windows 裝置註冊](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="f01a1-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="f01a1-132">下一步是什麼？</span><span class="sxs-lookup"><span data-stu-id="f01a1-132">What's next?</span></span>

<span data-ttu-id="f01a1-133">在您的裝置註冊基本行動性和安全性之後，您可以開始使用裝置上的 Office 應用程式來處理電子郵件、行事曆、連絡人及檔。</span><span class="sxs-lookup"><span data-stu-id="f01a1-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>