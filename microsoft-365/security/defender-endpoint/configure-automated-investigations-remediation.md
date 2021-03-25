---
title: 設定自動化調查和修正功能
description: 在 Microsoft Defender for Endpoint 中設定您的自動化調查和修正功能。
keywords: 設定、設定、自動化、調查、偵測、提醒、修復、回應
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 31a1c79440a8c1edc2bc8e2f2a163ded2a92fd64
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165762"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中設定自動調查和修正功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

如果您的組織使用 [Microsoft defender for](https://docs.microsoft.com/windows/security/threat-protection/) Endpoint (Defender for endpoint) ， [自動化調查和修復功能](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) 可儲存您的安全性作業小組時間和精力。 如 [這篇博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)所述，這些功能會模仿安全性分析員調查和修正威脅的理想步驟。 [深入瞭解自動化調查和修復](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)。 

若要設定自動調查和修正，請
1. [開啟功能](#turn-on-automated-investigation-and-remediation);和 
2. [設定裝置群組](#set-up-device-groups)。

## <a name="turn-on-automated-investigation-and-remediation"></a>開啟自動調查和修正

1. 以全域管理員或安全性管理員的身分，移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。
2. 在功能窗格中，選擇 [ **設定**]。
3. 在 [ **一般** ] 區段中，選取 [ **高級功能**]。
4. 開啟 **自動調查** 並 **自動解決提醒**。

## <a name="set-up-device-groups"></a>設定裝置群組

1. 在 [Microsoft Defender Security Center (] [https://securitycenter.windows.com](https://securitycenter.windows.com)) 的 [ **設定** ] 頁面上，選取 [ **許可權**] 底下的 [ **裝置群組**]。
2. 選取 [ **+ 新增裝置群組**]。
3. 建立至少一個裝置群組，如下所示：
   - 指定裝置群組的名稱和描述。
   - 在 [ **自動化層級] 清單** 中，自動選取一個層級（如 **完整–修正威脅**）。 「自動化」層級決定是否會自動採取或只在核准時採取修復動作。 若要深入瞭解，請參閱自動化 [調查和修正中的自動化層級](automation-levels.md)。
   - 在 [ **成員** ] 區段中，使用一或多個條件來識別及納入裝置。
   - 在 [ **使用者存取** ] 索引標籤上，選取應該存取您所建立之裝置群組的 [Azure Active Directory 群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) 。
4. 當您完成設定裝置群組時，請選取 [ **完成** ]。

## <a name="next-steps"></a>後續步驟

- [流覽行動中心以查看擱置和完成的修復動作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [審閱及核准擱置的動作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>另請參閱

- [在 Microsoft Defender for Endpoint 中處理誤報/負片](defender-endpoint-false-positives-negatives.md)
