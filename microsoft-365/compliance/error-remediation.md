---
title: 处理调查数据时的错误修正
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
ms.openlocfilehash: 614397a81fd898975e5163c669fb8693fcdfe77c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077074"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>处理调查数据时的错误修正

错误修正使调查人员能够纠正阻止数据调查（预览）正确处理内容的数据问题。 例如，由于文件已被锁定或加密，因此无法处理受密码保护的文件。 使用错误修正，调查人员可以下载包含此类错误的文件、删除密码保护并上载修复的文件。

使用以下工作流修复数据调查（预览）案例中的错误的文件。

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修正会话以修复具有处理错误的文件

>[!NOTE]
>如果错误修正向导在以下过程中随时关闭，则可以**通过在"查看"** 下拉菜单**中选择"错误修正"** 从"**处理"** 选项卡返回到错误修正会话。

1. 在数据调查中**的"处理"** 选项卡上，在"**查看"** 下拉菜单**中选择"错误"。**

2. 通过单击错误类型或文件类型旁边的单选按钮，选择要修复的错误。  在下面的示例中，我们正在修复受密码保护的文件。

3. 单击 **" 新建错误修正**。

    ![错误修正](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    错误修正会话从准备阶段开始，其中错误文件将复制到安全的 Azure 位置，以便可以下载它们。

    ![准备错误补救](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备完成后，**单击"下一步：下载文件"** 以继续下载。

    ![下载文件](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 要下载文件，请指定**要下载的目标路径。** 这是本地计算机上的路径，应在此路径中下载文件。  默认路径%USERPROFILE%_下载_错误指向登录用户的下载文件夹;这可以根据需要进行更改。

    >[!NOTE]
    >我们建议您使用本地文件路径而不是远程网络路径来获得最佳性能。

    > [!NOTE]
    > 如果您尚未安装 AzCopy，则可以从这里安装它：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. 通过单击"**复制到剪贴板"** 复制预定义的命令。 启动 windows 命令提示，粘贴命令，然后按**Enter。**  

    文件将被下载。

    ![准备错误补救](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > 如果在运行此命令时遇到问题，请参阅[高级电子数据展示中的"疑难解答"AzCopy。](troubleshooting-azcopy.md)

7. 下载文件后，您可以使用适当的工具进行修复。 对于受密码保护的文件，可以使用多种密码破解工具。 如果您知道这些文件的密码，则可以打开这些文件并删除密码保护。
    
   > [!NOTE]
    > 保留修复文件的目录结构和文件名非常重要。 下载的文件和文件夹的路径名称使得可以将修复的文件与原始文件相关联。  如果目录结构或文件名发生更改，您将收到以下错误： `Cannot apply Error Remediation to the current Evidenceset`。

8. 现在，返回到数据调查（预览），**然后单击"下一步：上传文件"。**  这将移动到下一步，您现在可以上传文件。

    ![上传文件](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 在"**文件位置路径"** 文本框中指定已修复文件的位置，然后单击"**复制到剪贴板"。**

10. 将命令粘贴到 Windows 命令提示符中，然后按**Enter**上载文件。

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 最后，返回到数据调查（预览），**然后单击"下一步：处理文件"。**

12. 处理完成后。  您可以返回到工作集并查看修复的文件。

## <a name="what-happens-when-files-are-remediated"></a>修复文件时会发生什么情况

上载修复的文件时，原始元数据将保留，但以下字段除外： 

- 提取的文本大小
- HasText
- 误位修正
- 加载 Id
- 处理错误消息
- 处理状态
- Text
- 字数
- 工作集Id

有关数据调查（预览）中所有文档元数据字段的定义，请参阅[文档元数据字段](document-metadata-fields.md)。