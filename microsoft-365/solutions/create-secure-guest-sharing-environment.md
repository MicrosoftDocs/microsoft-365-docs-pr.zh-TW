---
title: 建立安全的來賓共用環境
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 瞭解在 Microsoft 365 中建立安全的來賓共用環境的可用選項，提供來賓存取改善的共同作業。
ms.openlocfilehash: c52feeb8e5c85d38dfa1623ecdd7c2ee2a381fbd
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667702"
---
# <a name="create-a-secure-guest-sharing-environment"></a>建立安全的來賓共用環境

在本文中，我們將逐一介紹用於在 Microsoft 365 中建立安全的來賓共用環境的各種選項。 下列是可讓您了解可用選項的一些範例。 您可以用不同的組合使用這些程序，以符合貴組織的安全性和合規性需求。

本文包括：

- 為來賓設定多重要素驗證。
- 為來賓設定使用規定。
- 設定每季來賓存取權檢閱，以定期驗證來賓是否繼續需要小組和網站的使用權限。
- 將來賓限制為僅限網頁存取未受管理的裝置。
- 設定工作階段逾時原則，以確保來賓每天進行驗證。
- 為高敏感性專案建立敏感性資訊類型。
- 自動將高敏感性標籤指派給包含敏感性資訊類型的文件。
- 自動從具有敏感度標籤的檔案移除來賓存取。

本文中所述的部分選項要求來賓在 Azure Active Directory 中擁有帳戶。 若要確保共用檔案和資料夾時目錄中包含來賓，請使用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合 (預覽版)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。

請注意，我們不會在本文中討論啟用來賓共用設定。 如需針對不同案例啟用來賓共用的詳細資訊，請參閱[與組織外部人員共同作業](collaborate-with-people-outside-your-organization.md)。

## <a name="set-up-multi-factor-authentication-for-guests"></a>為來賓設定多重要素驗證

多重要素驗證可大幅降低帳戶遭入侵的機會。 由於來賓使用者可能使用不符合任何控管原則或最佳做法的個人電子郵件帳戶，因此要求來賓進行多重要素驗證特別重要。 若來賓使用者的使用者名稱和密碼遭竊，要求第二個驗證要素能大幅降低未知人員存取網站和檔案的機會。

在此範例中，我們將使用 Azure Active Directory 中的條件式存取原則為來賓設定多重要素驗證。

若要為來賓設定多重要素驗證

1. 移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。
2. 在 [條件式存取 | 原則 **]** 刀鋒視窗中，按一下 [新增原則 **]**。
3. 在 [名稱 **]** 欄位中，輸入名稱。
4. 在 **[指派]** 底下，按一下 **[使用者和群組]**。
5. 在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。
6. 在 **[指派]** 底下，按一下 **雲端應用程式或動作**。
7. 在 **雲端應用程式或動作** 刀鋒視窗中，選取 **[包含]** 索引標籤上的 **[所有雲端應用程式]**。
8. 在 **[存取控制]** 底下，按一下 **[授與]**。
9. 在 **[授與]** 刀鋒視窗中，選取 **[需要多重要素驗證]** 核取方塊，然後按一下 **[選取]**。
10. 在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。

現在，來賓必須先註冊多重要素驗證，才能存取共用的內容、網站或小組。

### <a name="more-information"></a>其他資訊

