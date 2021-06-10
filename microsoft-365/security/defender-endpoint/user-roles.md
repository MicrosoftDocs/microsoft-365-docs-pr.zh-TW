---
title: 建立及管理以角色為基礎的存取控制的角色
description: 在 Microsoft Defender 資訊安全中心中建立角色並定義指派給角色的許可權，做為以角色為基礎的存取控制執行的一部分
keywords: 使用者角色、角色、存取 rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059236"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="e86b3-104">建立及管理以角色為基礎的存取控制的角色</span><span class="sxs-lookup"><span data-stu-id="e86b3-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e86b3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e86b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="e86b3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e86b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e86b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e86b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e86b3-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e86b3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e86b3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e86b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="e86b3-110">建立角色並將角色指派給 Azure Active Directory 群組</span><span class="sxs-lookup"><span data-stu-id="e86b3-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="e86b3-111">下列步驟會引導您瞭解如何在 Microsoft Defender 資訊安全中心中建立角色。</span><span class="sxs-lookup"><span data-stu-id="e86b3-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e86b3-112">它會假設您已建立 Azure Active Directory 使用者群組。</span><span class="sxs-lookup"><span data-stu-id="e86b3-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="e86b3-113">使用已指派安全性管理員或全域系統管理員角色的帳戶登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="e86b3-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="e86b3-114">在功能窗格中，選取 [**設定 > 角色**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="e86b3-115">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-115">Select **Add item**.</span></span>

4. <span data-ttu-id="e86b3-116">輸入您想要指派給角色的角色名稱、描述及許可權。</span><span class="sxs-lookup"><span data-stu-id="e86b3-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="e86b3-117">選取 **[下一步]** ，將角色指派給 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e86b3-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="e86b3-118">使用篩選器來選取您想要新增至此角色的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="e86b3-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="e86b3-119">**儲存並關閉**。</span><span class="sxs-lookup"><span data-stu-id="e86b3-119">**Save and close**.</span></span>

8. <span data-ttu-id="e86b3-120">套用設定設定。</span><span class="sxs-lookup"><span data-stu-id="e86b3-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e86b3-121">建立角色之後，您將需要建立裝置群組，並將其指派給剛才建立的角色，以提供對該裝置群組的存取權。</span><span class="sxs-lookup"><span data-stu-id="e86b3-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="e86b3-122">許可權選項</span><span class="sxs-lookup"><span data-stu-id="e86b3-122">Permission options</span></span>

- <span data-ttu-id="e86b3-123">**查看資料**</span><span class="sxs-lookup"><span data-stu-id="e86b3-123">**View data**</span></span>
    - <span data-ttu-id="e86b3-124">**安全性作業** -查看入口網站中的所有安全性作業資料</span><span class="sxs-lookup"><span data-stu-id="e86b3-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="e86b3-125">**威脅及弱點管理**-View 威脅與弱點管理入口網站中的資料</span><span class="sxs-lookup"><span data-stu-id="e86b3-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="e86b3-126">**主動修正動作**</span><span class="sxs-lookup"><span data-stu-id="e86b3-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="e86b3-127">**安全性作業** -採取回應動作、核准或取消未決修正動作、管理允許/封鎖的自動化和指示器清單</span><span class="sxs-lookup"><span data-stu-id="e86b3-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="e86b3-128">**威脅及弱點管理例外** 狀況-建立新的例外狀況及管理作用中的例外狀況</span><span class="sxs-lookup"><span data-stu-id="e86b3-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="e86b3-129">**威脅與弱點管理修正處理**-提交新的修復要求、建立票證，以及管理現有的修復活動</span><span class="sxs-lookup"><span data-stu-id="e86b3-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="e86b3-130">**警示調查** -管理提醒、啟動自動化調查、執行掃描、收集調查套件、管理裝置標記，並只下載可遷移的可執行檔 (PE) 檔案</span><span class="sxs-lookup"><span data-stu-id="e86b3-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="e86b3-131">**管理入口網站系統設定** -設定儲存設定、SIEM 及威脅 intel API 設定 (會套用全域) 、高級設定、自動化檔案上傳、角色和裝置群組</span><span class="sxs-lookup"><span data-stu-id="e86b3-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="e86b3-132">此設定僅適用于 Microsoft Defender for Endpoint 管理員 (default) role。</span><span class="sxs-lookup"><span data-stu-id="e86b3-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="e86b3-133">**Manage Security Center 中的安全性設定** -設定警示抑制設定、管理自動化、板載和下架裝置的資料夾排除，以及管理電子郵件通知、管理評估實驗室</span><span class="sxs-lookup"><span data-stu-id="e86b3-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="e86b3-134">**即時回應功能**</span><span class="sxs-lookup"><span data-stu-id="e86b3-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="e86b3-135">**基本** 命令：</span><span class="sxs-lookup"><span data-stu-id="e86b3-135">**Basic** commands:</span></span>
        - <span data-ttu-id="e86b3-136">啟動 live response session</span><span class="sxs-lookup"><span data-stu-id="e86b3-136">Start a live response session</span></span>
        - <span data-ttu-id="e86b3-137">在遠端裝置上執行「唯讀即時回應」命令 (但不包括檔案複製和執行</span><span class="sxs-lookup"><span data-stu-id="e86b3-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="e86b3-138">**Advanced** 命令：</span><span class="sxs-lookup"><span data-stu-id="e86b3-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="e86b3-139">透過即時回應從遠端裝置下載檔案</span><span class="sxs-lookup"><span data-stu-id="e86b3-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="e86b3-140">從檔頁面下載 PE 和非 PE 檔案</span><span class="sxs-lookup"><span data-stu-id="e86b3-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="e86b3-141">將檔案 Upload 至遠端裝置</span><span class="sxs-lookup"><span data-stu-id="e86b3-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="e86b3-142">從檔案庫中查看腳本</span><span class="sxs-lookup"><span data-stu-id="e86b3-142">View a script from the files library</span></span>
        - <span data-ttu-id="e86b3-143">從檔案庫在遠端裝置上執行腳本</span><span class="sxs-lookup"><span data-stu-id="e86b3-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="e86b3-144">如需可用命令的詳細資訊，請參閱 [使用即時回應調查裝置](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="e86b3-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="e86b3-145">編輯角色</span><span class="sxs-lookup"><span data-stu-id="e86b3-145">Edit roles</span></span>

1. <span data-ttu-id="e86b3-146">使用已指派安全性管理員或全域系統管理員角色的帳戶登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="e86b3-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="e86b3-147">在功能窗格中，選取 [**設定 > 角色**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="e86b3-148">選取您要編輯的角色。</span><span class="sxs-lookup"><span data-stu-id="e86b3-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="e86b3-149">按一下 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-149">Click **Edit**.</span></span>

5. <span data-ttu-id="e86b3-150">修改指派給角色的詳細資料或群組。</span><span class="sxs-lookup"><span data-stu-id="e86b3-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="e86b3-151">按一下 [ **儲存並關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="e86b3-152">刪除角色</span><span class="sxs-lookup"><span data-stu-id="e86b3-152">Delete roles</span></span>

1. <span data-ttu-id="e86b3-153">使用已指派安全性管理員或全域系統管理員角色的帳戶登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="e86b3-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="e86b3-154">在功能窗格中，選取 [**設定 > 角色**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="e86b3-155">選取您想要刪除的角色。</span><span class="sxs-lookup"><span data-stu-id="e86b3-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="e86b3-156">按一下下拉式按鈕，然後選取 [ **刪除角色**]。</span><span class="sxs-lookup"><span data-stu-id="e86b3-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="e86b3-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="e86b3-157">Related topic</span></span>

- [<span data-ttu-id="e86b3-158">存取入口網站的使用者基本許可權</span><span class="sxs-lookup"><span data-stu-id="e86b3-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="e86b3-159">建立及管理裝置群組</span><span class="sxs-lookup"><span data-stu-id="e86b3-159">Create and manage device groups</span></span>](machine-groups.md)
