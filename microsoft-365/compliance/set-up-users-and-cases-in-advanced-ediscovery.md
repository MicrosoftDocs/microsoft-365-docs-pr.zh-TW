---
title: 在高級電子檔探索中設定使用者和案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '瞭解如何設定使用者角色、建立案例，以及在高級 eDiscovery 中將使用者指派給案例。  '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6cfc8e313816c0c01512dd0d4b71f1dbbd6e6505
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819173"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （古典）中設定使用者和案例

本主題說明如何針對高級 eDiscovery （古典）設定使用者和案例。
  
> [!IMPORTANT]
> 隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。 如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。 進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。 若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。 
  
## <a name="requirements-to-set-up-users-and-cases"></a>設定使用者和案例的需求

在 [Advanced eDiscovery] 中設定案例和使用者之前，需要下列專案：
  
- 若要使用高級電子檔探索來分析使用者的資料，則必須將 Office 365 E5 授權指派給使用者（資料的保管人）。 或者，您可以將高級 eDiscovery 獨立授權指派給使用 Office 365 E1 或 E3 授權的使用者。 獲指派案例的系統管理員和合規性監察官，以及使用高級 eDiscovery 來分析資料，不需要 E5 授權。 
    
- 您必須是安全性與合規性中心內 eDiscovery 管理員角色群組的成員， &amp; 才可建立 eDiscovery 案例並新增成員。 若要在安全性與合規性中心將自己新增至 eDiscovery 管理員角色群組 &amp; ，您必須是組織中的全域系統管理員。 如果您不是全域系統管理員，則必須要求全域系統管理員將您新增至 eDiscovery 管理員角色群組。 如需詳細資訊，請參閱：
    
  - [Microsoft 365 安全性與 &amp; 合規性中心的許可權](~/security/office-365-security/protect-against-threats.md)
    
  - [在 Microsoft 365 安全性與 &amp; 合規性中心指派 eDiscovery 許可權](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>步驟1：指派使用者的 eDiscovery 許可權

第一步是在安全性與合規性中心指派要求許可權， &amp; 讓他們可以新增為 eDiscovery 案例的成員。 在安全性與合規性中心內將使用者新增為案例的成員後 &amp; ，他們就能在「高級 eDiscovery」中存取案例。
  
若要指派使用者必要的許可權，使其可以新增為 eDiscovery 案例的成員，請參閱[Microsoft 365 安全性與 &amp; 合規性中心的 eDiscovery 案例中的](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)步驟1。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>步驟2：建立電子檔探索案例並新增成員

下一步是在安全性 & 合規性中心建立新的 eDiscovery 案例，並新增成員。 案例的成員就能在「高級 eDiscovery」中存取案例。
  
1. 若要建立新的 eDiscovery 案例，請參閱[核心 eDiscovery 開始使用](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)的步驟3。

2. 若要將成員新增至 eDiscovery 案例，請參閱[核心 EDiscovery 快速入門中的](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)步驟4

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>步驟3：在「高級電子檔探索」中開始案例

在您建立 eDiscovery 案例並新增成員之後，您（或任何案例的任何成員）都可以在高級 eDiscovery 中存取對應案例。 若要在高級 eDiscovery 中存取案例，請參閱[在「高級 ediscovery」中存取案例](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)。
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[準備資料以供高級 eDiscovery （經典）](prepare-data-for-advanced-ediscovery.md)
 