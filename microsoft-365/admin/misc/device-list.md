---
title: 裝置清單 CSV 檔案
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
description: 了解如何讓 AutoPilo 錫 Microsoft 365 商務版的 CSV 檔案。
ms.openlocfilehash: cd317bd5edaa3fdaea8a704f79a269387e8fe1c1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254299"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="9fc69-103">裝置清單 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="9fc69-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="9fc69-104">裝置清單的.csv 檔案格式</span><span class="sxs-lookup"><span data-stu-id="9fc69-104">Device list .csv file format</span></span>

<span data-ttu-id="9fc69-105">若要管理及部署透過 Windows Autopilot 裝置，您需要包含之裝置的特定資訊的.csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="9fc69-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="9fc69-106">在裝置清單檔案中的欄必須具備下列標頭中指定的順序：</span><span class="sxs-lookup"><span data-stu-id="9fc69-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="9fc69-107">欄 A：裝置序號</span><span class="sxs-lookup"><span data-stu-id="9fc69-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="9fc69-108">欄 B:WINDOWS 保留空白</span><span class="sxs-lookup"><span data-stu-id="9fc69-108">Column B: leave blank</span></span>

- <span data-ttu-id="9fc69-109">欄 C：硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="9fc69-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="9fc69-110">您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9fc69-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="9fc69-111">當您新增裝置時，您也需要將它們新增至設定檔。</span><span class="sxs-lookup"><span data-stu-id="9fc69-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="9fc69-112">設定檔用來將 AutoPilot 部署設定檔套用到單一裝置或一組裝置。</span><span class="sxs-lookup"><span data-stu-id="9fc69-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="9fc69-113">相關文章</span><span class="sxs-lookup"><span data-stu-id="9fc69-113">Related articles</span></span>

[<span data-ttu-id="9fc69-114">Microsoft 365 商務版文件和資源</span><span class="sxs-lookup"><span data-stu-id="9fc69-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="9fc69-115">開始使用 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9fc69-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="9fc69-116">管理 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9fc69-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  