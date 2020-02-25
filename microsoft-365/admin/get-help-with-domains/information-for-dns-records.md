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
description: '了解如何尋找您要建立 Office 365 的 DNS 記錄的值/資訊。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251653"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>收集建立 Office 365 DNS 記錄所需的資訊

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>步驟 1： 尋找 TXT 記錄值，並確認

1. 在 Microsoft 365 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
2. 在 [**網域**] 頁面上，選取您的網域，然後選取 [**啟動安裝程式**。 You'll go back to the domains setup wizard to see the specific value you need to add.
    
3. 在 [**驗證網域**] 頁面上選取**改為新增 TXT 記錄**，然後選取 [**下一步**]。
    
4. 複製所顯示的**TXT 值**。 它看起來像這樣： **MS = msXXXXXXXX**。 
    
5. 移至[任何 DNS 主機服務提供者處建立 DNS 記錄](create-dns-records-at-any-dns-hosting-provider.md)，並從若要查看的逐步指示的註冊機構的清單中選取您的 DNS 主機。
    
6. 按照在您的 DNS 主機建立 TXT 記錄 (或 MX 記錄) 的步驟進行，然後回到 Office 365 中驗證網域。

7. 從您的 DNS 主機移除 TXT 記錄 （或 MX 記錄），一旦網域驗證 Office 365 中。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>步驟 2： 找出電子郵件及其他的 MX 記錄值

1. 在 Microsoft 365 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
2. On the **Domains** page, select your domain. 
    
3. Under **Required DNS settings**, you'll see the DNS records to add.
    
    在您的 DNS 主機進行變更時，您會需要讓這些資訊保持可用，這樣您就能複製並貼上這些值。
    
    此頁面所列的 DNS 記錄群組取決於您列在 **[網域用途]** 下的選項。
    
4. 移至[任何 DNS 主機服務提供者處建立 DNS 記錄](create-dns-records-at-any-dns-hosting-provider.md)，然後再從若要查看在該 DNS 主機的網站新增記錄的逐步指示的註冊機構的清單中選取您的 DNS 主機。
    
5. 請在 DNS 主機上遵循相關步驟建立記錄。
