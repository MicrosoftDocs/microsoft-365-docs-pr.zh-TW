---
title: Microsoft Defender for Endpoint 中連線的應用程式
ms.reviewer: ''
description: View 使用 standard OAuth 2.0 通訊協定的已連接夥伴應用程式，以進行驗證，並提供標記以搭配 Microsoft Defender for Endpoint APIs 使用。
keywords: 合作夥伴、應用程式、協力廠商、連接、sentinelone、注意、bitdefender、corrata、morphisec、paloalto、ziften、更佳行動裝置
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4b212acdf4bdf8fa53ef00763463190e204fc1ed
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339163"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b744d-104">Microsoft Defender for Endpoint 中連線的應用程式</span><span class="sxs-lookup"><span data-stu-id="b744d-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b744d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b744d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b744d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b744d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b744d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b744d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="b744d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b744d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b744d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b744d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b744d-110">連接的應用程式會使用 APIs 與使用 Defender 的端點平臺整合。</span><span class="sxs-lookup"><span data-stu-id="b744d-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="b744d-111">應用程式使用 standard OAuth 2.0 通訊協定來驗證及提供與 Microsoft Defender for Endpoint APIs 搭配使用的權杖。</span><span class="sxs-lookup"><span data-stu-id="b744d-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="b744d-112">此外，Azure Active Directory (Azure AD) 應用程式允許租使用者管理員設定可使用對應的應用程式存取 APIs 的明確控制。</span><span class="sxs-lookup"><span data-stu-id="b744d-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="b744d-113">您必須遵循 [下列步驟](/microsoft-365/security/defender-endpoint/apis-intro) ，才能將 APIs 與連接的應用程式搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b744d-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="b744d-114">存取連線的應用程式頁面</span><span class="sxs-lookup"><span data-stu-id="b744d-114">Access the connected application page</span></span>
<span data-ttu-id="b744d-115">從左導覽功能表中，選取 [**端點**  >  **夥伴及 APIs**  >  **連線的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b744d-115">From the left navigation menu, select **Endpoints** > **Partners and APIs** > **Connected applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="b744d-116">查看連接的應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="b744d-116">View connected application details</span></span>
<span data-ttu-id="b744d-117">[連線的應用程式] 頁面會提供連線至您組織中之端點之 Azure AD 應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b744d-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="b744d-118">您可以查看已連接之應用程式的使用狀況：上次查看時間、過去24小時內的要求數量，以及過去30天的要求趨勢。</span><span class="sxs-lookup"><span data-stu-id="b744d-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![連接應用程式的影像](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="b744d-120">編輯、重新設定或刪除連接的應用程式</span><span class="sxs-lookup"><span data-stu-id="b744d-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="b744d-121">[ **開啟應用程式設定** ] 連結會在 azure 入口網站中開啟對應的 [Azure AD 應用程式管理] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b744d-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="b744d-122">從 Azure 入口網站，您可以管理許可權、重新設定或刪除連接的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b744d-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
