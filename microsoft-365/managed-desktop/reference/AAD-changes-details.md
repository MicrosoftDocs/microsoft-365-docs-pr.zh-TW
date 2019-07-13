---
title: Azure Active Directory 租用戶詳細資料
description: 本主題說明當您在 Microsoft 受管理電腦中註冊您的 AAD 帳戶所做的變更
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643944"
---
# <a name="azure-active-directory-tenant-details"></a>Azure Active Directory 租用戶詳細資料
{健身詳細帳戶、 API 呼叫、 所等等，等等。}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>傳送到及傳送自 AAD 帳戶資料


傳送給您的帳戶從 Microsoft 的資料：

- 群組名稱
- 安全性原則設定
- 裝置訂單
- 使用者帳戶 （msadmin、 mstest、 mwaas_soc_ro、 mwaas_wdgsoc）
- E5 授權指派給使用者帳戶
- Windows 更新的更新通道的原則

從您的帳戶傳送給 Microsoft 的資料：

- 裝置更新、 使用狀況和可靠性資料
- 應用程式部署及可靠性資料
- [更新與安全性原則部署資料
- 使用者指派到裝置  

從您的帳戶傳輸的資料會儲存在 Azure SQL 資料庫裝載在美國 Microsoft 租用戶中。 資料儲存和處理根據 {Microsoft Azure 安全性} 所述的原則。 

## <a name="api-permissions-and-calls"></a>API 權限及通話

**在註冊： 期間**

API 權限：
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

API 呼叫：
- POST /organization/ {organizationId} / setMobileDeviceManagementAuthority
- GET/POST /directoryRoles/ {id} / 成員
- GET/POST /users
- GET/POST /groups
- 修補程式 /groups/ {id}
- GET/POST/deviceManagement/deviceConfigurations
- 取得 /deviceManagement/detectedApps

**之後註冊，請在正常的管理期間所示：**

API 權限：
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

API 呼叫：
- GET/POST /directoryRoles/ {id} / 成員
- GET/修補程式/POST /users
- GET/POST /groups
- 修補程式 /groups/ {id}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- 取得 /deviceManagement/detectedApps
- 取得 /devices
- POST /users/ {識別碼 | userPrincipalName} / assignLicense
- 取得 /subscribedSkus

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Microsoft 受管理的電腦所使用的帳戶





| 帳戶 | 描述  | 條件式存取  | 多重要素驗證  | 為什麼這是 [確定] |
|---------|---------|---------|---------|--------------|
| msadmin@*onmmicrosoft.com | 以系統管理員權限，做為 Microsoft Intune 和使用者的系統管理員，{這是什麼？} 有限的服務帳戶 若要定義和設定 Microsoft 現代化電腦裝置租用戶。沒有互動式登入權限;執行作業只能透過該服務。  | 排除，因為它不會來自您網路中        | 排除，因為沒有任何互動的登入        | 密碼儲存在 Azure Key Vault |
| mstest@*onmmicrosoft.com     |         |         |         |
| mssupport@*onmmicrosoft.com     |         |         |         |
| msadminint@*onmmicrosoft.com     |         |         |         |
