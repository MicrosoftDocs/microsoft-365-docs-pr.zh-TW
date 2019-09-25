---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何为 Office 365 进行联机交换、业务 Skype、共享点联机和一个业务一个驱动器的客户密钥设置。 使用客户密钥，您可以控制组织的加密密钥，然后将 Office 365 配置为使用它们在 Microsoft 的数据中心中静态加密您的数据。
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076590"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>使用客戶金鑰控制 Office 365 中的資料

使用客户密钥，您可以控制组织的加密密钥，然后将 Office 365 配置为使用它们在 Microsoft 数据中心中静态加密您的数据。 换句话说，客户密钥允许客户使用密钥添加属于他们的加密层。 存放的資料包括 Exchange Online 資料和儲存在信箱的商務用 Skype 資料，以及儲存在 SharePoint Online 中和商務用 OneDrive 中的檔案。
  
必须先设置 Azure，然后才能将客户密钥用于 Office 365。 本主题介绍创建和配置所需的 Azure 资源所需的步骤，然后提供在 Office 365 中设置客户密钥的步骤。 完成 Azure 设置后，将确定要分配给组织中的邮箱和文件的策略，以及哪些密钥。 未为其分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。 有关客户密钥的详细信息，或有关一般概述的信息，请参阅[Office 365 常见问题解答的客户密钥](service-encryption-with-customer-key-faq.md)。
  
> [!IMPORTANT]
> 我们强烈建议您遵循本主题中的最佳做法。 这些**被称为TIP**和**重要。** 通过客户密钥，您可以控制根加密密钥，其范围可以与整个组织一样大。 这意味着使用这些密钥所犯的错误可能会产生广泛影响，并可能导致服务中断或不可撤销地丢失数据。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>在开始设置客户密钥之前
<a name="Beforeyoustart"> </a>

在开始之前，请确保为您的组织获得适当的许可。 Office 365 中的客户密钥在 Office 365 E5 或高级合规性 SKU 中提供。
  
