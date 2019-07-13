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
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="9333c-104">Azure Active Directory 租用戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="9333c-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="9333c-105">{健身詳細帳戶、 API 呼叫、 所等等，等等。}</span><span class="sxs-lookup"><span data-stu-id="9333c-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="9333c-106">傳送到及傳送自 AAD 帳戶資料</span><span class="sxs-lookup"><span data-stu-id="9333c-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="9333c-107">傳送給您的帳戶從 Microsoft 的資料：</span><span class="sxs-lookup"><span data-stu-id="9333c-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="9333c-108">群組名稱</span><span class="sxs-lookup"><span data-stu-id="9333c-108">Group names</span></span>
- <span data-ttu-id="9333c-109">安全性原則設定</span><span class="sxs-lookup"><span data-stu-id="9333c-109">Security policy configuration</span></span>
- <span data-ttu-id="9333c-110">裝置訂單</span><span class="sxs-lookup"><span data-stu-id="9333c-110">Device orders</span></span>
- <span data-ttu-id="9333c-111">使用者帳戶 （msadmin、 mstest、 mwaas_soc_ro、 mwaas_wdgsoc）</span><span class="sxs-lookup"><span data-stu-id="9333c-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="9333c-112">E5 授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="9333c-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="9333c-113">Windows 更新的更新通道的原則</span><span class="sxs-lookup"><span data-stu-id="9333c-113">Windows update policies for update rings</span></span>

<span data-ttu-id="9333c-114">從您的帳戶傳送給 Microsoft 的資料：</span><span class="sxs-lookup"><span data-stu-id="9333c-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="9333c-115">裝置更新、 使用狀況和可靠性資料</span><span class="sxs-lookup"><span data-stu-id="9333c-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="9333c-116">應用程式部署及可靠性資料</span><span class="sxs-lookup"><span data-stu-id="9333c-116">App deployment and reliability data</span></span>
- <span data-ttu-id="9333c-117">[更新與安全性原則部署資料</span><span class="sxs-lookup"><span data-stu-id="9333c-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="9333c-118">使用者指派到裝置</span><span class="sxs-lookup"><span data-stu-id="9333c-118">Users assigned to devices</span></span>  

<span data-ttu-id="9333c-119">從您的帳戶傳輸的資料會儲存在 Azure SQL 資料庫裝載在美國 Microsoft 租用戶中。</span><span class="sxs-lookup"><span data-stu-id="9333c-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="9333c-120">資料儲存和處理根據 {Microsoft Azure 安全性} 所述的原則。</span><span class="sxs-lookup"><span data-stu-id="9333c-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="9333c-121">API 權限及通話</span><span class="sxs-lookup"><span data-stu-id="9333c-121">API permissions and calls</span></span>

<span data-ttu-id="9333c-122">**在註冊： 期間**</span><span class="sxs-lookup"><span data-stu-id="9333c-122">**During enrollment:**</span></span>

<span data-ttu-id="9333c-123">API 權限：</span><span class="sxs-lookup"><span data-stu-id="9333c-123">API permissions:</span></span>
- <span data-ttu-id="9333c-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="9333c-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="9333c-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="9333c-130">API 呼叫：</span><span class="sxs-lookup"><span data-stu-id="9333c-130">API calls:</span></span>
- <span data-ttu-id="9333c-131">POST /organization/ {organizationId} / setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="9333c-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="9333c-132">GET/POST /directoryRoles/ {id} / 成員</span><span class="sxs-lookup"><span data-stu-id="9333c-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="9333c-133">GET/POST /users</span><span class="sxs-lookup"><span data-stu-id="9333c-133">GET/POST /users</span></span>
- <span data-ttu-id="9333c-134">GET/POST /groups</span><span class="sxs-lookup"><span data-stu-id="9333c-134">GET/POST /groups</span></span>
- <span data-ttu-id="9333c-135">修補程式 /groups/ {id}</span><span class="sxs-lookup"><span data-stu-id="9333c-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="9333c-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="9333c-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="9333c-137">取得 /deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="9333c-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="9333c-138">**之後註冊，請在正常的管理期間所示：**</span><span class="sxs-lookup"><span data-stu-id="9333c-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="9333c-139">API 權限：</span><span class="sxs-lookup"><span data-stu-id="9333c-139">API permissions:</span></span>
- <span data-ttu-id="9333c-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="9333c-143">Reports.Read.All</span></span>
- <span data-ttu-id="9333c-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9333c-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="9333c-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="9333c-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="9333c-147">API 呼叫：</span><span class="sxs-lookup"><span data-stu-id="9333c-147">API calls:</span></span>
- <span data-ttu-id="9333c-148">GET/POST /directoryRoles/ {id} / 成員</span><span class="sxs-lookup"><span data-stu-id="9333c-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="9333c-149">GET/修補程式/POST /users</span><span class="sxs-lookup"><span data-stu-id="9333c-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="9333c-150">GET/POST /groups</span><span class="sxs-lookup"><span data-stu-id="9333c-150">GET/POST /groups</span></span>
- <span data-ttu-id="9333c-151">修補程式 /groups/ {id}</span><span class="sxs-lookup"><span data-stu-id="9333c-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="9333c-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="9333c-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="9333c-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="9333c-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="9333c-154">取得 /deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="9333c-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="9333c-155">取得 /devices</span><span class="sxs-lookup"><span data-stu-id="9333c-155">GET /devices</span></span>
- <span data-ttu-id="9333c-156">POST /users/ {識別碼 | userPrincipalName} / assignLicense</span><span class="sxs-lookup"><span data-stu-id="9333c-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="9333c-157">取得 /subscribedSkus</span><span class="sxs-lookup"><span data-stu-id="9333c-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="9333c-158">Microsoft 受管理的電腦所使用的帳戶</span><span class="sxs-lookup"><span data-stu-id="9333c-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="9333c-159">帳戶</span><span class="sxs-lookup"><span data-stu-id="9333c-159">Account</span></span> | <span data-ttu-id="9333c-160">描述</span><span class="sxs-lookup"><span data-stu-id="9333c-160">Description</span></span>  | <span data-ttu-id="9333c-161">條件式存取</span><span class="sxs-lookup"><span data-stu-id="9333c-161">Conditional access</span></span>  | <span data-ttu-id="9333c-162">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="9333c-162">Multi-factor authentication</span></span>  | <span data-ttu-id="9333c-163">為什麼這是 [確定]</span><span class="sxs-lookup"><span data-stu-id="9333c-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="9333c-164">msadmin@\*onmmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9333c-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="9333c-165">以系統管理員權限，做為 Microsoft Intune 和使用者的系統管理員，{這是什麼？} 有限的服務帳戶</span><span class="sxs-lookup"><span data-stu-id="9333c-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="9333c-166">若要定義和設定 Microsoft 現代化電腦裝置租用戶。</span><span class="sxs-lookup"><span data-stu-id="9333c-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="9333c-167">沒有互動式登入權限;執行作業只能透過該服務。</span><span class="sxs-lookup"><span data-stu-id="9333c-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="9333c-168">排除，因為它不會來自您網路中</span><span class="sxs-lookup"><span data-stu-id="9333c-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="9333c-169">排除，因為沒有任何互動的登入</span><span class="sxs-lookup"><span data-stu-id="9333c-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="9333c-170">密碼儲存在 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9333c-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="9333c-171">mstest@\*onmmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9333c-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="9333c-172">mssupport@\*onmmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9333c-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="9333c-173">msadminint@\*onmmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9333c-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
