---
title: 將非 Office 365 的資料載入檢閱集
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
description: 将非 Office 365 数据导入高级电子数据展示案例中的审核集。
ms.openlocfilehash: 508346c3fe3a8f67addfed4ced08693daa2d49e7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077232"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>將非 Office 365 的資料載入檢閱集

并非所有需要在高级电子数据展示中分析的文档都位于 Office 365 中。 使用高级电子数据展示中的非 Office 365 数据导入功能，您可以将不在 Office 365 中的文档上载到审阅集。 本文介绍如何将非 Office 365 文档引入高级电子数据展示以进行分析。

>[!Note]
>高级电子数据展示需要适用于您的组织的 Microsoft 365 或 Office 365 E5 订阅，或具有高级合规性加载项订阅的 E3 订阅。 如果您没有该计划，并且想要尝试高级电子数据展示，则可以注册 Office 365 企业版 E5 试用版。

## <a name="before-you-begin"></a>開始之前

使用本文中描述的上载非 Office 365 功能需要具备以下功能：

- 要将非 Office 365 内容关联到的所有保管人都必须分配 E5 许可证或具有高级合规性附加许可证的 E3 许可证。

- 现有的高级电子数据展示案例。

- 必须先将保管人添加到案例中，然后才能将非 Office 365 数据上载并关联到他们。

- 非 Office 365 数据必须是高级电子数据展示支持的文件类型。 有关详细信息，请参阅[高级电子数据展示 中支持的文件类型。](supported-filetypes-ediscovery20.md)

- 上载到审阅集的所有文件都必须位于文件夹中，其中每个文件夹都与特定的保管人相关联。 这些文件夹的名称必须使用以下命名格式：*别名\域名。* 别名\域名必须是用户的 Office 365 别名和域。 您可以收集根文件夹中的所有别名\域名文件夹。 根文件夹只能包含别名\域名文件夹。 不支持根文件夹中的松散文件。

   要上载的非 Office 365 数据的文件夹结构类似于以下示例：

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   abraham.mcmahon@contoso.com、jewell.gordon@contoso.com和staci.gonzalez@contoso.com是案例中保管人的 SMTP 地址。

   ![非 Office 365 数据上传文件夹结构](media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 分配给电子数据展示管理器角色组（并添加为电子数据展示管理员）的帐户。

- AzCopy v8.1 工具安装在有权访问非 Office 365 内容文件夹结构的计算机上。 要安装 AzCopy，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) 请确保在默认位置安装 AzCopy，即 **%程序文件 （x86）%_微软 SDK_Azure_AzCopy**。 您必须使用 AzCopy v8.1。 在高级电子数据展示中加载非 Office 365 数据时，其他版本的 AzCopy 可能无法正常工作。


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将非 Office 365 内容上载到高级电子数据展示

1. 作为电子数据展示管理器或电子数据展示管理员，打开高级电子数据展示，然后将非 Office 365 数据上载到的情况下。  

2. **单击"审阅集"，** 然后选择审阅集以将非 Office 365 数据上载到 。  如果您没有审阅集，则可以创建一个审核集。 
 
3. 在审阅集中，**单击"管理审阅集"，** 然后单击"查看非 Office **365 数据**磁贴上的**上载"。**

4. **单击"上载文件"** 以启动非 Office 365 数据导入向导。

   ![上传文件](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   向导中的第一步准备 Microsoft 提供的安全 Azure 存储位置，以便将文件上载到 。  准备完成后，"**下一步：上传文件"** 按钮将变为活动状态。

   ![非 Office 365 导入：准备](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **单击"下一步：上传文件"。**

6. 在"**上传文件"** 页上，执行以下操作：

   ![非 Office 365 导入：上载文件](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. 在"**文件位置的路径"** 框中，验证或键入要上载的非 Office 365 数据的根文件夹的位置。 例如，对于"**开始之前"部分**中显示的示例文件的位置，将键入 **%USERPROFILE_下载_nonO365**。 提供正确的位置可确保正确更新路径下方框中显示的 AzCopy 命令。

   b. **单击"复制到剪贴板"** 以复制框中显示的命令。

7. 启动 Windows 命令提示，粘贴您在上一步中复制的命令，然后按**Enter**以启动 AzCopy 命令。  启动该命令后，非 Office 365 文件将上载到步骤 4 中准备的 Azure 存储位置。

   ![非 Office 365 导入：AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 如前所述，您必须使用 AzCopy v8.1 才能成功**使用"上载文件"** 页上提供的命令。 如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。

8. 返回安全&合规性中心，然后单击向导**中的"下一步：处理文件"。**  这将启动上载到 Azure 存储位置的非 Office 365 文件的处理、文本提取和索引。  

9. 通过查看**名为"将非 Office 365 数据添加到审阅集"** 的作业，跟踪**处理"进程文件"** 页**或"作业"** 选项卡上的非 Office 365 文件的进度。  作业完成后，新文件将在审阅集中可用。

   ![非 Office 365 导入：处理文件](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 处理完成后，可以关闭向导。