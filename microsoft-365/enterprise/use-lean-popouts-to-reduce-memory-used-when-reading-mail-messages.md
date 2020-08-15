---
title: 使用精益快顯減少讀取郵件訊息時所使用的記憶體
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 本文包含的資訊可讓您使用精益快顯，以改善 Outlook 網頁版中的郵件下載效能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688744"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="55c1a-103">使用精益快顯減少讀取郵件訊息時所使用的記憶體</span><span class="sxs-lookup"><span data-stu-id="55c1a-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="55c1a-104">本文包含改進 Outlook 網頁版中郵件下載效能的資訊。</span><span class="sxs-lookup"><span data-stu-id="55c1a-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="55c1a-105">本文是 Office 365 專案的 [網路規劃和效能調整](https://aka.ms/tune) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="55c1a-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="55c1a-106">做為 Office 365 全域系統管理員，您可以設定網頁型 Outlook，以在 Microsoft Edge 或 Internet Explorer 中提供 _精益快顯_，這是佔用大量記憶體的特定電子郵件的版本。</span><span class="sxs-lookup"><span data-stu-id="55c1a-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="55c1a-107">當網頁上的 Outlook 設定精益快顯時，會載入伺服器端呈現的元件，以優化效能。</span><span class="sxs-lookup"><span data-stu-id="55c1a-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55c1a-108">從3月2018，「精益快顯」不適用於指定使用許可權限制（如資訊版權管理 (IRM) ）的郵件。</span><span class="sxs-lookup"><span data-stu-id="55c1a-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="55c1a-109">這些功能將繼續在主視窗中運作，但無法在精益快顯中使用：</span><span class="sxs-lookup"><span data-stu-id="55c1a-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="55c1a-110">Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="55c1a-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="55c1a-111">商務用 Skype 目前狀態</span><span class="sxs-lookup"><span data-stu-id="55c1a-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="55c1a-112">為 Office 365 組織內的所有使用者設定精益快顯</span><span class="sxs-lookup"><span data-stu-id="55c1a-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="55c1a-113">[使用遠端 PowerShell 連接至 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )。</span><span class="sxs-lookup"><span data-stu-id="55c1a-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="55c1a-114">使用 LeanPopoutEnabled 參數執行 [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55c1a-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="55c1a-115">例如，若要為您組織中的所有使用者啟用精益快顯：</span><span class="sxs-lookup"><span data-stu-id="55c1a-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="55c1a-116">若要為您組織中的所有使用者停用精益快顯：</span><span class="sxs-lookup"><span data-stu-id="55c1a-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
