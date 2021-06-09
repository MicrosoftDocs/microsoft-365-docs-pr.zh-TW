---
title: 服務加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：瞭解 Microsoft Office 365 中的資料恢復功能。
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058546"
---
# <a name="service-encryption"></a>服務加密

除了使用磁片區層級加密之外，Exchange Online、Microsoft Teams、SharePoint 線上及商務用 OneDrive 也會使用服務加密來加密客戶資料。 服務加密允許兩個主要的管理選項：

## <a name="microsoft-managed-keys"></a>Microsoft 管理的金鑰
Microsoft 管理所有的加密金鑰，包括服務加密的根機碼。 預設會為 Exchange Online、SharePoint 線上商務用 OneDrive] 啟用此選項。 除非您決定使用客戶金鑰進行板載，否則 Microsoft 受管理的金鑰會提供預設的服務加密。 如果日後，您決定停止使用客戶金鑰而不遵循資料清除路徑，則您的資料會以 Microsoft 管理的金鑰加密。 您的資料通常會在此預設層級加密，至少一次。 

## <a name="customer-key"></a>客戶金鑰
您可以提供與服務加密搭配使用的根機碼，並使用 Azure Key Vault 管理這些金鑰。 Microsoft 管理所有其他機碼。 此選項叫用客戶機碼，目前可供 Exchange Online、SharePoint 線上及商務用 OneDrive 使用。  (先前稱為 BYOK 的高級加密。 請參閱增強 Office 365 原始宣告之[客戶的透明性和控制權](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。 ) 

服務加密可提供多項優點：

- 在 BitLocker 上提供新增的保護層。

- 讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的應用程式資料。

- 包含客戶金鑰選項，可讓多租使用者服務提供每個租使用者金鑰管理的服務。

- 增強 Microsoft 365 以滿足客戶對加密的特定合規性需求的需求的能力。

使用客戶金鑰，您可以使用內部部署硬體服務模組 (HSM) 或 Azure Key Vault (AKV) 來產生您自己的加密金鑰。 不論您產生金鑰的方式為何，您可以使用 AKV 來控制及管理 Office 365 所使用的加密金鑰。 當您的金鑰儲存在 AKV 中之後，即可將其當作用來加密您的信箱資料或檔案之其中一個 keychains 的根。

客戶金鑰的另一個好處是，您可以透過 Microsoft 處理資料的能力來控制。 如果您想要從 Office 365 中移除資料，例如，如果您想要使用 Microsoft 來終止服務，或移除儲存在雲端中的部分資料，您可以這樣做，並使用客戶金鑰做為技術控制。 移除資料可確保任何人（包括 Microsoft）都無法存取或處理資料。 客戶金鑰補充及補充客戶密碼箱，您可以用來控制 Microsoft 人員對資料的存取。

若要瞭解如何設定 Microsoft 365 用於 Exchange Online、Microsoft Teams、SharePoint 線上（包括小組網站）和商務用 OneDrive 的客戶金鑰，請參閱下列文章：

- [客戶金鑰服務加密](customer-key-overview.md)

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [瞭解可用性金鑰](customer-key-availability-key-understand.md)
