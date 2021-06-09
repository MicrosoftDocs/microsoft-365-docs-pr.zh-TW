---
title: 從 Microsoft Cloud Deutschland 進行遷移後的遷移後活動
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 microsoft cloud (德國移至 microsoft cloud Deutschland 後的後續活動：從 microsoft cloud) 到新德文 datacenter 區域中 Office 365 服務。
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899361"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移後的遷移後活動

下列各節會在從 microsoft 雲端 (德國 Deutschland) 到新德文 datacenter 區域中的 Office 365 服務後，提供多項服務的遷移後活動。

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD 同盟驗證與 AD FS
**適用于：** 所有使用同盟驗證與 AD FS 的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。 | 在完成轉換至 Azure AD 後，組織會完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。 只有在客戶的任何應用程式都指向 Microsoft Cloud Deutschland 端點時，當 Azure AD (IdP) 時，才會執行此動作。 | 同盟驗證組織 | 無。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>群組核准
**適用于：** 在遷移前30天內，未核准 Azure AD 群組核准要求的使用者 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 在過去30天內加入 Azure AD 群組的要求若未獲核准原始要求，將需要重新要求遷移。 | 若使用者在遷移前的30天內未獲核准，使用者的客戶將需要使用「存取面板」提交要求，以加入 Azure AD 群組。 |  最終使用者： <ol><li>流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>尋找在遷移前30天內，成員核准已擱置的 Azure AD 群組。</li><li>要求重新加入 Azure AD 群組。</li></ol> 在遷移後，若要求加入超過30天的群組，將無法進行核准。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>自訂 DNS 更新
**適用于：**  所有客戶都管理自己的 DNS 區域

| 步驟 (s)  | 描述 | 影響 |
|:------|:-------|:-------|
| 更新 Office 365 服務端點的內部部署 DNS 服務。 | 客戶管理的 DNS 專案（指向 Microsoft Cloud Deutschland）必須更新，以指向 Office 365 泛型服務端點。 | 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

## <a name="third-party-services"></a>協力廠商服務
**適用于：** 使用協力廠商服務做為 Office 365 服務端點的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新合作夥伴和協力廠商的 Office 365 服務端點服務。 | <ul><li>指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。 範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。 </li><li>將所有利用 Graph API 的自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` 。 其他含有已變更端點的 APIs 也必須更新（如果利用）。 </li><li>變更所有非協力廠商企業應用程式，以重新導向全球端點。 </li></ul>| 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**適用于**：使用 SharePoint 2013 工作流程的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 重新發佈 SharePoint 2013 工作流程。 | 在遷移前的工作中，我們減少了 SharePoint 2013 工作流程的數目。 現在已完成遷移，客戶便可重新發佈工作流程。 | 這是必要的動作。 若失敗，可能會造成使用者混淆和問訊台通話。 |
| 透過 Outlook 共用專案 | 在租使用者切換後，透過 Outlook 中的 SharePoint 線上及商務用 OneDrive 中共用專案已無法再運作。 |<ul><li>在 SharePoint 線上及商務用 OneDrive 中，您可以透過 Outlook 共用專案。 按 Outlook 按鈕之後，會建立可共用的連結，並將其推入 Outlook Web App 中的新郵件。</li><li>租使用者轉換後，這種共用方法將無法運作。 我們承認這是已知的問題。 不過，由於此 Outlook 功能位於棄用的路徑中，因此在完成棄用之前，不會規劃修正問題。 </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**適用于**：使用混合式 Exchange 設定的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 根據 Office 365 服務，重新執行混合式設定向導 (HCW) 。 | 現有的 HCW 設定是為了支援 Microsoft Cloud Deutschland。 在 Exchange 服務的遷移完成時，我們會將內部部署設定從 Microsoft Cloud Deutschland 中分離出來。 |<ul><li>必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 在開始 Exchange 信箱遷移 (有5天以上的通知) ，請通知用戶端他們應該停止並刪除其信箱的任何上架或脫離移動。  如果不是，他們會在移動要求中看到錯誤。 </li><li>Exchange 信箱遷移完成後，請通知用戶端他們可以繼續上架和脫離移動。 <br> 在從 Microsoft Cloud Deutschland Exchange 到 Office 365 服務時，執行 **MigrationServerAvailabiilty 指令程式** 的 PowerShell Cmdlet 可能無法運作。 不過，遷移完成後，它會正常運作。 </li><li>如果在遷移信箱之後，用戶端遇到認證或授權問題，使用者可以執行 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ，或是使用 Exchange 控制台 (ECP) ，在遷移端點中重新輸入其內部部署系統管理員認證。 </li></ul>|
