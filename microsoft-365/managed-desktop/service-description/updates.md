---
title: 如何在 Microsoft 受管理的電腦中處理更新
description: 將 Microsoft 管理的桌面保持在最新狀態，可平衡速度和穩定性。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 03a9b19a5b8ba957419e23c2bb12748c9c57e80d
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104615"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何在 Microsoft 受管理的電腦中處理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 受管理的桌面會將所有裝置連接至新式雲端架構基礎結構。 保持最新的 Windows、Office、驅動程式、固件及 Microsoft Store for Business 應用程式是速度和穩定性的平衡。 部署群組將用來確保作業系統更新及原則以安全的方式推出。 如需詳細資訊，請參閱影片 [Microsoft 受管理的桌面變更和發行處理](https://www.microsoft.com/videoplayer/embed/RE4mWqP)程式。

Microsoft 所發行的更新會累計，而且會分類為品質或功能更新。
如需詳細資訊，請參閱 [Windows update For Business： Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新群組

Microsoft 受管理的桌面會使用四個 Azure AD 群組來管理更新：

- **測試**：用於驗證 Microsoft 受管理的桌面原則變更、作業系統更新、功能更新和其他已推入租使用者的變更。 不應該有任何使用者放置在測試群組中。 測試群組免除任何已建立的服務等級協定和使用者支援。 此群組可用於驗證應用程式與新原則或作業系統變更的相容性。  
- **First**：包含早期的軟體採納者和裝置，其可能會受發行前更新的制約。 如果有測試環中測試期間未涵蓋的情況，則此群組中的裝置可能會遇到中斷問題。
- **Fast**：優先執行速度高於穩定性。 用於偵測品質問題，再將其提供給廣泛的群組。 這個群組是做為下一個驗證層，但通常比測試和第一個群組更穩定。 
- **廣泛**：上一個群組可提供功能和品質更新。 此群組包含租使用者中大部分的使用者，因此在部署時比速度更有利於穩定性。 在環境最穩定的情況時，應該在這裡進行應用程式的測試。 

> [!NOTE]
> 如果您需要將使用者移至不同的更新群組，請提交支援要求。 如需提交支援要求的詳細資訊，請參閱 [Microsoft Managed Desktop 的支援](support.md) 。 如果您自行移動使用者，移動將會還原。

如需這些部署群組的詳細資訊，請參閱 [Microsoft 受管理的桌面角色和責任](../intro/roles-and-responsibilities.md)

更新部署的運作方式：
- Microsoft 受管理的桌面會根據下列指定的排程，部署新的功能或品質更新。
- 在部署期間，Microsoft 受管理的桌面監視器會根據診斷資料和使用者支援系統) ，以取得失敗或中斷 (的跡象。 如果偵測到任何，則會立即暫停部署至所有目前和未來的群組。
    - 範例：如果在部署第一個群組的品質更新時會發現問題，則在解決問題之前，先將部署更新為第一個、快速和廣泛的部署。
    - 您可以在 Microsoft Managed Desktop Admin 入口網站中將票證歸檔，以報告相容性問題。
- 會獨立暫停功能和品質更新。 預設情況下，Pause 會生效于35天，但可根據問題是否已修正，加以縮短或擴充。
- 當群組未暫停時，部署會依照下列排程繼續進行。
- 此部署程式會同時適用于功能和品質更新，不過每個階段的時程表各有不同。




<table>
    <tr><th colspan="5">更新部署設定</th></tr>
    <tr><th>更新類型</th><th>測試</th><th>名字</th><th>快速</th><th>廣泛</th></tr>
    <tr><td>作業系統的品質更新</td><td>0天</td><td>0天</td><td>0天</td><td>3天</td></tr>
    <tr><td>作業系統的功能更新</td><td>0天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
    <tr><td>驅動程式/固件</td><td colspan="4">遵循品質更新的排程</td></tr>
    <tr><td>防病毒定義</td><td colspan="4">更新每個掃描</td></tr>
    <tr><td>Microsoft 365 Apps 企業版</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">深入了解</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">深入了解</a></td></tr>
</table>

>[!NOTE]
>這些延期期間是特意設計，以確保所有使用者的高安全性和效能標準。 此外，根據在所有 Microsoft 受管理的桌面裝置上收集的資料，以及更新的範圍和影響，Microsoft 受管理的桌面保留可靈活修改任何和所有部署群組的上述延遲週期長度。
>
>Microsoft 受管理的桌面會針對每個 Windows 功能版本執行獨立評估，以評估其必要和對其受管理承租人的有用性。 因此，Microsoft 受管理的桌面可能會或不會部署所有 Windows 功能更新。 

## <a name="windows-insider-program"></a>Windows 測試人員計畫

Microsoft 受管理的桌面不支援屬於 Windows 預覽體驗計畫的裝置。 Windows 有問必答計畫是用來驗證預先發行的 Windows 軟體，其適用于並非要徑任務的裝置。 雖然這是一個重要的 Microsoft 倡議，但不是要在實際執行環境中進行廣泛的部署。 

任何找到 Windows 測試人員組建的裝置，都可能會放入測試群組，且不會從 Microsoft Managed Desktop 的更新服務等級協定和使用者支援中免除。

## <a name="bandwidth-management"></a>頻寬管理

我們使用 [傳遞優化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) 來進行所有作業系統及驅動程式更新。 這可透過從公司網路中的對等機器尋找更新，將 Windows Update service 的下載大小降到最低。


