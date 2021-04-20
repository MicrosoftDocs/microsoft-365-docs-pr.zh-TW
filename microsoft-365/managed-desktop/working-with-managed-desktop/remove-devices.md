---
title: 移除裝置
description: 從 Microsoft 受管理的桌面管理移除裝置
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
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893734"
---
# <a name="remove-devices"></a><span data-ttu-id="c6638-103">移除裝置</span><span class="sxs-lookup"><span data-stu-id="c6638-103">Remove devices</span></span>

<span data-ttu-id="c6638-104">您可以使用管理入口網站，從 Microsoft Managed Desktop management 移除裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="c6638-105">此巨集指令是永久的，但是您可以遵循 [註冊步驟](../get-started/register-devices-self.md)，將其註冊至 Microsoft Managed Desktop。</span><span class="sxs-lookup"><span data-stu-id="c6638-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="c6638-106">當您移除裝置時，會發生下列所有情況：</span><span class="sxs-lookup"><span data-stu-id="c6638-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="c6638-107">我們會從 Autopilot 移除裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="c6638-108">我們會從所有「新式工作」裝置群組中移除裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="c6638-109">我們會從系統管理入口網站的 [ **裝置** ] 刀片式伺服器中移除裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="c6638-110">當您移除裝置時，您可以選擇同時從 Azure Active Directory (Azure AD) 和 Microsoft Intune 中移除它。</span><span class="sxs-lookup"><span data-stu-id="c6638-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="c6638-111">從 Azure AD 和 Microsoft Intune 中移除與裝置相關的物件是永久的。</span><span class="sxs-lookup"><span data-stu-id="c6638-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="c6638-112">如果您移除物件，您將無法從 Intune 和 Azure 入口網站中查看或管理裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="c6638-113">裝置將無法存取公司的公司資源。</span><span class="sxs-lookup"><span data-stu-id="c6638-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="c6638-114">如果裝置嘗試在刪除之後登入，公司資料可能會從這些資料中刪除。</span><span class="sxs-lookup"><span data-stu-id="c6638-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="c6638-115">在 [Microsoft 端點管理員](https://endpoint.microsoft.com/)的左導覽窗格中，選取 [ **裝置** ]。</span><span class="sxs-lookup"><span data-stu-id="c6638-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="c6638-116">尋找功能表中的 [ **Microsoft 受管理的桌面** ] 區段，然後選取 [ **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c6638-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="c6638-117">在 [Microsoft 受管理的電腦裝置] 工作區中，選取您要刪除的裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="c6638-118">選取 [ **裝置動作**]，然後選取 [刪除即時的 **裝置** ] 以移除裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="c6638-119">在 [飛入] 中，複查選取的裝置，然後選取 [ **移除裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c6638-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="c6638-120">若要同時移除 Azure AD 及 Intune 物件，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c6638-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="c6638-121">裝置移除可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="c6638-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="c6638-122">您無法移除處於 **擱置** 中註冊狀態的裝置。</span><span class="sxs-lookup"><span data-stu-id="c6638-122">You can't remove devices that are in a **pending** registration state.</span></span>