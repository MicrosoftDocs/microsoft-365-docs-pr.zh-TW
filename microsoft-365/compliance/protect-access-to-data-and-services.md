---
title: 保護使用者和裝置存取權
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用于保护对 O365 数据和服务的访问的登录页
ms.openlocfilehash: 9fc1691e7e36f994b5d0b8a6a9735fe8ccd8735a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077822"
---
# <a name="protect-user-and-device-access"></a>保護使用者和裝置存取權

保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。 相同的保护可以应用于环境中的其他 SaaS 应用程序，甚至适用于使用 Azure 活动目录应用程序代理发布的本地应用程序。
  
## <a name="step-1-review-recommendations"></a>第 1 步：审查建议

推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>第 2 步：保护管理员帐户和访问权限
用于管理 Office 365 环境的管理帐户包括提升的权限。 这些是黑客和网络攻击者的宝贵目标。 

首先，仅使用管理员帐户进行管理。 管理员应具有用于常规、非管理用途的单独用户帐户，并且仅在必要时使用其管理帐户来完成与其作业功能关联的任务。

通过多重身份验证和条件访问保护管理员帐户。 有关详细信息，请参阅[保护管理员帐户](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。 

接下来，在 Office 365 中配置特权访问管理。 特权访问管理允许对 Office 365 中的特权管理任务进行精细访问控制。 它可以帮助保护您的组织免受可能使用现有特权管理员帐户的违规事件，这些帐户具有对敏感数据的长期访问权限或对关键配置设置的访问。

- [特权访问管理概述](privileged-access-management-overview.md)
- [設定特殊權限存取管理](privileged-access-management-configuration.md)

另一个首要建议是使用专门为管理工作配置的工作站。 这些是仅用于管理任务的专用设备。 请参阅[保护特权访问](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最后，您可以通过在租户中创建两个或多个紧急访问帐户来减轻意外缺乏管理访问权限的影响。 请参阅[在 Azure AD 中管理紧急访问帐户。](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步骤 3：配置建议的标识和设备访问策略
多重身份验证 （MFA） 和条件访问策略是缓解帐户受损和未经授权的访问的强大工具。 我们建议实现一组一起测试的策略。 有关详细信息（包括部署步骤），请参阅[标识和设备访问配置](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)。

 这些策略实现以下功能：
- 木因身份验证
- 條件式存取
- Intune 应用保护（设备的应用和数据保护）
- Intune 设备合规性
- Azure AD Identity Protection

实现 Intune 设备合规性需要设备注册。 通过管理设备，在允许设备访问环境中的资源之前，确保设备是正常运行和合规的。 请参阅[在 Intune 中注册设备进行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步骤 4：配置 SharePoint 设备访问策略

Microsoft 建议您使用设备访问控制保护具有敏感且高度监管内容的 SharePoint 网站中的内容。 有关详细信息，请参阅保护[SharePoint 网站和文件的策略建议。](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)



    

