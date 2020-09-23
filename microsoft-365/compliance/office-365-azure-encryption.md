---
title: Azure 中的加密
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 瞭解 Azure 中可用的加密，例如 Azure 磁片加密
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a90f66ed7288d84785becbb4cd25c803ccf4fdbe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198326"
---
# <a name="encryption-in-azure"></a>Azure 中的加密

Azure 中的技術保護措施，例如加密通訊和工作處理程式，協助保護您的資料安全。 您也可以靈活地執行額外的加密功能和管理您自己的加密金鑰。 不論客戶設定為何，Microsoft 會套用加密，以保護 Azure 中的客戶資料。 Microsoft 也可讓您透過一系列的高級技術來控制 Azure 中的資料，以加密、控制和管理加密金鑰，以及控制及審核資料的存取。 此外，Azure Storage 提供一組完整的安全性功能，可搭配使用，讓開發人員建立安全的應用程式。

Azure 提供許多機制，可在資料從一個位置移動到另一個位置時加以保護。 當您的雲端服務與客戶之間的旅行時，Microsoft 會使用 TLS 來保護資料。 Microsoft 的資料中心會與連接至 Azure 服務的用戶端系統協商 TLS 連線。 完全向前保密 (PFS) 會以唯一金鑰保護客戶用戶端系統與 Microsoft 雲端服務之間的連線。 連接也會使用以 RSA 為基礎的2048位加密金鑰長度。 這種組合使得別人很難截獲和存取傳輸中的資料。

使用 [用戶端加密](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、HTTPS 或 SMB 3.0，可保護應用程式和 Azure 之間傳輸的資料。 您可以對您自己的虛擬機器 (Vm) 和您的使用者之間的流量啟用加密。 透過 [Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)，您可以使用業界標準的 IPsec 通訊協定，對您公司 VPN 閘道和 Azure 之間的流量以及位於虛擬網路上的 vm 之間的流量進行加密。

針對靜態的資料，Azure 提供許多加密選項（例如支援 AES-256），讓您可以靈活選擇最符合您需求的資料儲存案例。 資料可在使用 [Storage Service 加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)寫入 Azure 儲存區時自動加密，而 vm 所使用的作業系統和資料磁片可加密。 如需詳細資訊，請參閱 [Azure 中 Windows 虛擬機器的安全性建議](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。 此外，您可以使用 [共用存取簽名](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)授與委派 Azure 儲存區中資料物件的存取權。 Azure 也會使用 [AZURE SQL 資料庫和資料倉儲的透明資料加密，](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)提供靜態資料的加密。

如需 Azure 中加密的詳細資訊，請參閱 [azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) 和 [azure 資料加密（靜態](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)）。

## <a name="azure-disk-encryption"></a>Azure 磁片加密

Azure 磁片加密可讓您將 Windows 和 Linux 基礎結構加密為服務 (IaaS) 的 VM 磁片）。 Azure 磁片加密利用 Windows 的 BitLocker 功能和 Linux 的 DM Crypt 功能，提供作業系統和資料磁片的磁片區層級加密。 此外，它也可確保 VM 磁片上的所有資料在 Azure 儲存體中的靜止時已加密。 Azure 磁片加密與 Azure 金鑰保存庫整合，可協助您控制、管理及審核加密金鑰和機密的使用。

如需詳細資訊，請參閱 [Azure 中 Windows 虛擬機器的安全性建議](https://docs.microsoft.com/azure/virtual-machines/windows/security-recommendations)。

## <a name="azure-storage-service-encryption"></a>Azure Storage Service 加密

使用 [Azure Storage Service 加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)，azure 儲存裝置會在將資料保存至儲存區之前自動將資料加密，並在檢索之前解密資料。 加密、解密及金鑰管理程式對使用者而言完全透明。 Azure Storage Service 加密可用於 [Azure Blob 儲存區](https://azure.microsoft.com/services/storage/blobs/) 和 [Azure](https://azure.microsoft.com/services/storage/files/)檔案。 您也可以使用 Microsoft 受管理的加密金鑰搭配 Azure Storage Service 加密，也可以使用您自己的加密金鑰。  (如需使用您自己的金鑰的詳細資訊，請參閱 [使用 Azure Key Vault 中的客戶管理金鑰儲存服務加密](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)。 如需使用 Microsoft 管理金鑰的詳細資訊，請參閱存放 [區資料的 Storage Service Encryption](https://docs.microsoft.com/azure/storage/storage-service-encryption)。 ) 此外，您可以自動化加密的使用。 例如，您可以使用[Azure Storage Resource PROVIDER REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)、適用于 .Net、 [Azure POWERSHELL](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)或[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)的[儲存體資源提供者用戶端程式庫](https://msdn.microsoft.com/library/azure/mt131037.aspx)，以程式設計方式啟用或停用儲存帳戶上的 storage Service 加密。

有些 Microsoft 365 服務使用 Azure 儲存資料。 例如，在 Azure Blob 儲存中 SharePoint 線上及 OneDrive 商務存放區資料，而 Microsoft 團隊會將其 chat service 的資料儲存在資料表、blob 及佇列中。 此外，Microsoft 365 合規性中心的合規性管理員功能會將用戶端輸入的資料儲存在 [Azure COSMOS DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)中（即服務 (PaaS) 、全域分散式、多模型資料庫）。 Azure Storage Service 加密會加密儲存在 Azure Blob 儲存區和表格中的資料，而 Azure 磁片加密會加密佇列中的資料，以及 Windows 和 IaaS 虛擬機器盤，以提供作業系統和資料磁片的磁片區加密。 此解決方案可確保虛擬機器磁片上的所有資料在 Azure 儲存體中的靜止時已加密。 [Azure COSMOS DB 中的靜態加密](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) 是透過使用許多安全性技術（包括安全金鑰儲存系統、加密網路和加密 APIs）來執行。

## <a name="azure-key-vault"></a>Azure 金鑰保存庫

安全金鑰管理不只是加密最佳作法的核心;保護雲端中的資料也是必要的。 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) 可讓您加密金鑰及小型機密，例如密碼使用儲存在硬體安全模組 (hsm) 中的金鑰。 Azure Key Vault 是 Microsoft 建議的解決方案，用來管理和控制雲端服務所使用的加密金鑰的存取。 存取機碼的許可權可指派給服務或使用 Azure Active Directory 帳戶的使用者。 Azure 重要保險存儲區免除組織需要設定、修補及維護 Hsm 和金鑰管理軟體的需求。 使用 Azure 金鑰保存庫時，Microsoft 決不會看到您的金鑰和應用程式無法直接存取它們;您維護控制權。 您也可以匯入或產生 Hsm 中的金鑰。 具有包含 Azure 資訊保護之訂閱的組織可以設定其 Azure 資訊保護租使用者使用客戶管理的金鑰， [讓您自己的金鑰](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (BYOK) # A2，然後 [記錄其使用方式](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。
