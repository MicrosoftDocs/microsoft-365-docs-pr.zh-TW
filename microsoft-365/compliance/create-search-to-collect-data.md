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
# <a name="create-a-search"></a>Create a search

在案例中的"**搜索"** 选项卡上，可以通过**单击"新建"** 搜索并遵循向导创建新搜索。

## <a name="name-your-search-and-give-it-a-description"></a>命名您的搜索并给它一个描述

每个带有案例的搜索都应具有唯一的名称。 您可以选择提供搜索的说明。 

## <a name="define-your-search-query-and-conditions"></a>定义搜索查询和条件

您可以使用预构建的条件卡或使用关键字查询语言 （KQL） 定义关键字查询和搜索的任何条件。 有关详细信息，请参阅[生成搜索查询](building-search-queries.md)。

## <a name="choose-the-custodians-to-search-from"></a>选择要从中搜索的保管人

定义条件后，需要选择要搜索的位置。 一种方法是指定已添加到要搜索的案例中的保管人。 通过选择保管人，您将对映射到保管人的所有数据源运行搜索。 有关如何将保管人添加到您的案例并管理其数据源的详细信息，请参阅[与保管人合作。](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>选择非托管地点

在某些情况下，您可能希望搜索未映射到保管人的数据源。 在这种情况下，您可以指定要搜索的位置，或选择搜索特定 Office 365 服务的所有内容位置（例如搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive 业务网站）。