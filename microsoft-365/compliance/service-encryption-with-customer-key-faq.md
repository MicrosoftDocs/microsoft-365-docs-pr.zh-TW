---
title: Office 365 中使用客戶金鑰的服務加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: 除了通过 BitLocker 和分布式密钥管理器 （DKM） 启用的基准卷级加密外，Office 365 还为 Office 365 中的客户内容（包括来自 Exchange 的数据）在应用程序级别提供了额外的加密层联机、Skype 业务、共享点联机和一个业务驱动器。 这称为服务加密。
ms.openlocfilehash: 8b15369571e3a6c021ae0c7337782a0d64436297
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077408"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Office 365 中使用客戶金鑰的服務加密常見問題集

除了通过 BitLocker 和分布式密钥管理器 （DKM） 启用的基准卷级加密外，Office 365 还为 Office 365 中的客户内容（包括来自 Exchange 的数据）在应用程序级别提供了额外的加密层联机、Skype 业务、共享点联机和一个业务驱动器。 这称为服务加密。
  
客户密钥基于服务加密构建，使您能够提供和控制用于在 Office 365 中加密静态数据的[密钥，如在线服务条款 （OST）](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中所述。 客戶金鑰可協助您符合規範，因為您可以控制加密金鑰，Office 365 會使用該金鑰來解密資料。
  
要提供有关客户密钥（包括文档）的反馈，请将您的想法、建议和观点发送给customerkeyfeedback@microsoft.com。
  
## <a name="what-is-service-encryption-with-customer-key"></a>什么是使用客户密钥的服务加密？

客户密钥增强了您的组织满足法规遵从性要求的能力，这些要求指定与云服务提供商的关键安排。 使用客户密钥，您可以在应用程序级别提供和控制 Office 365 静态数据的加密密钥。 因此，如果您决定退出服务，您可以行使控制权并撤销组织的密钥。 通过吊销密钥，服务无法读取数据。 密钥吊销是数据删除路径上的第一步。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>客户密钥涵盖哪些 Office 365 静止数据？
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

涵盖 SharePoint 在线网站内容以及存储在该网站上的文件以及上传到 OneDrive 商业版的文件。 涵盖 Exchange 联机邮箱内容（电子邮件正文、日历条目和电子邮件附件的内容）。 涵盖来自 Skype 商务的文字对话，但不涵盖 Skype 会议广播录制和 Skype 会议内容上载。 Skype 会议广播和 Skype 会议内容上载与 Office 365 中的所有其他内容一起加密，但我们目前不提供客户对加密密钥的控制。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>使用 Azure 信息保护进行联机交换，客户密钥和自带密钥 （BYOK） 之间的区别是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

这两个选项都使您能够提供和控制自己的加密密钥;但是，使用客户密钥的服务加密在静态时加密您的数据，驻留在 Office 365 服务器中，而具有 Azure 联机交换信息保护的 BYOK 加密传输中的数据并提供持续的联机和脱机Office 365 的电子邮件和附件的保护。 具有 Azure 在线交换信息保护的客户密钥和 BYOK 是互补的，无论您选择使用 Microsoft 的服务托管密钥还是您自己的密钥，加密静态和传输中的数据都可以提供额外的保护。恶意攻击。
  
Office 365 消息加密功能提供了具有 Azure 联机交换信息保护的 BYOK。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Office 365 消息加密和自带密钥的 Azure 信息保护是否改变了 Microsoft 处理第三方数据请求（如传票）的方法？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 Office 365 消息加密以及使用自带密钥 （BYOK） 提供和控制自己的加密密钥的选项不是针对执法传票而设计的。 Office 365 消息加密与 BYOK AIP 专为需要履行其内部或外部合规性义务的以合规性为中心的客户而设计。 微软非常重视第三方对客户数据的请求。 作为云服务提供商，我们始终倡导客户数据的隐私。 如果我们收到传票，我们总是试图将第三方重定向到客户以获取信息。 （请阅读布拉德·史密斯的博客：[保护客户数据免受政府窥探）。](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 我们定期公布[我们在这里](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)收到的请求的详细信息。
  
有关详细信息，请参阅[Microsoft 信任中心，](https://www.microsoft.com/en-us/trustcenter/default.aspx)了解第三方数据请求和[在线服务条款 （OST）](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中的"客户数据泄露"。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>使用客户密钥的服务加密是否改变了 Microsoft 处理第三方数据请求（如传票）的方法？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 客户密钥并非旨在响应执法传票。 它专为受监管客户设计，以履行其内部或外部合规义务。 微软非常重视第三方对客户数据的请求。 作为云服务提供商，我们始终倡导客户数据的隐私。 如果我们收到传票，我们总是试图将第三方重定向到客户以获取信息。 （请阅读布拉德·史密斯的博客：[保护客户数据免受政府窥探）。](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 我们定期公布[我们在这里](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)收到的请求的详细信息。
  
有关详细信息，请参阅[Microsoft 信任中心，](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)了解第三方数据请求和[在线服务条款 （OST）](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中的"客户数据泄露"。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>FastTrack 支持是否可用于实施客户密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 FastTrack 仅用于收集注册客户密钥所需的租户和服务配置信息。 客户密钥产品/服务通过 FastTrack 发布，以便客户和合作伙伴能够使用相同的方法提交所需信息，并便于存档客户在产品/服务中提供的数据。
  
如果您需要文档之外的其他支持，请与 Microsoft 咨询服务 （MCS）、卓越现场工程 （PFE） 或 Microsoft 合作伙伴联系以获得帮助。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>如果我的钥匙已销毁，如何恢复？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥使您能够从您管理的根密钥的意外丢失中恢复。 如果丢失根密钥，请与 Microsoft 支持部门联系，Microsoft 将协助您完成启用可用性密钥的过程。 您将使用可用性密钥迁移到新的数据加密策略，并预配新密钥。 
  
## <a name="what-is-the-availability-key"></a>可用性密钥是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥是在创建数据加密策略时预配的根密钥。 可用性密钥在 Office 365 中存储和保护，在功能上类似于您提供的两个根密钥，用于与客户密钥一起使用的服务加密。 与在 Azure 密钥保管库中提供和管理的密钥不同，您无法直接访问可用性密钥。 可用性密钥的存储和控制与 Azure 密钥保管库密钥的存储和控制故意不同，原因有三：首先，在 Office 365 服务无法访问 Azure 密钥中托管的密钥时，可用性密钥提供了高可用性功能保险柜;其次，在 Azure 密钥保管库密钥都丢失的情况下，可用性密钥提供"碎玻璃"功能;第三，逻辑控件的分离提供纵深防御，防止单个攻击或故障点丢失所有键。 分担保护密钥的责任，同时使用各种保护和流程进行密钥管理，最终降低了所有密钥（以及您的数据）丢失或销毁的风险。 Microsoft 为您提供了销毁可用性密钥的唯一权限。 根据设计，Microsoft 中没有人能够访问可用性密钥 - 它只能由 Office 365 服务代码访问。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>我可以创建多少个数据加密策略 （DEP）？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **交换在线和 Skype 业务：** 您最多只能创建 50 个 DEP。 
  
 **共享点在线和一个驱动器的业务：** DEP 适用于一个地理位置（也称为地理）中的数据。 如果使用 Office 365 的多地理位置功能，则可以每个地理位置创建一个 DEP。 如果不使用多地理位置，可以创建一个 DEP。
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>在将邮箱迁移到云之前，是否可以分配数据加密策略？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可以。 在将邮箱迁移到 Office 365 之前，可以使用 Windows PowerShell cmdlet Set-Mail 用户向用户分配数据加密策略 （DEP）。 执行此操作时，在迁移内容时将使用分配的 DEP 对邮箱内容进行加密。 这比在邮箱迁移后分配 DEP 然后等待加密进行更有效，这可能需要数小时甚至数天。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>如何验证使用客户密钥加密已激活，Office 365 已完成使用客户密钥加密？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **交换在线和 Skype 业务：** 您可以使用[远程 PowerShell 连接到 Exchange 在线，](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)然后对要检查的每个邮箱使用 **[获取邮箱统计信息]** cmdlet。 在 Get-邮箱统计信息 cmdlet 的输出中，如果邮箱已加密，_则 IsEncrypted_属性返回**的值为 true;** 如果邮箱未加密，则返回**false**值。 如果邮箱已加密，则 Data_加密策略 ID_属性返回的值是加密邮箱的 DEP 的 GUID。 有关运行此 cmdlet 的详细信息，请参阅[获取邮箱统计信息](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx)以及使用 PowerShell 与联机交换。 
  
如果邮箱在分配 DEP 后等待 72 小时后未加密，则启动邮箱移动。 为此，[请使用远程 PowerShell 连接到 Exchange 在线，](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)然后使用 New-MoveRequest cmdlet 并提供邮箱的别名，如下所示： 
  
```
New-MoveRequest <alias>
```

 **共享点在线和一个驱动器的业务：** 您可以[连接到 SharePoint 在线 PowerShell，](https://technet.microsoft.com/en-us/library/fp161372.aspx)然后使用 **[获取-SPO数据加密策略]** cmdlet 来检查租户的状态。 如果启用了客户密钥加密，并且所有站点中的所有文件都已加密，则 _[State]_ 属性将返回**已注册**的值。 如果加密仍在进行中，此 cmdlet 会提供有关站点完成百分比的信息。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>如果我想切换到另一组密钥，则新密钥集需要多长时间才能保护数据？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **交换在线和 Skype 业务：** 根据新的数据加密策略 （DEP），从将新 DEP 分配给邮箱时，最多可能需要 72 小时来保护邮箱。 
  
 **共享点在线和一个驱动器的业务：** 分配新密钥后，最多可能需要四个小时才能重新加密整个租户。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>在使用客户密钥解密或加密时，我现有的数据存储是否随时没有加密？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 您的数据始终在使用 BitLocker 和 DKM 的 Office 365 服务中静态加密。 有关详细信息，请参阅 Office 365 的安全、隐私和合规性信息，以及[Exchange Online 如何保护您的电子邮件机密。](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>如果我不想再使用客户管理的加密密钥，是否可以切换到 Microsoft 管理的密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **交换在线和 Skype 业务：** 还没有。 一旦使用 Microsoft 托管密钥在 Office 365 中的服务加密广泛推出，将支持此功能。 我们希望在使用客户密钥发布服务加密后在服务中推出此功能。 
  
 **共享点在线和一个驱动器的业务：** 是的。 您可以选择为每个地理位置（如果使用多地理位置功能）单独使用 Microsoft 管理的密钥，或者如果数据位于单个地理位置中，则可以选择恢复使用所有数据。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>如果我丢失了密钥，使用恢复密钥恢复服务可用性需要多长时间？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **交换在线和 Skype 业务：** 调用以使用可用性密钥后，将在几分钟内访问邮箱。 
  
 **共享点在线和一个驱动器的业务：** 此操作与您拥有的网站数成正比。 一旦您致电 Microsoft 使用可用性密钥，您将在大约四小时内完全联机。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>如何与 Exchange 在线使用可用性密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥与 Exchange 联机一起使用有三种方式：
  
- 服务可用性 - 如果 Azure 密钥保管库密钥无法访问。
    
- 由 Office 365 服务代码启动的操作 - 例如搜索索引创建或邮箱移动。
    
- 从密钥丢失中恢复 - 例如与单个 DEP 关联的 Azure 密钥保管库密钥丢失。
    
 **在无法访问 Azure 密钥保管库密钥时，使用可用性密钥来提供服务可用性。**
  
Office 365 使用可用性密钥来提供服务可用性，并从不正常的客户密钥状态恢复 Exchange Online。 客户密钥使用的键层次结构。 下图说明了此层次结构。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
如果单个数据加密策略 （DEP） 的两个 Azure 密钥保管库密钥都不可用，Office 365 可以使用可用性密钥更改为新的 DEP。 Office 365 根据用户启动的活动（例如，当用户将电子邮件下载到 Outlook 客户端）还是系统启动的活动（如索引），确定是否对服务可用性使用不同情况密钥邮箱内容，或用于电子数据展示搜索，触发了该过程。
  
Office 365 遵循此过程以响应用户启动的操作，以确定是否对用户邮箱使用可用性密钥：
  
1. Office 365 读取邮箱分配到的 DEP，以确定 Azure 密钥保管库中的两个客户密钥的位置。
    
2. Office 365 从 DEP 中随机选择两个客户密钥之一，并向 Azure 密钥保管库发送请求，以便使用客户密钥解包 DEP 密钥。
    
3. 如果使用客户密钥打开 DEP 密钥的请求失败并返回错误，Office 365 会向 Azure 密钥保管库发送第二个请求，这一次指示它使用备用（第二个）客户密钥。
    
4. 如果使用客户密钥解包 DEP 密钥的第二个请求失败并返回错误，Office 365 将检查两个请求的结果：
    
  - 如果检查确定错误不反映客户标识的显式操作，则 Office 365 使用可用性密钥解密 DEP 密钥。 然后，使用 DEP 密钥解密邮箱密钥并完成用户请求。
    
    在这种情况下，Azure 密钥保管库无法响应，或者由于任何原因无法访问。 Office 365 无法确定客户是否有意撤销了对密钥的访问权限。
    
  - 如果检查指示已采取故意操作使客户密钥不可用，则可用性密钥将不会使用，用户请求失败，并且用户收到一条错误消息，如登录失败。
    
    发生这种情况时，客户会意识到服务受到影响，并且客户密钥的状况不正常。 例如，如果客户对组织中的所有邮箱使用单个 DEP，则客户可能会遇到用户无法访问其邮箱的广泛故障。 这可确保当两个客户密钥都不正常时，客户会意识到需要纠正这种情况并将服务恢复到正常状态。
    
 **对 Office 365 服务代码启动的操作使用可用性密钥。**
  
Office 365 服务代码始终具有有效的登录令牌，无法阻止。 因此，在删除可用性密钥之前，它可用于 Office 365 服务代码启动或内部启动的操作，如搜索索引创建或移动邮箱。
  
 **使用可用性密钥从密钥丢失中恢复。**
  
您可以使用可用性密钥从与同一 DEP 关联的两个 Azure 密钥保管库密钥的丢失中恢复，如常见问题解答条目"如果我的密钥已销毁，我如何恢复？
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>如何与 SharePoint 在线和一个业务一个驱动器使用可用性密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint 在线和 OneDrive 业务体系结构和客户密钥和可用性密钥的实施不同于 Exchange 在线和 Skype 业务。
  
当客户移动到客户管理的密钥时，Office 365 将创建特定于租户的中间密钥 （TIK）。 Office 365 对 TIK 加密两次，一次使用每个客户密钥加密，并存储两个加密版本的 TIK。 仅存储 TIK 的加密版本，并且只能使用客户密钥解密 TIK。 然后，TIK 用于加密站点密钥，然后用于加密 blob 密钥。 blob 本身已加密并存储在 Microsoft Azure Blob 存储服务中。
  
Office 365 遵循此过程来访问具有客户文件数据的 Blob：
  
1. 使用客户密钥解密 TIK。
    
2. 使用解密的 TIK 解密站点密钥。
    
3. 使用解密的站点密钥解密 blob 密钥。
    
4. 使用解密的 blob 密钥解密 Blob。
    
解密 TIK 时，Office 365 会向 Azure 密钥保管库发出两个解密请求，但略有偏移。 第一个完成提供的结果，取消另一个请求。
  
如果客户无法访问其客户密钥，Office 365 还会使用可用性密钥加密 TIK，并将其与使用每个客户密钥加密的 TIK 一起存储。 仅当客户呼叫 Microsoft 以在恶意或意外无法访问其密钥时，才使用使用使用可用性密钥加密的 TIK。
  
出于可用性和规模原因，解密的 TIK 缓存在有时间限制的内存缓存中。 在 TIK 缓存设置为过期前两小时，Office 365 尝试解密每个 TIK。 解密 TIK 可延长缓存的生存期。 如果 TIK 解密在相当长的时间内失败，Office 365 会生成警报，以便在缓存过期之前通知工程部门。 仅当客户致电 Microsoft 时，Office 365 才会启动恢复操作，这涉及使用存储在 Microsoft 机密存储中的可用性密钥解密 TIK，并使用解密的 TIK 和一组新的客户提供的 Azure 密钥保管库密钥。
  
时至今日，客户密钥涉及存储在 Azure Blob 存储中的 SharePoint 联机文件的加密和解密链，但不包括存储在 SQL 数据库中的 SharePoint 联机列表项或元数据。 Office 365 不使用 SharePoint Online 或 OneDrive 业务的可用性密钥，而不是上述情况（客户启动）。 人机访问客户数据受客户密码箱保护。
  
## <a name="how-is-customer-key-licensed"></a>如何获得客户密钥的许可？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Office 365 企业套件、"E5"和高级合规性 SKU 中提供了客户密钥。 此外，客户还必须购买用于使用 Azure 密钥保管库的相应许可证。
  
如果每个从客户密钥中受益的用户想要获得客户密钥的覆盖，则需要获得许可。
  
对于 SharePoint Online，配置客户密钥的 Office 365 管理员也需要获得许可，才能执行设置步骤。 此外，从该功能中受益的用户需要获得许可 - 这包括网站所有者和访问使用客户密钥加密的一个或多个网站上的文件的任何用户。 外部用户无需获得许可，就无需访问使用客户密钥加密的一个或多个站点上的文件。
  
对于联机交换，"用户"邮箱和"邮件用户"邮箱必须获得许可。 所有其他（如共享邮箱）都不需要拥有客户密钥许可证。 要检查您的 Exchange 在线邮箱是否获得正确许可，请运行以下 cmdlet：
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

如果字符串 BPOS_S_EquivioAnalytics 存在，则邮箱已正确授权。 如果没有，则必须应用适当的许可证才能使用此邮箱的客户密钥功能。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>我可以为试用订阅启用客户密钥吗？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 根据定义，试用订阅的生存期有限。 在试用订阅中托管的加密密钥可能会在试用生存期结束时丢失。 由于 Microsoft 不能也不妨碍客户将重要的客户数据放入试用订阅中，因此禁止在试用订阅中使用客户密钥。
  
## <a name="how-much-will-using-customer-key-cost"></a>使用客户密钥的成本是多少？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

除了客户密钥所需的许可外，客户还将产生密钥保管库使用成本。 [Azure 密钥保管库定价详细信息](https://azure.microsoft.com/en-us/pricing/details/key-vault/)描述成本模型，并将有助于估算成本模型。 由于使用模式不同，无法预测任何客户将产生的确切成本。 经验表明，成本非常低，通常属于每个用户每月 0.002 到 0.005 美元的范围，再加上 HSM 支持的密钥的成本。 成本还将根据客户选择的日志记录配置和用于 Azure 密钥保管库日志的 Azure 存储量而有所不同。 
  
## <a name="for-more-information"></a>如需詳細資訊
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

要开始使用客户密钥，请参阅[使用客户密钥在 Office 365 中控制数据。](controlling-your-data-using-customer-key.md)
  

