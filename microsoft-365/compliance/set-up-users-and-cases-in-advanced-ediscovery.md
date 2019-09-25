---
title: 在 Office 365 高级电子数据展示中设置用户和案例
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、创建案例以及将用户分配给 Office 365 高级电子数据展示中的案例。  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077512"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中设置用户和案例

本主题介绍如何为 Office 365 高级电子数据展示设置用户和案例。
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="prerequisites"></a>必要條件

在高级电子数据展示中设置案例和用户之前，需要以下操作：
  
- 要使用高级电子数据展示分析用户的数据，必须为该用户（数据的保管人）分配 Office 365 E5 许可证。 或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。 分配给案例并使用高级电子数据展示分析数据的管理员和合规官不需要 E5 许可证。 
    
- 您必须是 Office 365 安全&amp;合规性中心中的电子数据展示管理器角色组的成员，才能创建电子数据展示案例并将其成员添加到该案例中。 要将自己添加到安全&amp;合规性中心中的电子数据展示管理器角色组，您必须是 Office 365 组织中的全球管理员。 如果您不是全局管理员，则必须要求全局管理员将您添加到电子数据展示管理器角色组。 如需詳細資訊，請參閱：
    
  - [Microsoft 365 安全&amp;合规性中心的权限](/security/office-365-security/protect-against-threats.md)
    
  - [在 Microsoft 365 安全&amp;合规性中心分配电子数据展示权限](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>第 1 步：分配用户电子数据展示权限

第一步是在安全&amp;合规性中心向用户分配需求权限，以便他们可以将我添加为电子数据展示案例的成员。 将用户添加为安全&amp;合规性中心案例的成员后，他们将能够在高级电子数据展示中访问该案例。
  
要为用户分配必要的权限，以便他们可以添加为电子数据展示案例的成员，请参阅[Microsoft 365&amp;安全合规性中心中的电子数据展示案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步骤 1。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>第 2 步：创建电子数据展示案例并添加成员

下一步是在安全&amp;合规性中心创建新的电子数据展示案例并添加成员。 然后，案例的成员将能够访问高级电子数据展示中的案件。
  
1. 要创建新的电子数据展示案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-2-create-a-new-case)中的步骤 2。
    
2. 要将成员添加到电子数据展示案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-3-add-members-to-a-case)中的步骤 3
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>第 3 步：在高级电子数据展示中进行案例展示

创建电子数据展示案例并添加成员后，您（或案例中的任何成员）可以访问高级电子数据展示中的相应案例。 要访问高级电子数据展示中的案例，请参阅 Microsoft [365 安全&amp;合规性中心中电子数据展示案例](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)中的步骤 8。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[準備安裝](prepare-data-for-advanced-ediscovery.md)
 
