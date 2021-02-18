---
title: 設定 S/MIME 設定-web 上 Outlook 的 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: 簡要描述 Exchange Online 系統管理員需要執行哪些動作才能在 Exchange Online 的 Outlook 網頁版中查看和設定 S/MIME 設定。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290030"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="26acc-103">在 Exchange Online 中設定 Outlook 網頁版的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="26acc-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="26acc-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="26acc-104">**Applies to**</span></span>
- [<span data-ttu-id="26acc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="26acc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="26acc-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="26acc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="26acc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26acc-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="26acc-108">如果您是 Exchange Online 的系統管理員，您可以設定 Outlook 網頁版（先前稱為 Outlook Web App），允許傳送和接收 S/MIME 保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="26acc-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="26acc-109">在 Exchange Online PowerShell 中使用 **SmimeConfig** 和 **SmimeConfig** Cmdlet 來查看及管理這個功能。</span><span class="sxs-lookup"><span data-stu-id="26acc-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="26acc-110">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="26acc-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="26acc-111">如需詳細的語法及參數資訊，請參閱 [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) 和 [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="26acc-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="26acc-112">新的 Microsoft Edge (Chromium 基礎的考慮) </span><span class="sxs-lookup"><span data-stu-id="26acc-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="26acc-113">若要在 [Microsoft](https://www.microsoft.com/windows/microsoft-edge) 的 Outlook 網頁瀏覽器中使用 S/MIME，您 (或另一個系統管理員) 必須設定及設定名為 **ExtensionInstallForcelist** 的 microsoft Edge browser 原則，以在新的 Microsoft edge 中安裝 microsoft S/MIME 擴充。</span><span class="sxs-lookup"><span data-stu-id="26acc-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="26acc-114">原則值為 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。</span><span class="sxs-lookup"><span data-stu-id="26acc-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="26acc-115">請注意，套用此原則需要加入網域的裝置或 Azure 已加入 Azure 的裝置，所以在新的 Microsoft Edge 瀏覽器中使用 S/MIME，會有效地需要加入網域或 Azure 已加入 Azure 的裝置。</span><span class="sxs-lookup"><span data-stu-id="26acc-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="26acc-116">如需詳細的 **ExtensionInstallForcelist** 原則的資訊，請參閱 [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。</span><span class="sxs-lookup"><span data-stu-id="26acc-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="26acc-117">此步驟是使用新的 Microsoft Edge 的必要條件;它不會取代使用者所安裝的 S/MIME 控制項。</span><span class="sxs-lookup"><span data-stu-id="26acc-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="26acc-118">在初次使用 S/MIME 時，系統會提示使用者下載並安裝 Outlook 網頁版中的 S/MIME 控制。</span><span class="sxs-lookup"><span data-stu-id="26acc-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="26acc-119">或者，使用者可以主動移至 Outlook 網頁版設定中的 **S/MIME**，取得控制的下載連結。</span><span class="sxs-lookup"><span data-stu-id="26acc-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="26acc-120">Chrome 使用者的考量</span><span class="sxs-lookup"><span data-stu-id="26acc-120">Considerations for Chrome</span></span>

<span data-ttu-id="26acc-121">若要在 Google Chrome 網頁瀏覽器的 Outlook 網頁版中使用 S/MIME，您（或另一個系統管理員）必須設定名為 **ExtensionInstallForcelist** 的 Chromium 原則，以在 Chrome 中安裝 Microsoft S/MIME 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="26acc-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="26acc-122">原則值為 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。</span><span class="sxs-lookup"><span data-stu-id="26acc-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="26acc-123">請注意，若要套用此原則，必須有加入網域的電腦，因此，要有效地在 Chrome 使用 S/MIME 必須有加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="26acc-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="26acc-124">如需詳細的 **ExtensionInstallForcelist** 原則的資訊，請參閱 [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="26acc-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="26acc-125">此步驟是使用 Chrome 的先決條件；它不會取代由使用者安裝的 S/MIME 控制。</span><span class="sxs-lookup"><span data-stu-id="26acc-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="26acc-126">在初次使用 S/MIME 時，系統會提示使用者下載並安裝 Outlook 網頁版中的 S/MIME 控制。</span><span class="sxs-lookup"><span data-stu-id="26acc-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="26acc-127">或者，使用者可以主動移至 Outlook 網頁版設定中的 **S/MIME**，取得控制的下載連結。</span><span class="sxs-lookup"><span data-stu-id="26acc-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="26acc-128">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="26acc-128">For more information</span></span>

[<span data-ttu-id="26acc-129">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="26acc-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
