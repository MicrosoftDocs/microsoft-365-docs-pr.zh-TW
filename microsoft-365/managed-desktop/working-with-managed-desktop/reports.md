---
title: 使用報告
description: Microsoft 受管理的電腦中可用的各種報告
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729965"
---
# <a name="work-with-reports"></a><span data-ttu-id="ef077-104">使用報告</span><span class="sxs-lookup"><span data-stu-id="ef077-104">Work with reports</span></span>

<span data-ttu-id="ef077-105">Microsoft 受管理的電腦提供數個報告及儀表板，供組織中的系統管理員用來瞭解各設備的人口的各個層面。</span><span class="sxs-lookup"><span data-stu-id="ef077-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="ef077-106">您可以在兩個位置找到報表：在[Microsoft 端點管理員](https://endpoint.microsoft.com)和[Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。</span><span class="sxs-lookup"><span data-stu-id="ef077-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="ef077-107">Microsoft 端點管理員中的報表</span><span class="sxs-lookup"><span data-stu-id="ef077-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="ef077-108">Microsoft 端點管理員主控台將數個產品的報告彙集到單一位置，以協助您監視和調查您的 Azure AD 組織 ( "承租人" ) 設定和裝置的問題。</span><span class="sxs-lookup"><span data-stu-id="ef077-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="ef077-109">Microsoft 受管理的桌面在主功能表的 [**報告**] 中有一個區段，您可以在其中找到您已註冊之裝置的 Microsoft 受管理的電腦管理專用報告。</span><span class="sxs-lookup"><span data-stu-id="ef077-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="ef077-110">這些報告包括：</span><span class="sxs-lookup"><span data-stu-id="ef077-110">These reports include:</span></span>
- <span data-ttu-id="ef077-111">**受管理裝置**  > **功能更新**：此視圖顯示整個 Microsoft 受管理的電腦裝置中功能更新的整體狀態。</span><span class="sxs-lookup"><span data-stu-id="ef077-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="ef077-112">**受管理裝置**  > **Office 更新**：此視圖顯示所有 Microsoft 受管理的電腦裝置中 Office 更新的整體狀態。</span><span class="sxs-lookup"><span data-stu-id="ef077-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="ef077-113">此外，在 Microsoft 端點管理員中的數個位置，您可以從其他產品群組篩選報表，以特別包含或排除 Microsoft 受管理的電腦所管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="ef077-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef077-114">這些報告已整合此篩選功能：</span><span class="sxs-lookup"><span data-stu-id="ef077-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="ef077-115">所有裝置</span><span class="sxs-lookup"><span data-stu-id="ef077-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="ef077-116">裝置合規性</span><span class="sxs-lookup"><span data-stu-id="ef077-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="ef077-117">不相容的裝置</span><span class="sxs-lookup"><span data-stu-id="ef077-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="ef077-118">自訂 Microsoft 受管理的電腦角色保證只能存取 Microsoft 受管理的電腦報告。</span><span class="sxs-lookup"><span data-stu-id="ef077-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="ef077-119">若要存取 Microsoft 端點管理員的其他部分，例如 **所有裝置**，請參閱 [具有 Microsoft Intune 的角色型存取控制](/mem/intune/fundamentals/role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="ef077-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="ef077-120">庫存資料</span><span class="sxs-lookup"><span data-stu-id="ef077-120">Inventory data</span></span>

<span data-ttu-id="ef077-121">除了其他報告之外，您還可以匯出 Microsoft 受管理的電腦所管理之裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ef077-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="ef077-122">在 Microsoft 端點管理員 **的 [** **裝置**] 區域中，使用 [**匯出全部**] 索引標籤 [下載詳細的庫存報告](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="ef077-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>