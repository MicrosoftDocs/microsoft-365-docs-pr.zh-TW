---
title: 尋找您的網域註冊機構
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: 了解如何使用 InterNIC 搜尋來尋找您的網域註冊機構和 DNS 主機服務提供者。
ms.openlocfilehash: 77e4776946d51cb4f8dfe1a746e85d74a9e0a700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228024"
---
# <a name="find-your-domain-registrar"></a>尋找您的網域註冊機構

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。

## <a name="domain-registrar"></a>網域註冊機構

### <a name="find-your-domain-name-registrar"></a>尋找您的網域名稱註冊機構

> [!NOTE]
> 只有以 *.COM*、*.NET* 和 *.EDU* 結尾的網域才能使用這個工具。

1. 在 [InterNIC 搜尋頁面](https://go.microsoft.com/fwlink/p/?LinkId=402770)的 **[Whois Search] (Whois 搜尋)** 方塊中，輸入您的網域，例如 *contoso.com。*

2. 選取 **[Domain]** (網域) 選項，然後選取 **[Submit]** (提交)。

3. 在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Registrar]** (註冊機構) 項目。此項目列出的組織就是為您的網域提供註冊服務的組織。

## <a name="dns-hosting-provider"></a>DNS 主機服務提供者

### <a name="find-your-dns-hosting-provider"></a>尋找您的 DNS 主機服務提供者

> [!NOTE]
> 只有以 *.COM*、*.NET* 和 *.EDU* 結尾的網域才能使用這個工具。

1. 在 [InterNIC 搜尋頁面](https://go.microsoft.com/fwlink/p/?LinkId=402770)的 **[Whois Search]** (Whois 搜尋) 方塊中，輸入您的網域，例如 contoso.com。

2. 選取 **[Domain]** (網域) 選項，然後選取 **[Submit]** (提交)。

3. 在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Name Server]** (名稱伺服器) 項目。

4. 複製出現在冒號 (:) 之後的名稱伺服器 (NS) 資訊，然後貼到頁面上方的 **[Search]** (搜尋) 方塊中。選取 **Nameserver** (名稱伺服器)，然後選取 **[Submit]** (提交)。

5. 在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Registrar]** (註冊機構) 項目。此項目會列出您的 DNS 主機服務提供者，此 DNS 提供者擁有您網域的名稱伺服器。

---

