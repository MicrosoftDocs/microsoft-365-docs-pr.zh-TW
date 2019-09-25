---
title: 處理資料時的錯誤補救
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
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077164"
---
# <a name="error-remediation-when-processing-data"></a>處理資料時的錯誤補救

错误修正使电子数据展示管理员能够纠正阻止高级电子数据展示正确处理内容的数据问题。 例如，由于文件已被锁定或加密，因此无法处理受密码保护的文件。 使用错误修正，电子数据展示管理员可以下载有此类错误的文件，删除密码保护，然后上载修复的文件。

使用以下工作流修复在高级电子数据展示案例中出现错误的文件。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修正会话以修复具有处理错误的文件

>[!NOTE]
>如果错误修正向导在以下过程中随时关闭，则可以通过**选择"查看"** 下拉菜单中"**修复"** 从"**处理"** 选项卡返回到错误修正会话。

1. 在"高级电子数据展示"案例**中的"处理"** 选项卡上，**在"查看"** 下拉菜单**中选择"错误"，****然后在"范围"** 下拉菜单中选择审阅集或整个案例。 本部分显示来自案例的所有错误或特定审核集的错误。

   ![错误修正](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 通过单击错误类型或文件类型旁边的单选按钮，选择要修复的错误。  在下面的示例中，我们正在修复受密码保护的文件。

3. **单击"新建错误修正"。**

    错误修正工作流从准备阶段开始，其中错误的文件将复制到 Microsoft 提供的 Azure 存储位置，以便您可以将它们下载到本地计算机进行修复。

    ![准备错误补救](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备完成后，**单击"下一步：下载文件"** 以继续下载。

    ![下载文件](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 要下载文件，请指定**要下载的目标路径。** 这是本地计算机上的父文件夹的路径，将在那里下载该文件。  默认路径%USERPROFILE%_下载_错误指向登录用户的下载文件夹。 如果需要，可以更改此路径。 如果确实更改了它，我们建议您使用本地文件路径来获得最佳性能。 不要使用远程网络路径。 例如，可以使用路径**C：\修复**。 

   父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Dest**参数的值）。

6. 通过单击"**复制到剪贴板"** 复制预定义的命令。 打开 Windows 命令提示符，粘贴 AzCopy 命令，然后**按"输入"。**  

    ![准备错误补救](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > 您必须使用 AzCopy v8.1 才能成功**使用"下载文件"** 页上提供的命令。 您还必须使用 AzCopy v8.1 来上载步骤 10 中的文件。 要安装此版本的 AzCopy，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) 如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。

    您选择的文件将下载到您在步骤 5 中指定的位置。 在父文件夹中（**例如，C：\修复），** 将自动创建以下子文件夹结构：

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *子文件夹 1*使用案例 ID 或审阅集命名，具体取决于您在步骤 1 中选择的范围。

    - *子文件夹 2*使用下载文件的文件 ID 命名

    - 下载的文件位于*子文件夹 2*中，并且也使用文件 ID 命名。

    下面是在将项目下载到**C：\修复**父文件夹时创建的文件夹路径和错误文件名的示例：

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    如果下载了多个文件，则每个文件都将下载到使用文件 ID 命名的子文件夹。

    > [!IMPORTANT]
    > 在步骤 9 和步骤 10 中上载文件时，修复的文件必须具有相同的文件名，并且位于相同的子文件夹结构中。 子文件夹和文件名用于将修复的文件与原始错误文件相关联。 如果文件夹结构或文件名发生更改，您将收到以下错误： `Cannot apply Error Remediation to the current Workingset`。 为了防止任何问题，我们建议将修复的文件保留在同一父文件夹和子文件夹结构中。

7. 下载文件后，您可以使用适当的工具进行修复。 对于受密码保护的文件，可以使用多种密码破解工具。 如果您知道这些文件的密码，则可以打开这些文件并删除密码保护。

8. 返回到高级电子数据展示和错误修正向导，**然后单击"下一步：上传文件"。**  这将移动到下一页，您现在可以在其中上载文件。

    ![上传文件](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 指定修复的文件所在的父文件夹，该文件夹**位于"文件位置路径"** 文本框中。 同样，父文件夹必须具有下载文件时创建的子文件夹结构。

    父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Source**参数的值）。

10. 通过单击"**复制到剪贴板"** 复制预定义的命令。 打开 Windows 命令提示符，粘贴 AzCopy 命令，然后**按"输入"。** 上传文件。

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 运行 AzCopy 命令后，**单击"下一步：处理文件"。**

    处理完成后，可以转到查看集并查看修复的文件。 

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

有关高级电子数据展示中所有元数据字段的定义，请参阅[文档元数据字段](document-metadata-fields.md)。
