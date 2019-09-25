---
title: 使用 PST 收集工具查找、复制和删除组织中的 PST 文件
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: 使用 Microsoft PST 收集工具搜索组织网络，获取分散在整个组织的 PST 文件的清单。 找到 PST 文件后，可以使用 PST 收集工具将它们复制到中心位置，以便将它们导入 Office 365。
ms.openlocfilehash: 000da8aec988e85f935a96aabe9faa48932aaeaa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077137"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>使用 PST 收集工具查找、复制和删除组织中的 PST 文件

> [!IMPORTANT]
> 本文中描述的 PST 收集工具不受任何 Microsoft 标准支持计划或服务的支持。 该工具以各种形式提供，不作任何形式的保修。 Microsoft 还声明所有默示担保，包括但不限于任何隐含的可商业性或适合特定目的的保证。 使用或执行工具和文档所产生的全部风险仍由您承担。 在任何情况下，Microsoft、其作者或参与工具创建、生产或交付的任何其他人均不对任何损害（包括但不限于业务利润损失、业务中断、损失）负责。因使用或无法使用工具或文档而产生的业务信息或其他金钱损失，即使 Microsoft 已被告知此类损害的可能性。

您可以使用 Microsoft PST 收集工具在组织的网络中搜索 PST 文件。 该工具可帮助您获取分散在整个组织的 PST 文件的清单。 找到 PST 文件后，可以使用 PST 收集工具将它们复制到中心位置。 将 PST 放在一个位置，然后允许您将它们导入 Exchange 联机邮箱（或单个 Exchange Online 邮箱），然后您可以在 Office 365 中应用丰富的合规性功能集。 这包括将 PST 导入用户的存档邮箱，在使用电子数据展示搜索工具导入的 PST 文件中搜索特定邮件，使用电子数据展示保留和 Office 365 保留策略保留邮件，以及管理生命周期使用 Exchange 联机中的消息记录管理功能对这些消息的循环。 确信您收集的 PST 文件已成功导入 Office 365 后，可以使用该工具从网络上的原始位置删除这些文件。 
  
另一件事，你可以做与PST收集工具是防止用户创建新的PST文件和改变现有的PST文件，你找到你的网络。 这些"块"功能可让您查找、收集和导入 Office 365 的已知 PST 文件集，并防止将来在组织中出现 PST 文件激增。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST 收集工具的工作原理

以下是使用 PST 收集工具查找、控制、收集和删除组织中 PST 文件的过程的快速概述。
  
