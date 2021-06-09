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
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574544"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備列印資源

當您準備好在 Microsoft 受管理的電腦中註冊時，您應該評估列印需求，並決定適合您環境的方式。 您有三個選項：
 
- 部署 Microsoft 通用列印解決方案，讓 Microsoft 受管理的電腦裝置輕鬆探索印表機。 如需詳細資訊，請參閱 [何謂通用列印](/universal-print/fundamentals/universal-print-whatis)。
- 使用自訂的 PowerShell 腳本直接部署印表機。 依照 [ [設定本機印表機](#set-up-local-printers) ] 區段中的步驟進行。
- 使用與加入 Azure Active Directory 網域之 Windows 10 裝置相容的非 Microsoft 雲端列印解決方案。 解決方案必須符合 Microsoft 受管理的電腦的軟體需求。 如需詳細資訊，請參閱[Microsoft 受管理的電腦 app 需求](../service-description/mmd-app-requirements.md)。
 
在所有情況下，如果無法從 Microsoft Update 或 Microsoft Store 中取得印表機驅動程式，您必須自行取得，並使用 Microsoft Intune 將其打包以部署至 Microsoft 受管理的電腦裝置。 如需詳細資訊，請參閱 [Intune 獨立-Win32 應用程式管理](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>設定本機印表機

如果您已決定使用自訂的 PowerShell 腳本部署印表機，並準備好列印資源，請遵循下列步驟來部署共用印表機：

1.  流覽至 Microsoft 受管理的電腦入口網站。
2.  在管理入口網站的 **支援 > 支援要求** 區段中，送出標示為「*印表機部署*」的要求，提供這些詳細資料：
    - 需要為 Microsoft 受管理的電腦裝置部署之共用印表機位置的所有 UNC 路徑
    - 需要存取這些共用印表機的使用者群組
3.  您可以使用系統管理入口網站，告知您要求完成的時間。 起初，我們只會將設定部署至測試部署群組中的裝置。
4.  您必須測試及確認設定是否如預期那樣運作。 使用支援要求中的 [ **討論** ] 索引標籤回復我們，以告知您完成測試的時間。
5.  然後，我們會將設定部署至其他部署群組。

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [準備列印 Microsoft 受管理的電腦本文 (的資源](printing.md)) 
