---
title: 列出一個補救活動的公開裝置
description: 傳回所指定修復程式工作的公開裝置資訊。
keywords: api，修正，修正 api，get，修正工作，修正公開裝置
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 92b5a93e86a20f36469d2b5cb606a8ddc2e97077
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241709"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="545b0-104">列出一個補救活動的公開裝置</span><span class="sxs-lookup"><span data-stu-id="545b0-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="545b0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="545b0-105">**Applies to:**</span></span>

- [<span data-ttu-id="545b0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="545b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="545b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="545b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="545b0-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="545b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="545b0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="545b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="545b0-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="545b0-110">API Description</span></span>

<span data-ttu-id="545b0-111">傳回所指定修復程式工作的公開裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="545b0-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="545b0-112">[深入瞭解修復活動](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="545b0-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="545b0-113">列出與修復工作相關聯的公開裝置 (id) </span><span class="sxs-lookup"><span data-stu-id="545b0-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="545b0-114">**URL:** /Api/remediationTasks/ \{ id \} /machineReferences GET:</span><span class="sxs-lookup"><span data-stu-id="545b0-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="545b0-115">權限</span><span class="sxs-lookup"><span data-stu-id="545b0-115">Permissions</span></span>

<span data-ttu-id="545b0-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="545b0-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="545b0-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="545b0-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="545b0-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="545b0-118">Permission type</span></span> | <span data-ttu-id="545b0-119">權限</span><span class="sxs-lookup"><span data-stu-id="545b0-119">Permission</span></span> | <span data-ttu-id="545b0-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="545b0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="545b0-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="545b0-121">Application</span></span> | <span data-ttu-id="545b0-122">RemediationTask Read。 All</span><span class="sxs-lookup"><span data-stu-id="545b0-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="545b0-123">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="545b0-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="545b0-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="545b0-124">Delegated (work or school account)</span></span> | <span data-ttu-id="545b0-125">RemediationTask 讀取。</span><span class="sxs-lookup"><span data-stu-id="545b0-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="545b0-126">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="545b0-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="545b0-127">屬性詳細資料</span><span class="sxs-lookup"><span data-stu-id="545b0-127">Properties details</span></span>

<span data-ttu-id="545b0-128">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="545b0-128">Property (id)</span></span> | <span data-ttu-id="545b0-129">資料類型</span><span class="sxs-lookup"><span data-stu-id="545b0-129">Data type</span></span> | <span data-ttu-id="545b0-130">描述</span><span class="sxs-lookup"><span data-stu-id="545b0-130">Description</span></span> | <span data-ttu-id="545b0-131">範例</span><span class="sxs-lookup"><span data-stu-id="545b0-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="545b0-132">id</span><span class="sxs-lookup"><span data-stu-id="545b0-132">id</span></span> | <span data-ttu-id="545b0-133">字串</span><span class="sxs-lookup"><span data-stu-id="545b0-133">String</span></span> | <span data-ttu-id="545b0-134">裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="545b0-134">Device ID</span></span> | <span data-ttu-id="545b0-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="545b0-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="545b0-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="545b0-136">computerDnsName</span></span> | <span data-ttu-id="545b0-137">字串</span><span class="sxs-lookup"><span data-stu-id="545b0-137">String</span></span> | <span data-ttu-id="545b0-138">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="545b0-138">Device name</span></span> | <span data-ttu-id="545b0-139">SRV2012R2Foo-UserNameVldNet</span><span class="sxs-lookup"><span data-stu-id="545b0-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="545b0-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="545b0-140">osPlatform</span></span> | <span data-ttu-id="545b0-141">字串</span><span class="sxs-lookup"><span data-stu-id="545b0-141">String</span></span> | <span data-ttu-id="545b0-142">裝置作業系統</span><span class="sxs-lookup"><span data-stu-id="545b0-142">Device operating system</span></span> | <span data-ttu-id="545b0-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="545b0-143">WindowsServer2012R2</span></span>
<span data-ttu-id="545b0-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="545b0-144">rbacGroupName</span></span> | <span data-ttu-id="545b0-145">字串</span><span class="sxs-lookup"><span data-stu-id="545b0-145">String</span></span> | <span data-ttu-id="545b0-146">此裝置相關聯的裝置群組名稱</span><span class="sxs-lookup"><span data-stu-id="545b0-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="545b0-147">伺服器</span><span class="sxs-lookup"><span data-stu-id="545b0-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="545b0-148">範例</span><span class="sxs-lookup"><span data-stu-id="545b0-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="545b0-149">要求範例</span><span class="sxs-lookup"><span data-stu-id="545b0-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="545b0-150">回應範例</span><span class="sxs-lookup"><span data-stu-id="545b0-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="545b0-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="545b0-151">See also</span></span>

- [<span data-ttu-id="545b0-152">修正方法和屬性</span><span class="sxs-lookup"><span data-stu-id="545b0-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="545b0-153">根據識別碼取得一個補救活動</span><span class="sxs-lookup"><span data-stu-id="545b0-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="545b0-154">列出所有補救活動</span><span class="sxs-lookup"><span data-stu-id="545b0-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="545b0-155">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="545b0-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="545b0-156">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="545b0-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
