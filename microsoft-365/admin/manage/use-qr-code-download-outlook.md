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
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122369"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="c0e87-103">使用 QR 碼登錄 Outlook 行動應用程式</span><span class="sxs-lookup"><span data-stu-id="c0e87-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0e87-104">此 Microsoft 365 功能位於公開預覽中。</span><span class="sxs-lookup"><span data-stu-id="c0e87-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="c0e87-105">公開預覽可讓您及早存取 Microsoft 365 的功能。</span><span class="sxs-lookup"><span data-stu-id="c0e87-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="c0e87-106">做為 Microsoft 365 系統管理員，您可以讓您的使用者在其行動裝置上登入 Outlook for Android 或 iOS 應用程式，而不必輸入他們的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="c0e87-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="c0e87-107">透過掃描 QR 碼，使用者就可以安全地驗證和登入 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="c0e87-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="c0e87-108">在 Outlook 網頁版或其他的桌面 Outlook 應用程式中，使用者可能會看到通知，通知他們可以在行動裝置上使用 Outlook。</span><span class="sxs-lookup"><span data-stu-id="c0e87-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="c0e87-109">系統管理員可以使用 Exchange Powershell 來管理這些通知。</span><span class="sxs-lookup"><span data-stu-id="c0e87-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="c0e87-110">如果使用者選擇傳送自己的 SMS 文字訊息，以在其行動裝置上下載應用程式，則其電腦上會出現 QR 碼。</span><span class="sxs-lookup"><span data-stu-id="c0e87-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="c0e87-111">他們將可以掃描 QR 碼，以登入在其電話或平板電腦上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="c0e87-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="c0e87-112">此 QR 碼是一種簡短的存留期權杖，只能兌換一次。</span><span class="sxs-lookup"><span data-stu-id="c0e87-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e87-113">在某些情況下，您的使用者將必須在其電腦上重新驗證，以產生 QR 碼。</span><span class="sxs-lookup"><span data-stu-id="c0e87-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="c0e87-114">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0e87-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="c0e87-115">此體驗預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="c0e87-115">This experience is on by default.</span></span> <span data-ttu-id="c0e87-116">若要停用此功能，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c0e87-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="c0e87-117">[連接至 Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="c0e87-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="c0e87-118">您可以使用 PowerShell 來停用通知，告知使用者 Outlook 行動應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c0e87-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="c0e87-119">這也會使 QR 碼無法顯示登入流程。</span><span class="sxs-lookup"><span data-stu-id="c0e87-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="c0e87-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="c0e87-120">Related topics</span></span>

[<span data-ttu-id="c0e87-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="c0e87-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
