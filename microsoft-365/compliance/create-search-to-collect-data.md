---
title: Create a search
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1aa4ce6e406e4b3a3b72b9d93f651416b1fc65f9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076460"
---
# <a name="create-a-search"></a><span data-ttu-id="59a0a-102">Create a search</span><span class="sxs-lookup"><span data-stu-id="59a0a-102">Create a search</span></span>

<span data-ttu-id="59a0a-103">在案例中的"**搜索"** 选项卡上，可以通过**单击"新建"** 搜索并遵循向导创建新搜索。</span><span class="sxs-lookup"><span data-stu-id="59a0a-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-it-a-description"></a><span data-ttu-id="59a0a-104">命名您的搜索并给它一个描述</span><span class="sxs-lookup"><span data-stu-id="59a0a-104">Name your search and give it a description</span></span>

<span data-ttu-id="59a0a-105">每个带有案例的搜索都应具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="59a0a-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="59a0a-106">您可以选择提供搜索的说明。</span><span class="sxs-lookup"><span data-stu-id="59a0a-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-search-query-and-conditions"></a><span data-ttu-id="59a0a-107">定义搜索查询和条件</span><span class="sxs-lookup"><span data-stu-id="59a0a-107">Define your search query and conditions</span></span>

<span data-ttu-id="59a0a-108">您可以使用预构建的条件卡或使用关键字查询语言 （KQL） 定义关键字查询和搜索的任何条件。</span><span class="sxs-lookup"><span data-stu-id="59a0a-108">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="59a0a-109">有关详细信息，请参阅[生成搜索查询](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="59a0a-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="59a0a-110">选择要从中搜索的保管人</span><span class="sxs-lookup"><span data-stu-id="59a0a-110">Choose the custodians to search from</span></span>

<span data-ttu-id="59a0a-111">定义条件后，需要选择要搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="59a0a-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="59a0a-112">一种方法是指定已添加到要搜索的案例中的保管人。</span><span class="sxs-lookup"><span data-stu-id="59a0a-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="59a0a-113">通过选择保管人，您将对映射到保管人的所有数据源运行搜索。</span><span class="sxs-lookup"><span data-stu-id="59a0a-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="59a0a-114">有关如何将保管人添加到您的案例并管理其数据源的详细信息，请参阅[与保管人合作。](managing-custodians.md)</span><span class="sxs-lookup"><span data-stu-id="59a0a-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="59a0a-115">选择非托管地点</span><span class="sxs-lookup"><span data-stu-id="59a0a-115">Choose non-custodial locations</span></span>

<span data-ttu-id="59a0a-116">在某些情况下，您可能希望搜索未映射到保管人的数据源。</span><span class="sxs-lookup"><span data-stu-id="59a0a-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="59a0a-117">在这种情况下，您可以指定要搜索的位置，或选择搜索特定 Office 365 服务的所有内容位置（例如搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive 业务网站）。</span><span class="sxs-lookup"><span data-stu-id="59a0a-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>