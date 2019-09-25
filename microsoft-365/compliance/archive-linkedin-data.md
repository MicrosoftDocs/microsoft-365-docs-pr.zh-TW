---
title: 设置连接器以在 Office 365（预览版）中存档LinkedIn数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器，以便将数据从LinkedIn公司页面导入 Office 365。 这使您可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的合规性。
ms.openlocfilehash: 618cef7c0208378179d41a94f4a274a0bddadee9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076706"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>设置连接器以在 Office 365（预览版）中存档LinkedIn数据

用于存档 Office 365 中LinkedIn公司页面数据的连接器功能为"预览版"。

在 Office 365 中的安全&合规性中心中使用本机连接器从LinkedIn公司页面导入和存档数据。 设置和配置连接器后，它每 24 小时连接到特定LinkedIn公司页面的帐户。 连接器将发布到"公司"页的邮件转换为电子邮件，然后将这些项目导入 Office 365 中的邮箱。

在将LinkedIn公司页面数据存储在邮箱中后，您可以应用 Office 365 合规性功能，如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略来LinkedIn数据。 例如，您可以使用内容搜索搜索这些项目，或将存储邮箱与高级电子数据展示案例中的保管人相关联。 在 Office 365 中创建连接器以导入和存档LinkedIn数据可以帮助您的组织遵守政府和监管政策。

## <a name="before-you--begin"></a>开始之前

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 要同意此请求，请转到[此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全局管理员的凭据登录，然后接受该请求。

- 必须在 Exchange Online 中为创建LinkedIn公司页面连接器的用户分配邮箱导入导出角色。 这是访问安全&合规中心中的**存档第三方数据**页所必需的。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 您可以将邮箱导入导出角色添加到"联机交换"中的组织管理角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在联机交换中管理角色组"一文[中的"创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色组"](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)部分。

- 您必须具有LinkedIn用户帐户的登录凭据（电子邮件地址或电话号码和密码），该用户帐户是您要存档的LinkedIn公司页面的管理员。 设置连接器时，可以使用这些凭据登录LinkedIn。

## <a name="create-a-linkedin-connector"></a>创建LinkedIn连接器

1. <https://protection.office.com>转到，**然后单击"数据治理\>导入"，****然后单击"存档第三方数据"。**

2. 在"**存档第三方数据"** 页上，**单击"添加连接器"，** 然后单击**LinkedIn。**

3. 在"**服务条款"** 页上，单击"**接受"。**

4. 在"**使用LinkedIn登录"** 页上，**单击"使用LinkedIn登录"。**

   将显示LinkedIn登录页。

   ![LinkedIn登录页面](media/LinkedInSigninPage.png)

5. 在LinkedIn登录页中，输入与要存档的公司页面关联的LinkedIn帐户的电子邮件地址（或电话号码）和密码，然后单击"**登录"。**

   向导页面将显示与您登录的帐户关联的所有LinkedIn公司页面的列表。 只能为一个公司页面配置连接器。 如果您的组织有多个LinkedIn公司页面，您必须为每个页面创建一个连接器。

   ![将显示一个包含LinkedIn公司页面列表的页面](media/LinkedInSelectCompanyPage.png)

6. 选择要从中存档项目的公司页面，然后单击"**下一步"。**

7. 在"**设置筛选器"** 页上，可以应用筛选器来最初导入特定年龄的项目。 选择年龄，然后单击"**下一步"。**

8. 在"**设置存储帐户"** 页上，键入将导入LinkedIn项目的 Office 365 邮箱的电子邮件地址，然后单击"**下一步"。** 项目将导入到此邮箱中的收件箱文件夹。

9. 查看连接器设置，**然后单击"保存"** 以完成连接器设置。

创建连接器后，可以**返回"存档第三方数据"** 页（如有必要**单击"刷新"** 以更新连接器列表），查看新连接器。 **"状态"** 列中的值**为"等待启动"。** 启动初始导入过程最多需要 24 小时。 连接器首次运行并导入LinkedIn项后，连接器将每 24 小时运行一次，并导入以前 24 小时内在LinkedIn公司页面上创建的任何新项目。

要查看更多详细信息，**请单击"存档第三方数据"** 页上的列表中的连接器以显示弹出窗口。 **在"状态"** 下，显示的日期范围指示创建连接器时选择的年龄筛选器。 

## <a name="more-information"></a>詳細資訊

- LinkedIn项目将导入 Office 365 中的存储邮箱中的收件箱文件夹。 它们显示为电子邮件。 邮件发件人的显示名称是LinkedIn公司页面的名称。 发件人的实际电子邮件地址是存储邮箱的电子邮件地址。 公司页面的名称也预先追加到主题行。 

- 由于以前的行为，您可以在使用 Microsoft 电子`from`数据`subject`展示工具搜索 office 365 中存档LinkedIn项时搜索 或 通过电子邮件发送属性。 例如，如果公司页面的名称是"Contoso 公司页面"，则可以使用以下*属性之一：* 关键字搜索查询中的值对：
   
   ```
   from:"Contoso Company Page"
   ```

    或

   ```
   subject:"Contoso Company Page"
   ```

- 为了更轻松地查找或管理导入到 Office 365 的LinkedIn项目，存储邮箱的所有者（或分配了"完全访问"权限的任何人）可以设置收件箱规则，将项目从LinkedIn公司页面移动到特定文件夹。 如果存储邮箱用于存档从不同第三方数据源导入的项目，则此功能非常有用。 例如，您可以创建一个收件箱规则，将主题字段中包含特定LinkedIn公司页面名称的所有项目移动到特定文件夹。