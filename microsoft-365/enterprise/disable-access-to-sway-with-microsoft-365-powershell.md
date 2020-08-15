---
title: 使用 Microsoft 365 的 PowerShell 停用 Sway 的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: 7221a4c9-ae03-4598-81fe-a655c02f40ab
description: 瞭解從何處下載可讓您在 Microsoft 365 組織中停用 Sway 存取權的 ManageSway.ps1 PowerShell 腳本。
ms.openlocfilehash: bec96c6232eee88355997f56e49f1f99b8cc2fbd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688474"
---
# <a name="disable-access-to-sway-with-powershell-for-microsoft-365"></a><span data-ttu-id="2d518-103">使用 Microsoft 365 的 PowerShell 停用 Sway 的存取權</span><span class="sxs-lookup"><span data-stu-id="2d518-103">Disable access to Sway with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="2d518-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="2d518-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2d518-105">ManageSway.ps1 PowerShell 腳本可讓您查看及停用 Microsoft 365 組織中的服務，包括 Sway。</span><span class="sxs-lookup"><span data-stu-id="2d518-105">The ManageSway.ps1 PowerShell script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="2d518-106">這個指令碼會自動化下列主題中所述的程序︰</span><span class="sxs-lookup"><span data-stu-id="2d518-106">This script automates the procedures that are described in the following topics:</span></span>
  
- [<span data-ttu-id="2d518-107">使用 PowerShell 來查看授權和服務</span><span class="sxs-lookup"><span data-stu-id="2d518-107">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="2d518-108">使用 PowerShell 停用服務的存取權</span><span class="sxs-lookup"><span data-stu-id="2d518-108">Disable access to services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
    
<span data-ttu-id="2d518-109">您必須下載與指令碼相關聯的兩個檔案︰</span><span class="sxs-lookup"><span data-stu-id="2d518-109">You need to download the two files that are associated with the script:</span></span>
  
- <span data-ttu-id="2d518-110">[https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070) 上的 ManageSway.ps1 指令碼</span><span class="sxs-lookup"><span data-stu-id="2d518-110">The ManageSway.ps1 script at [https://go.microsoft.com/fwlink/p/?LinkId=785070](https://go.microsoft.com/fwlink/p/?LinkId=785070)</span></span>
    
- <span data-ttu-id="2d518-111">[https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072) 上的指令碼說明檔案</span><span class="sxs-lookup"><span data-stu-id="2d518-111">The help file for the script at [https://go.microsoft.com/fwlink/p/?LinkId=785072](https://go.microsoft.com/fwlink/p/?LinkId=785072)</span></span>
    

