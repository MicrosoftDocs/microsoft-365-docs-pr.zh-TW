---
title: 使用示例连接器在 Office 365（预览版）中存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器，将 Twitter 数据导入 Office 365。 这样，您就可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的治理。
ms.openlocfilehash: 6780e3fbb53e2326994e03815403c1e5ae0d0616
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076704"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a>使用示例连接器在 Office 365（预览版）中存档 Twitter 数据

用于在 Office 365 中存档 Twitter 数据的示例连接器功能处于预览版。

在 Office 365 中的安全&合规性中心中使用示例连接器从 Twitter 导入和存档数据。 设置和配置示例连接器后，它将连接到组织的 Twitter 帐户（按计划），将项目的内容转换为电子邮件格式，然后将这些项目导入 Office 365 中的邮箱。

导入 Twitter 数据后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略）应用于存储在邮箱中的数据。 例如，您可以使用内容搜索搜索 Twitter 数据，或者将存储数据的邮箱与高级电子数据展示案例中的保管人相关联。 使用示例连接器在 Office 365 中导入和存档 Twitter 数据可以帮助您的组织遵守政府和监管策略。

> [!NOTE]
> 目前，只有 Twitter 和[Facebook 商业页面](archive-facebook-data-with-sample-connector.md)的示例连接器可用于预览。 更多示例连接器即将推出。


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>为 Twitter 设置连接器的先决条件

必须先完成以下先决条件，然后才能在安全&合规性中心中设置和配置示例连接器，以便从组织的 Twitter 帐户导入和存档数据。 

- 您的组织需要一个 Twitter 帐户;设置连接器时需要登录到此帐户。

