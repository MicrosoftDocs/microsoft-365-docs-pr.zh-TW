---
title: 使用网络上载将 RMS 加密的 PST 文件导入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用网络上载将 RMS 加密的 PST 文件导入 Office 365 中的用户邮箱。
ms.openlocfilehash: e14c5a7260bc8b2092075dd2ab711f4da2d3b9c2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078286"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>使用网络上载将 RMS 加密的 PST 文件导入 Office 365

**本文是为管理员。您是否正在尝试将 PST 文件导入您自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用网络上载选项和 Office 365 导入服务将 PST 文件导入到用户邮箱。 网络上传意味着您在 Microsoft 云中上载 PST 文件的临时存储区域。 然后 Office 365 导入服务将 PST 文件从存储区域复制到目标用户邮箱。 通过导入服务的新功能，您可以在 PST 文件上载并存储在 Microsoft 云之前对其进行加密。 这些文件将取消加密时，它们被导入到用户邮箱。 
  
以下是加密 PST 文件并将其导入 Office 365 邮箱所需的步骤：
  
[步骤 1：为 PST 导入设置 Azure 权限管理](#step-1-set-up-azure-rights-management-for-pst-import)

[步骤 2：为 PST 导入生成加密密钥](#step-2-generate-an-encryption-key-for-pst-import)

[步骤 3：获取 RMS 租户 ID 和许可 URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[第 4 步：下载 PST 导入工具并复制 SAS URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[第 5 步：加密 PST 文件并将其上载到 Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[（可选）步骤 6：查看上载到 Office 365 的 PST 文件列表](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 7：创建 PST 导入映射文件](#step-7-create-the-pst-import-mapping-file)

[步骤 8：在 Office 365 中创建 PST 导入作业](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 您必须执行步骤 1 到步骤 4 一次，以设置和配置您的组织，以加密 PST 文件并将其导入 Office 365 邮箱。 执行这些步骤后，每次要加密、上载和导入一批 PST 文件时，请执行步骤 5 和步骤 8。 
  
有关将数据导入 Office 365 的详细信息，请参阅[将组织 PST 文件导入 Office 365 的概述。](importing-pst-files-to-office-365.md)
  
## <a name="before-you-begin"></a>開始之前

- 您必须在 Exchange 联机中分配邮箱导入导出角色才能将 PST 文件导入 Office 365 邮箱。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 有关详细信息，请参阅[管理角色组中](https://go.microsoft.com/fwlink/p/?LinkId=730688)的"将角色添加到角色组"或"创建角色组"部分。
    
    此外，要在安全&合规中心创建导入作业，以下必须为 true：
    
  - 您必须在"联机交换"中分配邮件收件人角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
  - 您必须是 Office 365 组织的全局管理员。
    
  > [!TIP]
  > 请考虑在 Exchange Online 中创建新的角色组，该角色组专门用于将 PST 文件导入 Office 365。 对于导入 PST 文件所需的最低权限级别，将邮箱导入导入和邮件收件人角色分配给新角色组，然后添加成员。 
  
- 您需要将要导入 Office 365 的 PST 文件存储在组织中的文件服务器或共享文件夹中。 在步骤 5 中，您将运行 Office 365 导入工具，它将加密存储在此文件服务器或共享文件夹上的 PST 文件并将其上载到 Office 365。
    
- 此过程涉及复制和保存加密密钥、存储密钥以及许多标识密钥和 URL 的副本。 此信息将在步骤 5 中使用来加密和上传您的 PST 文件。 請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。 舉例來說，您可能會將這些資訊儲存於受密碼保護的 Microsoft Word 文件內，或是將它們儲存於已加密的 USB 裝置中。 有关这些密钥、D 和 URL 的示例，请参阅[详细信息](#more-information)部分。 
    
- 您可以将 PST 文件导入 Office 365 中的非活动邮箱。 为此，您可以在 PST 导入映射文件中的`Mailbox`参数中指定非活动邮箱的 GUID。 有关详细信息，请参阅[步骤 7。](#step-7-create-the-pst-import-mapping-file) 
    
- 在 Exchange 混合部署中，您可以将 PST 文件导入到主邮箱位于本地的用户的基于云的存档邮箱。 通过在 PST 导入映射文件中执行以下操作来执行此操作：
    
  - 在`Mailbox`参数中指定用户本地邮箱的电子邮件地址。 
    
  - 在****`IsArchive`参数中指定 TRUE 值。 
    
    有关详细信息，请参阅[步骤 7。](#step-7-create-the-pst-import-mapping-file) 
    
- 将 PST 文件导入 Office 365 邮箱后，邮箱的保留保留设置将无限期打开。 这意味着，在关闭保留保留或设置关闭保留的日期之前，不会处理分配给邮箱的保留策略。 我们为什么要这么做？ 如果导入到邮箱的邮件是旧的，则可能会永久删除（清除），因为它们的保留期已根据为邮箱配置的保留设置过期。 将邮箱置于保留保留状态将使邮箱所有者有时间管理这些新导入的邮件，或让您有时间更改邮箱的保留设置。 有关管理保留保留的建议，[请参阅"详细信息"](#more-information)部分。 
    
- 如果在将 PST 文件上载到 Office 365 之前不需要对其进行加密，请参阅[使用网络上载将 PST 文件导入 Office 365](use-network-upload-to-import-pst-files.md)。
    
- 有关使用网络上载将 PST 文件导入 Office 365 的常见问题，请参阅[有关将 PST 文件导入 Office 365 的常见问题。](faqimporting-pst-files-to-office-365.md)
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>步骤 1：为 PST 导入设置 Azure 权限管理

PST 导入使用 Office 365 中的 Azure 权限管理 （Azure RMS） 服务提供的加密功能。 这允许您在将 PST 文件上载到 Office 365 之前对其进行加密。 
  
为 PST 导入配置 Azure RMS 包括三个步骤：
  
- [激活 Azure RMS](#activating-azure-rms)
    
- [在线交换中配置 RMS](#configuring-rms-in-exchange-online)
    
- [安装活动目录 RMS 客户端](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>激活 Azure RMS

默认情况下禁用 Azure RMS，但您或组织中的另一个管理员可能已激活它。 按照有关激活[Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)的说明安装和激活 Azure DRM。
  
### <a name="configuring-rms-in-exchange-online"></a>在线交换中配置 RMS

激活权限管理服务后，下一步是在 Exchange 联机中设置信息权限管理 （IRM） 以使用 Azure RMS。 有关详细信息，请参阅配置[IRM 以使用 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=394816)。
  
1. [使用远程电源外壳连接到在线交换。](https://go.microsoft.com/fwlink/p/?LinkId=396554 )
    
2. 运行以下命令以设置 RMS 密钥共享 URL。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    使用下表确定组织位置的正确 RMS 密钥共享位置。
    
    |**位置**|**RMS 金鑰共用位置**|
    |:-----|:-----|
    |北美  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |歐盟  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |亚洲  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南美洲  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 for Government (政府社群雲端)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup>只有购买了 Office 365 的政府 SKU（政府社区云）的客户才应使用此 RMS 密钥共享位置。 
  
    例如，此命令为位于北美的客户配置"交换联机"中的 RMS 联机密钥共享位置。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 运行以下命令，将受信任的发布域 （TPD） 从 RMS 联机导入 Office 365 组织。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD 包含组织中使用 RMS 功能所需的设置，包括加密 PST 文件。 
    
4. 运行以下命令以为您的 Office 365 组织启用 IRM。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>安装活动目录 RMS 客户端

本节的最后一步是下载权限管理服务 （RMS） 客户端 2.1。 此软件有助于保护对 Azure RMS 的访问，并保护通过使用 Azure RMS 的应用程序流经的信息。 在步骤 5 中用于加密和上载 PST 文件的同一台计算机上安装 RMS 客户端。 
  
1. 下载[权限管理服务客户端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).
    
2. 运行活动目录权限管理服务客户端 2.1 向导以安装客户端。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>步骤 2：为 PST 导入生成加密密钥

设置 Azure RMS 后，下一步是生成加密密钥（称为对称密钥），用于加密上载到 Office 365 的 PST 文件。 您将通过在 Azure 活动目录中将 PST 导入服务添加为服务主体来执行此操作。 将此应用程序添加为服务主体将允许 PST 导入服务在将加密的 PST 文件上载到步骤 5 中的 Azure 存储位置时，直接使用 Azure 活动目录进行身份验证。
  
1. 启动 Windows 电源外壳的 Azure 活动目录模块。
    
2. 运行以下命令以连接到 Microsoft 在线服务。
    
    ```
    Connect-MsolService
    ```

3. 在 Office 365 组织中输入管理员帐户的凭据，然后单击"**确定"。**
    
4. 运行以下命令以生成加密密钥（调用对称密钥）。 您将通过创建新的 PST 加密主体来执行此操作。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    系统显示对称密钥和新的 PST 加密主体的属性。
    
    ![複製並儲存所顯示的對稱金鑰](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 将对称键复制到文本或 Word 文件。 如先前所述，請確定已採取相關預防措施來保護此檔案。 由于这是显示对称键的唯一时间，因此您也可以考虑获取此窗口的屏幕截图并将其保存到同一文件。 
    
    > [!IMPORTANT]
    > 创建 PST 加密主体后，您将无法使用**Get-MsolServiceMmcmdlet**检索对称密钥。 这就是为什么保存密钥很重要的原因。 
  
保持 Windows PowerShell 的 Azure 活动目录模块处于打开状态并连接到 Microsoft 联机服务。 在下一步中，您将在此窗口中运行一个命令。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>步骤 3：获取 RMS 租户 ID 和许可 URL

下一步是为您的组织获取 Azure RMS 服务的租户 ID 和许可位置 URL。 将此信息复制并保存到包含步骤 2 中的对称密钥的同一文件。 ID 和 URL 将在步骤 5 中使用来加密您的 PST 文件。
  
1. 在 Windows PowerShell 的 Azure 活动目录模块（连接到 Microsoft 联机服务）中，运行以下命令以连接到 Office 365 组织的 Azure RMS 服务。
    
    ```
    Connect-AadrmService 
    ```

2. 在 Office 365 组织中输入管理员帐户的凭据，然后单击"**确定"。**
    
3. 运行以下命令以在 Office 365 组织中显示 Azure RMS 服务的租户 ID。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    复制并保存`BPOSId`该属性的值。 
    
4. 运行以下命令以显示 Azure RMS 服务的许可位置。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    复制并保存`LicensingIntranetDistributionPointUrl`该属性的值。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>第 4 步：下载 PST 导入工具并复制 SAS URL

现在，您已经配置了 Azure RMS 并获取了加密 PST 文件所需的标识，下一步是下载并安装将在步骤 5 中运行的工具，以加密 PST 文件并将其上载到 Office 365。 这些工具是 Azure AzCopy 工具和 Office 365 数据加密工具。 您还将复制组织的 SAS URL。 此 URL 是组织在 Microsoft 云中的 Azure 存储位置的网络 URL 和共享访问签名 （SAS） 密钥的组合。 此密钥为您提供了将 PST 文件上载到 Azure 存储位置所需的权限。 将其保存到步骤 2 和步骤 3 中已复制到其他信息的同一文件。 如前所述，采取预防措施以保护 SAS URL。 
  
> [!IMPORTANT]
> 您必须使用 Azure AzCopy 版本 5.0 才能成功将 PST 文件上载到 Azure 存储位置。 将 PST 文件导入 Office 365 时不支持新版本的 AzCopy 工具。 请务必按照此步骤中的步骤，从**通过网络页面上传文件**下载 AzCopy 工具。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用 Office 365 组织中管理员帐户的凭据登录到 Office 365。
    
3. 在左侧窗格中，**单击"数据治理"，** 然后单击"**导入"。**
    
4. 在 [匯入]**** 頁面中，按一下 [移至匯入服務]****。
    
5. 在"**将数据导入 Office 365"** 页上，**单击"新建作业**![添加图标"，](media/ITPro-EAC-AddIcon.gif)**然后单击"上传电子邮件（PST 文件）"。**
    
6. 在"**通过网络上传文件"** 页上，在步骤 2 中，单击**显示网络上传 SAS URL**。
    
7. 显示 URL 后，复制它并将其保存在保存其他密钥的文件中。 請務必複製完整 URL。 
    
8. 在步骤 3 中，单击**下载 Azure AzCopy 工具**以下载并安装 Azure AzCopy 工具。 
    
9. 在快顯視窗中，按一下 [執行]**** 來安裝 Azure AzCopy 工具。 
    
    > [!IMPORTANT]
    > 请确保在默认位置安装 Azure AzCopy 工具，该工具位于`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`运行 64 位 Windows 的计算机上。 这是因为当您在步骤 5 中运行 O365ImportTool.exe 时，它会在此位置查找 AzCopy 工具。 
  
10. 安装 Azure AzCopy 工具后，**单击"下载 Office 365 数据加密和导入工具"。**
    
11. 在弹出窗口中，\>**单击"保存保存"** 以将 O365ImportTool.zip 文件保存到本地计算机上的文件夹中。 **** 
    
12. 提取 O365导入工具.zip 文件。
    
13. **单击"取消"** 以关闭**通过网络页面上上传的文件。** 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>第 5 步：加密 PST 文件并将其上载到 Office 365

完成步骤 1 到步骤 4 后，即可使用 O365ImportTool.exe 工具加密 PST 文件并将其上载到 Office 365。 此工具对 PST 文件进行加密，然后将其上载并存储在 Microsoft 云中的 Azure 存储位置。 若要完成此步驟，PST 檔案必須位於貴組織的檔案共用內或檔案伺服器中。 在下列程序中，這就是所謂的 [來源目錄]。 每次运行 O365ImportTool.exe 工具时，都可以指定不同的源目录。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
2. 转到步骤 4 中安装 O365ImportTool.exe 工具的目录。
    
3. 运行以下命令以加密 PST 文件并将其上载到 Office 365。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    下表說明了參數與其需要的值。請注意，您在先前步驟中所取得的資訊，會在這些參數內的值中使用。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |指定组织中包含将上载到 Office 365 的 PST 文件的源目录。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |指定 Azure RMS 服务的许可位置。 使用您在步骤 3`LicensingIntranetDistributionPointUrl`中获取的属性的值。 请确保用双引号 （""） 环绕此参数的值  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |指定 Azure RMS 组织的标识。 使用您在步骤 3`BPOSId`中获取的属性的值。  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |指定在步骤 2 中获取的对称键。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |指定是通过网络上传 PST 文件还是将它们运送到硬盘驱动器上。 该值`upload`表示您通过网络上载文件。 该值`drive`表示您正在硬盘上运输 PST。  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |指定将 PST 文件上载到的 Office 365 中的目标;这是组织的 Azure 存储位置。 此参数的值由您在步骤 4 中复制的 SAS URL 中的网络上载 URL 组成。 請務必使用雙引號 (" ") 括住此參數的值。  <br/><br/> **提示：**（可选）您可以在 Azure 存储位置指定子文件夹以将加密的 PST 文件上载到。 为此，请添加网络上载 URL 中的子文件夹位置（在"引入数据"之后）。 第一个示例未指定子文件夹;第二个示例未指定子文件夹。这意味着 PST 将上载到 Azure 存储位置的根（名为*引入数据）。* 第二个示例将 PST 文件上载到 Azure 存储位置中的子文件夹（名为*加密 PST）。*           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> 或  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |指定组织的 SAS 密钥。 此参数的值由您在步骤 4 中复制的 SAS URL 中的 SAS 密钥组成。 请注意，SAS 键中的第一个字符是一个问号 （"？"）。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |此可选开关指定递归模式，以便 O365ImportTool.exe 工具将复制位于`/srcdir:`参数指定的源目录中子文件夹中的 PST 文件。  <br/><br/> **注意：** 如果包含此开关，则子文件夹中的 PST 文件在上载后将在 Azure 存储位置具有不同的文件路径名称。 您必须在步骤 7 中创建的 CSV 文件中指定确切的文件路径名称。           | `/recurse` <br/> |
   
    下面是使用每个参数的实际值的 O365ImportTool.exe 工具的语法示例：
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    运行该命令后，将显示状态消息，显示加密和上载 PST 文件的进度。 最终状态消息显示成功加密和上载的文件总数。 
    
    > [!TIP]
    > 成功运行 O365ImportTool.exe 命令并验证所有参数是否正确后，将命令行语法的副本保存到复制上述步骤中获得的信息的同一（安全）文件中。 然后，每次要运行 O365ImportTool.exe 工具以加密 PST 文件并将其上载到 Office 365 时，都可以在命令提示符中复制和粘贴此命令。 可能需要更改的唯一值是`/srcdir:`和`/upload-dest:`参数的值。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（可选）步骤 6：查看上载到 Office 365 的 PST 文件列表

作为可选步骤，您可以安装和使用 Microsoft Azure 存储资源管理器（这是一个免费的开源工具）来查看已上载到 Azure Blob 的 PST 文件的列表。 这样做有三个充分的理由：
  
- 验证组织中共享文件夹或文件服务器中的 PST 文件是否已成功上载到 Azure Blob。

- 验证 PST 文件是否加密。 加密的 PST`.pfile`文件有一个扩展名追加到 PST 文件名;例如， `pilarp.pst.pfile`.
    
- 验证上载到 Azure Blob 的每个 PST 文件的文件名（以及子文件夹路径名（如果包含一个）。 當您要在下一個步驟中建立 PST 對應檔案時，這項功能會很有幫助，因為您必須指定每個 PST 檔案的資料夾路徑名稱及檔名。 驗證這些名稱有助於減少 PST 對應檔中的潛在錯誤。
    
微软 Azure 存储资源管理器处于预览版。 
  
 > [!IMPORTANT]
>  不能使用 Azure 存储资源管理器上载或修改 PST 文件。 将 PST 文件导入 Office 365 的唯一受支持方法是使用 AzCopy。 此外，不能删除已上载到 Azure Blob 的 PST 文件。 如果您嘗試刪除 PST 檔案，您會收到沒有必要權限的相關錯誤。 请注意，所有 PST 文件都将自动从 Azure 存储区域中删除。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
要安装 Azure 存储资源管理器并连接到 Azure 存储区域，请执行以下操作：
  
1. 下载并安装[微软 Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器，在左侧窗格中右键**单击"存储帐户"，** 然后单击"**连接到 Azure 存储"。** 
    
    ![右键单击存储帐户，然后单击"连接到 Azure 存储"](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 在"连接到**Azure 存储"** 下的框中，粘贴在步骤 4 中获取的 SAS URL，然后单击"**下一步"。** 
    
    ![将 SAS URL 粘贴到"连接到 Azure 存储"页上的框中](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. 在"**连接摘要"** 页上，您可以查看连接信息，然后单击"**连接"。** 
    
5. **在"存储帐户"** 下，展开 **（服务 SAS）** 节点，然后展开**Blob 容器**节点。 
    
6. 以滑鼠右鍵按一下 **ingestiondata**，然後按一下 [ **開啟 Blob 容器編輯器]**。
    
    ![以滑鼠右鍵按一下 ingestiondata，然後按一下 [開啟 Blob 容器編輯器]](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    将显示 Azure 存储区域，其中显示您在步骤 5 中上载的 PST 文件的列表。
    
    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. 使用完 Microsoft Azure 存储资源管理器后，右键**单击"引入数据"，****然后单击"分离"** 以断开与 Azure 存储区域的连接。 否則，您會在下一次嘗試附加時收到錯誤。 
    
    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連結]，以中斷與 Azure 存放區域之間的連線](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>步骤 7：创建 PST 导入映射文件

PST 文件加密并上载到 Office 365 组织的 Azure 存储位置后，下一步是创建逗号分隔值 （CSV） 文件，该文件指定将 PST 文件导入到哪些用户邮箱。 當您建立 PST 匯入工作時，您將會在下一個步驟提交 CSV 檔案。
  
1. [下载PST导入映射文件的副本。](https://go.microsoft.com/fwlink/p/?LinkId=544717) 
    
2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 您將需要為每個要匯入至使用者信箱的 PST 檔案設定一列。 請務必在對應檔案中，使用您的實際資料來取代預留位置資料。
    
    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要将数据导入到的 Office 365 服务。 要将 PST 文件导入用户邮箱，`Exchange`请使用 。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |指定在步骤 5 中上载 PST 文件的 Azure 存储位置中的文件夹位置。  <br/>  如果在步骤 5 中的`/upload-dest:`参数中的参数中未在网络 URL 中包含可选子文件夹名称，请在 CSV 文件中保留此参数为空。 如果包含子文件夹名称，请在此参数中指定它。 此参数的值区分大小写。 无论采用哪种方式，*在*`FilePath`参数的值中不要包含"引入数据"。  <br/> <br/>**重要提示：** 如果步骤 5 中的`/upload-dest:`参数中的 SAS URL 中包含可选子文件夹名称，则文件路径名称的情况必须与您使用的情况相同。 例如，如果您在步骤 5`EncryptedPSTs`中用于子文件夹名称，然后在 CSV`encryptedpsts`文件中`FilePath`的参数中使用，则 PST 文件的导入将失败。 请确保在这两种情况下使用相同的情况。           |(保留空白)  <br/> 或  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。  此参数的值区分大小写。 由于上载到 Azure 存储位置的 PST 文件已加密，`.pfile`因此扩展名将添加到 PST 文件名中。 您必须将`.pfile`扩展名添加到 CSV 文件中的 PST 文件的名称。  <br/><br/> **重要提示：** CSV 文件中的 PST 文件名大小写必须与步骤 5 中上载到 Azure 存储位置的 PST 文件相同。 例如，如果在 CSV`annb.pst.pfile`文件中`Name`的参数中使用 ，但实际 PST 文件的名称为`AnnB.pst`，则该 PST 文件的导入将失败。 确保 CSV 文件中的 PST 名称与实际 PST 文件使用相同大小写。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。   <br/> 要将 PST 文件导入非活动邮箱，必须为此参数指定邮箱 GUID。 要获取此 GUID，在 Exchange 联机中运行以下 PowerShell 命令：`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **注意：** 在某些情况下，您可能有多个具有相同电子邮件地址的邮箱，其中一个邮箱是活动邮箱，另一个邮箱处于软删除（或非活动）状态。 在这些情况下，您已指定邮箱 GUID 以唯一标识要导入 PST 文件的邮箱。 要获取活动邮箱的 GUID，运行以下 PowerShell 命令： `Get-Mailbox - <identity of active mailbox> | FL Guid`。 要获取软删除（或非活动）邮箱的 GUID，请运行此命令`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。 其中有兩個選項：  <br/> **假**将 PST 文件导入用户的主邮箱。  <br/> **真实**将 PST 文件导入用户的存档邮箱。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **注意：** 要将 PST 文件导入其主邮箱位于本地的用户的基于云的存档邮箱，只需为此参数指定**TRUE，** 并为`Mailbox`该参数指定用户本地邮箱的电子邮件地址。           | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定将 PST 文件导入到的邮箱文件夹。  <br/>  如果此参数留空，PST 将导入到**名为"导入"** 的新文件夹，该文件夹位于邮箱的根级别（与收件箱文件夹和其他默认邮箱文件夹的级别相同）。  <br/>  如果指定`/`，则 PST 文件中的项目将直接导入用户的收件箱文件夹。  <br/>  如果指定`/<foldername>`，则 PST 文件中的项目将导入名为*\<文件夹名称\>的子文件夹。* 例如，如果使用`/ImportedPst`，项目将导入**名为"导入Pst**"的子文件夹。 此子文件夹将位于用户的收件箱文件夹中。  <br/><br/> **提示：** 请考虑运行几个测试批处理来试验此参数，以便您可以确定将 PST 文件导入到的最佳文件夹位置。           |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定用于导入 ANSI 文件格式的 PST 文件的代码页的数值。 此参数用于从中文、日文和韩文 （CJK） 组织导入 PST 文件，因为这些语言通常使用双字节字符集 （DBCS） 进行字符编码。 如果此参数不用于导入使用 DBCS 用于邮箱文件夹名称的语言的 PST 文件，则文件夹名称在导入后通常会乱码。 有关要用于此参数的支持值的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/><br/> **注意：** 如前所述，这是一个可选参数，您不必将其包含在 CSV 文件中。 或者，您可以包括它，并将值留为一行或多行的空白。           |(保留空白)  <br/> 或  <br/>  `932`（这是 ANSI/OEM 日语的代码页标识符）  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。   <br/> |不適用  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>步骤 8：在 Office 365 中创建 PST 导入作业

最后一步是在 Office 365 中的导入服务中创建 PST 导入作业。 如前所述，您将提交在步骤 7 中创建的 PST 导入映射文件。 创建新作业后，导入服务将使用映射文件中的信息取消加密，并将 PST 文件（在步骤 5 中上载到 Office 365）导入指定的用户邮箱。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用 Office 365 组织中管理员帐户的凭据登录到 Office 365。
    
3. 在左侧窗格中，**单击"数据治理"，** 然后单击"**导入"。**
    
4. 在 [匯入]**** 頁面中，按一下 [移至匯入服務]****。
    
5. 在"**将数据导入 Office 365"** 页上，**单击"新建作业**![添加图标"，](media/ITPro-EAC-AddIcon.gif)**然后单击"上传电子邮件（PST 文件）"。**
    
6. 在 [透過網路上傳檔案]**** 頁面中，按一下 [上傳檔案完成]**** 和 [我可存取對應檔案]**** 核取方塊，接著按 [下一步]****。  
    
7. 為 PST 匯入工作輸入名稱，然後按一下 [下一步]****。
    
8. **单击"添加**![图标"](media/ITPro-EAC-AddIcon.gif)以选择您在步骤 7 中创建的 PST 映射文件。 
    
9. 在 CSV 檔案名稱出現於清單後，請選取該項目，然後按一下 [驗證]**** 來檢查您的 CSV 檔是否有錯誤。  
    
    > [!NOTE]
    > 如前所述，当 PST 文件加密时，`.pfile`扩展名将追加到 PST 文件名中。 您必须将`.pfile`扩展名添加到 CSV 文件中的 PST 文件的名称。 如果不这样做，CSV 文件的验证将失败。 
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。如果驗證失敗，在 [狀態]**** 欄內按一下 [無效]**** 連結。您的 PST 匯入對應檔案複本已開啟，並針對檔案中每一列有問題項目提供錯誤訊息。 
    
10. 當 PST 對應檔案驗證成功時，請檢閱條款和條件文件，然後按一下 [核取方塊]。
    
11. 按一下 [完成]**** 來提交工作。 
    
    该作业**显示在"将数据导入 Office 365"** 页上的 PST 导入作业列表中。 
    
12. 选择作业并**单击"刷新**![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中显示的状态信息。 
    
13. 在詳細資料窗格中，按一下 [檢視詳細資料]****，便可針對選取的工作取得最新的狀態。 
 
## <a name="more-information"></a>詳細資訊

- 为什么要将 PST 文件导入 Office 365？
    
  - 这是将组织的电子邮件迁移到 Office 365 的好方法。
    
  - 它可讓您透過下列方式協助解決組織的法務遵循需求︰
    
  - 啟用封存信箱以提供使用者額外的信箱儲存空間。
    
  - 保存信箱以保留內容。
    
  - 使用 Microsoft eDiscovery 工具來搜尋信箱中的內容。
    
  - 使用保留原則來控制信箱內容要保留多久。
    
  - 在 Office 365 审核日志中搜索与邮箱相关的事件。
    
  - 其有助於防止資料遺失。 导入 Office 365 邮箱的 PST 文件继承 Exchange Online 的高可用性功能，而不是将数据存储在用户的计算机上。
    
  - 資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。
    
- 下面是在步骤 2、3 和 4 中获取的密钥、D 和 URL 的示例。 此示例还包含您在 O365ImportTool.exe 工具中运行的命令的语法，用于加密 PST 文件并将其上载到 Office 365。 請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- 如前所述，Office 365 导入服务在 PST 文件导入到邮箱后打开保留保留设置（无限期）。 这意味着*RentionHoldEnabled*属性设置为 ，`True`以便不会处理分配给邮箱的保留策略。 这为邮箱所有者提供了时间，通过阻止删除或存档策略删除或存档较旧的邮件来管理新导入的邮件。 以下是管理此保留保留的一些步骤： 
    
  - 一段时间后，可以通过运行命令`Set-Mailbox -RetentionHoldEnabled $false`关闭保留保留。 有关说明，请参阅[将邮箱置于保留保留状态。](https://go.microsoft.com/fwlink/p/?LinkId=544749)
    
  - 您可以配置保留保留，以便在将来的某个日期将其关闭。 通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令执行此操作。 例如，假设今天的日期是 2016 年 6 月 1 日，并且您希望保留保留在 30 天内关闭，则运行以下`Set-Mailbox -EndDateForRetentionHold 7/1/2016`命令： 。 在这种情况下，您将将*RentionHold 启用*属性设置为`True`。 有关详细信息，请参阅[设置邮箱](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以更改分配给邮箱的保留策略的设置，以便不会立即删除导入的旧项目或移动到用户的存档邮箱。 例如，您可以延长分配给邮箱的删除或存档策略的保留期。 在这种情况下，您将在更改保留策略的设置后关闭邮箱的保留保留。 有关详细信息，请参阅为[Office 365 组织中的邮箱设置存档和删除策略。](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
