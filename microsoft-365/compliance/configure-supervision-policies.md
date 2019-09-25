---
title: 為您的組織設定監督原則
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: 设置监督审核策略，以捕获员工通信以进行审核。
ms.openlocfilehash: ccbc5897ef8c6fb6018793ff7e3fe7731ee14710
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076612"
---
# <a name="configure-supervision-policies-for-your-organization"></a>為您的組織設定監督原則

使用监督策略捕获员工通信，供内部或外部审阅者检查。 有关监督策略如何帮助您监视组织中的通信的详细信息，请参阅[Office 365 中的"监督策略"。](supervision-policies.md)

> [!NOTE]
> 受监督策略监视的用户必须具有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中。
> 如果您没有现有的企业 E5 计划，并且想要尝试监督，则可以注册 Office [365 企业版 E5 的试用版。](https://go.microsoft.com/fwlink/p/?LinkID=698279)
  
按照以下步骤在 Office 365 组织中设置和使用监督：
  
- **第 1 步（可选）：**[设置监督组](#step-1-set-up-groups-for-supervision-optional) 

    在开始使用监督之前，请确定谁需要审核通信以及谁执行审核。 如果你想开始与几个用户，看看监督是如何工作的，你可以跳过设置组现在。

- **第 2 步（必需）：**[在组织中提供监督](#step-2-make-supervision-available-in-your-organization-required)

    将自己添加到"监督审核"角色组，以便可以设置策略。 分配了此角色的任何人都可以访问合规中心**中的"监督"** 页面。 如果可审阅的电子邮件托管在 Exchange 在线上，则每个审阅者必须具有[对 Exchange 在线的远程 PowerShell 访问权限。](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)

- **步骤 3（可选）：**[创建自定义敏感信息类型和自定义关键字字典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    如果您需要自定义敏感信息类型或自定义关键字字典作为监督策略，则需要在启动监督向导之前创建它。

- **第 4 步（必）：**[设置监督政策](#step-4-set-up-a-supervision-policy-required)

    您可以在合规中心创建监督策略。 这些策略定义组织中哪些通信需要审核，并指定执行审核的人员。 通信包括电子邮件和 Microsoft 团队通信以及第三方平台通信（如 Facebook、Twitter 等）

- **第 5 步（可选）：**[测试您的监督策略](#step-5-test-your-supervision-policy-optional)

    测试您的监督策略，以确保其按预期运行。 请务必确保您的合规战略符合您的标准。

- **步骤 6（可选）：**[为不想使用 Office 365 监督仪表板的审阅者配置 Outlook 以审阅受监督的通信](#step-6-configure-outlook-for-reviewers-optional)

    配置 Outlook 以允许审阅者访问 Outlook 客户端中的监督功能，以便他们可以评估和分类每个项目。

## <a name="step-1-set-up-groups-for-supervision-optional"></a>第 1 步：设置监督组（可选）

 创建监督策略时，您可以定义谁审阅了他们的通信，谁执行审核。 在策略中，您将使用电子邮件地址来标识个人或组。 为了简化您的设置，您可以为审核其通信的人员创建组，并为审阅这些通信的人员创建组。 如果您使用的是组，则可能需要多个组。 例如，您希望监视两个不同的人员组之间的通信，或者如果要指定一个不受监督的组。

使用以下图表帮助您在组织中配置组以进行监督策略：

| **政策成员** | **支持的组** | **不支持的组** |
|:-----|:-----|:-----|
|受监督的用户 <br> 非监督用户 | 通訊群組 <br> Office 365 群組 | 動態通訊群組 |
| 檢閱者 | 擁有郵件功能的安全性群組  | 通訊群組 <br> 動態通訊群組 |
  
当您为受监督的用户选择 Office 365 组时，策略将监视共享 Office 365 邮箱和与该组关联的 Microsoft Teams 通道的内容。 选择通讯组列表时，策略将监视各个用户邮箱。

要管理大型企业组织中受监督的用户，您可能需要监视大型组中的所有用户。 您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。 这使您能够使用单个策略监视数千个用户，并在新员工加入您的组织时更新监督策略。

1. 使用以下属性为全局监督策略创建专用[通讯组：](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)确保此通讯组未用于其他目的或其他 Office 365 服务。

    - **成员分类限制 = 已关闭**。 确保用户无法从通讯组中删除自己。
    - **成员联接限制 = 已关闭**。 确保用户无法将自己添加到通讯组。
    - **启用调节 = True**。 确保发送到此组的所有邮件都需获得批准，并且该组不用于在监督策略配置之外进行通信。

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. 选择未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)以跟踪添加到组织中监督策略的用户。

3. 定期运行以下 PowerShell 脚本，将用户添加到监督策略：

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

有关设置组的详细信息，请参阅：

- [建立並管理通訊群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理啟用郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 组概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>第 2 步：在组织中提供监督（必需）

要使"**监督"** 在合规中心中作为菜单选项可用，您必须分配监督审核管理员角色。
  
为此，您可以将自己添加为"监督审核"角色组的成员，也可以创建角色组。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>将成员添加到监督审核角色组

1. 使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。

2. 在合规中心，**转到"权限"。**

3. 选择"**监督审阅"** 角色组，然后单击"编辑"图标。

4. 在"**成员"** 部分中，添加要管理组织监督的人员。

### <a name="create-a-new-role-group"></a>创建新角色组

1. 使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。

2. 在合规性中心中，**转到"权限"，** 然后单击"添加**+**（ ）。

3. 在"**角色"** 部分中，单击"添加 （**+**）"并向下滚动**到"监督审阅管理员"。** 将此角色添加到角色组。

4. 在"**成员"** 部分中，添加要管理组织监督的人员。

有关角色组和权限的详细信息，请参阅[合规性中心的权限。](../security/office-365-security/protect-against-threats.md)

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>为审阅者启用远程 PowerShell 访问权限（如果电子邮件托管在 Exchange 在线上）

1. [按照"启用"或"禁用对 Exchange 在线电源外壳 "中的访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导操作。

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>步骤 3：创建自定义敏感信息类型和自定义关键字字典（可选）

为了从监管策略向导中现有的自定义敏感信息类型或自定义关键字字典中进行选择，首先需要根据需要创建这些项目。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>创建自定义关键字词典/词典（可选）

使用文本编辑器（如记事本）创建包含要在监督策略中监视的关键字字词的文件。 确保每个术语都位于单独的行上，并将文件以**Unicode/UTF-16（小 Endian）** 格式保存。

### <a name="create-custom-sensitive-information-types"></a>创建自定义敏感信息类型

1. 创建新的敏感信息类型，并在 Office 365 安全&合规性中心中添加自定义词典。 导航到**分类**\>**敏感信息类型，** 并**按照"新建敏感信息类型"向导**中的步骤操作。 在这里，您将：

    - 定义敏感信息类型的名称和说明
    - 定义邻近度、置信度和主要模式元素
    - 将自定义字典作为匹配元素的要求导入
    - 查看您的选择并创建敏感信息类型

    有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字字典](create-a-keyword-dictionary.md)

    创建自定义词典/词典后，您可以使用[Get-DlpKeyword](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)字典 cmdlet 查看已配置的关键字，或使用[Set-DlpKeyword 字典](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)cmdlet 添加和删除术语。

## <a name="step-4-set-up-a-supervision-policy-required"></a>第 4 步：设置监督策略（必需）
  
1. 使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。

2. 在合规中心中，**选择"监督"。**
  
3. **选择"创建"** 并按照向导设置策略配置。 使用向导，您将：

    - 为策略指定名称和说明。
    - 选择要监督的用户或组，包括选择要排除的用户或组。
    - 定义监督政策[条件。](supervision-policies.md#ConditionalSettings) 您可以从消息地址、关键字、文件类型和大小匹配条件中进行选择。
    - 选择是否希望包含敏感信息类型。 您可以在其中选择默认和自定义敏感信息类型。
    - 选择是否要启用攻击性语言模型。 这将检测电子邮件正文中发送或接收的不当语言。
    - 定义要审阅的通信的百分比。
    - 选择策略的审阅者。 审阅者可以是单个用户或[已启用邮件的安全组。](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group) 所有审阅者都必须在 Exchange 联机上托管邮箱。
    - 查看策略选择并创建策略。

## <a name="step-5-test-your-supervision-policy-optional"></a>第 5 步：测试您的监督策略（可选）

创建监督策略后，最好进行测试，以确保策略正确执行所定义的条件。 如果监管策略包含敏感信息类型，您可能还需要[测试数据丢失防护 （DLP） 策略。](create-test-tune-dlp-policy.md) 请按照以下步骤测试您的监督策略：

1. 打开电子邮件客户端或 Microsoft Teams 以要测试的策略中定义的受监督用户身份登录。
2. 发送电子邮件或 Microsoft 团队聊天，满足您在监督策略中定义的条件。 这可以是关键字、附件大小、域等。请确保确定策略中配置的条件设置是否过于严格或过于宽松。

    > [!Note]
    > 受定义策略约束的电子邮件将近乎实时地处理，并在策略配置后立即进行测试。 Microsoft Teams 中的聊天最多可能需要 24 小时才能在策略中完全处理。 

3. 作为监督策略中指定的审阅者登录到 Office 365 租户。 导航**到"监督** > *自定义策略* > **打开"** 以查看策略的报告。

## <a name="step-6-configure-outlook-for-reviewers-optional"></a>步骤 6：为审阅者配置 Outlook（可选）

想要使用 Outlook 而不是 Office 365 中的"监督"仪表板来审阅通信的审阅者必须配置其 Outlook 客户端。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>第 1 步：复制监督邮箱的地址

要配置 Outlook 桌面的审阅，您需要作为监督策略设置的一部分创建的监督邮箱的地址。
  
> [!NOTE]
> 如果其他人创建了该策略，则需要从他们那里获得此地址才能安装外接程序。

**查找监督邮箱地址**
  
1. 使用组织中管理员帐户的凭据登录到[合规性中心。](https://compliance.microsoft.com)

2. 转到**监督**。

3. 为要查看的通信选择监督策略。

4. 在策略详细信息弹出窗口中，**在"监督邮箱"** 下，复制地址。<br/>![监督政策详细信息的"监督邮箱"部分弹出窗口显示突出显示的监督邮箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>第 2 步：为 Outlook 访问配置监督邮箱

接下来，审阅者需要运行几个 Exchange 联机 PowerShell 命令，以便他们可以将 Outlook 连接到监督邮箱。
  
1. 連線至 Exchange Online PowerShell。 [該怎麼做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 运行以下命令，*其中SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步骤 1 中复制的地址，*而"用户"* 是将连接到步骤 3 中的监督邮箱的审阅者的名称。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 请等待至少一个小时，然后再继续执行步骤 3。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步骤 3：创建 Outlook 配置文件以连接到监督邮箱

对于最后一步，审阅者需要创建 Outlook 配置文件以连接到监督邮箱。

> [!NOTE]
> 要创建新的 Outlook 配置文件，您将在 Windows 控制面板中使用"邮件"设置。 您访问这些设置的路径可能取决于您使用的 Windows 操作系统（Windows 7、Windows 8 或 Windows 10）以及安装的 Outlook 版本。
  
1. 打开控制面板。 在窗口顶部**的"搜索"** 框中，**键入"邮件"。**<br/>（不确定如何进入控制面板？ 请参阅[控制面板在哪里？）](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. 打开"**邮件"** 应用。

3. 在**邮件设置 - Outlook**中，**单击"显示配置文件"。**<br/>![突出显示"显示配置文件"按钮的"邮件设置 - Outlook"对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. **在"邮件"** 中，**单击"添加"。** 然后，**在新配置文件**中，输入监督邮箱的名称（如**监督**）。<br/>!["配置文件名称"框中显示名称"新配置文件"对话框](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在**将 Outlook 连接到 Office 365**中，**单击"连接到其他帐户"。**<br/>![突出显示"将 Outlook 连接到 Office 365"消息，并突出显示"连接到其他帐户"链接](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. **在"自动帐户设置"** 中，**选择"手动设置"或其他服务器类型，** 然后单击"**下一步"。**

7. **在"选择帐户类型"** 中，选择**Office 365**。 然后，**在"电子邮件地址"** 框中输入以前复制的监督邮箱的地址。<br/>![Outlook 中的"添加帐户"对话框中的"选择帐户类型"页面突出显示了"电子邮件地址"框。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 当出现提示时，请输入 Office 365 凭据。

9. 如果成功，则"**监督\<"\>策略名称**文件夹将列在 Outlook 中的"文件夹列表"视图中。

## <a name="powershell-reference"></a>电源外壳参考

如果需要，您可以使用以下 PowerShell cmdlet 创建和管理监督策略：

- [新监督审查政策V2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [获取监督审查策略V2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [设置-监督审查策略V2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [删除-监督审查策略V2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新监督审查规则](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [设置-监督审查规则](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [获取监督审查活动](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [获取监督审查总体进度报告](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [获取监督审查顶级案例报告](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
