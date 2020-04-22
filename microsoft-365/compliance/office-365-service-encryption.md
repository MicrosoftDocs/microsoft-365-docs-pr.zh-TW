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
description: 摘要：瞭解 Microsoft Office 365 中的資料恢復能力。
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632238"
---
# <a name="service-encryption"></a>服務加密

除了使用大量的加密、Exchange Online、商務用 Skype、SharePoint 線上和 OneDrive 商務用，也會使用服務加密來加密客戶資料。 服務加密允許兩個主要的管理選項：

- Microsoft 管理所有的加密金鑰。 （目前 SharePoint 線上 OneDrive、商務用 Skype 和商務用 Skype 等此選項。）

- 您的組織提供根機碼。 您可以使用 Azure Key Vault 管理這些金鑰。 此選項稱為「客戶金鑰」。 客戶金鑰目前適用于 Exchange Online、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype 及小組檔案。 如果您使用客戶金鑰，這些金鑰會取代 Microsoft 受管理的金鑰來加密您的資料。

服務加密可提供多項優點。 例如，客戶金鑰：

- 在增強式加密保護之上提供版權保護和管理功能。

- 包含客戶金鑰選項，可讓多租使用者服務提供每個租使用者金鑰管理的服務。

- 讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。

- 增強 Microsoft 365 的功能，以滿足具有加密之相容性需求的客戶的需求。

## <a name="customer-key"></a>客戶金鑰

使用客戶金鑰，您可以使用內部部署硬體服務模組（HSM）或 Azure Key Vault （AKV）來產生您自己的加密金鑰。 不論您產生金鑰的方式為何，您可以使用 AKV 來控制和管理 Office 365 所使用的加密金鑰。 當您的金鑰儲存在 AKV 中之後，即可將其當作用來加密您的信箱資料或檔案之其中一個 keychains 的根。

客戶金鑰的另一個好處是，您可以透過 Microsoft 處理資料的能力來控制。 如果您想要從 Office 365 中移除資料，例如，如果您想要使用 Microsoft 來終止服務，或移除儲存在雲端中的部分資料，您可以這麼做，並使用客戶金鑰做為技術控制。 這可確保任何人（包括 Microsoft）都無法存取或處理資料。 客戶金鑰補充及補充客戶密碼箱，您可以用來控制 Microsoft 人員對資料的存取。

若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint Online （包括小組網站）和商務 OneDrive 的 Microsoft 365 的客戶金鑰，請參閱下列文章：

- [使用客戶金鑰的服務加密](customer-key-overview.md)

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [瞭解可用性金鑰](customer-key-availability-key-understand.md)
 
