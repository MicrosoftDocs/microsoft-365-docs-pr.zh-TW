---
title: 指定雲端傳送的 Microsoft Defender 防毒軟體保護層級
description: 設定 Microsoft Defender 防毒軟體的雲端傳送保護層級。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274901"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>指定雲端提供的保護層級

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用 Microsoft 端點管理員 (建議的) 或群組原則，指定 Microsoft Defender 防毒軟體所提供的雲端提供保護層級。

> [!TIP]
> 雲端保護不只是保護儲存在雲端中的檔案。 Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞至您的網路和裝置 (也稱為端點) 。 Cloud protection with Microsoft Defender 防毒軟體會使用分散式資源和機器教學，以比傳統的安全性智慧更新更快的速率來提供對端點的保護。 Microsoft Intune 和 Microsoft 端點管理員現在是[Microsoft 端點管理員](/mem/endpoint-manager-overview)的一部分。 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>使用 Microsoft 端點管理員來指定雲端傳送保護的層級

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。

2. 選擇 [ **Endpoint security**  >  **防病毒**]。

3. 選取防病毒設定檔。  (如果您尚沒有其中一個，或若您想要建立新的設定檔，請參閱[在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。

4. 選取 [ **屬性**]。 然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。

5. 展開 [ **cloud protection**]，然後在 [ **雲端提供的保護層級** ] 清單中，選取下列其中一項：

    1. **High**：套用強層次的偵測。
    2. **High plus**：使用 **高階** ，套用其他保護措施 (可能會影響用戶端效能) 。
    3. **零容錯**：封鎖所有的未知可執行檔。

6. 選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。 

> [!TIP]
> 需要協助嗎？ 請參閱下列資源：
> - [設定 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [在 Intune 中新增 endpoint protection 設定](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>使用群組原則指定雲端傳送保護的層級

1.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

3.  在 [**群組原則管理編輯器**] 中，移至 [電腦設定]**系統**  >  **管理範本**。

4.  展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **MpEngine**。

5.  按兩下 [ **選取 cloud protection level** ] 設定，並將其設定為 [ **啟用**]。 選取保護層級：
    - **預設封鎖層級** 提供強偵測，但不會增加偵測合法檔案的風險。
    - **適中的封鎖層級** 只對高度信賴的偵測提供適中功能
    - **高封鎖程度** 會在優化用戶端效能 (時套用強層次的偵測，但也可讓您更有可能) 誤報。
    - **高 + 封鎖層級** 套用額外的保護措施 (可能會影響用戶端效能，並增加誤報) 的機率。
    - **零容忍封鎖層級** 會封鎖所有的未知可執行檔。
    
    > [!WARNING]
    > 雖然不太可能，將此參數設定為 **高** 或 **高的 +** 時可能會造成某些合法檔案 (，但您可以選擇取消封鎖或爭議偵測) 。

6. 按一下 ****[確定]。

7. 部署更新的群組原則物件。 請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 您是否在內部部署使用群組原則物件？ 請參閱他們在雲端中的翻譯方式。 [在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)
- [如何建立及部署反惡意程式碼原則： Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)