- 您的组织必须具有有效的 Azure 订阅。 如果没有现有的 Azure 订阅，则可以注册以下选项之一：

    - [注册免费 1 年 Azure 订阅](https://azure.microsoft.com/free) 

    - [注册即用即付 Azure 订阅](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Office 365 订阅中包含的[免费 Azure 活动目录订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全&合规性中心中的示例连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 要同意此请求，请转到[此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全局管理员的凭据登录，然后接受该请求。

- 在"安全&合规性"中设置自定义连接器的用户（在步骤 7 中）必须在 Exchange 联机中分配邮箱导入导出角色。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 您可以将邮箱导入导出角色添加到"联机交换"中的组织管理角色组。 或者，您可以创建一个新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在联机交换中管理角色组"一文[中的"创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色组"](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)部分。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>第 1 步：从 Github 下载预构建的连接器应用包

第一步是下载 Twitter 示例连接器应用的源代码，该应用程序将使用 Twitter API 连接到您的 Twitter 帐户并提取数据，以便将其导入 Office 365。

1. 转到[此 GitHub 站点。](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases) 
2. 在最新版本下，单击**示例连接器.zip**文件。
3. 将 ZIP 文件保存到本地计算机上的位置。 在步骤 4 中将此 zip 文件上载到 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤 2：在 Azure 活动目录中创建应用

下一步是在 Azure 活动目录 （AAD） 中注册新应用。 此应用程序对应于您在步骤 4 中为 Twitter 连接器实现的 Web 应用资源。 

有关分步说明，请参阅[步骤 2：在 Azure 活动目录中创建应用。](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)

在完成此步骤期间（按照分步说明执行），您将将以下信息保存到文本文件中。 这些值将在部署过程中的后续步骤中使用。

- AAD 应用程序 ID
- AAD 应用程序机密
- AAD 应用程序 Uri
- 租户 ID

## <a name="step-3-create-an-azure-storage-account"></a>步骤 3：创建 Azure 存储帐户

为组织部署的 Twitter 连接器将项目从 Twitter 上载到您在此步骤中创建的 Azure 存储位置。 在安全&合规性中心（在步骤 7 中）创建自定义连接器后，Office 365 导入服务将从 Azure 存储位置将 Twitter 数据复制到 Office 365 中的邮箱。 如前面[在"先决条件"](#prerequisites-for-setting-up-a-connector-for-twitter)部分中所述，您必须具有有效的 Azure 订阅才能创建 Azure 存储帐户。

有关分步说明，请参阅[步骤 3：创建 Azure 存储帐户](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。

在完成此步骤（按照分步说明执行）期间，可以保存生成的连接字符串 Uri。 在步骤 4 中在 Azure 中创建 Web 应用资源时使用此字符串。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>步骤 4：在 Azure 中创建 Web 应用资源

下一步是在 Azure 中为 Twitter 连接器创建 Web 应用资源。 

有关分步说明，请参阅[步骤 4：在 Azure 中创建新的 Web 应用资源。](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)

在完成此步骤期间（按照分步说明执行），您将在创建 Web 应用资源时提供以下信息（在完成上述步骤后已复制到文本文件）。

- API机密密钥 – 在完成此步骤期间，您创建此机密;它在步骤 7 中使用。
- 存储帐户连接字符串 – 在步骤 3 中创建 Azure 存储帐户后复制的连接字符串 Uri。
- 租户 Id = 在步骤 2 中在 Azure 活动目录中创建 Twitter 连接器应用后复制的 Office 365 组织的租户 ID。

此外，在此步骤中，您还会上传 SampleConnector.zip 文件（在步骤 1 中下载的文件），以部署 Twitter 连接器应用的源代码。

完成此步骤后，请确保复制 Azure 应用服务 URL（例如。 https://twitterconnector.azurewebsites.net) 您需要使用它来完成步骤 5、步骤 6 和步骤 7）。

## <a name="step-5-create-developer-app-on-twitter"></a>第 5 步：在 Twitter 上创建开发人员应用程序

下一步是在 Twitter 上创建和配置开发人员应用。 您在步骤 7 中创建的自定义连接器使用 Twitter 应用与 Twitter API 交互，以便从组织的 Twitter 帐户获取数据。

有关分步说明，请参阅[步骤 5：创建 Twitter 应用](deploy-twitter-connector.md#step-5-create-the-twitter-app)。

在完成此步骤期间（按照分步说明执行），您可以将以下信息保存到文本文件中。 这些值将用于在步骤 6 中配置 Twitter 连接器应用。

- 推特API密钥
- 推特API密钥
- 推特访问令牌
- 推特访问令牌秘密

## <a name="step-6-configure-the-twitter-connector-app"></a>第 6 步：配置 Twitter 连接器应用

下一步是向在步骤 4 中创建 Azure Web 应用资源时上传的 Twitter 连接器应用添加配置设置。 为此，请访问连接器应用的主页并配置它。

有关分步说明，请参阅[步骤 6：配置连接器 Web 应用](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。

在完成此步骤期间（按照分步说明执行），您将提供以下信息（在完成上述步骤后已复制到文本文件）：

- 推特 API 密钥（在步骤 5 中获得）
- 推特 API 密钥（在步骤 5 中获得）
- 推特访问令牌（在步骤 5 中获得）
- Twitter 访问令牌机密（在步骤 5 中获取）
- Azure 活动目录应用程序 ID（步骤 2 中获取的 AAD 应用程序 ID）
- Azure 活动目录应用程序密钥（步骤 2 中获取的 AAD 应用程序密钥）
- Azure 活动目录应用程序 Uri（步骤 2 中获取的 AAD 应用程序 Uri;例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步骤 7：在安全&合规性中心设置自定义连接器

最后一步是在安全&合规性中心中设置自定义连接器，该连接器将数据从组织的 Twitter 帐户导入 Office 365 中的指定邮箱。 成功完成此步骤后，Office 365 导入服务将开始将数据从 Twitter 导入 Office 365 的过程。 

有关分步说明，请参阅[步骤 7：在安全和合规性中心中设置自定义连接器。](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center) 

在完成此步骤期间（按照分步说明执行），您将提供以下信息（完成这些步骤后已复制到文本文件）。

- Azure 应用服务 URL（在步骤 4 中获取;例如，https://twitterconnector.azurewebsites.net)
- API 机密密钥（您在步骤 4 中创建）
