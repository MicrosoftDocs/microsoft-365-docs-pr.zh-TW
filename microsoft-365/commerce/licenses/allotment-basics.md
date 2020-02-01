---
title: 分配基本概念
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: 了解新的分配功能。
ms.openlocfilehash: 22f7c35b1a5baf97fb72f541d57da28adeeffbe4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594684"
---
# <a name="allotment-basics"></a><span data-ttu-id="909e3-103">分配基本概念</span><span class="sxs-lookup"><span data-stu-id="909e3-103">Allotment basics</span></span>

<span data-ttu-id="909e3-104">授權分配可讓您設定授權限制及委派管理的授權指派給只有產品和您所選取的授權限制。</span><span class="sxs-lookup"><span data-stu-id="909e3-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="909e3-105">分配用於群組為基礎的授權指派授權給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="909e3-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="909e3-106">授權限制提供透過多少將授權指派給您的群組中的使用者加入的控制項。</span><span class="sxs-lookup"><span data-stu-id="909e3-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="909e3-107">因此即使作為群組增加中的使用者數目，您可以確保您保持在已為您分配的授權限制內。</span><span class="sxs-lookup"><span data-stu-id="909e3-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="909e3-108">您也可以委派管理您分配。</span><span class="sxs-lookup"><span data-stu-id="909e3-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="909e3-109">委派的分配擁有者存取系統管理中心中，但只能看到並管理自己的分配中的授權。</span><span class="sxs-lookup"><span data-stu-id="909e3-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="909e3-110">這可提供更細微的委派授權管理組織內。</span><span class="sxs-lookup"><span data-stu-id="909e3-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="909e3-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="909e3-111">Prerequisites</span></span>

<span data-ttu-id="909e3-112">您必須符合[群組為基礎之授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)的授權需求。</span><span class="sxs-lookup"><span data-stu-id="909e3-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="909e3-113">您可以使用任何使用者可用的 Office 365 產品的分配：</span><span class="sxs-lookup"><span data-stu-id="909e3-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="909e3-114">Office 套件和獨立的產品</span><span class="sxs-lookup"><span data-stu-id="909e3-114">Office suites and standalone products</span></span>
- <span data-ttu-id="909e3-115">企業和行動性的產品</span><span class="sxs-lookup"><span data-stu-id="909e3-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="909e3-116">Dynamics 365 產品</span><span class="sxs-lookup"><span data-stu-id="909e3-116">Dynamics 365 products</span></span>

<span data-ttu-id="909e3-117">下列產品不能分配與：</span><span class="sxs-lookup"><span data-stu-id="909e3-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="909e3-118">Microsoft 市集應用程式</span><span class="sxs-lookup"><span data-stu-id="909e3-118">Microsoft Store apps</span></span>
- <span data-ttu-id="909e3-119">永久軟體或直接指派給使用者如果沒有任何授權所涉及的軟體。</span><span class="sxs-lookup"><span data-stu-id="909e3-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="909e3-120">Azure 的資源</span><span class="sxs-lookup"><span data-stu-id="909e3-120">Azure resources</span></span>

<span data-ttu-id="909e3-121">您必須是全域或授權管理員] 以開始使用分配。</span><span class="sxs-lookup"><span data-stu-id="909e3-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="909e3-122">快速入門</span><span class="sxs-lookup"><span data-stu-id="909e3-122">Getting started</span></span>

<span data-ttu-id="909e3-123">在只有少量客戶私人預覽] 中使用分配功能。</span><span class="sxs-lookup"><span data-stu-id="909e3-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="909e3-124">如果您有興趣加入，填寫此表單： [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)。</span><span class="sxs-lookup"><span data-stu-id="909e3-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
