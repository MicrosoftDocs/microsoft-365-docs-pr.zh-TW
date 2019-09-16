---
title: 步驟 1：適用於使用者與群組的方案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 適用於您組織之使用者和群組的方案。
ms.openlocfilehash: 05b854c182b6f624cf143ed93920c344391ee416
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981804"
---
# <a name="step-1-plan-for-users-and-groups"></a>步驟 1：適用於使用者與群組的方案

*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您將建立身分識別基礎結構，其會結合使用者、群組和群組成員資格與正確設定中的安全性功能。這可讓您：

- 持續控制誰擁有對您環境中資源的存取權。
- 透過可強烈確保身分識別之控制項 (使用者的身分即為他們宣稱的身分) 與來自安全裝置的存取權來保護存取權。
- 使用適當的權限來在環境中佈建資源，以降低損害與資料外洩的可能性。 
- 監控您的環境，確認是否有異常使用者行為，並自動採取行動。

## <a name="plan-your-primary-identity-provider"></a>規劃您的主要身分識別提供者

若要建立您的身分識別基礎結構，您將指定主要身分識別提供者。這個服務會儲存使用者帳戶與其屬性、群組和其成員資格，並支援其進行中的管理。

當貴組織採用 Microsoft 365 企業版時，您主要的身分識別提供者是以下其中一項：

- **Active Directory 網域服務 (AD DS)**，是裝載於執行 Windows Server 的電腦上的內部網路身分識別提供者。 一般使用對象為具有現有內部部署身分識別提供者的組織。
- **Azure Active Directory (Azure AD**)，為以雲端為基礎的身份認證即服務 (IDaaS)，提供管理及保護環境的各種功能。 一般使用對象為不具現有內部部署基礎結構的組織。

如果您的組織有現有的內部部署身分識別提供者，您需要將來自 AD DS 的使用者帳戶與群組同步處理至 Azure AD，以提供更多 Microsoft 365 Enterprise 雲端服務的無縫存取。 您也可以使用 Azure AD 來建立及管理只存在於 Microsoft 雲端中的群組。

在使用者和群組都位於 Azure AD 中後，您可以：

- 為所有雲端應用程式管理 Azure AD 帳戶。 
- 使用一組相同的控制項來保護您環境中對應用程式的存取權。
- 與外部合作夥伴共同作業。
- 監控異常帳戶行為 (例如可疑登入嘗試)，並自動採取行動。

請依照下列兩個區段中的指示來規劃並實作您的使用者帳戶和群組。

## <a name="categorize-your-users"></a>分類使用者
可以使用多種方式來分類組織中的使用者。比方說，有些是員工並具有永久性狀態。有些是狀態是暫時性的廠商、承包商或合作夥伴。有些是外部使用者，他們沒有使用者帳戶，但仍必須獲予特定服務和資源的存取權，以支援互動與共同作業。例如：

- 租用戶帳戶代表您為雲端服務授權之組織內的使用者
- 企業對企業 (B2B) 帳戶代表不屬於您邀請參與共同作業之組織的使用者

請仔細審查貴組織的使用者類型。什麼是群組？比方說，您可以依高層級的功能和用途將使用者分組至您的組織。

此外，某些雲端服務可以與組織外的使用者共用，而不需使用任何使用者帳戶。您也必須識別使用者的這些群組。

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>規劃 AD DS 和 Azure AD 群組

您可以使用 Azure AD 中的群組，以實現簡化雲端環境管理的多個目的。例如，針對 Azure AD 群組，您可以：

- 使用以群組為基礎的授權，以在 Azure AD 中新增您的使用者帳戶或從 AD DS 進行同步處理後，立即將授權自動指派給將這些使用者帳戶。 
- 根據使用者帳戶屬性 (例如部門) 以動態方式將使用者帳戶新增至特定群組。  
- 為軟體即服務 (SaaS) 應用程式自動佈建使用者，並透過多重要素驗證和其他條件式存取規則來保護對這些應用程式的存取權。
- 佈建 SharePoint Online 小組網站的權限和存取層級。Azure AD 群組也可與敏感度或 Azure 資訊保護標籤一起使用來透過加密和權限保護檔案。 

## <a name="results"></a>結果

完成此步驟後的結果：

- 在 Azure AD 中的使用者帳戶清單，其與貴組織的員工和與貴組織合作的廠商、承包商及外部夥伴相對應。
- Azure AD 中一組群組和其成員反映的使用者帳戶和其他群組的邏輯集合，適用於為 Microsoft 雲端服務的安全性設定佈建進行自動授權。

做為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-user-groups)。

Azure AD 使用者和群組建立之後，您就可以開始指派授權及使用生產力工作負載，例如商務用 OneDrive 或 Exchange Online。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [保護您的特殊權限身分識別](identity-designate-protect-admin-accounts.md) |

