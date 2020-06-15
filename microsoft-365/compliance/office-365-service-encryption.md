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
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717344"
---
# <a name="service-encryption"></a>服務加密

除了使用大量的加密、Exchange Online、商務用 Skype、SharePoint 線上和 OneDrive 商務用，也會使用服務加密來加密客戶資料。 服務加密允許兩個主要的管理選項：

## <a name="microsoft-managed-keys"></a>Microsoft managed 金鑰： 
Microsoft 管理所有的加密金鑰，包括服務加密的根機碼。 此選項目前可用於 SharePoint 線上和商務 OneDrive。 此選項目前正為 Exchange Online 進行推出。 除非您決定使用客戶金鑰進行板載，否則 Microsoft 受管理的金鑰會提供預設的服務加密。 如果您在稍後的日期決定停止使用客戶金鑰而不遵循資料清除路徑，則您的資料會以 Microsoft 受管理的金鑰保持加密。 您的資料通常會在此預設層級加密，至少一次。 

## <a name="customer-key"></a>客戶金鑰： 
您可以提供與服務加密搭配使用的根機碼，並使用 Azure Key Vault 管理這些金鑰。 Microsoft 管理所有其他機碼。 此選項叫用客戶機碼，目前可用於 Exchange Online、SharePoint 線上和商務 OneDrive。 （先前稱為 BYOK 的高級加密。 請參閱增強針對原始宣告的[Office 365 客戶的透明性和控制權](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。

服務加密可提供多項優點。 例如，客戶金鑰：

- 在增強式加密保護之上提供版權保護和管理功能。

- 包含客戶金鑰選項，可讓多租使用者服務提供每個租使用者金鑰管理的服務。

- 讓 Windows 作業系統管理員分開存取作業系統所儲存或處理的客戶資料。

- 增強 Microsoft 365 的功能，以滿足具有加密之相容性需求的客戶的需求。

使用客戶金鑰，您可以使用內部部署硬體服務模組（HSM）或 Azure Key Vault （AKV）來產生您自己的加密金鑰。 不論您產生金鑰的方式為何，您可以使用 AKV 來控制和管理 Office 365 所使用的加密金鑰。 當您的金鑰儲存在 AKV 中之後，即可將其當作用來加密您的信箱資料或檔案之其中一個 keychains 的根。

客戶金鑰的另一個好處是，您可以透過 Microsoft 處理資料的能力來控制。 如果您想要從 Office 365 中移除資料，例如，如果您想要使用 Microsoft 來終止服務，或移除儲存在雲端中的部分資料，您可以這麼做，並使用客戶金鑰做為技術控制。 這可確保任何人（包括 Microsoft）都無法存取或處理資料。 客戶金鑰補充及補充客戶密碼箱，您可以用來控制 Microsoft 人員對資料的存取。

若要瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint Online （包括小組網站）和商務 OneDrive 的 Microsoft 365 的客戶金鑰，請參閱下列文章：

- [使用客戶金鑰的服務加密](customer-key-overview.md)

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [瞭解可用性金鑰](customer-key-availability-key-understand.md)