[規劃 Azure AD Multi-Factor Authentication 部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>為來賓設定使用規定

在某些情況下，來賓使用者可能沒有與貴組織簽署保密合約或其他法律合約。 在來賓存取與他們共用的檔案之前，您可以要求來賓同意使用規定。 使用規定可在來賓首次嘗試存取共用檔案或網站時顯示。

若要建立使用規定，您必須先在 Word 或其他撰寫程式建立文件，然後將文件儲存為 .pdf 檔案。 然後便能將此檔案上傳到 Azure AD。

若要建立 Azure AD 使用規定

1. 以全域管理員、安全性系統管理員或條件式存取系統管理員的身分登入 Azure。
2. 瀏覽至 [[使用規定]](https://aka.ms/catou)。
3. 按一下 **[新增規定]**。

   ![Azure AD 新使用規定設定的螢幕擷取畫面](../media/azure-ad-guest-terms-of-use.png)

4. 輸入 [名稱 **]** 和 [顯示名稱 **]**。
6. 在 **使用規定文件**，瀏覽及選取您建立的 PDF 檔案。
7. 選取使用規定文件的語言。
8. 將 **[要求使用者展開使用規定]** 設為 **[開啟]**。
9. 在 **[條件式存取]** 底下的 **[強制使用條件式存取原則範本]** 清單中，選擇 **[稍後建立條件式存取原則]**。
10. 按一下 **[建立]**。

建立使用規定後，下一個步驟是建立條件式存取原則，以顯示來賓使用者的使用規定。

若要建立條件式存取原則

1. 移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。
2. 在 [條件式存取 | 原則 **]** 刀鋒視窗中，按一下 [新增原則 **]**。
3. 在 [名稱 **]** 方塊中，輸入名稱。
4. 在 **[指派]** 底下，按一下 **[使用者和群組]**。
5. 在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。
6. 在 **[指派]** 底下，按一下 **雲端應用程式或動作**。
7. 在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。
8. 在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。
9. 在 **[存取控制]** 底下，按一下 **[授與]**。
10. 在 **[授與]** 刀鋒視窗中，選取 **[來賓使用規定]**，然後按一下 **[選取]**。
11. 在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。

現在，來賓使用者首次嘗試存取貴組織中的內容、小組或網站時，必須接受使用規定。

> [!NOTE]
> 使用條件式存取需要 Azure AD Premium P1 授權。 如需詳細資訊，請參閱[何謂條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

### <a name="more-information"></a>詳細資訊

[Azure Active Directory 使用規定](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>設定來賓存取權檢閱

透過 Azure AD 中的存取權檢閱，您可以自動定期檢閱各小組和群組的使用者存取權。 透過特別要求來賓的存取權檢閱，您可以協助確保來賓使用者不會在非必要時持續存取貴組織的敏感性資訊。

存取權檢閱可組織為程式。 程式是一組類似的存取權檢閱，可用於組織存取權檢閱，以便進行報告和稽核。

若要建立程式

1. 登入 Azure 入口網站，並開啟 [Identity Governance 頁面](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)。
2. 按一下左方功能表中的 **[程式]**。
3. 按一下 **[新增程式]**。
4. 輸入 [名稱 **]** 和 [描述 **]**。
5. 按一下 **[建立]**。

程式建立後，我們就可以建立來賓存取權檢閱，並將其與程式建立關聯。

若要設定來賓使用者存取權檢閱

1. 在 [Identity Governance 頁面](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)的左側功能表中，按一下 **[存取權檢閱]**。
2. 按一下 **[新增存取權檢閱]**。

   ![Azure AD 存取權檢閱設定的螢幕擷取畫面](../media/azure-ad-create-access-review.png)

3. 在 [名稱 **]** 方塊中，輸入名稱。
4. 在 **[頻率]** 選擇 **[每季]**。
5. 在 **[結束]** 選擇 **[永不]**。
6. 在 **[範圍]**，選擇 **[僅限來賓使用者]**。
7. 按一下 **[群組]**，選取要包含在存取權檢閱中的群組，然後按一下 **[選取]**。
8. 按一下 **[程式]** 底下的 **[連結至程式]**。
9. 在 **[選取程式]** 刀鋒視窗中，選擇 **[來賓存取權檢閱程式]**
10. 按一下 **[開始]**。

系統會針對您指定的每個群組建立個別存取權檢閱。 每個群組的群組擁有者每季會收到電子郵件，以核准或拒絕來賓對其群組的存取權。

請注意，來賓可取得小組或群組，或個別檔案和資料夾的存取權。 取得檔案和資料夾存取權時，系統可能不會將來賓新增至任何特定群組。 如果您要對不屬於某小組或群組的來賓使用者執行存取權檢閱，您可以在 Azure AD 中建立動態群組以包含所有來賓，然後建立該群組的存取權檢閱。 網站擁有者也可以管理[網站的來賓到期日](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)

### <a name="more-information"></a>詳細資訊

[使用 Azure AD 存取權檢閱來管理來賓存取權](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[在 Azure AD 存取權檢閱中建立群組或應用程式的存取權檢閱](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>為來賓使用者設定僅限網頁存取

您可以要求來賓使用者僅使用網頁瀏覽器存取小組、網站和檔案，以縮小受攻擊面，並輕鬆進行管理。

若為 Microsoft 365 群組和 Teams，這會使用 Azure AD 條件式存取原則來完成。 若為 SharePoint，這會在 SharePoint 系統管理中心設定。 (您也可以[使用敏感度標籤將來賓限制在僅限 Web 存取](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。)

為群組和小組將來賓限制在僅限 Web 存取：

1. 移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。
2. 在 [條件式存取 - 原則 **]** 刀鋒視窗上，按一下 [新增原則 **]**。
3. 在 [名稱 **]** 方塊中，輸入名稱。
4. 在 **[指派]** 底下，按一下 **[使用者和群組]**。
5. 在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。
6. 在 **[指派]** 底下，按一下 **雲端應用程式或動作**。
7. 在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。
8. 在 [選取 **]** 刀鋒視窗上，選取 **Microsoft Teams** 和 **Outlook Groups**，然後按一下 [選取 **]**。
9. 按一下 **[指派]** 底下的 **[條件]**。
10. 在 **[條件]** 刀鋒視窗中，按一下 **[用戶端應用程式]**。
11. 在 [用戶端應用程式 **]** 刀鋒視窗上，對 [設定 **]** 按一下 [是 **]**，然後選取 [行動裝置應用程式和桌面用戶端 **]**、[Exchange ActiveSync 用戶端 **]** 和 [其他用戶端 **]** 設定。 清除 [瀏覽 **]** 核取方塊。

    ![Azure AD 條件式存取用戶端應用程式設定的螢幕擷取畫面](../media/azure-ad-conditional-access-client-mobile.png)

12. 按一下 [完成 **]**。
13. 在 **[存取控制]** 底下，按一下 **[授與]**。
14. 在 **[授與]** 刀鋒視窗中，選取 **[裝置需要標記為合規]** 和 **[需要已加入混合式 Azure AD 的裝置]**。 
15. 在 **[針對多個控制項]** 底下，選取 **[需要其中一個選取的控制項]**，然後按一下 **[選取]**。
16. 在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。

為 SharePoint 將來賓限制在僅限 Web 存取

1. 在 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)，展開 [原則 **]**，然後按一下 [存取控制 **]**。
2. 按一下 [未受管理的裝置 **]**。
3. 選取 [允許有限的僅限 Web 存取 **]** 選項，然後按一下 [儲存 **]**。

請注意，SharePoint 系統管理中心的此設定會在 Azure AD 中建立支援的條件式存取原則。

## <a name="configure-a-session-timeout-for-guest-users"></a>設定來賓使用者的工作階段逾時

若來賓使用者的裝置不安全，要求來賓定期驗證可降低未知的使用者存取貴組織內容的可能性。 您可以在 Azure AD 中設定來賓使用者的工作階段逾時條件式存取原則。

若要設定來賓工作階段逾時原則

1. 移至 [[Azure 條件式存取原則]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)。
2. 在 **[條件式存取原則]** 刀鋒視窗中，按一下 **[新增原則]**。
3. 在 **[名稱]** 方塊中，輸入 *來賓工作階段逾時*。
4. 在 **[指派]** 底下，按一下 **[使用者和群組]**。
5. 在 **[使用者和群組]** 刀鋒視窗中，選取 **[選取使用者與群組]**，選取 **[所有來賓和外部使用者]** 核取方塊。
6. 在 **[指派]** 底下，按一下 **雲端應用程式或動作**。
7. 在 **[包含]** 索引標籤上，選取 **[選取應用程式]**，然後按一下 **[選取]**。
8. 在 **[選取]** 刀鋒視窗中，選取 **Microsoft Teams**、**Office 365 SharePoint Online** 和 **Outlook Groups**，然後按一下 **[選取]**。
9. 在 **[存取控制]** 底下，按一下 **[工作階段]**。
10. 在 **[工作階段]** 刀鋒視窗中，選取 **[登入頻率]**。
11. 選取 **1**，並在時間週期選取 **[天]** ，然後按一下 **[選取]**。
12. 在 **[新增]** 刀鋒視窗的 **[啟用原則]** 底下，按一下 **[開啟]**，然後按一下 **[建立]**。

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>建立高敏感度專案的敏感性資訊類型

敏感性資訊類型是預先定義的字串，可用於原則工作流程中，以強制執行法規遵循需求。 Microsoft 365 合規性中心隨附超過 100 種敏感性資訊類型，包括駕照編號、信用卡號、銀行帳號等。

您可以建立自訂敏感性資訊類型以協助管理貴組織的特定內容。 在此範例中，我們將建立高敏感度專案的敏感性資訊類型。 然後，我們可以使用此敏感性資訊類型自動套用敏感性標籤。

若要建立敏感性資訊類型

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com)的左側瀏覽窗格中，展開 **[分類]**，然後按一下 **[敏感性資訊類型]**。
2. 按一下 **[建立]**。
3. 在 **名稱** 和 **描述** 輸入 **Saturn 專案**，然後按一下 **[下一步]**。
4. 按一下 **[新增元素]**。
5. 在 **[偵測內容包含]** 清單中，選取 **[關鍵字]**，然後在關鍵字方塊中輸入 *Saturn 專案*。
6. 按一下 **[下一步]**，然後按一下 **[完成]**。
7. 若系統詢問您是否要測試敏感性資訊類型，請按一下 **[否]**。

### <a name="more-information"></a>詳細資訊

[自訂敏感性資訊類型](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a>建立自動標籤原則，以根據敏感性資訊類型指派敏感度標籤

如果您在組織中使用敏感度標籤，則可以自動將標籤套用至包含所定義敏感性資訊類型的檔案。 

建立自動套用標籤原則

1. 開啟 [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com)。
2. 在左側導覽中，按一下 [資訊保護 **]**。
3. 在 [自動加上標籤 **]** 索引標籤上，按一下 [建立自動加上標籤原則 **]**。
4. 在 [選擇要套用此標籤的資訊 **]** 頁面上，選擇 [自訂 **]**，然後按 [下一步 **]**。
5. 輸入原則的名稱和描述，然後按 [下一步 **]**。
6. 在 [選擇您要套用標籤的位置 **]** 頁面上，開啟 [SharePoint 網站 **]**，然後按一下 [選擇網站 **]**。
7. 新增您要開啟自動加上標籤的網站 URL，然後按一下 [完成 **]**。
8. 按 [下一步 **]**。
9. 在 [設定一般或進階規則 **]** 頁面上，選擇 [一般規則 **]**，然後按 [下一步 **]**。
10. 在 [定義所有位置的內容規則 **]** 頁面上，按一下 [新增規則 **]**。
11. 在 [新增規則 **]** 頁面上，為規則命名，按一下 [新增條件 **]**，然後按一下 [內容包含敏感性資訊類型 **]**。
12. 按一下 [新增 **]**，按一下 [敏感性資訊類型 **]**，選擇您要使用的敏感性資訊類型，按一下 [新增 **]**，然後按一下 [儲存 **]**。
13. 按 [下一步 **]**。
14. 按一下 [選擇標籤 **]**，選取您要使用的標籤，然後按一下 [新增 **]**。
15. 按 [下一步 **]**。
16. 將原則保留為模擬模式，然後按 [下一步 **]**。
17. 按一下 [建立原則 **]**，然後按一下 [完成 **]**。

建立原則後，當使用者在文件中輸入「Saturn 專案」時，自動標籤原則將在掃描檔案時自動套用指定的標籤。

### <a name="more-information"></a>其他資訊

[自動將敏感性標籤套用到內容](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a>建立 DLP 原則以移除高敏感性檔案的來賓存取

您可以使用[資料外洩防護 (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 以防止不必要的來賓共用敏感性內容。 資料外洩防護可以根據檔案的敏感度標籤採取動作，並移除來賓存取。

建立 DLP 規則

1. 在 Microsoft 365 合規性系統管理中心中，移至 [資料外外洩防護頁面](https://compliance.microsoft.com/datalossprevention)。
2. 按一下 **[建立原則]**。
3. 選擇 **[自訂]** ，然後按一下 **[下一步]**。
4. 輸入原則的名稱，並按 **[下一步]**。
5. 在 **[套用原則的位置]** 頁面上，關閉 **SharePoint 網站** 和 **OneDrive 帳戶** 以外的所有設定，然後按一下 **[下一步]**。
6. 在 **[定義原則設定]** 頁面上，按一下 **[下一步]**。
7. 在 **[自訂進階資料外洩防護規則]** 頁面上，按一下 **[建立規則]**，然後輸入規則的名稱。
8. 在 [條件 **]** 底下，按一下 [新增條件 **]**，並選擇 [內容包含 **]**。
9. 按一下 [新增 **]**，選擇 [敏感度標籤 **]**，選擇您要使用的標籤，然後按一下 [新增 **]**。

   ![條件選項、敏感性資訊類型、敏感性標籤及保留標籤的螢幕擷取畫面。](../media/limit-accidental-exposure-dlp-conditions.png)

10. 在 [動作 **]** 底下，按一下 [新增動作 **]**，然後選擇 [限制存取或加密 Microsoft 365 位置中的內容 **]**。
11. 選取 [限制存取或在 Microsoft 365 位置中加密內容 **]** 核取方塊，然後選擇 [只有組織外的人員 **]** 選項。

      ![DLP 規則動作選項的螢幕擷取畫面](../media/dlp-remove-guest-access-sensitive-files.png)

12. 按一下 **[儲存]**，然後按 **[下一步]**。
13. 選擇您的測試選項，然後按一下 **[下一步]**。
14. 按一下 [提交 **]**，然後按一下 [完成 **]**。

請注意，如果來賓是網站或小組整體的成員，則此原則不會移除存取。 如果您計劃讓具有來賓成員的網站或團隊擁有高敏感度文件，請考慮[在 Teams 中使用私人頻道](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)，且只允許組織中的成員使用私人頻道。

## <a name="additional-options"></a>其他選項

Microsoft 365 和 Azure Active Directory 中有一些其他選項可以協助保護您的來賓共用環境。

- 您可以建立允許或拒絕共用網域的清單，以限制要共用的使用者。 如需詳細資訊，請參閱[依網域限制 SharePoint 和 OneDrive 內容的共用](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)和[允許或封鎖對特定組織的 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。
- 您可以限制使用者可以連線到哪些其他 Azure Active Directory 租用戶。 如需詳細資訊，請參閱[使用租用戶限制管理 SaaS 雲端應用程式的存取](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)。
- 您可以建立受管理環境，讓合作夥伴能夠協助管理來賓帳戶。 如需詳細資訊，請參閱[建立 B2B 外部網路](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)。

## <a name="see-also"></a>另請參閱

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[使用受管理來賓建立 B2B 外部網路](b2b-extranet.md)
