---
title: 整合具有 Blackboard 的 Microsoft Teams 類別瞭解超
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 整合具有 Blackboard 的 Microsoft Teams 類別瞭解超
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314486"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>使用具有 Blackboard 的 Microsoft Teams 類別瞭解超

團隊合作是在每個現代組織的核心。 透過鼓勵共同作業，它是定義每個成功之機構的特性。 您可以加強 Blackboard 的所有功能，並將其與 Microsoft Teams 類別配對。

您的類別可能包括即時交談、影片會議或非同步互動。 您可以在一個地方新增學生的檔案共用和 cocreation 體驗。 使用「學習」的 Microsoft Teams 類別會以「大量重新定義教學」和有效學習的意義。

> [!IMPORTANT]
> 確定您已在學生資訊系統 (SIS 中成功設定機構電子郵件欄位) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`
>
>Microsoft Teams 類別整合依賴您 SIS 中的「機構電子郵件」欄位，以對應至正確的 Microsoft Azure Active Directory (AAD) 使用者主體名稱 (UPN) 。 若尚未布建任何機構電子郵件，這將會預設為現有的電子郵件。 建議您為每位使用者設定此欄位，以確保其資料同步處理，且 Microsoft AAD 和 Blackboard 間的電子郵件資料沒有衝突。
>
> 如果您未在 SIS 對應中適當地設定此欄位，整合將繼續運作，但使用者可能不會出現在所建立的 Teams 類別中，而且可能會發生錯誤。

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>支援機構資料對應–機構電子郵件 SIS 欄位

當您使用雲端提供者整合的一部分演變時，Blackboard 會透過「學生資訊系統架構整合」和「公用 REST」 APIs 等方式，在 Blackboard 中建立新的 **機構電子郵件** 欄位，讓組織能夠在 Blackboard 上有效地管理資料同步處理常式。

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>機構的電子郵件含義為何？

「 **機構電子郵件** 」欄位允許用戶端外部支援的資料來源與 Blackboard 的自訂欄位對應。 如果資料來源是雲端提供者（例如 Microsoft），則使用者主體名稱 (UPN) 是由 UPN 首碼組成的每一位使用者的主要唯一識別碼 (使用者的帳戶名稱) 及 UPN 尾碼， (使用 @ 符號加入的 DNS 功能變數名稱。 這會為 Microsoft Azure Active Directory 中的每個特定使用者建立唯一的電子郵件地址。

為了確保資料在 Blackboard 中的準確性和註冊或成員資格可正確地取得，且可正確地取得 Microsoft Teams 類別，使用者的電子郵件地址必須符合兩個系統之間的條件。 在 Blackboard 中，使用者可以在使用者介面中變更或覆寫其現有的電子郵件地址，這可能會導致同步處理錯誤，以及使用者未正確加入類別小組。 使用者可以使用「 **電子郵件** 欄位對應」功能來正確管理此層級的安全性和驗證檢查，不論使用者是否已變更 Blackboard 中的電子郵件。

 當兩個電子郵件地址不同時，請執行下列其中一項：

- 您必須進行決策，使其具有優先權，並將其當作人員和機構電子郵件。
  或
- 機構可以在其機構電子郵件中設定自訂欄位對應，這樣可以解決可能的衝突。

「**機構電子郵件** 欄位對應」現在可用於「**高級設定設定** 的所有現有 SIS 整合類型  >  。使用者會 **瞭解物件類型**  >  **欄位對應**。

> [!NOTE]
> 請務必注意，根據預設， **機構電子郵件** 會設定為所有 SIS 格式的 **電子郵件** ，且每個人都必須是唯一的。 所有已設定並執行的現有整合都會就地進行此資料對應，因為當電子郵件重複時，SIS 會無法匯入使用者。 如果機構需要將機構電子郵件變更為 [**自訂**]，他們必須透過 SIS 中的「**高級設定設定** 來管理這項功能。

## <a name="requirements"></a>需求

**僅限 Ultra 課程查看課程** 可使用 Microsoft Teams 類別整合。 您的機構必須完成這些需求才能使用：

- 讓 Blackboard 瞭解超深入瞭解 SaaS 啟用超基礎導覽

- 啟用 LTI 以供課程使用。

  a. 移至 **系統管理員面板**  >  **LTI 工具提供者**  >  **管理全域屬性**。

  b. **在課程中選取 LTI 啟用**，並選擇性地選取 [**在組織中啟用**]。

  c. 選取 **[提交]**。

- 必須設定 LTI

- 新增 Blackboard 瞭解 Ultra Teams 類別 LTI 整合

- 新增 Microsoft Teams 類別 LTI 1.3 工具

- 新增 REST API 工具和跨原始資源分享

- 設定及核准 Microsoft Teams 類別整合

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Add Blackboard 獲知 Ultra Teams 類別 LTI 1.3 工具

1. 從 [ **管理員] 面板** 中，選取 [ **LTI 工具提供者**]。

2. 選取 [ **註冊 LTI 1.3 工具**]。

3. 在 [ **用戶端識別碼** ] 欄位中，輸入或複製並貼上此 ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. 請檢查所有預先填入的設定及 **工具狀態**，然後選取 [ **啟用**]。

5. 在 **[機構原則**] 中，選取 [**課程]、[名稱**] 和 [**電子郵件地址**] 中的 [角色]，然後選取 **[是]**

6. 選取 [ **允許評分服務存取** 及 **允許成員資格服務存取**]。

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>新增 Microsoft Teams 類別 LTI 1.3 工具

1. 從 [ **管理員] 面板** 中，選取 [ **LTI 工具提供者**]。

2. 選取 [ **註冊 LTI 1.3 工具**]。

3. 在 [ **用戶端識別碼** ] 欄位中，輸入或複製並貼上此 ID:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. 檢查所有預先填入的設定和 [ *工具狀態* ]，然後選取 [ *啟用]。*

5. 在 [**機構原則**] 中，選取 [**課程]、[名稱**] 和 [**電子郵件地址** 為這兩者選取 **[是]** 。

6. 選取 [ **允許評分服務存取** 及 **允許成員資格服務存取**]。

## <a name="add-the-rest-api-tool"></a>新增 REST API 工具

1. 在 [ **管理員] 面板** 中， **流覽至 [整合]，然後** 選取 [ **Rest API** 整合]。

2. 選取 [ **建立整合**]。

3. 在 [ **應用程式識別碼** ] 欄位中，輸入或複製並貼上此 ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. 輸入此整合的使用者。

   此使用者將是應用程式所關聯的家鄉 API 存取的使用者。

5. 選取 **[提交]**。

## <a name="add-the-cross-origin-resource-sharing"></a>新增跨原始資源分享

1. 在 [ **管理員] 面板** 中， **流覽至 [整合]，然後** 選取 [**跨原始資源分享*]。

2. 選取 [ **建立** 設定]。

3. 在 [ **來源** ] 欄位中，輸入複製及貼上此 URL:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. 在 [ **允許的標頭** ] 欄位中，輸入 **授權**。

5. 設定 **為** **[是]**。

6. 選取 **[提交]**。

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>設定及核准 Microsoft Teams 類別整合

若要使用 Microsoft Teams 類別成功整合您的 Blackboard，請確定已核准 blackboard 取得超級應用程式，以便在您的 Microsoft Azure 租使用者記憶體取。 這是您的機構 Microsoft 365 全域管理員需要完成的程式。

您可以在您已設定 Blackboard 中的 LTI 應用程式之前或之後，再執行一步。

### <a name="before-configuring-the-lti-applications"></a>設定 LTI 應用程式之前

如果您選擇核准 Blackboard 在設定 LTI 整合之前，先向 Azure 應用程式獲知 Ultra Teams 類別，您必須重新導向至 **Microsoft Identity Platform 系統管理員同意端點**。 URL 如下：

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> 您會將 **{租** 使用者更換為您的特定機構 Microsoft Azure 租使用者識別碼。

### <a name="after-configuring-the-lti-applications"></a>設定 LTI 應用程式之後

1. 在 [**系統管理員] 面板** 上，流覽至 [**工具及公用程式**]，然後選取 [ **Microsoft Teams Integration Admin**]。

2. 選取 [**啟用 Microsoft Teams**]。

3. 將您的 **Microsoft 租使用者識別碼** 新增至 [可用] 文字欄位。

4. 選擇下列其中一個選項：

   - 如果此應用程式預先同意，它會顯示一個小核取記號。 如果出現核取記號，請選取 [ **提交**]。

   - 若未經核准，請遵循所述的步驟，以產生同意的 URL，並將其傳送給 Microsoft 365 全域管理員以核准。

5. 確認核准後，請選取 [ **重試** 以確認]，然後選取 [ **提交**]。
