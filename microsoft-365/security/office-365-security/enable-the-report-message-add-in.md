---
title: 啟用報告訊息增益集
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何為個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的 [報告訊息] 增益集。
ms.openlocfilehash: bb01d7d2bf4992e6d0e7ed2a01ef0a689e25fc22
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112237"
---
# <a name="enable-the-report-message-add-in"></a>啟用報告訊息增益集

> [!NOTE]
> Outlook 和 Outlook 網頁版的 [報告訊息] 增益集與 [Outlook 垃圾郵件篩選工具](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)並不完全相同，但兩者皆可用來將電子郵件標示為垃圾郵件、非垃圾郵件或網路釣魚。 差異在於 Outlook 和 Outlook 網頁版的 [報告訊息] 增益集會通知 Microsoft 有關分類錯誤的電子郵件，而 Outlook 垃圾郵件篩選工具則用來組織使用者信箱中的電子郵件。

## <a name="overview"></a>概觀

Outlook 和 Outlook 網頁版的 [報告訊息] 增益集可讓人員輕鬆地向 Microsoft 及其子公司報告分類錯誤的電子郵件 (無論安全或惡意)，以便進行分析。 Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。 此外，如果貴組織使用 [Office 365 進階威脅防護方案 1](office-365-atp.md) 或[方案 2](office-365-ti.md)，則 [報告訊息] 增益集會向貴組織的安全性小組提供實用資訊，以便用於檢閱及更新安全性原則。

例如，假設使用者將大量訊息回報為網路釣魚。 此資訊會顯示在[安全性儀表板](security-dashboard.md)及其他報告中。 貴組織的安全性小組可以使用此資訊來表示可能需要更新防網路釣魚原則。 或者，如果有人使用 [報告訊息] 增益集，回報大量被標示為垃圾郵件的訊息，則貴組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。

[報告訊息] 增益集適用於您的 Office 365 訂用帳戶和下列產品：
 - Outlook 網頁版
 - Outlook 2013 SP1
 - Outlook 2016
 - Mac 版 Outlook 2016
 - Office 365 專業增強版隨附的 Outlook

您現有的網頁瀏覽器應足以讓 [報告訊息] 增益集運作。不過，如果您發現增益集無法使用或無法如預期般運作，請嘗試使用不同的瀏覽器。