然后，为了了解本主题中的概念和过程，应查看[Azure 密钥保管库](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。 此外，还要熟悉 Azure 中使用的术语，例如[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)。
  
要提供有关客户密钥（包括文档）的反馈，请将您的想法、建议和观点发送给customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>为 Office 365 设置客户密钥的概述
<a name="Overview"> </a>

要设置客户密钥，您将完成这些任务。 本主题的其余部分提供每个任务的详细说明，或链接到流程中每个步骤的详细信息。
  
**在 Azure 和 Microsoft 快速通道中：**
  
您将通过远程连接到 Azure PowerShell 来完成这些任务的大部分。 为获得最佳效果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。
  
- [创建新的 Azure 订阅](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [注册 Azure 订阅以使用强制保留期](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    注册可能需要一到五个工作日。
    
- [提交激活 Office 365 的客户密钥的请求](controlling-your-data-using-customer-key.md#FastTrack)
    
    创建两个新的 Azure 订阅后，需要通过填写托管在 Microsoft FastTrack 门户中的 Web 窗体来提交相应的客户密钥产品/服务请求。 **FastTrack 团队不提供客户密钥方面的帮助。Office只是使用FastTrack门户，允许您提交表格，并帮助我们跟踪客户密钥的相关优惠。**
  
提交客户密钥产品/服务后，Microsoft 会审核您的请求，并通知您何时可以继续其余设置任务。 此过程最多可能需要五个工作日。
    
- [在每个订阅中创建高级 Azure 密钥保管库](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [为每个密钥保管库分配权限](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [在密钥保管库上启用并确认软删除](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [通过创建或导入密钥，向每个密钥保管库添加密钥](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [检查密钥的恢复级别](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [备份 Azure 密钥保管库](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [验证 Azure 密钥保管库配置设置](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [获取每个 Azure 密钥保管库密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**在 Office 365 中：**
  
交换在线和 Skype 业务：
  
- [创建数据加密策略 （DEP），以便与 Exchange 在线和 Skype 业务一起使用](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [将 DEP 分配给邮箱](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [验证邮箱加密](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
共享点在线和一个驱动器的业务：
  
- [为每个共享点联机和一个业务地理创建数据加密策略 （DEP）](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [验证针对企业的组网站、团队网站和 OneDrive 的加密](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure 密钥保管库和 Microsoft 客户密钥快速跟踪中完成任务
<a name="AzureSteps"> </a>

在 Azure 密钥保管库中完成这些任务，以便为 Office 365 设置客户密钥。 无论您打算为联机交换和 Skype 进行联机交换或共享点联机和 OneDrive 业务或 Office 365 中所有受支持的服务，您都需要完成这些步骤。
  
### <a name="create-two-new-azure-subscriptions"></a>创建新的 Azure 订阅
<a name="Create2newsubs"> </a>

客户密钥需要两个 Azure 订阅。 最佳做法是 Microsoft 建议您创建新的 Azure 订阅，以便与客户密钥一起使用。 Azure 密钥保管库密钥只能为同一 Azure 活动目录 （AAD） 租户中的应用程序授权，必须使用与 Office 365 组织一起使用的相同 Azure AD 租户创建新订阅，其中将分配 IP。 例如，在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户。 有关详细步骤，请参阅[将 Azure 注册为组织](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客户密钥需要每个数据加密策略 （DEP） 两个密钥。 为此，必须创建两个 Azure 订阅。 最佳做法是，Microsoft 建议组织中的单独成员在每个订阅中配置一个密钥。 此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。 这样可保护您的组织，以防您的某个操作员意外、故意或恶意删除或以其他方式错误管理他们负责的密钥。 <br/> 我们建议您设置仅用于管理 Azure 密钥保管库资源以便与客户密钥一起使用的新 Azure 订阅。 可以为组织创建的 Azure 订阅数没有实际限制。 遵循这些最佳实践将最大限度地减少人为错误的影响，同时帮助管理客户密钥使用的资源。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交激活 Office 365 的客户密钥的请求
<a name="FastTrack"> </a>

完成 Azure 步骤后，需要在[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交产品/服务请求。 通过 FastTrack Web 门户提交请求后，Microsoft 将验证您提供的 Azure 密钥保管库配置数据和联系信息。 您在产品/服务表单中针对组织授权人员做出的选择对于完成客户密钥注册至关重要且必要。 您在表单中选择的组织官员将用来确保撤销和销毁客户密钥数据加密策略中使用的所有密钥的任何请求的真实性。 您需要执行此步骤一次，以激活联机交换的客户密钥和用于业务覆盖范围的 Skype，第二次激活用于 SharePoint 联机和 OneDrive 的业务的客户密钥。
  
要提交要约以激活客户密钥，请完成以下步骤：
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。
    
2. 登录后，浏览到**仪表板**。
    
3. 选择**优惠，** 并查看当前优惠列表。
    
4. 选择适用于您的优惠**的更多功能：** 
    
  - **交换在线和 Skype 业务：** 选择有关**交换产品/服务的客户密钥****了解有关详细信息。** 
    
  - **共享点在线和一个驱动器的业务：** 选择了解有关**SharePoint 和 OneDrive 商业产品/服务的客户密钥****的更多详细信息。** 
    
5. 在"**产品/服务详细信息"** 页上，**选择"创建请求"。**
    
6. 填写所有适用的详细信息，并在优惠表格上提供所要求的信息。 特别注意您要授权组织的官员批准永久和不可逆转地销毁加密密钥和数据的选择。 填写完表单后，**选择"提交"。**
    
    一旦 Microsoft 收到您的请求通知，此过程最多可能需要五个工作日。
    
7. 继续以下强制保留期部分。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期
<a name="RegisterSubsforMRP"> </a>

根加密密钥的临时或永久丢失可能会对服务操作造成极大的干扰甚至灾难性后果，并可能导致数据丢失。 因此，客户密钥中使用的资源需要强大的保护。 与客户密钥一起使用的所有 Azure 资源都提供默认配置以外的保护机制。 Azure 订阅可以标记或注册，以防止立即取消和不可撤销。 这称为注册强制保留期。 注册 Azure 订阅以进行强制保留期所需的步骤需要与 Office 365 团队协作。 此过程可能需要 1 到 5 个工作日。 以前，这有时被称为"不取消"。
  
在联系 Office 365 团队之前，必须对与客户密钥一起使用的每个 Azure 订阅执行以下步骤：
  
1. 使用 Azure PowerShell 登录到 Azure 订阅。 有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
2. 运行注册 Azure Rm 提供程序功能 cmdlet 以注册订阅以使用强制保留期。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. 请与 Microsoft 联系，以完成该过程。 对于业务团队的 SharePoint 和 OneDrive，[请联系spock@microsoft.com。](mailto:spock@microsoft.com) 如需在线交换和 Skype 业务，[请联系exock@microsoft.com。](mailto:exock@microsoft.com) 完成此过程的服务级别协议 （SLA） 是 Microsoft 收到通知（和验证）您已注册订阅以使用强制保留期后五个工作日。 在电子邮件中包括以下内容：
    
    **主题**：\<*租户完全限定域名*的客户密钥\> 
    
    **正文：** 您希望为其最终确定强制保留期的订阅 ID。 
    
4. 收到 Microsoft 通知注册已完成后，请通过运行 Get-Azure RmProvider 功能 cmdlet 来验证注册状态，如下所示：
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. 验证 Get-AzureRmProviderFeature cmdlet 中的**注册状态**属性是否**返回"已注册"** 的值后，运行以下命令以完成此过程：
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库
<a name="CreateKeyVault"> </a>

创建密钥保管库的步骤在[Azure 密钥保管库入门](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)中记录，该保管库将指导您安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建其中的密钥保管库。资源组。
  
创建密钥保管库时，必须选择 SKU：标准库或高级库。 标准 SKU 允许使用软件保护 Azure 密钥保管库密钥 - 没有硬件安全模块 （HSM） 密钥保护 - 高级 SKU 允许使用 HSM 来保护密钥保管库密钥。 客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议您仅使用高级 SKU。 任一类型密钥的操作成本相同，因此成本的唯一区别是每个受 HSM 保护的密钥的每月成本。 有关详细信息，请参阅[密钥保管库定价。](https://azure.microsoft.com/pricing/details/key-vault/) 
  
> [!IMPORTANT]
> 将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，并且仅使用标准 SKU 密钥保管库和密钥进行测试和验证。 
  
对于将使用客户密钥的每个 Office 365 服务，在创建的两个 Azure 订阅中为每个订阅创建一个密钥保管库。 例如，对于仅为业务进行交换和 Skype 或仅为业务共享点和 OneDrive，您将只创建一对保管库。 要启用联机交换和共享点联机的客户密钥，您将创建两对密钥保管库。
  
对密钥保管库使用命名约定，该约定反映了将关联保管库的 DEP 的预期用途。 有关命名约定建议，请参阅下面的最佳实践部分。
  
为每个数据加密策略创建一组单独的成对保管库。 对于 Exchange Online，当您将策略分配给邮箱时，您将选择数据加密策略的范围。 邮箱只能分配一个策略，并且您最多只能创建五十个策略。 对于 SharePoint Online，策略的范围是组织内地理位置或地理位置中的所有数据。
  
创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量（虽然非常小），密钥保管库日志记录（如果启用）也会生成存储的数据。 作为最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，管理与将管理所有相关客户密钥资源的管理员集保持一致。
  
> [!IMPORTANT]
> 为了最大限度地提高可用性，密钥保管库应位于靠近 Office 365 服务的区域。 例如，如果您的 Exchange 在线组织位于北美，请将密钥保管库放在北美。 如果您的 Exchange 在线组织位于欧洲，请将您的关键保管库放在欧洲。<br/>对密钥保管库使用通用前缀，并包括密钥保管库和密钥的使用和范围的缩写（例如，对于保管库将位于北美的 Contoso SharePoint 服务，可能的名称对是 Contoso-O365SP-NA-VaultA1 和康托索-O365SP-NA-VaultA2。 保管库名称是 Azure 中的全局唯一字符串，因此您可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需名称。 自 2017 年 7 月起，无法更改保管库名称，因此最佳做法是制定书面设置计划，并使用第二个人验证计划是否正确执行。<br/>如果可能，在非配对区域中创建保管库。 配对的 Azure 区域跨服务失败域提供高可用性。 因此，区域对可以被视为彼此的备份区域。 这意味着放置在一个区域中的 Azure 资源通过配对区域自动获得容错能力。 因此，为 DEP 中使用的两个区域选择区域，其中区域已配对意味着总共只有两个可用性区域处于使用状态。 大多数地理位置只有两个区域，因此尚无法选择非配对区域。 如果可能，为与 DEP 一起使用的两个保管库选择两个非配对区域。 这得益于四个可用区域。 有关详细信息，请参阅[业务连续性和灾难恢复 （BCDR）：](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)当前区域对列表的 Azure 配对区域。 
  
### <a name="assign-permissions-to-each-key-vault"></a>为每个密钥保管库分配权限
<a name="KeyVaultPerms"> </a>

对于每个密钥保管库，您需要为客户密钥定义三组单独的权限，具体取决于您的实现。 例如，您需要为以下各项定义一组权限：
  
- **关键保管库管理员，** 将执行对组织密钥保管库的日常管理。 这些任务包括备份、创建、获取、导入、列出和恢复。 
    
    > [!IMPORTANT]
    > 分配给密钥保管库管理员的权限集不包括删除密钥的权限。 这是有意的，也是一项重要的做法。 删除加密密钥通常不会完成，因为这样做会永久销毁数据。 最佳做法是，默认情况下不要向密钥保管库管理员授予此权限。 相反，请为关键保管库参与者保留此项，并且仅在了解对后果的明确理解后，才将其短期分配给管理员。 
  
    要将这些权限分配给 Office 365 组织中的用户，请使用 Azure PowerShell 登录到 Azure 订阅。 有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
- 运行设置 AzureRmKeyVault 访问策略 cmdlet 以分配必要的权限。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  例如：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- 可以更改 Azure 密钥保管库本身权限**的主要保管库参与者。** 当员工离开或加入您的团队时，或者在密钥保管库管理员合法需要删除或还原密钥的权限的极罕见情况下，您需要更改这些权限。 需要授予这组密钥保管库参与者在密钥保管**库中的参与者**角色。 可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅[使用基于角色的访问控制来管理对 Azure 订阅资源的访问。](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 创建订阅的管理员具有隐式此访问权限，以及将其他管理员分配给参与者角色的能力。
    
- 如果您打算将客户密钥与联机交换和 Skype 业务使用，则需要授予 Office 365 权限，以代表 Exchange Online 和 Skype 进行业务使用密钥保管库。 同样，如果您打算将客户密钥与 SharePoint Online 和 OneDrive 用于业务，则需要添加 Office 365 的权限，以便代表 SharePoint Online 和 OneDrive 代表企业使用密钥保管库。 要授予 Office 365 权限，请使用以下语法运行**Set-AzureRmKeyVault 访问策略**cmdlet： 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    其中：
    
  - *保管库名称*是您创建的密钥保管库的名称。 
    
  - 对于联机交换和 Skype 业务，将*Office 365 应用 ID*替换为`00000002-0000-0ff1-ce00-000000000000`
    
  - 对于共享点在线和一个驱动器业务，将*Office 365 应用 ID*替换为`00000003-0000-0ff1-ce00-000000000000`
    
  示例：为"联机交换"和"业务 Skype"设置权限：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  示例：为"在线共享点"和"一个驱动器"设置业务共享点权限
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>在密钥保管库上启用并确认软删除
<a name="SoftDelete"> </a>

当您可以快速恢复密钥时，由于意外或恶意删除的密钥，您不太可能遇到扩展的服务中断。 您需要启用此配置（称为"软删除"），然后才能将密钥与客户密钥一起使用。 启用软删除允许您在删除后的 90 天内恢复密钥或保管库，而无需从备份中还原它们。
  
要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用 Windows 电源外壳登录到 Azure 订阅。 有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。
    
2. 运行[获取 Azure RmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。 在此示例中，*保管库名称*是启用软删除的密钥保管库的名称： 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. 通过运行**Get-Azure RmKeyVault** cmdlet，确认为密钥保管库配置了软删除。 如果为密钥保管库正确配置了软删除，则启用软删除？属性返回**的值为 True**： 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥，向每个密钥保管库添加密钥
<a name="AddKeystoKeyVault"> </a>

有两种方法可以将密钥添加到 Azure 密钥保管库;例如，可通过以下方法将密钥添加到 Azure 密钥保管库。可以直接在密钥保管库中创建密钥，也可以导入密钥。 直接在密钥保管库中创建密钥是不太复杂的方法，而导入密钥可以完全控制密钥的生成方式。
  
要直接在密钥保管库中创建密钥，请运行[Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet，如下所示： 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：
  
-  *保管库名称*是要在其中创建密钥的密钥保管库的名称。 
    
-  *键名*是要为新密钥提供的名称。 
    
    > [!TIP]
    > 使用与上文所述的类似命名约定对密钥保管库命名密钥。 这样，在仅显示键名的工具中，字符串是自描述的。 
  
- 如果要使用 HSM 保护密钥，请确保指定**HSM**作为_目标_参数的值，否则，请**指定"软件"。**
    
For example,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

要将密钥直接导入密钥保管库，需要具有 Thales nShield 硬件安全模块。
  
有些组织喜欢使用这种方法来确定其密钥的来源，此方法还提供以下内容：
  
- 用于导入的工具集包括来自 Thales 的证明，证明用于加密您生成的密钥的密钥交换密钥 （KEK） 不可导出，并且是在 Thales 制造的真实 HSM 中生成的。
    
- 该工具集包括来自 Thales 的证明，证明 Azure 密钥保管库安全世界也是在 Thales 制造的真实 HSM 上生成的。 这个证明证明你，微软也使用真正的泰雷兹硬件。
    
请与您的安全小组核实，以确定是否需要上述证明。 有关在本地创建密钥并将其导入密钥保管库的详细步骤，请参阅[如何为 Azure 密钥保管库生成和传输受 HSM 保护的密钥。](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) 使用 Azure 说明在每个密钥保管库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 要求将 Azure 密钥保管库订阅设置为"不取消"，并且启用了客户密钥使用的密钥。 您可以通过查看密钥上的恢复级别来确认这一点。
  
要检查密钥的恢复级别，请在 Azure PowerShell 中运行获取 AzureKeyVaultKey cmdlet，如下所示：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

如果"_恢复级别"_ 属性**返回"可恢复"保护订阅**的值以外的任何内容，则需要查看本主题，并确保已执行所有步骤将订阅放在"不取消"列表上，并在每个密钥保管库上启用了软删除。
  
### <a name="backup-azure-key-vault"></a>备份 Azure 密钥保管库
<a name="BackupAzureKeyVaultkeys"> </a>

在创建密钥或更改密钥后立即执行备份并存储备份副本，包括联机和脱机备份。 脱机副本不应连接到任何网络，例如在物理安全或商业存储设施中。 备份的至少一个副本应存储在发生灾难时可访问的位置。 如果密钥保管库密钥被永久销毁或无法操作，备份 blob 是还原密钥材料的唯一方法。 Azure 密钥保管库外部并导入到 Azure 密钥保管库的密钥不符合备份条件，因为外部密钥不存在客户密钥使用密钥所需的元数据。 只有从 Azure 密钥保管库获取的备份可用于使用客户密钥还原操作。 因此，在上载或创建密钥后，必须备份 Azure 密钥保管库。
  
要创建 Azure 密钥保管库密钥的备份，请运行[备份 Azure 密钥密钥密钥](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)cmdlet，如下所示：
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

确保输出文件使用后缀`.backup`。
  
由此生成的输出文件已加密，不能在 Azure 密钥保管库之外使用。 只能将备份还原到从中进行备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件，选择保管库名称和密钥名称的组合。 这将使文件名自描述。 它还将确保备份文件名不会发生冲突。 
  
例如：
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure 密钥保管库配置设置
<a name="Validateconfiguration"> </a>

在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。 特别是，如果使用步骤设置密钥和保管库（本主题中介绍的键和保管库）以外的步骤，则应在配置客户密钥之前验证 Azure 密钥保管库资源的运行状况。
  
要验证密钥是否已启用，请包装密钥和展开密钥操作：
  
运行[获取 AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet，如下所示： 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

在输出中，查找访问策略和 Exchange 联机标识 （GUID） 或 SharePoint 联机标识 （GUID）。 上述所有三个权限都必须显示在"密钥权限"下。
  
如果访问策略配置不正确，请运行 Set-AzureRmKeyVault 访问策略 cmdlet，如下所示：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，对于联机交换和 Skype 业务：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，对于共享点在线和一个驱动器的业务：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

要验证未为密钥设置到期日期，请运行[Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet，如下所示： 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

客户密钥无法使用过期密钥，使用过期密钥尝试的操作将失败，并可能导致服务中断。 我们强烈建议客户密钥中使用的密钥没有到期日期。 过期日期（一旦设置）无法删除，但可以更改为其他日期。 如果必须使用设置到期日期的密钥，则将过期值更改为 12/31/9999。 到期日期设置为 12/31/9999 日期的密钥不会通过 Office 365 验证。
  
要更改已设置为 12/31/9999 以外的任何值的到期日期，请运行[Set-AzureKeyKey属性](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)cmdlet，如下所示： 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不要为使用客户密钥的加密密钥设置到期日期。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 密钥保管库密钥的 URI
<a name="GetKeyURI"> </a>

完成 Azure 中设置密钥保管库并添加密钥的所有步骤后，运行以下命令以获取每个密钥保管库中的密钥的 URI。 稍后创建和分配每个 DEP 时，需要使用这些 URI，因此将此信息保存在安全的地方。 请记住为每个密钥保管库运行此命令一次。
  
在 Azure 电源外壳中：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365：为在线交换和 Skype 业务设置客户密钥
<a name="AzureSteps"> </a>

开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。 有关详细信息，请参阅[Azure 密钥保管库和 Microsoft 快速跟踪中有关客户密钥的完成任务。](controlling-your-data-using-customer-key.md#AzureSteps) 
  
要设置联机交换客户密钥和 Skype 业务密钥，您需要通过使用 Windows PowerShell 远程连接到 Exchange Online 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>创建数据加密策略 （DEP），以便与 Exchange 在线和 Skype 业务一起使用
<a name="CreateDEP4EXOSkype"> </a>

DEP 与存储在 Azure 密钥保管库中的一组密钥相关联。 将 DEP 分配给 Office 365 中的邮箱。 然后，Office 365 将使用策略中标识的密钥对邮箱进行加密。 要创建 DEP，您需要之前获取的密钥保管库 URI。 有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](controlling-your-data-using-customer-key.md#GetKeyURI) 
  
记得！ 创建 DEP 时，指定两个驻留在两个不同的 Azure 密钥保管库中的密钥。 确保这些密钥位于两个单独的 Azure 区域中，以确保地理冗余。
  
要创建 DEP，请按照以下步骤操作：
  
1. 在本地计算机上，使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，通过打开 Windows PowerShell 并运行以下命令[连接到 Exchange Online PowerShell。](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) 
    
   ```
   $UserCredential = Get-Credential
   ```

2. 在 Windows PowerShell 凭据请求对话框中，输入您的工作或学校帐户信息，单击"**确定"，** 然后输入以下命令。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 執行下列命令。
    
   ```
   Import-PSSession $Session
   ```

4. 要创建 DEP，请使用新数据加密策略 cmdlet，键入以下命令。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：
    
   -  *策略名称*是要用于策略的名称。 名称不能包含空格。 例如，美国邮箱。 
    
   -  *策略说明*是策略的用户友好描述，可帮助您记住策略的用点。 您可以在说明中包含空格。 例如，美国及其区域中的邮箱的根键。 
    
   -  *KeyVaultURI1*是策略中第一个键的 URI。 例如 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*是策略中第二个键的 URI。 例如 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。 用逗号和空格分隔两个 URI。 
    
   範例：
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配给邮箱
<a name="assignDEPtomailbox"> </a>

使用设置邮箱 cmdlet 将 DEP 分配给邮箱。 分配策略后，Office 365 可以使用 DEP 中指定的密钥加密邮箱。
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*邮箱Id参数*指定邮箱的位置。 有关设置邮箱 cmdlet 的详细信息，请参阅[设置邮箱](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密
<a name="validatemailboxencryption"> </a>

加密邮箱可能需要一些时间。 对于第一次策略分配，邮箱还必须完成从一个数据库到另一个数据库的移动，服务才能加密邮箱。 我们建议您在更改 DEP 或首次将 DEP 分配给邮箱后尝试验证加密之前等待 72 小时。
  
使用获取邮箱统计信息 cmdlet 确定邮箱是否已加密。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，IsEncrypted 属性返回**的值为 true;** 如果邮箱未加密，则 IsEncrypted 属性返回**的值为 false。** 

完成邮箱移动的时间取决于首次分配 DEP 的邮箱数以及邮箱的大小。 如果邮箱在分配 DEP 后一周后未加密，请使用 New-MoveRequest cmdlet 启动未加密邮箱的邮箱移动。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365：为共享点在线和一个业务设置客户密钥
<a name="AzureSteps"> </a>

开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。 有关详细信息，请参阅[Azure 密钥保管库和 Microsoft 快速跟踪中有关客户密钥的完成任务。](controlling-your-data-using-customer-key.md#AzureSteps) 
  
要为"共享点联机"和"企业 OneDrive"设置客户密钥，您需要通过使用 Windows PowerShell 远程连接到共享点联机来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为每个共享点联机和一个业务地理创建数据加密策略 （DEP）
<a name="CreateDEP4SPOODfB"> </a>

DEP 与存储在 Azure 密钥保管库中的一组密钥相关联。 您将 DEP 应用于一个地理位置（也称为地理）中的所有数据。 如果使用 Office 365 的多地理位置功能（当前处于预览版中），则可以每个地理位置创建一个 DEP。 如果不使用多地理位置，则可以在 Office 365 中创建一个 DEP，以便与 SharePoint Online 和 OneDrive 一起使用。 然后，Office 365 将使用 DEP 中标识的密钥在该地理位置中加密数据。 要创建 DEP，您需要之前获取的密钥保管库 URI。 有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](controlling-your-data-using-customer-key.md#GetKeyURI) 
  
记得！ 创建 DEP 时，指定两个驻留在两个不同的 Azure 密钥保管库中的密钥。 确保这些密钥位于两个单独的 Azure 区域中，以确保地理冗余。
  
要创建 DEP，您需要使用 Windows PowerShell 远程连接到共享点联机。
  
1. 在本地计算机上，使用 Office 365 组织中具有全局管理员权限的工作或学校帐户"连接到[SharePoint 联机电源外壳](https://technet.microsoft.com/library/fp161372.aspx)"。
    
2. 在 Microsoft SharePoint 联机管理命令行中，运行[注册-SPO数据加密策略](https://technet.microsoft.com/library/mt843950.aspx)cmdlet，如下所示： 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   注册 DEP 时，加密从地理数据开始。 这可能需要一些时间。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>验证针对企业的组网站、团队网站和 OneDrive 的加密
<a name="validateencryptionSPO"> </a>

您可以通过运行 Get-SPOData 加密策略 cmdlet 来检查加密状态，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。
    
- 辅助键的 URI。
    
- 地理的加密状态。 可能状态包括：
    
  - **未注册：** 尚未应用客户密钥加密。 
    
  - **注册：** 已应用客户密钥加密，您的文件正在加密中。 如果您的地理位置处于此状态，则还会显示有关地理中站点已完成的百分比的信息，以便您可以监视加密进度。 
    
  - **注册：** 已应用客户密钥加密，并且所有站点中的所有文件都已加密。 
    
  - **滚动：** 关键卷正在进行中。 如果您的地理位置处于此状态，则还会显示有关已完成密钥滚动操作的网站百分比的信息，以便您可以监视进度。 
    
## <a name="managing-customer-key-for-office-365"></a>管理 Office 365 的客户密钥
<a name="ManageCustomerKey"> </a>

为 Office 365 设置客户密钥后，可以执行这些其他管理任务。
  
- [还原 Azure 密钥保管库密钥](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [在与客户密钥一起使用的 Azure 密钥保管库中滚动或旋转密钥](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [管理密钥保管库权限](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [确定分配给邮箱的 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>还原 Azure 密钥保管库密钥
<a name="RestoreAzureKeyVaultKeys"> </a>

在执行还原之前，请使用软删除提供的恢复功能。 与客户密钥一起使用的所有密钥都需要启用软删除。 软删除功能类似于回收站，允许恢复长达 90 天，而无需恢复。 只有在极端或异常情况下（例如，如果密钥或密钥保管库丢失）才需要还原。 如果必须还原用于客户密钥的密钥，请使用 Azure PowerShell，按如下方式运行还原 Azure KeyVaultKey cmdlet：
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

例如：
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥保管库中已存在同名密钥，则还原操作将失败。 还原 AzureKeyVaultKey 还原密钥的所有密钥版本和所有元数据，包括密钥名称。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>在与客户密钥一起使用的 Azure 密钥保管库中滚动或旋转密钥
<a name="RollCKkey"> </a>

Azure 密钥保管库或客户密钥不需要滚动密钥。 此外，受 HSM 保护的密钥几乎不可能泄露。 即使根密钥属于恶意参与者，也没有任何可行的方法来使用它来解密数据，因为只有 Office 365 代码知道如何使用它。 但是，滚动密钥由客户密钥支持。
  
> [!CAUTION]
> 仅当存在明确的技术原因或合规性要求要求必须滚动密钥时，才滚动与客户密钥一起使用的加密密钥。 此外，不要删除任何与策略关联的密钥。 当您滚动密钥时，将会有使用以前的密钥加密的内容。 例如，虽然活动邮箱将频繁重新加密，但非活动、断开连接和禁用的邮箱仍可以使用以前的密钥进行加密。 SharePoint Online 执行内容备份以进行恢复和恢复，因此仍有可能使用旧密钥存档的内容。 <br/> 为确保数据的安全，SharePoint Online 一次只允许进行一次密钥滚动操作。 如果要在密钥保管库中滚动两个密钥，则需要等待第一个密钥滚动操作完全完成。 我们的建议是以不同的时间间隔错开您的关键辊操作，这样这不是问题。 
  
滚动密钥时，正在请求现有密钥的新版本。 为了请求现有密钥的新版本，您可以使用相同的 cmdlet [Add-AzureKeyKey，](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)使用与最初用于创建密钥相同的语法。
  
例如：
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

在此示例中，由于名为**Contoso-O365EX-NA-VaultA1-Key001**的密钥已存在于**Contoso-O365EX-NA-VaultA1**保管库中，因此将创建新的密钥版本。 该操作添加了一个新的密钥版本。 此操作将保留密钥版本历史记录中的以前的密钥版本，以便以前使用该密钥加密的数据仍可以解密。 完成滚动与 DEP 关联的任何密钥后，必须运行另一个 cmdlet 以确保客户密钥开始使用新密钥。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>启用联机交换和 Skype 业务在 Azure 密钥保管库中滚动或旋转密钥后使用新密钥

当您滚动与与 Exchange Online 和 Skype 业务版使用的 DEP 关联的任一 Azure 密钥保管库密钥时，必须运行以下命令来更新 DEP 并启用 Office 365 开始使用新密钥。
  
要指示客户密钥使用新密钥加密 Office 365 中的邮箱，请运行 Set-Data 加密策略 cmdlet，如下所示：
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

在 48 小时内，使用此策略加密的活动邮箱将与更新的密钥关联。 [使用"确定分配给邮箱的 DEP"](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的数据加密策略 ID 属性的值。 应用更新的键后，此属性的值将更改。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>启用企业共享点联机和 OneDrive 在 Azure 密钥保管库中滚动或旋转密钥后使用新密钥

当您滚动与与 SharePoint Online 和 OneDrive 业务中使用的 DEP 关联的任一个 Azure 密钥保管库密钥时，必须运行[更新 SPOData 加密策略](https://technet.microsoft.com/library/mt843948.aspx)cmdlet 以更新 DEP 并启用 Office 365 开始使用新密钥。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

这将启动 SharePoint 联机和一个业务一个驱动器的密钥滚动操作。 此操作不是立即执行的。 要查看密钥滚动操作的进度，请运行获取 SPO 数据加密策略 cmdlet，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>管理密钥保管库权限
<a name="Managekeyvaultperms"> </a>

有几个 cmdlet 可用，使您能够查看并在必要时删除密钥保管库权限。 您可能需要删除权限，例如，当员工离开团队时。
  
要查看密钥保管库权限，请运行获取 Azure RmKeyVault cmdlet：
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

例如：
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

要删除管理员的权限，请运行删除 AzureRmKeyVault 访问策略 cmdlet：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

例如：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP
<a name="DeterminemailboxDEP"> </a>

要确定分配给邮箱的 DEP，请使用获取邮箱统计信息 cmdlet。 cmdlet 返回唯一标识符 （GUID）。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

在*其中"常规邮箱"或"邮件用户参数"* 指定邮箱。 有关获取邮箱统计信息 cmdlet 的详细信息，请参阅[获取邮箱统计信息](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。
  
使用 GUID 通过运行以下 cmdlet 找出邮箱分配到的 DEP 的友好名称。
  
```
Get-DataEncryptionPolicy <GUID>
```

其中*GUID*是上一步中获取邮箱统计信息 cmdlet 返回的 GUID。 
  

