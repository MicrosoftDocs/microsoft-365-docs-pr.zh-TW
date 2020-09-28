---
title: Microsoft 365 的基本行動及安全性概述
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
description: 使用基本行動及安全性設定裝置安全性原則和存取規則。
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430105"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="9dc00-103">Microsoft 365 的基本行動及安全性概述</span><span class="sxs-lookup"><span data-stu-id="9dc00-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="9dc00-104">您可以使用基本行動性和安全性，在行動裝置連線至 Microsoft 365 組織時，管理並保護行動裝置。</span><span class="sxs-lookup"><span data-stu-id="9dc00-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="9dc00-105">行動裝置（例如 smartphone 和平板電腦），用來存取工作電子郵件、行事曆、連絡人及檔，可確保員工隨時隨地從任何地方完成工作。</span><span class="sxs-lookup"><span data-stu-id="9dc00-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="9dc00-106">所以很重要的一點是，當使用者使用裝置時，您可以協助保護組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="9dc00-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="9dc00-107">您可以使用基本行動及安全性，設定裝置安全性原則和存取規則，以及在行動裝置遺失或遭盜時加以清除。</span><span class="sxs-lookup"><span data-stu-id="9dc00-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本行動及安全性設定":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="9dc00-109">您可以管理哪些類型的裝置？</span><span class="sxs-lookup"><span data-stu-id="9dc00-109">What types of devices can you manage?</span></span>

<span data-ttu-id="9dc00-110">您可以使用基本行動性和安全性來管理許多類型的行動裝置，例如 Windows Phone、Android、iPhone 和 iPad。</span><span class="sxs-lookup"><span data-stu-id="9dc00-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="9dc00-111">若要管理組織中人員所使用的行動裝置，每個人都必須有適用的 Microsoft 365 授權，而且其裝置必須以基本行動性和安全性進行註冊。</span><span class="sxs-lookup"><span data-stu-id="9dc00-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="9dc00-112">若要查看每種裝置類型所支援的基本行動性和安全性，請參閱 [基本行動性和安全性的功能](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc00-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="9dc00-113">基本行動性和安全性的設定步驟</span><span class="sxs-lookup"><span data-stu-id="9dc00-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="9dc00-114">Microsoft 365 全域管理員必須完成下列步驟，才能啟動和設定基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="9dc00-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="9dc00-115">如需詳細步驟，請遵循 [設定基本行動性和安全性](set-up.md)中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="9dc00-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="9dc00-116">以下是步驟的摘要：</span><span class="sxs-lookup"><span data-stu-id="9dc00-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="9dc00-117">**步驟1：** 依照 [設定基本行動性和安全性](set-up.md)中的步驟，啟用基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="9dc00-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="9dc00-118">**步驟2：** 例如，建立 APNs 憑證以管理 iOS 裝置，並新增網域名稱系統 (DNS) 的網域名稱系統來支援 Windows phone，以設定基本行動性及安全性。</span><span class="sxs-lookup"><span data-stu-id="9dc00-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="9dc00-119">**步驟3：** 建立裝置原則，並將其套用至使用者群組。</span><span class="sxs-lookup"><span data-stu-id="9dc00-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="9dc00-120">當您執行此動作時，您的使用者會在其裝置上取得註冊訊息，當他們完成註冊時，其裝置會受到您為其所設定的原則所限制。</span><span class="sxs-lookup"><span data-stu-id="9dc00-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="9dc00-121">如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc00-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和行動性原則設定":::

## <a name="device-management-tasks"></a><span data-ttu-id="9dc00-123">裝置管理工作</span><span class="sxs-lookup"><span data-stu-id="9dc00-123">Device management tasks</span></span>

<span data-ttu-id="9dc00-124">當您已設定基本行動性和安全性，且使用者已註冊其裝置後，您就可以管理裝置、封鎖存取或擦除裝置（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="9dc00-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="9dc00-125">若要深入瞭解一些常見的裝置管理工作（包括完成工作的位置），請參閱 [Manage device In Mobile Device management For Microsoft 365](manage-enrolled-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc00-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="9dc00-126">其他管理裝置和應用程式的方法</span><span class="sxs-lookup"><span data-stu-id="9dc00-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="9dc00-127">如果您只需要行動電話應用程式管理 (MAM) （可能是因為人員在自己的裝置上更新工作專案），則 Intune 除了註冊及管理裝置之外，還提供另一個選項。</span><span class="sxs-lookup"><span data-stu-id="9dc00-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="9dc00-128">Intune 訂閱可讓您使用 Azure 入口網站來設定 MAM 原則，即使人員的裝置並未在 Intune 中註冊也是一樣。</span><span class="sxs-lookup"><span data-stu-id="9dc00-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="9dc00-129">如需詳細資訊，請參閱 [App protection 原則一覽](https://go.microsoft.com/fwlink/?LinkId=2132517)。</span><span class="sxs-lookup"><span data-stu-id="9dc00-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9dc00-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="9dc00-130">Related topics</span></span>

[<span data-ttu-id="9dc00-131">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="9dc00-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="9dc00-132">使用基本行動性和安全性註冊行動裝置</span><span class="sxs-lookup"><span data-stu-id="9dc00-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="9dc00-133">管理登記于 Microsoft 365 行動裝置管理的裝置</span><span class="sxs-lookup"><span data-stu-id="9dc00-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="9dc00-134">取得基本行動性和安全性所管理之裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="9dc00-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)