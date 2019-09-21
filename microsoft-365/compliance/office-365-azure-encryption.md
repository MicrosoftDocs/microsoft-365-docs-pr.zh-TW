---
title: 在 Azure 中的 office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要： 在 Azure 中的加密的說明。
ms.openlocfilehash: b8980b3979ada9ac02232065a27a7891936aa945
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077871"
---
# <a name="office-365-encryption-in-azure"></a>在 Azure 中的 office 365 加密

## <a name="introduction"></a>簡介

技術的防護措施 in Azure，例如加密的通訊和操作的程序，協助保護資料安全。 您也必須實作其他加密功能和管理自己的密碼編譯金鑰的彈性。 無論客戶組態中，Microsoft 適用於保護在 Azure 中的客戶資料的加密。 Microsoft 也可讓您控制資料範圍的進階技術來加密、 控制及管理密碼編譯金鑰，透過裝載於 Azure 中的控制項和稽核資料的存取權。 此外，Azure 儲存體提供一組完整的同時啟用 [開發人員建置安全的應用程式的安全性功能。

Azure 提供許多機制，以保護資料，從一個位置移動至另一個。 Microsoft 會使用 TLS 來保護資料，它旅行雲端服務與客戶之間的時候。 Microsoft 資料中心交涉 TLS 連線，連線到 Azure 服務的用戶端系統。 完整轉寄密碼 (PF) 會依唯一索引鍵保護客戶的用戶端系統與 Microsoft 雲端服務之間的連線。 連線也會使用 RSA 型為 2048 位元加密金鑰長度。 此組合會讓困難的某人截距及存取為傳輸中的資料。

可以使用[用戶端加密](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、 HTTPS 或 SMB 3.0，在應用程式與 Azure 之間傳輸保護資料。 您可以啟用流量加密您自己的虛擬機器 (Vm) 與您的使用者之間。 與[Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)中，您可以使用的業界標準 IPsec 通訊協定來加密您公司的 VPN 閘道與 Azure 也筆電位於您的虛擬網路的 Vm 之間的流量。

靜態資料，Azure 會提供許多加密選項，例如支援 AES 256，讓您選擇最符合您需求的資料儲存區案例的彈性。 資料可以自動加密時寫入至 Azure 儲存體使用的[儲存體服務加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)，而且作業系統和 Vm 所使用的資料磁碟可以加密使用[Azure 磁碟加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。 此外，在 Azure 儲存體中的資料物件的委派存取權授與使用[共用的存取簽章](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)。 Azure 也會提供資料的使用[Azure SQL Database 和資料倉儲的透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)的靜態加密。

如需在 Azure 中的加密的詳細資訊，請參閱[Azure 加密概觀](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)和[Azure 資料加密待用](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)。

## <a name="azure-disk-encryption"></a>Azure 磁碟加密

[Azure 磁碟加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)可讓您加密您的 Windows 和 Linux 基礎結構即服務 (IaaS) VM 磁碟。 Azure 磁碟加密運用 Windows BitLocker 功能和 Linux 作業系統和資料磁碟提供磁碟區層級加密 DM 窖功能。 它也能確保 VM 磁碟上的所有資料都在您的 Azure 儲存體中的靜態都加密。 可協助您控制、 管理及稽核使用加密金鑰和密碼的 Azure 金鑰儲藏室整合 azure 磁碟加密。

如需詳細資訊，請參閱[Azure 磁碟加密 for Windows 和 Linux IaaS Vm](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。

## <a name="azure-storage-service-encryption"></a>Azure 儲存體服務加密

使用[Azure 儲存體服務加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)，Azure 儲存體會自動加密資料之前保存它之前擷取的儲存區與解密資料。 加密、 解密和金鑰管理程序是完全不透明給使用者。 Azure 儲存體服務加密可以用於[Azure Blob 儲存體](https://azure.microsoft.com/services/storage/blobs/)和[Azure 檔案](https://azure.microsoft.com/services/storage/files/)。 您也可以使用 Microsoft 受管理加密金鑰與 Azure 儲存體服務加密，或者您可以使用您自己的加密金鑰。 （如使用自己的機碼的詳細資訊，請參閱[使用客戶的儲存體服務加密受管理的 Azure 金鑰保存庫中的機碼](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)。 如需使用 Microsoft 受管理的機碼的詳細資訊，請參閱[靜態資料的儲存體服務加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)。）此外，您可以自動使用加密。 例如，您可以透過程式設計方式啟用或停用使用的[Azure 儲存體資源提供者 REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)、[存放裝置資源提供者用戶端程式庫 for.NET](https://msdn.microsoft.com/library/azure/mt131037.aspx)、 [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)，儲存體帳戶上的儲存體服務加密或[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)中。

某些 Office 365 服務使用 Azure 來儲存資料。 例如，SharePoint Online 和商務用 OneDrive 將資料儲存在 Azure Blob 儲存和 Microsoft Teams 中的資料表、 blob 和佇列儲存其聊天服務的資料。 此外，在服務信任入口網站的合規性管理員功能會儲存客戶輸入的資料儲存在[Azure 宇宙 DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)、 平台即服務 (PaaS)，全域分散式、 多模型資料庫中的加密形式。 Azure 儲存體服務加密來加密資料儲存在 Azure Blob 儲存區和在表格中，與 Azure 磁碟加密來加密佇列，以及提供作業系統的磁碟區加密的 Windows 和 IaaS 虛擬機器磁碟和資料磁碟中的資料。 解決方案可確保虛擬機器的磁碟上的所有資料都在您的 Azure 儲存體中的靜態都加密。 [在 [Azure 宇宙 DB 靜態加密](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)是由使用數種安全性技術，包括安全金鑰的儲存系統大小、 加密的網路，以及密碼編譯 Api 實作。

## <a name="azure-key-vault"></a>Azure 金鑰保存庫

安全金鑰管理不是只核心加密最佳作法。它也是不可或缺的保護雲端中的資料。 [Azure 金鑰保存庫](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)可讓您將加密金鑰及小型的機密資料，例如使用儲存在硬體安全性模組 (Hsm) 中的機碼的密碼。 Azure 金鑰保存庫是適用於管理和控制存取雲端服務所使用的加密金鑰的 Microsoft 的建議的解決方案。 服務或 Azure Active Directory 帳戶的使用者，可指派權限來存取索引鍵。 Azure Key Vault 減輕組織的設定、 修補程式，以及維護 Hsm 和金鑰管理軟體的需求。 Azure 金鑰保存庫，Microsoft 永遠不會看到您的金鑰與應用程式不可以直接存取這些;您可以維護控制項。 您也可以匯入或 Hsm 中產生金鑰。 若要使用[攜帶您自己的金鑰](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)(BYOK) 客戶管理金鑰其 Azure 資訊保護租用戶時，可以設定有包含 Azure 資訊保護訂閱的組織） 和[記錄其用法](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。