![PST 收集工具流程概述](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[步骤 1：在网络上查找 PST 文件](#step-1-find-pst-files-on-your-network)**- 当您运行该工具查找 PST 文件时，您可以指定一个位置，例如包含客户端和服务器计算机的 Active Directory 对象的组织单位。 您还可以搜索特定计算机或网络文件共享。 运行该工具时，目标计算机上会安装"轻量级"收集代理。 此代理搜索目标计算机的 PST 文件，然后将有关它找到的任何 PST 文件的信息发送回 PST 收集工具。 该工具创建日志文件，其中包含有关在指定位置找到的 PST 文件的信息。 在后续步骤中运行该工具时，将使用这些文件。 
    
2. **[（可选）步骤 2：控制对 PST 文件的访问](#optional-step-2-control-access-to-pst-files)**- 该工具创建一个组策略对象 （GPO），其设置会阻止用户创建或更改 PST 文件。 此 GPO 应用于域中的每个用户。 这个可选步骤可帮助您"锁定"步骤 1 中找到的 PST 文件，以便您可以收集、导入和删除这些文件，而无需创建新的 PST 文件或更改现有的 PST 文件。 
    
3. **[步骤 3：将 PST 文件复制到收集位置](#step-3-copy-the-pst-files-to-a-collection-location)**- 这允许您在一个位置收集 PST 文件，以便通过使用步骤 4 中的 Office 365 导入服务将它们导入到 Exchange 联机邮箱。 在"收集"模式下运行该工具时，每个收集代理都会将代理安装的目标计算机中的 PST 文件复制到收集位置。 
    
4. **[步骤 4： 将 PST 文件导入 Office 365](#step-4-import-the-pst-files-to-office-365)** - 将 PST 文件复制到一个位置后，即可将其导入 Exchange 联机邮箱。 
    
5. **[步骤 5： 删除在网络上找到的 PST 文件](#step-5-delete-the-pst-files-found-on-your-network)**- 在您找到和收集的 PST 文件已导入 Office 365 中的 Exchange 联机邮箱后，您可以使用 PST 收集工具从原始位置删除 PST 文件在步骤 1 中找到。 

## <a name="before-you-begin"></a>開始之前

- 按照以下步骤将 PST 收集工具下载到本地计算机。 
    
    1. [下载PST收集工具。](https://aka.ms/pstcollectiontool)
    
    2. 在弹出窗口中，\>**单击"保存保存"** 以将 PSTCollectionTool.zip 文件保存到本地计算机上的文件夹中。 **** 
    
    3. 将 PSTCollectionTool.zip 文件提取到本地计算机上的文件夹;默认文件夹名称为 PSTCollectionTool。
    
- 要在任何模式（查找、阻止、复制或删除）中运行 PST 集合工具，您必须是活动目录域中的域管理员组的成员。 

## <a name="step-1-find-pst-files-on-your-network"></a>第 1 步：在网络上查找 PST 文件

第一步是运行 PST 收集工具，以查找组织中的 PST 文件。 您可以使用该工具搜索以下类型的位置。 
  
- 本地活动目录域中的组织单位 （O.）。 该工具搜索指定 OU 中包含的所有计算机。 
    
- 客户端和服务器计算机。 该工具搜索指定的计算机。 
    
- 网络文件共享。 该工具搜索指定的网络文件共享。 
    
有关用于每种位置类型的`Locations`语法示例，请参阅以下过程中表中参数的说明。 
  
> [!IMPORTANT]
> 您必须在"查找"模式下运行 PST 收集工具，然后才能执行其他操作，如阻止、收集或删除 PST 文件。 
  
1. 在本地计算机上打开命令提示符（以管理员身份运行）。
    
2. 转到 PSTCollectionTool 文件夹（或您提取 PSTCollectionTool.zip 文件的文件夹）。
    
3. 更改为数据收集器主目录。
    
4. 运行以下命令以查找指定位置中的 PST 文件。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    下表描述了在运行 DataCollectorMaster.exe 命令以查找 PST 文件时所需的参数及其所需值。 
    
    |参数*|****描述****|示例*|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据类型。 目前，您可以使用 PST 收集工具来搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作类型。 使用 值`Find`在指定位置定位 PST 文件。 请注意，该工具可以查找和获取有关在 Outlook 和连接到 Outlook 配置文件的 PST 文件中打开的 PST 文件的信息。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |指定 PST 集合作业的名称。 当您运行 PST 收集工具时，您将使用相同的作业名称来阻止、收集和删除运行该工具以查找 PST 文件时发现的 PST 文件。 作业名称也将添加到日志和配置文件名称中。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | 指定一个或多个位置以搜索 PST 文件。 如果指定多个位置，请使用分号 （;)分隔各个位置。 请确保用双引号 （" ） 环绕此参数的单个值。  <br/><br/>   以下是可搜索的位置类型所需的标识值格式。  <br/><br/>        **O-** 使用可分辨名称 （DN） 标识 O.例如：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]>您无法指定内置计算机容器（例如，CN_计算机、DC_contoso、DC_com），因为它不是组织单位。<br/> <br/> **计算机**- 使用 DN 或完全限定的域名 （FQDN） 来识别网络上的客户端和服务器计算机;例如：  <br/>  Dn：`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  或  <br/>  Fqdn：`"FILESERVER01.contoso.com"` <br/><br/>  **网络文件共享**- 使用 UNC 名称标识网络文件共享;例如，`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |指定要复制到的日志文件的文件夹。 如果该文件夹不存在，将在运行该工具时创建该文件夹。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |指定将 .xml 配置文件复制到的文件夹。 此文件包含有关运行该工具时找到的每个 PST 文件的信息。 当您在步骤 3 中运行该工具以复制找到的 PST 文件时，将使用此文件。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |此可选参数指定在"查找"操作期间要跳过的位置。 您可以排除特定的 O、计算机和网络文件共享。 例如，可以排除用户无法访问的计算机，例如配置为 SQL 服务器（或其他类型的应用程序服务器）的计算机。 如果指定要排除的多个位置，请使用分号（;)分隔各个位置。 请确保用双引号 （" ） 环绕此参数的单个值。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在"查找"模式下为现有 PST 集合作业运行该工具。 使用`ForceRestart`switch 时，作业上一个 Find 操作的结果将被丢弃，该工具将重新扫描指定的位置并创建新的日志和配置文件。  <br/> | `-ForceRestart` <br/> |
   
    下面是使用每个参数的实际值的 DataCollectorMaster.exe 命令的语法示例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    运行该命令后，将显示详细的状态消息，显示在指定位置查找 PST 文件的进度。 一段时间后，最终状态消息将显示找到的 PST 文件总数、作业是否已完成以及是否存在任何错误。 相同的状态消息将复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>在"查找"模式下运行数据收集器Master.exe的结果

成功运行 PST 集合工具"查找"模式后，将创建以下文件并将其存储在`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>__\<作业名称 查找日期时间\>戳 .log - 日志文件包含显示的状态消息。 \<** 此文件在`LogLocation`参数指定的文件夹中创建。 
    
- **\>\<\>作业名查找日期时间戳 .csv - CSV 文件包含找到的每个 PST 文件的行。__ \<** 每个 PST 的信息包括找到 PST 文件的计算机、PST 文件的完整文件路径位置、PST 文件的所有者以及 PST 文件的大小（以千字节为单位的 KB）。 此文件在`LogLocation`参数指定的文件夹中创建。 
    
    > [!TIP]
    > 使用 Excel 中的自动求和工具计算 CSV 文件中列出的所有 PST 文件的总大小（以 KB 为单位）。 然后，您可以使用转换计算器将总大小转换为兆字节 （MB） 或 GB。 
  
- **\>\<\>作业名查找日期时间戳 .xml - XML 文件包含有关在"查找"模式下运行该工具时使用参数值的信息。__ \<** 此文件还包含有关找到的每个 PST 文件的信息。 当您为同一作业运行该工具以阻止、收集或删除找到的 PST 文件时，使用此文件中的数据。 此文件在`ConfigurationLocation`参数指定的文件夹中创建。 
    
    > [!IMPORTANT]
    > 不要重命名、更改或移动此文件。 当您为同一作业在"阻止、复制"或"删除"模式下重新运行该工具时，PST 集合工具会使用它。 

## <a name="optional-step-2-control-access-to-pst-files"></a>（可选）第 2 步：控制对 PST 文件的访问

此选项允许您"锁定"步骤 1 中找到的 PST 文件，以便您可以收集和导入一组已知的 PST 文件到 Office 365。 在块模式下运行 PST 收集工具时，会发生以下情况： 
  
- 该工具创建名为*PST 使用控制的*组策略对象 （GPO）。 此 GPO 链接到您的域，并应用于组织中所有经过身份验证的用户。 
    
- PST 使用情况控制 GPO 会在组织中的计算机上创建注册表设置。 根据所使用的参数，您可以创建注册表设置以防止用户创建新的 PST 文件和阻止用户更改现有 PST 文件的注册表设置。
    
> [!NOTE]
> 如果控制对 PST 文件的访问对您的组织来说太具有破坏性，则可以考虑跳过此步骤，并执行步骤 3 将 PST 文件复制到中心位置。 然后，您可以重复同一作业的步骤 1（通过使用`ForceRestart`参数）查找在将 PST 文件复制到收集位置后创建的其他 PST 文件。 如果找到新的 PST 文件，您可以将它们复制到收集位置。 在"查找"`ForceRestart`模式下重新运行该工具时，使用 参数时，作业的上一个"查找"操作的结果将被丢弃，该工具将重新扫描指定的位置。 

要阻止对 PST 文件的访问，

1. 在本地计算机上打开命令提示符（以管理员身份运行）。
    
2. 转到下载 PST 收集工具的目录。
    
3. 运行以下命令以阻止对步骤 1 中找到的 PST 文件的访问。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    下表描述了在运行 DataCollectorMaster.exe 命令以阻止创建和更改 PST 文件时所需的参数及其所需值。 
    
    |参数*|****描述****|示例*|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据类型。 目前，您可以使用 PST 收集工具来搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作类型。 使用 值`Block`可防止用户创建新的 PST 文件并对现有 PST 文件进行更改。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在步骤 1 中的"查找"模式下运行该工具时使用的作业名称。 此作业名称也会添加到在块模式下运行该工具时创建的日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定该文件夹包含在"查找"模式下运行该工具时创建的 .xml 配置文件。 使用步骤 1 中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定将复制块操作的日志文件的文件夹。 这是一个可选参数。 如果不包括日志文件，日志文件将复制到下载 PST 收集工具的文件夹。 请考虑使用在步骤 1 中的"查找"模式下运行该工具时使用的相同日志位置，以便将所有日志文件都保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |使用此开关可防止用户更改 PST 文件。 使用此开关时，将创建以下注册表项：`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow`并将数据值设置为 1。 此注册表设置由在块模式下运行 PST 集合工具时创建的 GPO 在组织中的计算机上创建。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |使用此开关可防止用户创建新的 PST 文件、打开和将 PST 文件导入 Outlook 以及从 Outlook 导出 PST 文件。 使用此开关时，将创建以下注册表项：`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst`并将数据值设置为 1。 此注册表设置由在块模式下运行 PST 集合工具时创建的 GPO 在组织中的计算机上创建。  <br/> | `-BlockNewFiles` <br/> |
   
    下面是使用每个参数的实际值的 DataCollectorMaster.exe 命令的语法示例：

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    系统会提示您确认是否要阻止新的 PST 文件或对现有 PST 文件的更改。 确认要继续并成功运行命令后，将显示一条消息，指出已创建新的 GPO，名为"PST 使用控制"。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>步骤 3：将 PST 文件复制到收集位置

下一步是复制在"查找"模式下运行 PST 收集工具时找到的 PST 文件。 这允许您在一个位置收集 PST 文件，以便以后可以将它们导入 Office 365。 在将 PST 文件复制到收集位置之前，请考虑确定所需的存储空间总量。 您可以使用在步骤 1 中创建的 CSV 文件来计算所有 PST 文件的总大小。
  
> [!NOTE]
> 将 PST 文件导入 Office 365 并从其原始位置删除后，您可能希望从此步骤中将其复制到的集合位置中删除这些文件。 
  
1. 在本地计算机上打开命令提示符（以管理员身份运行）。
    
2. 转到下载 PST 收集工具的目录。
    
3. 运行以下命令将 PST 文件复制到指定位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表描述了运行 DataCollectorMaster.exe 命令以复制 PST 文件时所需的参数及其所需值。 
    
    |参数*|****描述****|示例*|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据类型。 目前，您可以使用 PST 收集工具来搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作类型。 使用 值`Collect`复制在"查找"模式下运行到该工具时发现的 PST 文件。 请注意，该工具能够复制在 Outlook 中打开的 PST 文件，并复制连接到 Outlook 配置文件的 PST 文件。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在步骤 1 中的"查找"模式下运行该工具时使用的作业名称。 此作业名称也会添加到在"收集"模式下运行该工具时创建的日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用与步骤 1 中`Locations`参数相同的值。 如果要在步骤 5 中重新运行该工具以从其源位置删除 PST 文件，则在"收集"模式下运行该工具时，包含此参数。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |指定包含在"查找"模式下运行该工具时创建的 .xml 配置文件的文件夹。 使用步骤 1 中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |指定要将 PST 文件复制到的收集位置。 您可以将文件复制到文件服务器、网络文件共享或硬盘驱动器。 在"收集"模式下运行该工具之前，该位置必须存在。 该工具不会创建该位置，并将返回一个错误，指出它不存在。  <br/> 此外，您必须将权限写入此参数指定的收集位置。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |指定将"收集"模式的日志文件复制到的文件夹。 这是一个可选参数。 如果不包括日志文件，日志文件将复制到下载 PST 收集工具的文件夹。 请考虑使用在步骤 1 中的"查找"模式下运行该工具时使用的相同日志位置，以便将所有日志文件都保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在收集模式下为现有 PST 集合作业重新运行该工具。 如果您以前在"收集"模式下运行该工具，但随后在"查找"模式下再次运行该工具，`ForceRestart`并切换到重新扫描 PST 文件的位置，则可以使用此开关在"收集"模式下重新运行该工具，并在找到时重新复制其中的 PST 文件。重新扫描位置。 在收集模式下`ForceRestart`使用开关时，该工具将忽略任何以前的收集操作，并尝试从头开始复制 PST 文件。  <br/> | `-ForceRestart` <br/> |
   
    下面是使用每个参数的实际值的 DataCollectorMaster.exe 工具的语法示例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    运行该命令后，将显示详细的状态消息，显示收集步骤 1 中找到的 PST 文件的进度。 一段时间后，最终状态消息将显示是否存在任何错误以及日志复制到的位置。 相同的状态消息将复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>在收集模式下运行数据收集器Master.exe的结果

在"收集"模式下成功运行 DataCollectorMaster.exe 后，将创建以下文件并将其存储在`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>\<\>作业名收集日期时间戳 .log - 日志文件包含显示的状态消息。__ \<** 此文件在`LogLocation`参数指定的文件夹中创建。 
    
- **\>\<\>作业名收集日期时间戳 .xml - XML 文件仅包含有关工具在"收集"模式下使用的参数值的信息。__ \<** 当您运行重新运行 DataCollectorMaster.exe 工具以删除 PST 文件时，使用此文件中的数据;请参阅[步骤 5](#step-5-delete-the-pst-files-found-on-your-network)。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>步骤 4：将 PST 文件导入 Office 365

收集步骤 1 中的 PST 文件后，下一步是将它们导入 Office 365 中的邮箱。 作为部分或导入过程，您必须创建一个 CSV 映射文件，该文件包含要导入的每个 PST 文件的一行。 每行中的信息指定 PST 文件的名称、用户的电子邮件地址，以及是否要将 PST 文件导入用户的主邮箱或存档邮箱。 使用**作业名\>_查找_\<日期时间戳.csv**文件（在步骤中创建）1 中的信息帮助您创建 CSV 映射文件。 
  
有关将 PST 文件导入 Office 365 的分步说明，请参阅以下主题之一：
  
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>第 5 步：删除网络上的 PST 文件

将找到和收集的 PST 文件导入 Office 365 中的 Exchange 联机邮箱后，可以使用 PST 收集工具从步骤 1 中找到这些文件的原始源位置中删除 PST 文件。 
  
1. 在本地计算机上打开命令提示符（以管理员身份运行）。
    
2. 转到下载 PST 收集工具的目录。
    
3. 运行以下命令以删除 PST 文件。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表描述了在运行 DataCollectorMaster.exe 命令以删除 PST 文件时所需的参数及其所需值。 
    
    |参数*|****描述****|示例*|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据类型。 目前，您可以使用 PST 收集工具来搜索 PST 文件。 ![间隔](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作类型。 使用 值`Delete`可删除在"查找"模式下运行到该工具时找到的 PST 文件。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在步骤 1 和步骤 3 中以"查找"模式和"收集"模式运行该工具时使用的作业名称。 此作业名称也会添加到在"删除"模式下运行该工具时创建的日志文件的名称中。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定包含在"收集"模式下运行该工具时创建的 .xml 配置文件的文件夹。 使用步骤 3 中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定将复制"删除"模式的日志文件的文件夹。 这是一个可选参数。 如果不包括日志文件，日志文件将复制到下载 PST 收集工具的文件夹。 请考虑使用在步骤 1 和步骤 3 中的"查找和收集"模式下运行该工具时使用的相同日志位置，以便将所有日志文件都保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在"删除"模式下为现有 PST 集合作业重新运行该工具。 如果您以前在"删除"模式下运行该工具，但随后在"查找"模式下再次运行该工具，`ForceRestart`并切换到重新扫描 PST 文件的位置，则可以使用此开关在"删除"模式下重新运行该工具，并删除重新搜索时找到的 PST 文件nn 位置。 在"删除"模式下使用`ForceRestart`开关时，该工具将忽略任何以前的删除操作，并尝试再次删除 PST 文件。  <br/> | `-ForceRestart` <br/> 

    下面是使用每个参数的实际值的 DataCollectorMaster.exe 工具的语法示例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    运行该命令后，将显示详细的状态消息，显示删除步骤 1 中找到并在步骤 3 中收集的 PST 文件的进度。 一段时间后，最终状态消息将显示是否存在任何错误以及日志复制到的位置。 相同的状态消息将复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>在删除模式下运行数据收集器Master.exe的结果

在"删除"模式下成功运行 DataCollectorMaster.exe 后，将创建以下文件并将其存储在`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>\<\>作业名删除日期时间戳 .log - 日志文件包含显示的状态消息。__ \<** 此文件在`LogLocation`参数指定的文件夹中创建。 
    
- **\>\<\>作业名删除日期时间戳 .xml - XML 文件仅包含有关工具在"删除"模式下使用的参数值的信息。__ \<** 它还列出了已删除的每个 PST 文件的名称和文件路径。 此文件在`ConfigurationLocation`参数指定的文件夹中创建。 
