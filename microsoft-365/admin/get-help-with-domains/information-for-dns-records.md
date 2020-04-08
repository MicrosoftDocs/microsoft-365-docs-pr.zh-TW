---
title: 收集建立 Office 365 DNS 記錄所需的資訊
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '瞭解如何尋找您為 Office 365 建立 DNS 記錄所需的值/資訊。 '
ms.custom: okr_smb
ms.openlocfilehash: d6093dd8a7e8d901be7b172a31dcd0e56c549ab3
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189004"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>收集建立 Office 365 DNS 記錄所需的資訊

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>步驟1：尋找 TXT 記錄值，並確認

1. 在 Microsoft 365 系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。

::: moniker-end
    
2. 在 [**網域**] 頁面上，選取您的網域，然後選取 [**開始設定**]。 You'll go back to the domains setup wizard to see the specific value you need to add.
    
3. 在 [**驗證網域**] 頁面上，選取 [**新增 TXT 記錄**]，然後選取 **[下一步]**。
    
4. 複製所顯示的**TXT 值**。 它看起來像這樣： **MS=msXXXXXXXX**。 
    
5. 移至[在任何 DNS 主機服務提供者處建立 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取 dns 主機以查看逐步指示。
    
6. 按照在您的 DNS 主機建立 TXT 記錄 (或 MX 記錄) 的步驟進行，然後回到 Office 365 中驗證網域。

7. 在 Office 365 中驗證網域之後，從 DNS 主機移除 TXT 記錄（或 MX 記錄）。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>步驟2：尋找電子郵件及其他專案的 MX 記錄值

1. 在 Microsoft 365 系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。

::: moniker-end
    
2. On the **Domains** page, select your domain. 
    
3. Under **Required DNS settings**, you'll see the DNS records to add.
    
    在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。
    
    此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。
    
4. 移至[任何 DNS 主機服務提供者的 dns 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後從註冊機構清單中選取您的 dns 主機，以查看在該 dns 主機的網站上新增記錄的逐步指示。
    
5. 請在 DNS 主機上遵循相關步驟建立記錄。
