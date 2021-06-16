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
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930412"
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
| 從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。 | 在完成轉換至 Azure AD 後，組織會完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。 只有在客戶的任何應用程式都指向 Microsoft Cloud Deutschland 端點時，當 Azure AD (IdP) 時，才會執行此動作。 | 同盟驗證組織 | 
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

## <a name="custom-dns-updates"></a>自訂 DNS 更新
**適用于：**  所有客戶都管理自己的 DNS 區域

| 步驟 (s)  | 描述 | 影響 |
|:------|:-------|:-------|
| 更新 Office 365 服務端點的內部部署 DNS 服務。 | 客戶管理的 DNS 專案（指向 Microsoft Cloud Deutschland）必須更新，以指向 Office 365 泛型服務端點。 請參閱[Microsoft 365 系統管理中心的網域](https://admin.microsoft.com/Adminportal/Home#/Domains)，並在您的 DNS 設定中套用變更。 | 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

## <a name="third-party-services"></a>協力廠商服務
**適用于：** 使用協力廠商服務做為 Office 365 服務端點的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新合作夥伴和協力廠商的 Office 365 服務端點服務。 | <ul><li>指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。 範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。 </li><li>將所有利用 Graph API 的自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` 。 其他含有已變更端點的 APIs 也必須更新（如果利用）。 </li><li>變更所有非協力廠商企業應用程式，以重新導向全球端點。 </li></ul>| 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||