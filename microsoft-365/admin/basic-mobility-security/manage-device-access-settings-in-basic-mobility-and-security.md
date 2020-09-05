---
title: 在基本行動及安全性中管理裝置存取設定
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
description: 基本行動性和安全性可協助您保護和管理行動裝置。
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336773"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="5e662-103">在基本行動及安全性中管理裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="5e662-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="5e662-104">如果您使用基本行動性和安全性，則可能是無法使用基本行動性和安全性來管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="5e662-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="5e662-105">如果是的話，您應該封鎖 Exchange ActiveSync app 存取 Microsoft 365 電子郵件，以供基本行動及安全性所不支援的行動裝置使用。</span><span class="sxs-lookup"><span data-stu-id="5e662-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="5e662-106">這可協助您保護組織中的資訊，使其超過多種裝置。</span><span class="sxs-lookup"><span data-stu-id="5e662-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="5e662-107">請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5e662-107">Use these steps:</span></span>

1. <span data-ttu-id="5e662-108">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5e662-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="5e662-109">在您的瀏覽器中輸入：  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="5e662-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="5e662-110">如果這是您第一次使用 MDM for Microsoft 365 商務標準，請在這裡啟動： [啟動行動裝置管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5e662-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="5e662-111">啟動之後，使用 [Office 365 安全性 & 合規性](https://protection.office.com/)來管理裝置。</span><span class="sxs-lookup"><span data-stu-id="5e662-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="5e662-112">移至 [資料遺失防護 > **裝置管理**   >  **裝置原則**]，然後選取 [ **管理整個組織的裝置存取設定**]。</span><span class="sxs-lookup"><span data-stu-id="5e662-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="5e662-113">選取 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="5e662-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本行動及安全性封鎖存取核取方塊":::

5. <span data-ttu-id="5e662-115">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="5e662-115">Select **Save**.</span></span> 

<span data-ttu-id="5e662-116">若要瞭解基本行動性和安全性可支援哪些裝置，請參閱 [基本行動性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。</span><span class="sxs-lookup"><span data-stu-id="5e662-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>