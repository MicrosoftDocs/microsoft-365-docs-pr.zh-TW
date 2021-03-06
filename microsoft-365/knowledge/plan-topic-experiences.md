---
title: Microsoft Viva 主題的計畫
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 瞭解如何規劃 Microsoft Viva 主題的計畫
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229536"
---
# <a name="plan-for-microsoft-viva-topics"></a>Microsoft Viva 主題的計畫

您可以掌控組織中主題的經驗。 針對主題的規劃決策可確保向您的使用者顯示高品質的主題，且具有適當的許可權來使用及參與知識。

在本文中，我們將會檢查這些規劃決策：

- 您想要為主題編目的 SharePoint 網站
- 您想要從主題經驗中排除哪些主題（如果有的話）
- 您要將主題顯示在哪個使用者上
- 您要在主題中心提供許可權以管理主題的使用者
- 您要在主題中心提供許可權以建立或編輯主題的使用者
- 您想要在主題中心提供什麼名稱

考慮到資料的安全性和隱私權，主題經驗不會授與使用者對他們沒有許可權之檔案的其他存取權。 建議您在規劃過程中，閱讀 [Microsoft Viva 主題的安全性和隱私權](topic-experiences-security-privacy.md) 。

若要深入瞭解 Viva 主題背後的 AI 技術，請參閱 [Microsoft Viva 主題中的 Alexandria：從大型資料到大型知識](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)。

## <a name="requirements"></a>需求

