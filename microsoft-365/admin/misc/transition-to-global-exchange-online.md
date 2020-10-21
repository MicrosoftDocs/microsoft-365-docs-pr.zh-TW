---
title: 更新您的 MX 記錄以轉換為全域 Exchange Online 服務
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何從 Microsoft Cloud 德國 Exchange Online 轉換為全域 Exchange Online 服務
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644852"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="89534-103">更新您的 MX 記錄以轉換為全域 Exchange Online 服務</span><span class="sxs-lookup"><span data-stu-id="89534-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="89534-104">登入[Microsoft 365 管理入口網站](https://admin.microsoft.com)，然後移至 [**設定**] [  >  **網域**]。</span><span class="sxs-lookup"><span data-stu-id="89534-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="89534-105">每個網域的狀態將會顯示在右側。</span><span class="sxs-lookup"><span data-stu-id="89534-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="89534-106">如果您組織的網域指向 [Microsoft Cloud 德國 Exchange Online]，您將需要更新您的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="89534-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="89534-107">按一下網域，然後按一下 [偵測 **到 DNS 錯誤]，按一下這裡以進行查看**。</span><span class="sxs-lookup"><span data-stu-id="89534-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="89534-108">此頁面可讓您向您說明如何修正 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="89534-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="89534-109">如果您網域的註冊機構使用 [網域 Connect](../setup/add-domain.md#registrars-with-domain-connect)，您可以按一下 [修正我的記錄] 上方的。</span><span class="sxs-lookup"><span data-stu-id="89534-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="89534-110">否則，您可以依照嚮導中的連結，進行註冊機的逐步 **指示** 。</span><span class="sxs-lookup"><span data-stu-id="89534-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>