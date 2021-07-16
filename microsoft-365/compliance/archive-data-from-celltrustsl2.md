---
title: 將資料從 CellTrust SL2 平臺封存至 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 瞭解如何設定和使用 CellTrust SL2 資料連線器，以匯入及封存行動通訊資料。
ms.openlocfilehash: 191160921c9e949aa7b82520d72dc7a18bfb26ef
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453968"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365"></a>將資料從 CellTrust SL2 封存至 Microsoft 365

CellTrust SL2 會捕獲行動通訊資料，並與領先的封存技術整合，以符合 FINRA、HIPAA、FOIA 和 TCPA 等法規的電子探索需求。 SL2 資料連線器會將行動通訊專案匯入 Microsoft 365。 本文說明使用 CellTrust SL2 資料連線器進行封存，將 SL2 與 Microsoft 365 進行整合的處理常式。 完成此程式假設您已訂閱 CellTrust SL2 服務，並且熟悉 SL2 架構。 如需 SL2 的相關資訊，請參閱 <www.celltrust.com>。

在 Microsoft 365 中將資料匯入至使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、Microsoft 365 保留原則及通訊法規遵從性。 在 Microsoft 365 中使用 CellTrust SL2 資料連線器匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>使用 CellTrust SL2 資料連線器封存的概覽

CellTrust 的 SL2 平臺會從多個來源捕獲通訊資料。 SL2 資料來源是人員對個人 (P2P) 或應用程式對人員 (A2P) 。 本文所述的程式僅適用于 P2P 的資料來源。 對於所有的 P2P 資料來源，合作中至少有一個參與方是訂閱 SL2 服務的 SL2 使用者。 下列概要說明在 Microsoft 365 中使用 CellTrust SL2 資料連線器的程式。

![CellTrust SL2 服務的封存工作流程](../media/CellTrustSL2ConnectorWorkflow.png)

1. SL2 使用者在 Microsoft Azure 雲端中傳送和接收 SL2 服務的資料。

2. 您的組織在 CellTrust 的 SL2 雲端服務環境中有 SL2 網域。 您的網域可能會有一或多個組織單位 (Ou) 。 SL2 雲端服務會將您的資料傳送至 Microsoft Azure 平臺中的高度安全區域，使您的資料永遠不會離開 Microsoft Azure 環境。 根據您的 SL2 方案 (Enterprise、SMB 或政府) ，您的網域是在 Microsoft Azure Global 或 Microsoft Azure 政府上主控。

3. 在您建立 CellTrust SL2 資料連線器之後，您的網域和 Ou (不論您的 SL2 計畫) ，開始將資料傳送至 Microsoft 365。 資料摘要的結構化是以資料來源、Ou 或網域為基礎的方式支援報告。 因此，您的組織只需要一個連接器，即可將所有資料來源送入 Microsoft 365。

4. 連接器會在每個對應的使用者下建立一個資料夾，且該資料夾具有適當的 Office 365 授權，名稱為 **CellTrust SL2**。 這種對應使用電子郵件地址，將 CellTrust SL2 使用者連線至 Office 365 信箱。 如果 CellTrust SL2 中的使用者識別碼在 Office 365 中沒有符合，將不會封存使用者的資料。

## <a name="before-you-set-up-a-connector"></a>在您設定連接器之前

