---
title: 設定 Microsoft Defender 安全性中心設定
description: 使用 [設定] 頁面來設定一般設定、許可權、api 及規則。
keywords: 設定、一般設定、許可權、api、規則
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5869e8406158eb6d6b2f48b3083cb9011bb3951d
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604342"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="a536c-104">設定 Microsoft Defender 安全性中心設定</span><span class="sxs-lookup"><span data-stu-id="a536c-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a536c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a536c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a536c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a536c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a536c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a536c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a536c-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a536c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a536c-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a536c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="a536c-110">使用 [ **設定** ] 功能表，修改一般設定、高級功能、啟用預覽體驗、電子郵件通知及自訂威脅智慧功能。</span><span class="sxs-lookup"><span data-stu-id="a536c-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a536c-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="a536c-111">In this section</span></span>

<span data-ttu-id="a536c-112">主題</span><span class="sxs-lookup"><span data-stu-id="a536c-112">Topic</span></span> | <span data-ttu-id="a536c-113">描述</span><span class="sxs-lookup"><span data-stu-id="a536c-113">Description</span></span>
:---|:---
<span data-ttu-id="a536c-114">一般設定</span><span class="sxs-lookup"><span data-stu-id="a536c-114">General settings</span></span> | <span data-ttu-id="a536c-115">修改先前定義為上架過程一部分的一般設定。</span><span class="sxs-lookup"><span data-stu-id="a536c-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="a536c-116">權限</span><span class="sxs-lookup"><span data-stu-id="a536c-116">Permissions</span></span> | <span data-ttu-id="a536c-117">使用 RBAC 和裝置群組來管理入口網站存取。</span><span class="sxs-lookup"><span data-stu-id="a536c-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="a536c-118">API</span><span class="sxs-lookup"><span data-stu-id="a536c-118">APIs</span></span> | <span data-ttu-id="a536c-119">啟用 intel 和 SIEM 整合的威脅。</span><span class="sxs-lookup"><span data-stu-id="a536c-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="a536c-120">規則</span><span class="sxs-lookup"><span data-stu-id="a536c-120">Rules</span></span> | <span data-ttu-id="a536c-121">設定禁止顯示規則和自動化設定。</span><span class="sxs-lookup"><span data-stu-id="a536c-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="a536c-122">裝置管理</span><span class="sxs-lookup"><span data-stu-id="a536c-122">Device management</span></span> | <span data-ttu-id="a536c-123">板載和下架裝置。</span><span class="sxs-lookup"><span data-stu-id="a536c-123">Onboard and offboard devices.</span></span>
<span data-ttu-id="a536c-124">網路評估</span><span class="sxs-lookup"><span data-stu-id="a536c-124">Network assessments</span></span> | <span data-ttu-id="a536c-125">選擇要定期掃描的裝置，並將其新增至裝置庫存。</span><span class="sxs-lookup"><span data-stu-id="a536c-125">Choose devices to be scanned regularly and added to the device inventory.</span></span>
