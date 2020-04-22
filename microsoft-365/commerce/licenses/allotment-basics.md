---
title: 服務配額基礎
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
description: 深入瞭解新的服務配額功能。
ms.openlocfilehash: d1f926165678b57ec46195d525f2fcdaa6976501
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632410"
---
# <a name="allotment-basics"></a><span data-ttu-id="e4a8e-103">服務配額基礎</span><span class="sxs-lookup"><span data-stu-id="e4a8e-103">Allotment basics</span></span>

<span data-ttu-id="e4a8e-104">授權服務配額可讓您將授權指派的授許可權制，只委派給您所選取的產品和授許可權制。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="e4a8e-105">服務配額使用以群組為基礎的授權，將授權指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="e4a8e-106">授許可權制可讓您新增控制指派給群組中使用者的授權數目。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="e4a8e-107">因此，即使您的群組中的使用者數目增加，您也可以確保您保持在您為您的服務配額所設定的授許可權制內。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="e4a8e-108">您也可以委派對您的服務配額的管理。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="e4a8e-109">委派的服務配額可取得系統管理員中心的存取權，但只能查看和管理其擁有的服務配額中的授權。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="e4a8e-110">這可讓您的組織內的授權管理更精細委派。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4a8e-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="e4a8e-111">Prerequisites</span></span>

<span data-ttu-id="e4a8e-112">您必須符合以[群組為基礎之授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)的授權需求。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="e4a8e-113">您可以搭配任何可供使用者使用的產品配額：</span><span class="sxs-lookup"><span data-stu-id="e4a8e-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="e4a8e-114">Office 套件和獨立產品</span><span class="sxs-lookup"><span data-stu-id="e4a8e-114">Office suites and standalone products</span></span>
- <span data-ttu-id="e4a8e-115">企業和行動產品</span><span class="sxs-lookup"><span data-stu-id="e4a8e-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="e4a8e-116">Dynamics 365 產品</span><span class="sxs-lookup"><span data-stu-id="e4a8e-116">Dynamics 365 products</span></span>

<span data-ttu-id="e4a8e-117">下列產品無法與服務配額搭配使用：</span><span class="sxs-lookup"><span data-stu-id="e4a8e-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="e4a8e-118">Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="e4a8e-118">Microsoft Store apps</span></span>
- <span data-ttu-id="e4a8e-119">永久軟體，或直接指派給使用者的軟體（如果沒有相關授權）。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="e4a8e-120">Azure 資源</span><span class="sxs-lookup"><span data-stu-id="e4a8e-120">Azure resources</span></span>

<span data-ttu-id="e4a8e-121">您必須是通用或授權的系統管理員，才可開始使用服務配額。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="e4a8e-122">快速入門</span><span class="sxs-lookup"><span data-stu-id="e4a8e-122">Getting started</span></span>

<span data-ttu-id="e4a8e-123">僅限少數客戶可以使用「服務配額」功能的私人預覽。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="e4a8e-124">如果您想要加入，請填寫此表單： [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)。</span><span class="sxs-lookup"><span data-stu-id="e4a8e-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
