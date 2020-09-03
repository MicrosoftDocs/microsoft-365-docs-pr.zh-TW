---
title: Azure Active Directory 中的 Microsoft 365 隔離與存取控制
ms.author: robmazz
author: robmazz
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
description: 在本文中，您將瞭解隔離和存取控制如何在 Azure Active Directory 中讓多個承租人相互隔離的資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332409"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="92282-103">Azure Active Directory 中的 Microsoft 365 隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="92282-103">Microsoft 365 Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="92282-104">Azure Active Directory (Azure AD) 設計為透過邏輯資料隔離以高安全性的方式主控多個承租人。</span><span class="sxs-lookup"><span data-stu-id="92282-104">Azure Active Directory (Azure AD) was designed to host multiple tenants in a highly secure way through logical data isolation.</span></span> <span data-ttu-id="92282-105">存取 Azure AD 的方式是透過授權層來封閉。</span><span class="sxs-lookup"><span data-stu-id="92282-105">Access to Azure AD is gated by an authorization layer.</span></span> <span data-ttu-id="92282-106">Azure AD 隔離以租使用者容器為安全性界限的客戶，以保護客戶的內容，使其內容無法透過共同承租人進行存取或破壞。</span><span class="sxs-lookup"><span data-stu-id="92282-106">Azure AD isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants.</span></span> <span data-ttu-id="92282-107">Azure AD 的授權層會執行三項檢查：</span><span class="sxs-lookup"><span data-stu-id="92282-107">Three checks are performed by Azure AD's authorization layer:</span></span>

- <span data-ttu-id="92282-108">是否啟用主體以存取 Azure AD 租使用者？</span><span class="sxs-lookup"><span data-stu-id="92282-108">Is the principal enabled for access to Azure AD tenant?</span></span>
- <span data-ttu-id="92282-109">是否已啟用主體來存取此承租人中的資料？</span><span class="sxs-lookup"><span data-stu-id="92282-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="92282-110">此租使用者中的主體角色是否獲得要求的資料存取類型？</span><span class="sxs-lookup"><span data-stu-id="92282-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="92282-111">沒有任何應用程式、使用者、伺服器或服務可以存取未適當驗證與 token 或憑證的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="92282-111">No application, user, server, or service can access Azure AD without the proper authentication and token or certificate.</span></span> <span data-ttu-id="92282-112">若未附帶適當的認證，便會拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="92282-112">Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="92282-113">實際上，Azure AD 會將每個租使用者放在其本身受保護的容器中，並在容器內和容器內，以完全擁有和管理的原則和許可權為主機。</span><span class="sxs-lookup"><span data-stu-id="92282-113">Effectively, Azure AD hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure 容器](../media/office-365-isolation-azure-container.png)

<span data-ttu-id="92282-115">租使用者容器的概念在所有層級的目錄服務中，從入口網站一直到持續儲存的方式，都很深層 ingrained。</span><span class="sxs-lookup"><span data-stu-id="92282-115">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage.</span></span> <span data-ttu-id="92282-116">即使多個 Azure AD 租使用者中繼資料儲存在同一個實體磁片上，除了目錄服務所定義的容器以外，其他容器之間並沒有任何關係，也是由租使用者管理員所決定。</span><span class="sxs-lookup"><span data-stu-id="92282-116">Even when multiple Azure AD tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator.</span></span> <span data-ttu-id="92282-117">任何要求的應用程式或服務，都不能直接連線至 Azure AD 儲存體，您必須先進行授權層級的連接。</span><span class="sxs-lookup"><span data-stu-id="92282-117">There can be no direct connections to Azure AD storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="92282-118">在下列範例中，Contoso 和 Fabrikam 都有個別、專用的容器，即使這些容器共用某些相同的基礎結構（例如伺服器和儲存區），它們仍然彼此分開且彼此隔離，並依授權和存取控制層來封閉。</span><span class="sxs-lookup"><span data-stu-id="92282-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 專用容器](../media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="92282-120">此外，Azure AD 內沒有任何可執行檔應用程式元件，一個承租人不可能強制破壞其他租使用者的完整性、存取另一個租使用者的加密金鑰，或從伺服器讀取原始資料。</span><span class="sxs-lookup"><span data-stu-id="92282-120">In addition, there are no application components that can execute from within Azure AD, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="92282-121">根據預設，Azure AD 不允許其他承租人中的身分識別所發出的所有作業。</span><span class="sxs-lookup"><span data-stu-id="92282-121">By default, Azure AD disallows all operations issued by identities in other tenants.</span></span> <span data-ttu-id="92282-122">每個租使用者會透過宣告式的存取控制，在 Azure AD 中以邏輯方式隔離。</span><span class="sxs-lookup"><span data-stu-id="92282-122">Each tenant is logically isolated within Azure AD through claims-based access controls.</span></span> <span data-ttu-id="92282-123">目錄資料的讀取和寫入會限定在租使用者容器中，並以內部抽象層來封閉，並以角色為基礎的存取控制 (RBAC) 層，其共同執行租使用者作為安全性界限。</span><span class="sxs-lookup"><span data-stu-id="92282-123">Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary.</span></span> <span data-ttu-id="92282-124">所有的目錄資料存取要求都是由這些層處理，而 Microsoft 365 中的每個存取要求都是透過以上邏輯 policed。</span><span class="sxs-lookup"><span data-stu-id="92282-124">Every directory data access request is processed by these layers and every access request in Microsoft 365 is policed by the logic above.</span></span>

<span data-ttu-id="92282-125">Azure AD 具有北美、美國政府、歐盟、德國及全球通用磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="92282-125">Azure AD has North America, U.S. Government, European Union, Germany, and World Wide partitions.</span></span> <span data-ttu-id="92282-126">租使用者存在於單一分割區中，而分割區可包含多個承租人。</span><span class="sxs-lookup"><span data-stu-id="92282-126">A tenant exists in a single partition, and partitions can contain multiple tenants.</span></span> <span data-ttu-id="92282-127">磁碟分割資訊會從使用者中抽象出來。</span><span class="sxs-lookup"><span data-stu-id="92282-127">Partition information is abstracted away from users.</span></span> <span data-ttu-id="92282-128">指定的分割區 (包括其內的所有承租人) 會複寫至多個資料中心。</span><span class="sxs-lookup"><span data-stu-id="92282-128">A given partition (including all the tenants within it) is replicated to multiple datacenters.</span></span> <span data-ttu-id="92282-129">租使用者的分割區時，會根據租使用者的屬性來選擇 (例如，國家/地區代碼) 。</span><span class="sxs-lookup"><span data-stu-id="92282-129">The partition for a tenant is chosen based on properties of the tenant (e.g., the country code).</span></span> <span data-ttu-id="92282-130">每個分割區中的機密和其他敏感資訊都會以專用金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="92282-130">Secrets and other sensitive information in each partition is encrypted with a dedicated key.</span></span> <span data-ttu-id="92282-131">建立新的分割區時，會自動產生機碼。</span><span class="sxs-lookup"><span data-stu-id="92282-131">The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="92282-132">Azure AD 系統功能是每個使用者會話的唯一實例。</span><span class="sxs-lookup"><span data-stu-id="92282-132">Azure AD system functionalities are a unique instance to each user session.</span></span> <span data-ttu-id="92282-133">此外，Azure AD 使用加密技術，在網路層級提供共用系統資源的隔離，以防止未經授權和非預期的資訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="92282-133">In addition, Azure AD uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
