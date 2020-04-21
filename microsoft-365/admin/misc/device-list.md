---
title: 裝置清單 CSV-檔案
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 瞭解如何在 Microsoft 365 for business 中 AutoPilot 建立 CSV 檔案。
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627857"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="81978-103">裝置清單 CSV-檔案</span><span class="sxs-lookup"><span data-stu-id="81978-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="81978-104">裝置清單 .csv 檔案格式</span><span class="sxs-lookup"><span data-stu-id="81978-104">Device list .csv file format</span></span>

<span data-ttu-id="81978-105">若要透過 Windows Autopilot 管理及部署裝置，您需要包含裝置特定資訊的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="81978-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="81978-106">裝置清單檔案中的欄必須以指定的順序排列下列標頭：</span><span class="sxs-lookup"><span data-stu-id="81978-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="81978-107">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="81978-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="81978-108">欄 B：保留空白</span><span class="sxs-lookup"><span data-stu-id="81978-108">Column B: leave blank</span></span>

- <span data-ttu-id="81978-109">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="81978-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="81978-110">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="81978-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="81978-111">當您新增裝置時，您也需要將裝置新增至設定檔。</span><span class="sxs-lookup"><span data-stu-id="81978-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="81978-112">設定檔是用來將 AutoPilot 部署設定檔套用至裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="81978-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="81978-113">相關文章</span><span class="sxs-lookup"><span data-stu-id="81978-113">Related articles</span></span>

[<span data-ttu-id="81978-114">商務用 Microsoft 365 檔和資源</span><span class="sxs-lookup"><span data-stu-id="81978-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="81978-115">開始使用 Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="81978-115">Get started with Microsoft 365 for business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="81978-116">管理 Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="81978-116">Manage Microsoft 365 for business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
