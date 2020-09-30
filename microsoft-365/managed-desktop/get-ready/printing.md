---
title: 為 Microsoft 受管理的電腦準備列印資源
description: 確保列印順利運作的重要步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5198691a38b179a5491a36de95531edb9f32d691
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322220"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備列印資源

當您準備好在 Microsoft 受管理的電腦上註冊時，您應該評估列印需求，並決定適合您環境的方式。 您有三個選項：
 
- 部署 Microsoft 通用列印解決方案，讓 Microsoft 受管理的桌面裝置可輕鬆探索印表機。 如需詳細資訊，請參閱 [何謂通用列印](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)。
- 使用自訂的 PowerShell 腳本直接部署印表機。 請遵循 [ [設定本機印表機](#set-up-local-printers) ] 區段中的步驟來執行此動作。
- 使用與加入 Azure Active Directory 網域的 Windows 10 裝置相容的非 Microsoft 雲端列印解決方案。 解決方案必須符合 Microsoft Managed Desktop 的軟體需求。 如需詳細資訊，請參閱 [Microsoft Managed Desktop app 需求](../service-description/mmd-app-requirements.md)。
 
在所有情況下，如果無法從 Microsoft Update 或 Microsoft Store 取得印表機驅動程式，您必須自行取得，並使用 Microsoft Intune 將其打包以部署至 Microsoft 受管理的桌面裝置。 如需詳細資訊，請參閱 [Intune 獨立-Win32 應用程式管理](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>設定本機印表機

如果您已決定使用自訂的 PowerShell 腳本部署印表機，並準備好列印資源，請遵循下列步驟來部署共用印表機：

1.  流覽至 Microsoft 受管理的桌面入口網站。
2.  在管理入口網站的**支援 > 支援要求**區段中，送出標示為「*印表機部署*」的要求，提供這些詳細資料：
    - 將需要為 Microsoft 受管理的桌面裝置部署的共用印表機位置的所有 UNC 路徑
    - 需要存取這些共用印表機的使用者群組
3.  您可以使用系統管理入口網站，告知您要求完成的時間。 起初，我們只會將設定部署至測試部署群組中的裝置。
4.  您必須測試及確認設定是否如預期那樣運作。 使用支援要求中的 [ **討論** ] 索引標籤回復我們，以告知您完成測試的時間。
5.  然後，我們會將設定部署至其他部署群組。
