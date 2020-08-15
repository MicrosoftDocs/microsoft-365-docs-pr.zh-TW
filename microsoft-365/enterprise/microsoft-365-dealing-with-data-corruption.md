---
title: Microsoft 365 處理資料損毀
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 本文說明 Microsoft 365 中的資料損毀，以及 Microsoft 採取的工作，以防止及復原資料。
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688443"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="829f0-103">處理 Microsoft 365 中的資料損毀</span><span class="sxs-lookup"><span data-stu-id="829f0-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="829f0-104">執行大規模雲端服務的一個富有挑戰性的層面是如何處理資料損毀，並提供大量的資料和獨立的系統。</span><span class="sxs-lookup"><span data-stu-id="829f0-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="829f0-105">資料損毀可能是由下列原因所造成：</span><span class="sxs-lookup"><span data-stu-id="829f0-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="829f0-106">應用程式或基礎結構錯誤，破壞部分或所有應用程式狀態</span><span class="sxs-lookup"><span data-stu-id="829f0-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="829f0-107">導致資料遺失或無法讀取資料的硬體問題</span><span class="sxs-lookup"><span data-stu-id="829f0-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="829f0-108">人力運作錯誤</span><span class="sxs-lookup"><span data-stu-id="829f0-108">Human operational errors</span></span>
- <span data-ttu-id="829f0-109">惡意駭客和不滿的員工</span><span class="sxs-lookup"><span data-stu-id="829f0-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="829f0-110">外部服務中導致資料遺失的事件</span><span class="sxs-lookup"><span data-stu-id="829f0-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="829f0-111">因為資料完整性的彈性程度較高，所以 Microsoft 已內置 Microsoft 365 保護機制，以避免發生損毀，以及可讓我們恢復資料的系統和流程。</span><span class="sxs-lookup"><span data-stu-id="829f0-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="829f0-112">在工程發佈過程的各個階段內，都存在檢查和處理常式，以提升資料損毀的復原能力，包括：</span><span class="sxs-lookup"><span data-stu-id="829f0-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="829f0-113">系統設計</span><span class="sxs-lookup"><span data-stu-id="829f0-113">System Design</span></span>
- <span data-ttu-id="829f0-114">程式碼組織和結構</span><span class="sxs-lookup"><span data-stu-id="829f0-114">Code organization and structure</span></span>
- <span data-ttu-id="829f0-115">程式碼檢查</span><span class="sxs-lookup"><span data-stu-id="829f0-115">Code review</span></span>
- <span data-ttu-id="829f0-116">單元測試、整合測試及系統測試</span><span class="sxs-lookup"><span data-stu-id="829f0-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="829f0-117">行程電線測試/關口</span><span class="sxs-lookup"><span data-stu-id="829f0-117">Trip wires tests/gates</span></span>

<span data-ttu-id="829f0-118">在 Microsoft 365 的實際執行環境中，資料中心之間的對等複寫可確保任何資料都有多個即時複本。</span><span class="sxs-lookup"><span data-stu-id="829f0-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="829f0-119">標準映射和腳本用於復原遺失的伺服器，而複寫的資料則用於還原客戶資料。</span><span class="sxs-lookup"><span data-stu-id="829f0-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="829f0-120">由於內建的資料恢復檢查和程式，Microsoft 只會維護 Microsoft 365 資訊系統檔 (的備份，包括安全性相關檔) ，使用內建複寫 SharePoint 線上和內部程式碼存放庫工具，來源集。</span><span class="sxs-lookup"><span data-stu-id="829f0-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="829f0-121">系統檔儲存在 SharePoint 線上，來源返廠包含系統和應用程式影像。</span><span class="sxs-lookup"><span data-stu-id="829f0-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="829f0-122">線上和來源返廠 SharePoint 都使用版本設定，而且會以接近即時的時間進行複製。</span><span class="sxs-lookup"><span data-stu-id="829f0-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
