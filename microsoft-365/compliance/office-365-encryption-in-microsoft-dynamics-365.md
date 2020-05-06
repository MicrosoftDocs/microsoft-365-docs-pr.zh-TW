---
title: Microsoft Dynamics 365 中的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 瞭解 Microsoft 如何使用加密技術來保護 Microsoft Dynamics 365 中的客戶資料，同時還可以在 Microsoft 資料庫和傳輸期間進行。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd349890fc7fc1ae7f1f7eaf07f90c22423637cf
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031409"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的加密

Microsoft 使用加密技術來保護 Dynamics 365 中的客戶資料，同時也是在 Microsoft 資料庫中，而且在使用者裝置與我們的資料中心之間的傳輸。 會加密客戶與 Microsoft 資料中心之間建立的連線，並使用業界標準 TLS 來保護所有公用端點。 TLS 可有效地建立安全性增強的瀏覽器對伺服器連線，以協助確保桌面和資料中心之間的資料機密性及完整性。 啟用資料加密後，就無法將其關閉。 如需詳細資訊，請參閱[欄位層級資料加密](https://msdn.microsoft.com/library/dn481562.aspx)。

Dynamics 365 針對包含機密資訊的預設實體屬性集（如使用者名稱和電子郵件密碼），使用標準 Microsoft SQL Server 儲存格層級加密。 這項功能可協助組織滿足與 FIPS 140-2 相關的相容性需求。 在利用[Microsoft DYNAMICS CRM 電子郵件路由器](https://technet.microsoft.com/library/hh699800.aspx)的情況下，欄位層級的資料加密特別重要，它必須儲存使用者名稱和密碼，以啟用 Dynamics 365 實例和電子郵件服務之間的整合。 

所有 Dynamics 365 實例都使用[MICROSOFT SQL Server 透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)（TDE），在寫入磁片（靜態）時執行資料的即時加密。 TDE 會加密 SQL Server、Azure SQL Database 和 Azure SQL 資料倉儲資料檔案。 根據預設，Microsoft 會儲存和管理 Dynamics 365 實例的資料庫加密金鑰。 （Dynamics 365 用於財務的按鍵是由 .NET Framework Data Protection API 產生。） 

Dynamics 365 Administration Center 中的管理機碼功能可讓系統管理員自行管理與 Dynamics 365 實例相關聯的資料庫加密金鑰。 （自我管理的資料庫加密金鑰只適用于 Microsoft Dynamics 365 的2017年1月更新，而且可能無法供後續版本使用。 如需詳細資訊，請參閱[管理 Dynamics 365 （online）實例的加密金鑰](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)。金鑰管理功能支援 PFX 和 BYOK 加密金鑰檔案，例如儲存在 HSM 中的金鑰。 （如需在網際網路上產生及轉移受 HSM 保護的金鑰的詳細資訊，請參閱 how [to 針對 Azure Key Vault 產生及傳送受保護性保護的](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)金鑰。） 

若要使用 [上傳加密金鑰] 選項，您需要使用 public 和私用加密金鑰。

使用 Azure 金鑰保存庫安全地儲存加密金鑰時，金鑰管理功能會使加密金鑰管理的複雜性變得很複雜。 Azure 金鑰 Vault 可協助保護 cloud 應用程式和服務所使用的加密金鑰和機密。 「金鑰管理」功能不需要您有 Azure 金鑰 Vault 訂閱，但在大多數情況下，您不需要存取用於 Vault 中 Dynamics 365 的加密金鑰。
