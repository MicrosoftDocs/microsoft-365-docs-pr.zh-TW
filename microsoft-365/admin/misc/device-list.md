---
title: 裝置清單 CSV-檔案
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 瞭解如何為商務 Microsoft 365 中的 AutoPilot 建立 CSV 檔案。
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579215"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="c9d1c-103">裝置清單 CSV-檔案</span><span class="sxs-lookup"><span data-stu-id="c9d1c-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="c9d1c-104">裝置清單 .csv 檔案格式</span><span class="sxs-lookup"><span data-stu-id="c9d1c-104">Device list .csv file format</span></span>

<span data-ttu-id="c9d1c-105">若要透過 Windows Autopilot 管理及部署裝置，您需要包含裝置特定資訊的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="c9d1c-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="c9d1c-106">裝置清單檔案中的欄必須以指定的順序排列下列標頭：</span><span class="sxs-lookup"><span data-stu-id="c9d1c-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="c9d1c-107">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="c9d1c-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="c9d1c-108">欄 B：保留空白</span><span class="sxs-lookup"><span data-stu-id="c9d1c-108">Column B: leave blank</span></span>

- <span data-ttu-id="c9d1c-109">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="c9d1c-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="c9d1c-110">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c9d1c-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="c9d1c-111">當您新增裝置時，您也需要將裝置新增至設定檔。</span><span class="sxs-lookup"><span data-stu-id="c9d1c-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="c9d1c-112">設定檔是用來將 AutoPilot 部署設定檔套用至裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="c9d1c-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c9d1c-113">相關文章</span><span class="sxs-lookup"><span data-stu-id="c9d1c-113">Related articles</span></span>

[<span data-ttu-id="c9d1c-114">商務檔和資源的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9d1c-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="c9d1c-115">開始使用商務 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9d1c-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="c9d1c-116">管理商務 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9d1c-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
