---
title: 设置连接器以在 Office 365 中存档即时彭博数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器，将数据从即时彭博聊天工具导入 Office 365。 这样，您就可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如法律保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: eda68a0fdc887a2042a78683eaef0693264d0684
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076705"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365"></a>设置连接器以在 Office 365 中存档即时彭博数据

在 Office 365 的安全&合规性中心中使用本机连接器从[即时彭博](https://www.bloomberg.com/professional/product/collaboration/)协作工具导入和存档金融服务聊天数据。 设置和配置连接器后，它每天连接到组织的彭博安全 FTP 站点 （SFTP） 一次，将聊天邮件的内容转换为电子邮件格式，然后将这些项目导入 Office 365 中的邮箱。

将即时彭博数据存储在用户邮箱中后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略）应用于即时彭博数据。 例如，您可以使用内容搜索搜索"即时彭博聊天邮件"，或者将包含"即时彭博"数据的邮箱与高级电子数据展示案例中的保管人相关联。 使用即时彭博连接器在 Office 365 中导入和存档数据可帮助您的组织遵守政府和监管政策。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>存档即时彭博数据概述

以下概述说明了使用连接器在 Office 365 中存档即时彭博聊天数据的过程。 

![即时彭博导入和存档流程](media/InstantBloombergDataArchiving.png)

1. 您的组织与彭博社合作，建立一个彭博SFTP网站。 您还将与彭博社合作，配置即时彭博将聊天消息复制到您的彭博SFTP网站。

2. 每24小时一次，来自即时彭博的聊天消息被复制到彭博SFTP网站。
    
3. 您在安全&合规性中心创建的即时彭博连接器每天连接到彭博 SFTP 站点，并将聊天消息从以前的 24 小时传输到 Microsoft 云中的安全 Azure 存储区域。 连接器还将聊天按摩的内容转换为电子邮件格式。
    
4. 连接器将聊天邮件项目导入特定用户的邮箱或备用邮箱。 连接器通过使用*公司电子邮件地址*属性的值进行。 每个聊天消息都包含此属性，该属性填充了聊天消息的每个参与者的电子邮件地址。 项目是导入到特定用户邮箱还是替代邮箱，基于以下条件：
    
    a. **在"公司电子邮件地址"属性中具有对应于 Office 365 用户帐户的值的项目：** 如果连接器*可以将"公司电子邮件地址"* 属性中的电子邮件地址与 Office 365 中的特定用户帐户相关联，则该项目将复制到用户的 Office 365 邮箱中的收件箱文件夹。
    
    b. **"公司电子邮件地址"属性中的值与 Office 365 用户帐户不对应的项目：** 如果连接器无法*将"公司电子邮件地址"* 属性中的电子邮件地址与 Office 365 中的特定用户帐户相关联，则该项目将复制到 Office 365 中替代的"全部捕获"邮箱的收件箱文件夹。

## <a name="before-you-begin"></a>開始之前

存档即时彭博数据所需的许多实施步骤都位于 Office 365 外部，必须在安全&合规性中心中创建连接器之前完成。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 要同意此请求，请转到[此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤 3 中成功创建即时彭博连接器。

- [订阅彭博任何地方。](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) 这是必要的，以便您可以登录到彭博任何地方访问彭博SFTP网站，你必须设置和配置。

- 设置彭博 SFTP（安全文件传输协议）站点。 在与彭博社合作建立SFTP网站后，来自即时彭博的数据每天都会上传到SFTP网站。 您在步骤 2 中创建的连接器连接到此 SFTP 站点，并将聊天数据传输到 Office 365 邮箱。 SFTP 还加密在传输过程中发送到 Office 365 邮箱的即时彭博聊天数据。

    有关彭博 SFTP 的信息（也称为*BB-SFTP*）：

    - 请参阅[彭博支持](https://www.bloomberg.com/professional/support/documentation/)公司的"SFTP 连接标准"文档。
    
    - 联系[彭博客户支持。](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

    与彭博社合作建立SFTP网站后，在您回复彭博实施电子邮件后，彭博将为您提供一些信息。 保存以下信息的副本。 您可以使用它在步骤 3 中设置连接器。

    - 公司代码，它是组织的 ID，用于登录到彭博 SFTP 网站。

    - 您的彭博SFTP网站的密码

    - 彭博 SFTP 网站的 URL（例如，sftp.bloomberg.com）

    - 彭博 SFTP 站点的端口号

- 在步骤 3 中创建即时彭博连接器的用户（并在步骤 1 中下载公钥和 IP 地址）必须在 Exchange 联机中分配邮箱导入导出角色。 这是访问安全&合规中心中的**存档第三方数据**页所必需的。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 您可以将邮箱导入导出角色添加到"联机交换"中的组织管理角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在联机交换中管理角色组"一文[中的"创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色组"](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)部分。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤 1：获取 SSH 和 PGP 公钥

第一步是获取安全外壳 （SSH） 和良好隐私 （PGP） 的公钥的副本。 在步骤 2 中使用这些键来配置 Bloomberg SFTP 站点，以允许连接器（在步骤 3 中创建）连接到 SFTP 站点并将即时彭博聊天数据传输到 Office 365 邮箱。 在此步骤中，您还可以获得一个 IP 地址，在配置彭博 SFTP 站点时可以使用该 IP 地址。

1. <https://protection.office.com>转到，**然后单击"数据治理\>导入"，****然后单击"存档第三方数据"。**

2. 在"**存档第三方数据"** 页上，**单击"添加连接器"，****然后单击"即时彭博"。**

3. 在"**服务条款"** 页上，单击"**接受"。**

4. 在步骤 1**下的"为彭博 SFTP 网站添加凭据"** 上，**单击"下载 SSH 密钥、****下载 PGP 密钥"****和"下载 IP 地址"** 链接，将每个文件的副本保存到本地计算机。 这些文件包含用于在步骤 2 中配置彭博 SFTP 站点的以下项目：

   - SSH 公钥：此密钥用于配置安全外壳 （SSH），以便在连接器连接到 Bloomberg SFTP 站点时启用安全远程登录。

   - PGP 公钥：此密钥用于配置从彭博 SFTP 站点传输到 Office 365 的数据的加密。

   - IP 地址：彭博 SFTP 站点配置为仅接受来自此 IP 地址的连接请求，该 IP 地址由您在步骤 3 中创建的即时彭博连接器使用。 

5. **单击"取消"** 以关闭向导。 返回步骤 3 中的此向导以创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>第 2 步：配置彭博 SFTP 站点

下一步是使用 SSH 和 PGP 公钥以及您在步骤 1 中获得的 IP 地址为彭博 SFTP 站点配置 SSH 身份验证和 PGP 加密。 这样，您在步骤 3 中创建的即时彭博连接器将连接到彭博 SFTP 站点，并将即时彭博数据传输到 Office 365。 您需要与彭博客户支持合作，建立您的彭博 SFTP 网站。 请联系[彭博客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)寻求帮助。 

> [!IMPORTANT]
> Bloomberg 建议您在步骤 1 中下载的三个文件附加到电子邮件中，并在与客户支持团队合作设置彭博 SFTP 网站时将其发送给他们。

## <a name="step-3-create-an-instant-bloomberg-connector"></a>第 3 步：创建即时彭博连接器

最后一步是在安全&合规中心创建即时彭博连接器。 连接器使用您提供的信息连接到 Bloomberg SFTP 站点并将聊天邮件传输到 Office 365 中的相应用户邮箱框。 

1. <https://protection.office.com>转到，**然后单击"数据治理\>导入"，****然后单击"存档第三方数据"。**

2. 在"**存档第三方数据"** 页上，**单击"添加连接器"，****然后单击"即时彭博"。**

3. 在"**服务条款"** 页上，单击"**接受"。**

4. 在"**为彭博 SFTP 网站添加凭据"页上**的步骤 3 中，在以下框中输入所需信息，然后单击"**下一步"。**

    - **公司代码：** 您组织的 ID，用作彭博 SFTP 站点的用户名。

    - **密码：** 彭博SFTP网站的密码

    - **SFTP URL：** 彭博 SFTP 站点的 URL（例如，sftp.bloomberg.com）。

    - **SFTP 端口：** 彭博 SFTP 站点的端口号。 连接器使用它连接到 SFTP 站点。

5. 在"**替代邮箱"** 页上，键入用于存储来自 Instant Bloomberg 的聊天邮件的邮箱的电子邮件地址，这些邮件与组织中的用户邮箱无关。

   > [!NOTE]
   > Instant Bloomberg 中每个对话中的每个聊天消息都包含一*个名为"公司电子邮件地址"* 的属性，其中包含您组织的聊天参与者的电子邮件地址。 在导入过程中，连接器尝试将聊天邮件导入 Office 365 中的用户邮箱，该用户邮箱的电子邮件地址*与"公司电子邮件地址"* 属性中的电子邮件地址相同。 如果 Office 365 邮箱的地址*与"公司电子邮件地址"* 属性中的邮箱相同，则连接器会将聊天邮件导入到您在此页上指定的备用邮箱。 此时，Office 365 中存档的即时彭博聊天邮件不受 Office 365 中的监督策略监视。

6. **单击"下一步"，** 查看设置，**然后单击"准备"** 以创建连接器。

7. **转到"存档第三方数据"** 页，查看新连接器的导入过程。