如果您是個人使用者，您可以[自行啟用 [報告訊息] 增益集](#get-the-report-message-add-in-for-yourself)。

如果您是 Office 365 全域系統管理員或 Exchange Online 系統管理員，且 Exchange 已設定為使用 OAuth 驗證，您可以[為貴組織啟用 [報告訊息] 增益集](#get-and-enable-the-report-message-add-in-for-your-organization)。 [報告訊息] 增益集現可透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)提供。

## <a name="get-the-report-message-add-in-for-yourself"></a>自行取得報告訊息增益集

1. 在 [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps) 中，搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。

2. 選擇 [立即取得]****。

   ![報告訊息 - 立即取得](../media/ReportMessageGETITNOW.png)

3. 檢閱使用條款和隱私權原則。 然後選擇 [繼續]****。

4. 使用您的公司或學校帳戶 (商務用途) 或您的 Microsoft 帳戶 (個人用途) 登入 Office 365。

安裝並啟用增益集之後，您會看到下列圖示：

- 在 Outlook 中，圖示如下所示：

  ![Outlook 的報告訊息增益集圖示](../media/OutlookReportMessageIcon.png)

- 在 Outlook 網頁版 (先前為 Outlook Web 應用程式) 中，圖示如下所示：

  ![Outlook 的網頁報告訊息增益集圖示](../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> 在下一個步驟中，了解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>為貴組織取得和啟用報告訊息增益集

> [!IMPORTANT]
> 您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員才能完成此工作。 此外，Exchange 必須設定為使用 OAuth 驗證。若要深入了解，請參閱 [Exchange 需求 (增益集的集中式部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。

1. 移至 Microsoft 365 系統管理中心的[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 選擇 [+ 部署增益集]****。

   ![選擇部署增益集](../media/ServicesAddIns-ChooseDeployAddIn.png)

3. 在 [新增增益集]**** 畫面中，檢閱資訊，然後選擇 [下一步]****。

   ![新增增益集詳細資料](../media/NewAddInScreen1.png)

4. 選取 [我想要從 Office 市集新增增益集]****，然後選擇 [下一步]****。

   ![我想要新增增益集](../media/NewAddInScreen2.png)

5. 搜尋 [報告訊息]****，然後在結果清單中，選擇 [報告訊息增益集]**** 旁邊的 [新增]****。

   ![搜尋 [報告訊息]，然後選擇 [新增]](../media/NewAddInScreen3.png)

6. 在 [報告訊息]**** 畫面上，檢閱資訊，然後選擇 [下一步]****。

   ![報告訊息詳細資料](../media/ReportMessageAdd-InNewScreen4.png)

7. 指定 Outlook 的使用者預設設定，然後 選擇 [下一步]****。

   ![Outlook 的 [報告訊息] 預設設定](../media/ReportMessageOptionsScreen5.png)

8. 指定誰可取得 [報告訊息] 增益集，然後選擇 [儲存]****。

   ![誰可取得 [報告訊息] 增益集](../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> 我們建議[設定規則，以取得由使用者所報告的電子郵件複本](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。

視您在設定增益集時 (上面步驟 7-8) 所選取的內容而定，貴組織中的人員將擁有[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。 貴組織中的人員會看到下列圖示：

- 在 Outlook 中，圖示如下所示：

  ![Outlook 的報告訊息增益集圖示](../media/OutlookReportMessageIcon.png)

- 在 Outlook 網頁版中，圖示如下所示：

  ![Outlook 的網頁報告訊息增益集圖示](../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> 當您通知使用者關於 [報告訊息] 增益集時，請包含[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>設定規則，以取得由您的使用者所報告的電子郵件複本

> [!IMPORTANT]
> 您必須是 Exchange Online 系統管理員才能執行此工作。

您可以設定規則，以取得貴組織中的使用者所報告的電子郵件複本。 為貴組織下載並啟用 [報告訊息] 增益集之後，您就會這麼做。

1. 在 Exchange 系統管理中心，選擇 [郵件流程]**** \> [規則]****。

2. 選擇 **+** \> [建立新的規則]****。

3. 在 [名稱]**** 方塊中，鍵入名稱，例如 [提交]。

4. 在 [如果出現下列情況，請套用這個規則]**** 清單中，請選擇 [收件者位址包含...]****。

5. 在 [指定字詞或片語]**** 畫面中，新增 `junk@office365.microsoft.com` 和 `phish@office365.microsoft.com`，然後選擇 [確定]****。

   ![針對此規則指定垃圾郵件和網路釣魚電子郵件地址](../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. 在 [執行下列動作...]**** 清單中，選擇 [將此郵件以密件副本傳送到…]****。

7. 新增全域系統管理員、安全性系統管理員和/或安全性讀者，他們應會收到人員向 Microsoft 回報告的每封電子郵件複本，然後選擇 [確定]****。

   ![新增全域或安全性系統管理員，以接收每個報告郵件的複本](../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. 選取 [以嚴重性等級稽核此規則]****，然後選擇 [中]****。

9. 在 [選擇此規則的模式]**** 底下，選擇 [強制執行]****。

   ![設定規則以取得每個報告的訊息複本](../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. 選擇 [儲存]****。

備妥此規則後，每當貴組織中的人員使用 [報告訊息] 增益集來報告電子郵件時，您的全域系統管理員、安全性系統管理員和/或安全性讀者將會收到該郵件的複本。 此資訊可讓您設定或調整原則，例如 [Office 365 ATP 安全連結](atp-safe-links.md)原則，或[反垃圾郵件](anti-spam-protection.md)設定。

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用報告訊息增益集

請參閱[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>檢閱或編輯報告訊息增益集的設定

您可以在[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上檢閱及編輯 [報告訊息] 增益集的預設設定。

> [!IMPORTANT]
> 您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員才能完成此工作。

1. 移至 Microsoft 365 系統管理中心的[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 尋找並選取報告訊息增益集。

   ![尋找並選取報告訊息增益集](../media/FindReportMessageAddIn.png)

3. 在 [報告訊息] 畫面上，檢閱及編輯您組織的相關設定。

   ![報告訊息增益集的設定](../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a>相關主題

[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[檢視安全性與合規性中心內的電子郵件安全性報告](view-email-security-reports.md)

[檢視 Office 365 進階威脅防護的報告](view-reports-for-atp.md)

[使用安全性與合規性中心的總管](threat-explorer.md)