- 確認您在 CellTrust SL2 雲端服務環境中有網域。 如需取得實際執行或試用 SL2 網域的詳細資訊， [請與 CellTrust 聯繫](https://www.celltrust.com/contact-us/#form)。

- 取得認證以存取 SL2 網域的系統管理員帳戶。

- 在步驟1中建立 CellTrust SL2 資料連線器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。 在 Microsoft 365 合規性中心中的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-create-a-celltrust-sl2-connector"></a>步驟1：建立 CellTrust SL2 connector

第一步是在 Microsoft 365 合規性中心中建立資料連線器。

1. 移至 <https://compliance.microsoft.com> 並按一下左導覽窗格上的 [ **資料連線器** ]。

2. 在 [ **概覽** ] 索引標籤上，按一下 [ **篩選** ]，然後選取 [ **依 CellTrust**]，然後套用篩選器。

   ![設定篩選以顯示 CellTrust 連接器](../media/DataConnectorsFilter.png)

3. 按一下 [ **CELLTRUST SL2 (預覽** ]) 。

4. 在 [ **CELLTRUST SL2 (預覽**) 產品描述] 頁面上，按一下 [ **新增連接器**]。

5. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

6. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。 您輸入的名稱會在您建立後，識別 [ **資料連線器** ] 頁面上的連接器。

7. 在 [登 **入您的 CellTrust 帳戶** ] 頁面上，按一下 [登 **入 CellTrust**]。 您將會重新導向至 **CellTrust 入口網站**，以在新的瀏覽器視窗中 Microsoft 365。

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>步驟2：選取要封存的網域或組織單位

下一步是登入 CellTrust SL2 網域的系統管理員帳戶，然後選取要 Microsoft 365 中封存的網域和 Ou。

1. 在 [CellTrust **Microsoft 365 連接器**] 頁面上，選取 SL2 雲端服務中您的環境，以顯示登入頁面。

   一般來說，您應該會看到一個代表您環境的選項。 不過，如果您在一個以上的環境中有網域，您會看到每個環境的選項。 進行選取之後，您將會重新導向至 SL2 登入頁面。

2. 使用您的網域或 OU 管理員帳戶認證登入。

   如果您以 SL2 域管理員身分登入，您將會看到您的功能變數名稱和該網域中的 Ou 名稱。 如果您沒有 Ou，您只會看到您的網功能變數名稱稱。 如果您以 OU 管理員身分登入，您只會看到 OU 的名稱。

3. 啟用您想要封存的商務單位。 選取 [網域] 不會自動選取 Ou。 您必須個別啟用每個 OU 以進行封存。

   ![啟用 Ou 進行封存](../media/EnableCellTrustOUs.png)

4. 當您完成選取時，請關閉瀏覽器視窗，並回到 Microsoft 365 合規性中心中的 [嚮導] 頁面。 幾秒後，嚮導會自動前進至下一步的對應使用者。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

最後一個步驟是將使用者對應，並完成 Microsoft 365 合規性中心中的連接器設定。

1. 在 [**使用者對應**] 頁面上，如果使用者的電子郵件地址在 SL2 和 Microsoft 365 中相同，請選取 [**啟用自動使用者對應**]。 否則，您應該將使用者的 SL2 位址對應至其 Microsoft 365 位址的 CSV 檔案，手動傳送使用者的電子郵件地址。

2. 按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。

   新的連接器會新增至 [ **資料連線器** ] 頁面上的清單中。

## <a name="get-help-from-celltrust"></a>從 CellTrust 取得協助

如需聯繫 CellTrust 的詳細資訊，請參閱 [CellTrust 客戶支援頁面](https://www.celltrust.com/contact-us/#support) ，以取得設定 CellTrust SL2 資料連線器的相關詳細資訊。

## <a name="more-information"></a>其他相關資訊

- 網域管理員可以為網域或該網域中的任何 Ou 設定連接器。 如果您使用 [OU 管理員] 帳戶，您只能為該特定 OU 設定連接器。

- 若要順利完成上述步驟，您必須獲指派 Microsoft 365 E5 授權，且具有適當的 Microsoft Office 系統管理員權力。

- 若要測試新的連接器，請使用您的 SL2 行動應用程式或 SL2 入口網站傳送短信。 移至您的 Microsoft 365 信箱，並在您的收件匣中開啟 [ **CellTrust SL2** ] 資料夾。 可能需要幾分鐘的時間，文字郵件才會顯示在您的信箱中。

- 許多的法律和規章都需要電子通訊才能加以保留，在要求時，可將其當作證據產生。 電子化探索 (eDiscovery) 是用來符合電子通訊的實際執行。 Enterprise資訊封存 (EIA) 解決方案的設計目的是要執行 eDiscovery，並提供保留原則管理、資料分類和內容監控等功能。 Microsoft 365 提供長期保留解決方案，以符合影響組織的規章和標準。

- 這份檔 *中所用的術語「* 封存」是指在 Enterprise 資訊封存 (EIA) 解決方案內使用的內容。 EIA 方案具有 eDiscovery 功能，可產生法律訴訟、訴訟、審核和調查的檔。 在用於災難復原和商務持續性的備份與還原內容中封存，並非本檔中的術語用途。
