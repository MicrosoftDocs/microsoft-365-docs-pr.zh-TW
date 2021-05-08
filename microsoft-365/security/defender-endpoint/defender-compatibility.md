---
title: 與適用于 Endpoint 的 Defender 的防病毒解決方案相容性
description: 深入瞭解 Windows Defender 如何與 Microsoft Defender for Endpoint 搭配使用，以及如何在使用協力廠商反惡意軟體用戶端時運作。
keywords: windows defender 相容性，defender，Microsoft Defender for Endpoint，defender for endpoint，殺毒軟體，mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274877"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>與 Microsoft Defender for Endpoint 的防病毒解決方案相容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint agent 因某些功能（例如檔案掃描）而異 Microsoft Defender 防毒軟體。

>[!IMPORTANT]
>Endpoint 不會遵循 Microsoft Defender 防毒軟體的排除設定。 

您必須在 Defender for Endpoint 裝置上設定安全性智慧更新，不論 Microsoft Defender 防毒軟體是否為作用中的反惡意程式碼。 如需詳細資訊，請參閱[Manage Microsoft Defender 防毒軟體 updates 和 apply 基準](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。

如果架裝置是由協力廠商反惡意軟體用戶端保護，該端點上的 Microsoft Defender 防毒軟體會進入被動模式。

Microsoft Defender 防毒軟體會繼續接收更新，且 *mspeng.exe* 程式會列為執行服務，但它不會執行掃描，也不會取代執行中的協力廠商反惡意軟體用戶端。

將會停用 Microsoft Defender 防毒軟體介面，而且裝置上的使用者將無法使用 Microsoft Defender 防毒軟體執行隨選掃描或設定大部分選項。

如需詳細資訊，請參閱[Microsoft Defender 防毒軟體和 Defender for Endpoint 相容性主題](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
