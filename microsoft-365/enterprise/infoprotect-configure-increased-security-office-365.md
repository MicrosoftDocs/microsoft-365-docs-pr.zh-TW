---
title: 步驟 3：設定增強的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定增強的 Office 365 安全性，包括 Office 365 ATP。
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866645"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>步驟 3：設定增強的 Office 365 安全性

*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

若要確保 Office 365 訂用帳戶及其資料開始使用並保持安全抵禦惡意威脅，請參閱[設定 Office 365 租用戶的增強安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)，並設定下列的額外安全性：

- Office 365 安全與規範中心中的威脅管理原則
- Exchange Online 的其他全租用戶設定
- SharePoint 系統管理中心中的全租用戶共用原則
- Azure Active Directory 中的設定

設定之後，您可以從以下位置取得安全性狀態的資訊：

- 安全與規範中心中的儀表板和報告
- [Office 365 安全分數](https://securescore.office.com/)
 
  若要存取此頁面，您必須以 Office 365 租用戶系統管理員的身分登入。

您也可以使用 Cloud App Security 或 Office 365 雲端 App 安全性來監視安全性事件並採取行動。如需詳細資訊，請參閱 [Office 365 Cloud App Security 概觀](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)。

另一個安全性功能是 Office 365 進階威脅防護 (ATP)，可透過以下方式協助組織更安全地進行共用作業：

- 電子郵件中的保護連結和附件。 
- 為 Exchange Online 中的電子郵件以及 SharePoint Online、商務用 OneDrive、Microsoft Teams 中的檔案，提供詐騙情報和防網路釣魚的功能。 

>[!Note]
>Microsoft 365 企業版 E5 內含 Office 365 ATP。如果您有 Microsoft 365 企業版 E3，可以單獨購買 ATP 授權。
>

若要啟用 Office 365 ATP，請參閱[開啟](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。

如需詳細資訊，請參閱 [Office 365 ATP SharePoint、OneDrive 及 Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)。


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：設定增強的 Office 365 安全性](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step4)。

## <a name="next-step"></a>下一步


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[設定特殊權限存取管理](infoprotect-configure-privileged-access-management.md)|


