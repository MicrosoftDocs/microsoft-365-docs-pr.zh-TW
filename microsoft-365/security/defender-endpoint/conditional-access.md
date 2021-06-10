---
title: 啟用條件式存取，以更好地保護使用者、裝置和資料
description: 啟用條件式存取，以防止在裝置遭到危險時執行應用程式，並判斷應用程式是否不相容。
keywords: 條件式存取、封鎖應用程式、安全性層級、intune
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166194"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>啟用條件式存取，以更好地保護使用者、裝置和資料 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

條件式存取是一項功能，可確保只有安全的裝置能夠存取應用程式，以協助您更好地保護使用者和公司資訊。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

使用條件式存取，您可以根據裝置的風險層級來控制公司資訊的存取。 這有助於讓信任的使用者在信任的裝置上使用受信任的應用程式。

您可以在裝置回到相容狀態時強制執行原則，以阻止應用程式執行並存取網路上的資訊，以定義安全性條件。 

在 Defender for Endpoint 中的條件式存取的實施是根據 Microsoft Intune (Intune) 裝置相容性原則及 Azure Active Directory (Azure AD) 條件式存取原則。 

相容性原則與條件式存取一起使用，僅允許滿足一或多項裝置合規性原則規則的裝置存取應用程式。 

## <a name="understand-the-conditional-access-flow"></a>瞭解條件式存取流程
設定條件式存取時，當在裝置上看到威脅時，就會封鎖敏感內容的存取，直到威脅修正為止。 

流程會從顯示為低、中或高風險的裝置開始。 然後這些風險會決定會傳送至 Intune。 

根據您在 Intune 中設定原則的方式，可以設定條件式存取，以便在符合某些條件時，套用原則。

例如，您可以設定 Intune 在具有高風險的裝置上套用條件式存取。

在 Intune 中，裝置相容性原則會搭配 Azure AD 條件式存取使用，以封鎖對應用程式的存取。 同時會啟動自動化調查和修正處理常式。

 當自動調查和修正進行時，使用者仍可使用裝置，但是會封鎖企業資料存取，直到威脅完全得以修正為止。 

若要解決裝置上發現的風險，您必須將該裝置恢復為相容的狀態。 當裝置上未出現任何風險時，裝置會回到相容狀態。 

有三種方法可以解決風險：
1. 使用手動或自動修復。
2. 解決裝置上的主動警示。 這將會移除裝置中的風險。
3. 您可以從作用中的原則移除裝置，因此不會在裝置上套用條件式存取。 

手動修正需要 secops 管理員才能調查警示，並解決裝置上看到的風險。 自動修正是透過下列各節中提供的設定設定來設定：設定 [條件式存取](configure-conditional-access.md)。

透過手動或自動修復來移除風險時，裝置會回到相容狀態，並且會授與應用程式的存取權。

下列事件的範例會說明條件式存取的動作：

1. 使用者開啟惡意檔案和 Defender for Endpoint，將裝置旗標為高風險。
2. 將高風險評估傳遞給 Intune。 在並行中，會啟動自動化調查以修正已識別的威脅。 您也可以採取手動修正以修正已識別的威脅。
3. 根據在 Intune 中建立的原則，裝置會標示為不相容。 然後，會透過 Intune 條件式存取原則將評估傳遞給 Azure AD。 在 Azure AD 中，會套用對應的原則，以封鎖對應用程式的存取。
4. 手動或自動調查和修正已完成，且威脅已移除。 Defender for Endpoint 會看到裝置上沒有任何風險，而且 Intune 會將裝置評估為相容狀態。 Azure AD 會套用允許存取應用程式的原則。
5. 使用者現在可以存取應用程式。

 
## <a name="related-topic"></a>相關主題
- [在 Microsoft Defender for Endpoint 中設定條件式存取](configure-conditional-access.md)
