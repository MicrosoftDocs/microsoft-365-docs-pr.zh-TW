---
title: 如何在 Microsoft 受管理的電腦中處理更新
description: 將 Microsoft 管理的桌面保持在最新狀態，可平衡速度和穩定性。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5d78f695785cd81b51e20b90cdefbb3790cf6197
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984733"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何在 Microsoft 受管理的電腦中處理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 受管理的桌面會將所有裝置連接至新式雲端架構基礎結構。 保持最新的 Windows、Office、驅動程式、固件及 Microsoft Store for Business 應用程式是速度和穩定性的平衡。 我們使用更新群組，以確保作業系統更新及原則以安全的方式推出。 如需詳細資訊，請參閱影片 [Microsoft 受管理的桌面變更和發行](https://www.microsoft.com/videoplayer/embed/RE4mWqP)程式。 

Microsoft 所發行的更新會累計，而且會分類為品質或功能更新。
如需詳細資訊，請參閱 [Windows update For Business： Update types](/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新群組


Microsoft 受管理的桌面會使用四個 Azure AD 群組來管理更新：

- **測試**：用來驗證 Microsoft 受管理的桌面原則變更、作業系統更新、功能更新，以及已推入 Azure AD 組織 ( "租使用者" ) 中的其他變更。 最適合用來測試或提供早期意見反應的使用者。 測試群組免除任何已建立的服務等級協定和使用者支援。 此群組可用於驗證應用程式與新原則或作業系統變更的相容性。  
- **First**：包含早期的軟體採納者和裝置，其可能會受發行前更新的制約。 如果有測試環中測試期間未涵蓋的案例，則此群組中的裝置可能會遇到中斷問題。
- **Fast**：優先執行速度高於穩定性。 用於偵測品質問題，再將其提供給廣泛的群組。 這個群組是做為下一個驗證層，但通常比測試和第一個群組更穩定。 
- **廣泛**：上一個群組可提供功能和品質更新。 此群組包含 Azure AD 組織中大部分的使用者，因此在部署時比速度高。 在環境最穩定的情況時，應該在這裡進行應用程式的測試。

### <a name="moving-devices-between-update-groups"></a>在更新群組之間移動裝置
您可能想要讓某些裝置接收最後的更新，以及您想要最先移的其他裝置。 若要將這些裝置移至適當的更新群組，請參閱 [將裝置指派給部署群組](../working-with-managed-desktop/assign-deployment-group.md)。

如需這些部署群組中角色和責任的詳細資訊，請參閱 [Microsoft 受管理的桌面角色與責任](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>使用 Microsoft 受管理的桌面更新群組 
您管理的服務有些部分（如應用程式部署），您可能需要將其設定為針對所有受管理的裝置。

## <a name="how-update-deployment-works"></a>更新部署的運作方式：
1. Microsoft 受管理的桌面會根據下表中所指定的排程，部署新的功能或品質更新。
2. 在部署期間，Microsoft 受管理的桌面監視器會根據診斷資料和使用者支援系統，針對失敗或中斷的跡象進行標記。 如果偵測到任何情況，我們會立即暫停部署至所有目前和未來的群組。
    - 範例：如果在部署第一個群組的品質更新時會發現問題，則在解決問題之前，先將部署更新為第一個、快速和廣泛的部署。
    - 您可以在 Microsoft Managed Desktop Admin 入口網站中歸檔票證，以報告相容性問題。
    - 會獨立暫停功能和品質更新。 預設情況下，Pause 會生效于35天，但可根據問題是否已修正，加以縮短或擴充。
3. Unpaused 群組之後，就會根據資料表中的排程，繼續進行部署。

此部署程式會同時適用于功能和品質更新，不過每個階段的時程表各有不同。


<table>
    <tr><th colspan="5">更新部署設定</th></tr>
    <tr><th>更新類型</th><th>測試</th><th>名字</th><th>快速</th><th>廣泛</th></tr>
    <tr><td>作業系統的品質更新</td><td>0天</td><td>0天</td><td>0天</td><td>3天</td></tr>
    <tr><td>作業系統的功能更新</td><td>0天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
    <tr><td>驅動程式/固件</td><td colspan="4">遵循品質更新的排程</td></tr>
    <tr><td>防病毒定義</td><td colspan="4">更新每個掃描</td></tr>
    <tr><td>Microsoft 365 Apps 企業版</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">深入了解</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">深入了解</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">深入了解</a></td></tr>
</table>

>[!NOTE]
>這些延期期間是特意設計，以確保所有使用者的高安全性和效能標準。 此外，根據在所有 Microsoft 受管理的桌面裝置上收集的資料，以及更新的範圍和影響，Microsoft 受管理的桌面保留可靈活修改任何和所有部署群組的上述延遲週期長度。
>
>Microsoft 受管理的桌面會針對每個 Windows 功能版本執行獨立評估，以評估其必要和對其受管理承租人的有用性。 因此，Microsoft 受管理的桌面可能會或不會部署所有 Windows 功能更新。 

## <a name="windows-insider-program"></a>Windows 測試人員計畫

Microsoft 受管理的桌面不支援屬於 Windows 預覽體驗計畫的裝置。 Windows 有問必答計畫是用來驗證預先發行的 Windows 軟體，其適用于並非要徑任務的裝置。 雖然這是一項重要的 Microsoft 倡議，但不適用於實際執行環境中的部署。 

任何找到 Windows 測試人員組建的裝置，都可能會放入測試群組，且不會從 Microsoft Managed Desktop 的更新服務等級協定和使用者支援中免除。

## <a name="bandwidth-management"></a>頻寬管理

我們使用 [傳遞優化](/windows/deployment/update/waas-delivery-optimization) 來進行所有作業系統及驅動程式更新。 傳遞優化會從公司網路中的對等機器上尋找更新，將 Windows Update service 的下載大小降到最低。