您必須[訂閱 Viva 主題](https://www.microsoft.com/microsoft-viva/topics)，以及全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定相關主題。

所有要使用主題的使用者都需要經驗豐富的授權 **主題** 。 在 [設定 Microsoft Viva 主題](set-up-topic-experiences.md)中涵蓋指派授權。

## <a name="topic-discovery"></a>主題探索

主題探索設定會指定使用哪些 SharePoint 網站作為主題的來源。 這包括傳統和現代的網站，以及與 Microsoft Teams 和 Microsoft 365 群組相關聯的網站。 不包含 OneDrive 網站。

您可以選擇包含所有 SharePoint 網站、特定網站清單或沒有網站。 建議您選擇 [所有網站]，讓主題體驗能夠為您的使用者探索大量的良好主題。

當您設定 Viva Topics 時，可以選擇下列選項：

- **所有網站**：貴組織的所有 SharePoint 網站。 這包括目前和未來的網站。
- **除了選取的網站以外的所有網站**：除了您所指定網站之外的所有網站。 在未來建立的網站將會包含為主題探索的來源。 
- **僅限選取的網站**：僅限您指定的網站。 未來建立的網站將不會包含為主題探索的來源。
- **沒有網站**：不包含任何 SharePoint 網站。

如果您選擇 [ **全部] （選取的網站除外** 或 **僅限選取的網站**），您可以上傳具有網站清單的 .csv 檔案。 如果您正在執行試驗，而且想要包含有限數目的網站來啟動，這些選項會非常有用。

您可以複製下列的 .csv 範本：

``` csv
Site name,URL
```

建議您不要選擇「 **沒有網站** 」，因為這會使主題不會自動建立或更新。 不過，如果您想要設定後續主題，然後再新增網站，您可以選擇此選項。

建議您為使用者或知識管理員建立一個程式，以便在組織中需要從主題探索中移除個別網站。

### <a name="multi-geo"></a>多地理位置

如果您的組織已部署[Microsoft 365 多地理](/microsoft-365/enterprise/microsoft-365-multi-geo)位置，主題中心會布建于中央位置，而且位於中央位置的 SharePoint 網站可作為主題的來源使用。  (如果選取 [ **所有網站**]，Viva 主題將使用中央位置中的所有網站。 ) 

內容的所有處理及儲存都是在中央位置進行的。

## <a name="user-permissions"></a>使用者權限

您指定的使用者權限會決定您的組織中的哪些人員與主題及可執行檔動作進行互動。

> [!Note] 
> 在這個階段中，Viva 主題不支援提供來賓 (外部) 使用者的授權或使用者許可權。 

*管理主題*

知識管理員會監督資訊的品質，以及組織中其結構化及其他最佳作法的方式。 他們可以確認和拒絕主題。

雖然您可以指定個別的主題管理員，但建議您建立安全性群組 (或使用現有的一個) ，其中包含您想要成為知識管理員的人員。 您可以在安裝過程中指定此安全性群組。

*建立和編輯主題*

主題參與者是組織中的擁護者和主題專家。 他們可以建立及編輯主題。 

建議您讓組織中的每個人都可以建立及編輯主題，因為在所有使用者都能共用資訊時，主題所能發揮最佳作用。

如果您想要限制建立及編輯特定人員或群組的主題，請為他們建立安全性群組並在安裝過程中加以指定。

您可以選擇不允許任何人參與主題，但是不建議您這麼做。 如果您選擇此選項，則知識管理員仍可編輯及建立主題。

*主題檢視器*

主題檢視器可以查看主題頁面上的資訊、搜尋結果和主題在 SharePoint 頁面等內容中的反白顯示。 當使用者可以存取已發現主題的檔案和頁面時，使用者才會看到已發現的主題。

當您設定主題檢視器時，您可以選擇：

- **組織中的所有人**
- **僅限選取的人員或安全性群組**
- **沒人**

我們建議您 **在組織中的每個人**，但如果您要進行試生產，您可能只想選擇選取的人員或安全性群組。 如果您想要設定主題，但不允許人員查看主題，也可以選擇 [ **否** ]。  (知識管理員仍具有存取權，讓他們可以查看主題，並協助您決定是否要讓主題獲得廣泛的使用。 ) 

## <a name="knowledge-rules"></a>知識規則

以管理員的身分，您可以從主題經驗中排除特定主題。 如果您想要讓機密資料不會出現在主題中，這是很有用的。 雖然知識管理員可以排除主題中心的主題，但不是管理員所排除的主題，也不會對知識管理員顯示。  (知識管理員也可以移除探索之後主題中心的主題。 ) 

如果您想要在系統管理員層級排除主題，您必須將它們新增至 .csv 檔案，並上傳檔案。 您可以在安裝程式或更新版本期間執行這項作業。

.csv 檔必須包含下列參數：

- **名稱**：輸入要排除之主題的名稱。 執行這項作業的方法有兩種：
- **MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。
    - 完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。
    - 部分相符：您可以排除包含特定單字的所有主題。  例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。
- **代表 (選用)**： (也稱為 *擴充*) 若要排除縮寫，請輸入縮寫詞代表的字。

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

您可以複製下列 csv 範本：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>系統管理

當您設定主題時，會自動建立主題中心。 請考慮您想要為主題中心命名的專案，以及您想要的 URL 的名稱。 您可以設定名稱及 URL 做為安裝程式的一部分，您可以變更 Microsoft 365 系統管理中心稍後的名稱 (但不能變更 URL) 。 您可以只有一個主題中心。

## <a name="setup-checklist"></a>安裝檢查清單

當您設定主題經驗時，當您執行安裝精靈時，需要下列專案：

> [!div class="checklist"]
> * 要包含或排除的網站清單 (如果不包含所有網站以進行主題探索)
> * 主題檢視者的安全性群組 (如果不允許所有使用者檢視主題)
> * 主題參與者的安全性群組 (如果不允許所有使用者建立及編輯主題)
> * 主題知識管理員的安全性群組 (如果不允許所有使用者管理主題)
> * 要從主題探索中排除的機密主題清單
> * 主題中心網站的名稱

## <a name="see-also"></a>另請參閱

[設定主題體驗](set-up-topic-experiences.md)

[在 Microsoft 365 中管理主題探索](topic-experiences-discovery.md)

[在 Microsoft 365 中管理主題可見度](topic-experiences-knowledge-rules.md)

[管理 Microsoft 365 中的主題許可權](topic-experiences-user-permissions.md)

[在 Microsoft 365 中變更主題中心的名稱](topic-experiences-administration.md)
