---
title: Windows 10 定位服務
description: 如何開啟裝置的 Windows 位置服務
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929475"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="1561e-104">Windows 10 定位服務</span><span class="sxs-lookup"><span data-stu-id="1561e-104">Windows 10 location service</span></span>

<span data-ttu-id="1561e-105">Microsoft 受管理的電腦中的裝置會使用 Windows Autopilot 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="1561e-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="1561e-106">此程式可讓我們使用 Azure Active Directory 和 Microsoft Intune 進行管理。</span><span class="sxs-lookup"><span data-stu-id="1561e-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="1561e-107">預設會在裝置第一次開啟時停用 Windows 10 位置服務，除非在「全新體驗」期間的隱私權設定中啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="1561e-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="1561e-108">在 Microsoft 受管理的電腦中 Autopilot 登記期間會隱藏這些設定。</span><span class="sxs-lookup"><span data-stu-id="1561e-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1561e-109">如需如何設定 Autopilot 的詳細資訊，請參閱 [使用 Autopilot 的第一次執行體驗和註冊狀態頁面](esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="1561e-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="1561e-110">因此，Microsoft 受管理的電腦裝置無法取得其裝置位置，這會限制許多 Windows 功能的功能，例如時區。</span><span class="sxs-lookup"><span data-stu-id="1561e-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="1561e-111">如需 Windows 10 位置服務的詳細資訊，請參閱[Windows 10 位置服務和隱私權](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="1561e-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="1561e-112">您不需要使用 location 服務來參與 Microsoft 受管理的電腦，但會限制使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="1561e-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="1561e-113">例如，當使用者在不同的時區中工作時，裝置將無法自動判斷其所在時區。</span><span class="sxs-lookup"><span data-stu-id="1561e-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="1561e-114">啟用位置服務</span><span class="sxs-lookup"><span data-stu-id="1561e-114">Enable the location service</span></span>

<span data-ttu-id="1561e-115">您可以選擇在將裝置登記至 Microsoft 受管理的電腦服務時使用 location 服務，也可以在註冊後開啟或關閉服務。</span><span class="sxs-lookup"><span data-stu-id="1561e-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="1561e-116">在註冊期間自願加入</span><span class="sxs-lookup"><span data-stu-id="1561e-116">Opt in during enrollment</span></span>

<span data-ttu-id="1561e-117">您可以讓 Microsoft 受管理的電腦服務啟用位置服務。</span><span class="sxs-lookup"><span data-stu-id="1561e-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="1561e-118">在註冊順序期間，系統會要求您選取是否要允許在裝置上啟用 Windows 10 位置服務。</span><span class="sxs-lookup"><span data-stu-id="1561e-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="1561e-119">在註冊後控制位置服務</span><span class="sxs-lookup"><span data-stu-id="1561e-119">Control the location service after enrollment</span></span>

<span data-ttu-id="1561e-120">您可以隨時 (或關閉) 的位置服務，方法是透過[管理入口網站](access-admin-portal.md)提交[支援要求](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="1561e-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="1561e-121">Microsoft 受管理的電腦如何設定 Windows 10 位置服務</span><span class="sxs-lookup"><span data-stu-id="1561e-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="1561e-122">如果您選擇使用位置服務，我們會使用必要的最低設定，而不會影響使用者的隱私權。</span><span class="sxs-lookup"><span data-stu-id="1561e-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="1561e-123">如需詳細資訊，請參閱[Windows 10 位置服務和隱私權](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="1561e-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="1561e-124">Microsoft 受管理的電腦會在 **Windows 設定** 中啟用 **位置隱私權** 設定，以 **允許存取此裝置上的位置**。</span><span class="sxs-lookup"><span data-stu-id="1561e-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="1561e-125">使用者介面如下所示：</span><span class="sxs-lookup"><span data-stu-id="1561e-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Windows 設定中的位置設定":::

> [!NOTE]
> <span data-ttu-id="1561e-127">如果您選擇使用位置服務，這只適用于 Windows 作業系統本身。</span><span class="sxs-lookup"><span data-stu-id="1561e-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="1561e-128">不允許應用程式使用位置服務。</span><span class="sxs-lookup"><span data-stu-id="1561e-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="1561e-129">每個使用者都可以選擇是否允許應用程式存取其位置。</span><span class="sxs-lookup"><span data-stu-id="1561e-129">Each user can choose whether to allow apps to access their location.</span></span>