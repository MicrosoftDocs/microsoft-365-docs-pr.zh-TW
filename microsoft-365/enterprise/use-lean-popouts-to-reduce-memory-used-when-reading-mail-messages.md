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
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925253"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>使用精益快顯減少讀取郵件訊息時所使用的記憶體

本文包含改進 Outlook 網頁版中郵件下載效能的資訊。 本文是 Office 365 專案的 [網路規劃和效能調整](./network-planning-and-performance.md) 的一部分。
  
做為 Office 365 全域系統管理員，您可以設定網頁型 Outlook，以在 Microsoft Edge 或 Internet Explorer 中提供 _精益快顯_，這是佔用大量記憶體的特定電子郵件的版本。 當網頁上的 Outlook 設定精益快顯時，會載入伺服器端呈現的元件，以優化效能。
  
> [!NOTE]
> 從3月2018，「精益快顯」不適用於指定使用許可權限制（如資訊版權管理 (IRM) ）的郵件。
  
這些功能將繼續在主視窗中運作，但無法在精益快顯中使用：
  
- Outlook 增益集
  
- 商務用 Skype 目前狀態
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>為 Office 365 組織內的所有使用者設定精益快顯
  
1. [使用遠端 PowerShell 連接至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。
  
2. 使用 LeanPopoutEnabled 參數執行 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) Cmdlet，如下所示：

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  例如，若要為您組織中的所有使用者啟用精益快顯：
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  若要為您組織中的所有使用者停用精益快顯：

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```