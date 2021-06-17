---
title: 將裝置指派給部署群組
description: 如何指定您要裝置的部署群組
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985541"
---
# <a name="assign-devices-to-a-deployment-group"></a><span data-ttu-id="9a320-104">將裝置指派給部署群組</span><span class="sxs-lookup"><span data-stu-id="9a320-104">Assign devices to a deployment group</span></span>

<span data-ttu-id="9a320-105">Microsoft 受管理的電腦會將裝置指派給不同的部署群組，但是您可以使用管理入口網站指定或變更群組指派給裝置的裝置。</span><span class="sxs-lookup"><span data-stu-id="9a320-105">Microsoft Managed Desktop will assign devices to the various deployment groups, but you can specify or change group a device is assigned to a device by using the Admin portal.</span></span> <span data-ttu-id="9a320-106">在註冊裝置或使用者進行註冊後，您可以變更工作分派。</span><span class="sxs-lookup"><span data-stu-id="9a320-106">You change the assignment after a device is registered or after a user has enrolled.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a320-107">如果您變更指派，該群組特有的原則會套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="9a320-107">If you change the assignment, policies that are specific to that group will be applied to the device.</span></span> <span data-ttu-id="9a320-108">變更可能會安裝最新版的 Windows 10 (包括任何新功能或品質更新) 。</span><span class="sxs-lookup"><span data-stu-id="9a320-108">The change might install the latest version of Windows 10 (including any new feature or quality updates).</span></span> <span data-ttu-id="9a320-109">最好一開始只移動幾部裝置，然後檢查產生的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="9a320-109">It's best to move just a few devices at first and then check the resulting user experience.</span></span> <span data-ttu-id="9a320-110">請注意，特定的更新將會重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="9a320-110">Be aware that certain updates will restart the device.</span></span> <span data-ttu-id="9a320-111">重複檢查您已選取正確的裝置以進行指派。</span><span class="sxs-lookup"><span data-stu-id="9a320-111">Double-check that you've selected the right devices to assign.</span></span> <span data-ttu-id="9a320-112">最多可能需要24小時的時間，工作分派才會生效。</span><span class="sxs-lookup"><span data-stu-id="9a320-112">It can take up to 24 hours for the assignment to take effect.</span></span>

<span data-ttu-id="9a320-113">若要將裝置指派給部署群組，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9a320-113">To assign devices to a deployment group, follow these steps.</span></span> <span data-ttu-id="9a320-114">如果您想要將個別裝置移至不同的群組，請對每個群組重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="9a320-114">If you want to move separate devices to different groups, repeat these steps for each group.</span></span>

1. <span data-ttu-id="9a320-115">在 Microsoft 端點管理員中，選取左窗格中的 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="9a320-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span></span> <span data-ttu-id="9a320-116">在 [ **Microsoft 受管理的電腦**] 區段中，選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="9a320-116">In the **Microsoft Managed Desktop** section, select **Devices**.</span></span>
2. <span data-ttu-id="9a320-117">選取您要指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="9a320-117">Select the devices you want to assign.</span></span> <span data-ttu-id="9a320-118">所有選取的裝置將會指派給您指定的群組。</span><span class="sxs-lookup"><span data-stu-id="9a320-118">All selected devices will be assigned to the group you specify.</span></span>
3. <span data-ttu-id="9a320-119">從功能表中選取 [ **裝置動作** ]。</span><span class="sxs-lookup"><span data-stu-id="9a320-119">Select **Device actions** from the menu.</span></span>
4. <span data-ttu-id="9a320-120">選取 [ **指派裝置至群組**]。</span><span class="sxs-lookup"><span data-stu-id="9a320-120">Select **Assign device to group**.</span></span> <span data-ttu-id="9a320-121">飛入隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="9a320-121">A fly-in opens.</span></span>
5. <span data-ttu-id="9a320-122">使用下拉式功能表選取要移動裝置的群組，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9a320-122">Use the drop-down menu to select the group to move devices to, and then select **Save**.</span></span> <span data-ttu-id="9a320-123">**指派的群組** 將變更為 **擱置**。</span><span class="sxs-lookup"><span data-stu-id="9a320-123">The **Group assigned by** will change to **Pending**.</span></span>

<span data-ttu-id="9a320-124">工作分派完成時，[ **指派者] 的群組** 會變更為 **Admin** (表示您已進行變更) 而 **群組** 欄會顯示新的群組指派。</span><span class="sxs-lookup"><span data-stu-id="9a320-124">When the assignment is complete, **Group assigned by** will change to **Admin** (indicated that you made the change) and the **Group** column will show the new group assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="9a320-125">如果裝置處在「錯誤」或「擱置」註冊狀態，您就無法將裝置移至其他群組。</span><span class="sxs-lookup"><span data-stu-id="9a320-125">You can't move devices to other groups if they're in the "error" or "pending" registration state.</span></span>
>
><span data-ttu-id="9a320-126">如果裝置沒有正確移除，它可能會顯示「就緒」狀態。</span><span class="sxs-lookup"><span data-stu-id="9a320-126">If a device hasn't been properly removed, it could show a status of "ready."</span></span> <span data-ttu-id="9a320-127">如果您移動這類裝置，可能會無法完成移動。</span><span class="sxs-lookup"><span data-stu-id="9a320-127">If you move such a device, it's possible that the move won't complete.</span></span> <span data-ttu-id="9a320-128">如果您在步驟5中看不到 [變更為 **待處理\*\*\*\*指派的群組**]，請在 Intune 中搜尋時，檢查該裝置是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="9a320-128">If you don't see **Group assigned by** change to **Pending** in Step 5, check that the device is available by searching for it in Intune.</span></span> <span data-ttu-id="9a320-129">如需詳細資訊，請參閱[在 Intune 中查看裝置詳細資料](/mem/intune/remote-actions/device-inventory)。</span><span class="sxs-lookup"><span data-stu-id="9a320-129">For more information, see [See device details in Intune](/mem/intune/remote-actions/device-inventory).</span></span>