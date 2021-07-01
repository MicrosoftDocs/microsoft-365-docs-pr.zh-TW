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
# <a name="find-your-domain-registrar"></a><span data-ttu-id="d4949-103">尋找您的網域註冊機構</span><span class="sxs-lookup"><span data-stu-id="d4949-103">Find your domain registrar</span></span>

 <span data-ttu-id="d4949-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="d4949-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

## <a name="domain-registrar"></a><span data-ttu-id="d4949-105">網域註冊機構</span><span class="sxs-lookup"><span data-stu-id="d4949-105">Domain registrar</span></span>

### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="d4949-106">尋找您的網域名稱註冊機構</span><span class="sxs-lookup"><span data-stu-id="d4949-106">Find your domain name registrar</span></span>

> [!NOTE]
> <span data-ttu-id="d4949-107">只有以 *.COM*、*.NET* 和 *.EDU* 結尾的網域才能使用這個工具。</span><span class="sxs-lookup"><span data-stu-id="d4949-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="d4949-p101">在 [InterNIC 搜尋頁面](https://go.microsoft.com/fwlink/p/?LinkId=402770)的 **[Whois Search] (Whois 搜尋)** 方塊中，輸入您的網域，例如 *contoso.com。*</span><span class="sxs-lookup"><span data-stu-id="d4949-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span>

2. <span data-ttu-id="d4949-110">選取 **[Domain]** (網域) 選項，然後選取 **[Submit]** (提交)。</span><span class="sxs-lookup"><span data-stu-id="d4949-110">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="d4949-p102">在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Registrar]** (註冊機構) 項目。此項目列出的組織就是為您的網域提供註冊服務的組織。</span><span class="sxs-lookup"><span data-stu-id="d4949-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span>

## <a name="dns-hosting-provider"></a><span data-ttu-id="d4949-113">DNS 主機服務提供者</span><span class="sxs-lookup"><span data-stu-id="d4949-113">DNS hosting provider</span></span>

### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="d4949-114">尋找您的 DNS 主機服務提供者</span><span class="sxs-lookup"><span data-stu-id="d4949-114">Find your DNS hosting provider</span></span>

> [!NOTE]
> <span data-ttu-id="d4949-115">只有以 *.COM*、*.NET* 和 *.EDU* 結尾的網域才能使用這個工具。</span><span class="sxs-lookup"><span data-stu-id="d4949-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="d4949-p103">在 [InterNIC 搜尋頁面](https://go.microsoft.com/fwlink/p/?LinkId=402770)的 **[Whois Search]** (Whois 搜尋) 方塊中，輸入您的網域，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d4949-p103">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span>

2. <span data-ttu-id="d4949-118">選取 **[Domain]** (網域) 選項，然後選取 **[Submit]** (提交)。</span><span class="sxs-lookup"><span data-stu-id="d4949-118">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="d4949-119">在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Name Server]** (名稱伺服器) 項目。</span><span class="sxs-lookup"><span data-stu-id="d4949-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span>

4. <span data-ttu-id="d4949-p104">複製出現在冒號 (:) 之後的名稱伺服器 (NS) 資訊，然後貼到頁面上方的 **[Search]** (搜尋) 方塊中。選取 **Nameserver** (名稱伺服器)，然後選取 **[Submit]** (提交)。</span><span class="sxs-lookup"><span data-stu-id="d4949-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>

5. <span data-ttu-id="d4949-p105">在 **[Whois Search Results]** (Whois 搜尋結果) 頁面，尋找 **[Registrar]** (註冊機構) 項目。此項目會列出您的 DNS 主機服務提供者，此 DNS 提供者擁有您網域的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4949-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span>

---

