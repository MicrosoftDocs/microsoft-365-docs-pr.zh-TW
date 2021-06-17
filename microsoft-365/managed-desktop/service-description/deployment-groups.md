---
title: 裝置部署群組
description: 用來管理更新及其他變更的部署群組
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985543"
---
# <a name="device-deployment-groups"></a>裝置部署群組

Microsoft 受管理的電腦會使用部署群組來管理裝置的更新和設定變更的發行。 裝置會在註冊 Microsoft 受管理的電腦時自動 ) 新增至部署群組 ( 「震鈴」或「更新群組」。 部署群組可讓裝置接收階段性時程表中的變更。

您可能會想要指派特定裝置以進行測試，或指定特定的早期目標，以先接收變更。 如果您有重要裝置，例如高層所使用的裝置或執行業務關鍵型功能的裝置，您可能想要將其保留在最慢節奏上更新的群組中。 Microsoft 受管理的電腦可讓您指定裝置應該保留在下列任何一個群組中。

- **測試**：適合用於測試的裝置，或可容忍經常變更並可容忍新功能的使用者，同時提供更早的意見反應。 這個群組會在此群組中經常接收變更，且經驗很強大。 測試群組免除任何已建立的服務等級協定和使用者支援。 最好一開始只移動幾部裝置，然後再查看使用者經驗。 Microsoft 受管理的電腦不會自動將裝置指派給此群組;它只會有您指定的裝置。
- **First**：適用于先期採用者、自願或指定驗證者、IT 專業人員或業務職能代表，也就是可驗證變更的人員，也就是提供您對經驗的意見反應。
- **廣泛** 接收變更的最後。 您的組織通常會位於此群組中。 您也可以指定必須在此群組中的裝置，並且應該只接收最後的變更，因為它們會執行業務重要的職能或屬於重要角色的使用者。 
- **自動**：當您想要 Microsoft 受管理的電腦自動將裝置指派給其他其中一個群組時，請選取此選項。  (我們不會自動指派要測試的裝置。 ) 如果您想要發行先前指定的裝置，以便自動指派該裝置，請選取此選項。 

Microsoft 受管理的電腦會使用一些額外的群組來控制部署，但無法將裝置指派給它們。 不過，您可以將這些群組中的裝置移至本文中的其中一個群組。 如需群組中 Windows 更新的管理方式的詳細資訊，請參閱[Microsoft 受管理的電腦中的更新的處理方式](updates.md)。

如果裝置位於您已指定的群組中，則 **指派給群組的群組** 會是 **Admin**。如果 Microsoft 受管理的電腦已指派群組，它會顯示 [**自動**]。當裝置正在移至群組時，它會被 **擱置**。 **Group** 欄位一定會顯示裝置目前所在的群組，而且只會在移動完成時進行更新。

> [!IMPORTANT]
> 不要嘗試直接修改這些群組的成員資格。 請務必遵循 [將裝置指派給部署群組](../working-with-managed-desktop/assign-deployment-group.md)中所述的步驟。
