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
# <a name="assign-devices-to-a-deployment-group"></a>將裝置指派給部署群組

Microsoft 受管理的電腦會將裝置指派給不同的部署群組，但是您可以使用管理入口網站指定或變更群組指派給裝置的裝置。 在註冊裝置或使用者進行註冊後，您可以變更工作分派。

> [!IMPORTANT]
> 如果您變更指派，該群組特有的原則會套用至裝置。 變更可能會安裝最新版的 Windows 10 (包括任何新功能或品質更新) 。 最好一開始只移動幾部裝置，然後檢查產生的使用者經驗。 請注意，特定的更新將會重新開機裝置。 重複檢查您已選取正確的裝置以進行指派。 最多可能需要24小時的時間，工作分派才會生效。

若要將裝置指派給部署群組，請遵循下列步驟。 如果您想要將個別裝置移至不同的群組，請對每個群組重複執行這些步驟。

1. 在 Microsoft 端點管理員中，選取左窗格中的 [**裝置**]。 在 [ **Microsoft 受管理的電腦**] 區段中，選取 [**裝置**]。
2. 選取您要指派的裝置。 所有選取的裝置將會指派給您指定的群組。
3. 從功能表中選取 [ **裝置動作** ]。
4. 選取 [ **指派裝置至群組**]。 飛入隨即開啟。
5. 使用下拉式功能表選取要移動裝置的群組，然後選取 [ **儲存**]。 **指派的群組** 將變更為 **擱置**。

工作分派完成時，[ **指派者] 的群組** 會變更為 **Admin** (表示您已進行變更) 而 **群組** 欄會顯示新的群組指派。

> [!NOTE]
> 如果裝置處在「錯誤」或「擱置」註冊狀態，您就無法將裝置移至其他群組。
>
>如果裝置沒有正確移除，它可能會顯示「就緒」狀態。 如果您移動這類裝置，可能會無法完成移動。 如果您在步驟5中看不到 [變更為 **待處理****指派的群組**]，請在 Intune 中搜尋時，檢查該裝置是否可供使用。 如需詳細資訊，請參閱[在 Intune 中查看裝置詳細資料](/mem/intune/remote-actions/device-inventory)。