---
title: 使用 QR 碼登錄 Outlook 行動應用程式
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 瞭解如何使用 QR 碼來驗證和下載 Outlook mobile。
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242351"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="5a449-103">使用 QR 碼登錄 Outlook 行動應用程式</span><span class="sxs-lookup"><span data-stu-id="5a449-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a449-104">此功能僅適用于已在 Microsoft 365 系統管理中心中開啟目標版本的組織。</span><span class="sxs-lookup"><span data-stu-id="5a449-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5a449-105">若要開啟目標版本並深入瞭解其運作方式，請參閱 [設定標準或目標發行選項](release-options-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5a449-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="5a449-106">我們將透過公開預覽，將更多組織擴充至未來的幾周。</span><span class="sxs-lookup"><span data-stu-id="5a449-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="5a449-107">公開預覽可讓您及早存取 Microsoft 365 的功能。</span><span class="sxs-lookup"><span data-stu-id="5a449-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="5a449-108">做為 Microsoft 365 系統管理員，您可以讓您的使用者在其行動裝置上登入 Outlook for Android 或 iOS 應用程式，而不必輸入他們的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="5a449-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="5a449-109">透過掃描 QR 碼，使用者就可以安全地驗證和登入 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="5a449-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="5a449-110">在 Outlook 網頁版或其他的桌面 Outlook 應用程式中，使用者可能會看到通知，通知他們可以在行動裝置上使用 Outlook。</span><span class="sxs-lookup"><span data-stu-id="5a449-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="5a449-111">系統管理員可以使用 Exchange Powershell 來管理這些通知。</span><span class="sxs-lookup"><span data-stu-id="5a449-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="5a449-112">如果使用者選擇傳送自己的 SMS 文字訊息，以在其行動裝置上下載應用程式，則其電腦上會出現 QR 碼。</span><span class="sxs-lookup"><span data-stu-id="5a449-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="5a449-113">他們將可以掃描 QR 碼，以登入在其電話或平板電腦上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="5a449-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="5a449-114">此 QR 碼是一種簡短的存留期權杖，只能兌換一次。</span><span class="sxs-lookup"><span data-stu-id="5a449-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="5a449-115">在某些情況下，您的使用者將必須在其電腦上重新驗證，以產生 QR 碼。</span><span class="sxs-lookup"><span data-stu-id="5a449-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="5a449-116">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a449-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="5a449-117">這項功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="5a449-117">This feature is on by default.</span></span> <span data-ttu-id="5a449-118">若要停用此功能，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5a449-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="5a449-119">[連接至 Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="5a449-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="5a449-120">您可以使用 PowerShell 來停用通知，告知使用者 Outlook 行動應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5a449-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="5a449-121">這也會使 QR 碼無法顯示登入流程。</span><span class="sxs-lookup"><span data-stu-id="5a449-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="5a449-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="5a449-122">Related topics</span></span>

[<span data-ttu-id="5a449-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="5a449-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
