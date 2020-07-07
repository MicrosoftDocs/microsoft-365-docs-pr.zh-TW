---
title: 透過 Microsoft 雲端服務合規性管理員來滿足資料的保護和法規要求
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 429e686f-d8a6-455e-a2b6-3791d763f000
description: 瞭解如何使用 Microsoft 服務信任入口網站中的合規性管理員，以符合資料保護和法規需求。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aedadc682bd45f363f1e97599383dd901c3eae7f
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016254"
---
# <a name="microsoft-compliance-manager-classic"></a>Microsoft 合規性管理員 (傳統)

> [!NOTE]
> 本文件說明此產品之前的版本。 我們*不鼓勵使用者使用此版本的合規性管理員*。 **如果您使用的是合規性管理員目前的預覽版本，請參閱[合規性管理員 (預覽) 文件](working-with-compliance-manager.md)。**

 合規性管理員無法使用 21Vianet 運作的 Office 365、Office 365 德國、Office 365 U.S. Government Community High (GCC High)，或 Office 365 美國國防部。**
  
合規性管理員是 Microsoft [服務信任入口網站](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal)中以工作流程為基礎的風險評估工具，可讓您追蹤、指派及驗證貴組織與 Microsoft 專業服務和 Microsoft 雲端服務相關的法規遵循活動，例如 Microsoft Office 365、Microsoft Dynamics 365，以及 Microsoft Azure。 

合規性管理員：
  
- 將針對各種標準的 Microsoft 雲端服務進行的各種協力廠商稽核中，Microsoft 提供給稽核員及管理者的詳細資訊 (例如 ISO 27001、ISO 27018 和 NIST)，以及 Microsoft 在內部編譯以遵循法規的資訊 (例如 HIPAA 和歐盟一般資料保護規範或稱 GDPR)，結合貴組織遵循這些標準和法規的自我評估。
    
- 可讓您指派、追蹤及記錄合規性與評估相關的活動，從而協助貴組織跨小組障礙，達成貴組織的合規性目標。
    
- 提供「合規性分數」來協助您追蹤進度，並排定稽核控制項的優先順序，可協助減少貴組織的風險。
    
- 提供安全存放庫，讓您可上傳並管理辨識項，以及與您合規性活動相關的其他成品。
    
- 在 Microsoft Excel 中產生豐富詳細的報告，以記錄由 Microsoft 與貴組織執行的合規性活動，可提供給稽核員、管理者，以及其他法規遵循專案關係人。

如需合規性管理員的簡短示範，請參閱這個[合規性管理員](https://www.youtube.com/watch?v=r1vs8NdSXKQ)影片。

    
> [!IMPORTANT]
> Compliance Manager is a dashboard that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance. The Customer Actions provided in Compliance Manager are recommendations; it is up to each organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation. Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.

    
## <a name="what-is-compliance-manager"></a>合規性管理員為何？

Compliance Manager is a workflow-based risk assessment tool designed to help you manage regulatory compliance within the shared responsibility model of the cloud. Compliance Manager provides you with a dashboard view of standards and regulations and assessments that contain Microsoft's control implementation details and test results and customer control implementation guidance and tracking for your organization to enter. Compliance Manager provides certification assessment control definitions, guidance on implementation and testing of controls, risk-weighted scoring of controls, role-based access management, and an in-place control action assignment workflow to track control implementation, testing status and evidence management. Compliance Manager optimizes compliance workload by enabling customers to logically group assessments together and apply assessment control testing to identical or related controls, reducing the duplication of effort that might otherwise be required to satisfy identical control requirements across different certifications.

## <a name="assessments-in-compliance-manager"></a>合規性管理員中的評估

The core component of Compliance Manager is called an *Assessment*. An Assessment is an assessment of a Microsoft service against a certification standard or data protection regulation (such as ISO 27001:2013, and the GDPR). Assessments help you to discern your organization's data protection and compliance posture against the selected industry standard for the selected Microsoft cloud service. Assessments are completed by the implementation of the controls that map to the certification standard being assessed. 
  
「評估」的結構取決於責任，會在 Microsoft 與貴組織之間共用，以評估雲端中的安全性與合規性風險，並實作合規性標準、資料保護標準、規定或法律所指定的資料保護。
  
「評估」是由多個元件所組成，也就是：
  
- **範圍內的服務** - 每個評估適用於一組特定的 Microsoft 服務，會列在「範圍內的雲端服務」一節中。 
    
- **Microsoft-Managed Controls** - For each cloud service, Microsoft implements and manages a set of  *controls*  as part of Microsoft's compliance with various standards and regulations. These controls are organized into  *control families*  that align with the structure from the corresponding certification or regulation that the Assessment is aligned to. For each Microsoft-managed control, Compliance Manager provides details about how Microsoft implemented the control, along with how and when that implementation was tested and validated by an independent third-party auditor. 
    
    以下是 Office 365 的「評估」和 GDPR 中「安全性」**** 控制項系列中，三種 Microsoft 管理控制項的範例。 

    ![「合規性管理員」中 Microsoft 管理控制項的詳細資料](../media/d1351212-1ebf-424e-91b8-930c2b2edef1.png)
  
  a. Specifies the following information from the certification or regulation that maps to the Microsoft-managed control.

  - **控制識別碼** - 控制項所對應認證或規定中的小節或文章號碼。
    
  - **標題** - 所對應憑證或規定的標題。
    
  - **文章識別碼** - 僅 GDPR 評估包含此欄位，因為它會指定對應的 GDPR 文章編號。
    
  - **描述** - 標準或法規的文字，對應至所選的 Microsoft 管理控制項。

  b. The Compliance Score for the control, which indicates the level of risk (due to non-compliance or control failure) associated with each Microsoft-managed control. See [Understanding the Compliance Score](#understanding-the-compliance-score) for more information. Note that Compliance Scores are rated from 1 to 10 and are color-coded. Yellow indicates low risk controls, orange indicates medium-risk controls, and red indicated high-risk controls. 
    
  c. Information about the implementation status of a control, the date the control was tested, who performed the test, and the test result.
    
  d. For each control, you can click **More** to see additional information, including details about Microsoft's implementation of the control and details about how the control was tested and validated by an independent third-party auditor. 
    
- **Customer-Managed Controls** - This is the collection of controls that are managed by your organization. Your organization is responsible for implementing these controls as part of your compliance process for a given standard or regulation. Customer-managed controls are also organized into control families for the corresponding certification or regulation. Use the customer-managed controls to implement the recommended actions suggested by Microsoft as part of your compliance activities. Your organization can use the prescriptive guidance and recommended Customer Actions in each customer-managed control to manage the implementation and assessment process for that control.
    
    Customer-managed controls in Assessments also have built-in workflow management functionality that you can use to manage and track your organization's progress towards completing the Assessment. For example, a Compliance Officer in your organization can assign an Action Item to an IT admin who has the responsibility and necessary permissions to perform the actions that are recommended for the control. When that work is complete, the IT admin can upload evidence of their implementation tasks (for example, screenshots of configuration or policy settings) and then assign the Action Item back to the Compliance Officer to evaluate the collected evidence, test the implementation of the control, and record the implementation date and test results in Compliance Manager. For more information, see the [Managing the assessment process](#managing-the-assessment-process) section in the article. 
  
## <a name="permissions-and-role-based-access-control"></a>權限和角色型存取控制

合規性管理員使用以角色為基礎的存取控制權限模型。 只有獲指派使用者角色的使用者才能存取合規性管理員，而每位使用者所允許的動作會受角色類型限制。
  
請注意，已不再有預設的**來賓存取**角色。 每個使用者都必須獲指派角色，才能在合規性管理員中存取及作業。
  
The following table describes each Compliance Manager permission and what it allows the user do. The table also indicates the role that each permission is assigned to.
  
||**合規性管理員讀取者**|**合規性參與者**|**合規性管理員評估者**|**合規性管理員管理者**|**入口網站管理員**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**讀取資料** - 使用者可以讀取但無法編輯資料。  <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|
|**編輯資料** - 使用者可以編輯所有欄位，除了 [測試結果] 和 [測試日期] 欄位以外。  <br/> ||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**編輯測試結果** - 使用者可以編輯 [測試結果] 和 [測試日期] 欄位。  <br/> ||<br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**管理評估** - 使用者可以建立、封存和刪除「評估」。  <br/> |||<br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Manage users** - Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles. Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.  <br/> ||||<br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
## <a name="understanding-the-compliance-score"></a>了解合規性分數

在儀表板上，合規性管理員會在磚的右上角顯示 Office 365 評定的總分。 這是評定的整體總計合規性分數，而且在該評定中標示為已實作和測試的每個控制措施評定的累積得分。 新增評估時，您會看到合規性分數已接近完成，因為 Microsoft 已實作、且經獨立第三方測試的 Microsoft 管理控制項都已套用。
  
![合規性管理員儀表板 - 合規性總分](../media/756091aa-1afd-4aff-93ab-c6f6824f2add.png)
  
其餘的分數是來自成功的客戶控制項評估、來自實作及測試客戶管理控制項，每一項都有特定值，作為整體合規性分數。 
  
每個評定會顯示以風險為基礎的合規性分數，協助您評定與某個評定中的每個控制措施 (包括 Microsoft 管理和客戶管理的控制措施) 關聯的風險等級 (由於不符合合規性或控制措施失敗)。 每個客戶管理的控制措施都會獲派可能的得分數字 (稱為嚴重性排名)；以 1 到 10 進行評分，如果控制措施失敗，與較高風險因素關聯的控制措施會獲頒較多得分，而較低風險控制措施則會獲頒較少得分。 
  
例如，如下所示的使用者存取管理評估控制項具有非常高的嚴重性風險排名，因此會顯示 10 的指派值。
  
![合規性管理員 - 評估控制項高嚴重性 - 10 分](../media/174ecb2c-aaed-436e-9950-74da7dadf5db.png)
  
 相較之下，如下所示的資訊備份評估控制項具有較低的嚴重性風險排名，因此會顯示 3 的指派值。 
  
![合規性管理員 - 評估控制項低嚴重性 - 3 分](../media/11749f20-5f22-40c2-bbc1-eaccbf29e2ae.png)
  
The Compliance Manager assigns a default severity ranking to each control. Risk rankings are calculated based on the following criteria:
  
- 控制項是否避免事件發生 (最高排名) 會偵測所發生的事件，或修正事件的影響 (最低排名)。 針對嚴重性排名，可防止威脅且為強制性的控制措施會獲派最高的得分數字；偵測型或矯正型的控制措施 (不論它們是強制性還是選擇性) 會獲派最低的得分數字。
    
- 控制項 (經實作之後) 是必要的，因此使用者無法繞徑 (例如，使用者必須重設使用者密碼，並符合密碼長度和字元要求)，或是選擇性的，而使用者可以繞徑 (例如，要求使用者在他們的電腦自動安裝時鎖定螢幕畫面的商務規則)。
    
- Controls related to risks to data confidentiality, integrity, and availability, whether these risks come from internal or external threats, and whether the threat is malicious or accidental. For example, controls that would help prevent an external attacker from breaching that network and gaining access to personally identifiable information would be assigned more points than a control related to preventing an employee from accidentally mis-configuring a network router setting that results in a network outage).
    
- 每個控制項與法律和外部驅動程式相關的風險，例如合約、法規和公用承諾。
    
The displayed Compliance Score values for the control are applied  *in their entirety*  to the Total Compliance Score on a pass/fail basis--either the control is implemented and passes the subsequent assessment test or it does not; there is no partial credit for a partial implementation. Only when the control has its **Implementation Status** set to **Implemented** or **Alternative Implementation** and the **Test Result** is set to **Passed** are the assigned points added to the Total Compliance Score. 
  
最重要的是，合規性分數能指出倘若發生與某個控制措施相關的失敗，哪些控制措施有較高的潛在風險，藉此協助您排定優先順序，決定要專注於實作哪些控制措施。 除了以風險為基礎的優先順序以外，在評定控制措施與其他控制措施相關時 (無論是在相同的評定中，或是在位於相同評定群組內的另一個評定中)，如果成功完成單一控制措施，可能就會根據控制措施測試結果的同步處理情形大幅減少工作。
  
例如，在下圖中，我們看到 Office 365 - GDPR 評估目前已評估 46%，111 個控制項評估中，有 51 個已完成，合規性總分為 289 分 (滿分 600)。
  
![合規性管理員 - 評估摘要](../media/595eedae-e3e0-4d1f-8cf5-7c1c9f4fd1e8.png)
  
在評定中，GDPR 控制措施 7.5.5 與其他 5 個控制措施 (7.4.1、7.4.3、7.4.4、7.4.8 和 7.4.9) 有關，每個各有中等到高嚴重性風險評分 6 或 8)。 我們使用評定篩選選取了所有這些控制措施，讓它們能夠在評定檢視中顯示，而且我們可以在下方看見它們之中沒有任何一個已經評定。 
  
![合規性管理員 - 評估檢視 - 篩選控制項，全都未評估](../media/b2ae7120-2d7a-4247-b0a9-f5f65433395f.jpg) As those 6 controls are related, the completion of any one them will result in a synchronization of those test results across the related controls within this assessment (just as it will for any related controls in an assessment that is in the same assessment grouping). Upon completion of the implementation and testing of GDPR control 7.5.5, the control detail area refreshes to show that all 6 controls have been assessed, with a corresponding increase in the number of assessed controls to 57 and 51% assessed, and a change in total Compliance Score of +40. 
  
![合規性管理員評估檢視 - 已同步處理控制結果](../media/e9da2b30-053a-4d40-ace9-ae1b39cdaf66.jpg)
  
如果您要使用會影響其他相關控制項的方式來變更相關控制項的 [實作狀態]，將會顯示此確認更新對話方塊。
  
![合規性管理員評估 - 相關的控制項更新確認對話方塊](../media/8be25bd2-1aee-455f-8aa4-10b1184ca4c3.png)
  
> [!NOTE]
> Currently, only Assessments for Office 365 cloud services include a Compliance Score. Assessments for Azure and Dynamics show an assessment status. 

## <a name="compliance-score-methodology"></a>合規性分數方法

合規性分數 (如 Microsoft 安全分數) 類似於其他行為式評分系統；貴組織的活動會增加其合規性分數，方法為執行與資料保護、隱私權和安全性相關的活動。
  
> [!NOTE]
> The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way. 
  
Assessments in Compliance Manager are based on the shared responsibility model for cloud computing. In the shared responsibility model, Microsoft and each customer share responsibility for the protection of the customer's data when that data is stored in our cloud.
  
如下列的 Office 365 GDPR 評定所示，Microsoft 和客戶都各自負有責任，需執行各種專為滿足標準或法規的合規性評定而設計的動作。 為了合理化並了解各種標準和規定所需的動作， 合規性管理員會將所有標準和規定當成控制項架構。 因此，對 Microsoft 和客戶所執行的動作的合規性評定，包含各種控制措施的實作與驗證。
  
![合規性管理員 - GDPR 摘要](../media/123f8126-85b8-4baa-9c4e-c6295cf4a5ca.png)
  
以下是執行一般動作的基本工作流程：
  
1. The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns the task to someone in the organization to implement a control. That person could be:

    - 企業原則擁有者
    
    - IT 實施者
    
    - 組織中負責執行工作的另一個人員
    
2. That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the control(s) tied to the Action as implemented. Once these tasks are completed, they assign the Action to an Assessor for validation. Assessors can be:
    
    - 在組織中執行控制項驗證的內部評估者
    
    - 檢查、驗證及證實合規性的外部評估者，例如稽核 Microsoft 雲端服務的協力廠商獨立組織
    
3. 評估者會驗證控制項及檢查辨識項，並將控制項標記為已評估，以及評估的結果 (例如，跳過)。
    
一旦評估過所有與「評估」相關聯的控制項後，評估就會視為完成。
  
Every Assessment in Compliance Manager comes pre-loaded with information that provides details about the Actions taken by Microsoft to satisfy the requirements of the controls for which Microsoft is responsible. This information includes details about how Microsoft has implemented each control and how and when Microsoft's implementation was assessed and verified by a third-party auditor. For this reason, the Microsoft Managed Controls for each Assessment are marked as Assessed, and the Compliance Score for the Assessment reflects this.
  
Each Assessment includes a total Compliance Score based on the shared responsibility model. Microsoft's implementation and testing of controls for Office 365 contributes a portion of the total possible points associated with a GDPR assessment. As the customer implements and tests each of the customer Actions, the Compliance Score for the Assessment will increase by the value assigned to the control. 
  
 ### <a name="risk-based-scoring-methodology"></a>風險計分方法
  
Compliance Manager uses a risk-based scoring methodology with a scale from 1-10 that assigns a higher value to controls that represent a higher risk in the event the control fails or is non-compliant. The scoring system used by Compliance Score is based on several key factors, such as:
  
- 控制項的本質
    
- 根據威脅類型的控制項風險層級
    
- 控制項的外部驅動程式
    
![合規性管理員 - 合規性分數方法](../media/e48764c4-828e-44b0-8636-fb3c352f2bac.png)
  
 ### <a name="essence-of-the-control"></a>控制項的本質
  
控制項的本質取決於控制項是強制或是選擇性的，以及是否為預防性、偵測性還是修正性的。
  
 ### <a name="mandatory-or-discretionary"></a>必要或選擇性
  
 *Mandatory controls*  are controls that cannot be bypassed either intentionally or accidentally. An example of a common mandatory control is a centrally-managed password policy that sets requirements for password length, complexity, and expiration. Users must comply with these requirements in order to access the system. 
  
 *Discretionary controls*  rely upon users to understand policy and act accordingly. For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user. 
  
 ### <a name="preventative-detective-or-corrective"></a>預防性、偵測性或修正性
  
 *Preventative controls*  are those that prevent specific risks. For example, protecting information at rest using encryption is a preventative control against attacks, breaches, etc. Separation of duties is a preventative control to manage conflict of interest and to guard against fraud. 
  
 *Detective controls*  are those that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred. System access auditing and privileged administrative actions auditing are types of detective monitoring controls; regulatory compliance audits are a type of detective control used to find process issues. 
  
 *Corrective controls*  are those that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible. Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach. 
  
我們使用這些因素評估每一個控制項，可決定控制項的本質，並將相對於其所代表之風險的值指派給它。
  
 **威脅**
  
|<br>|<br>|<br>|
|:-----|:-----|:-----|
||**強制性** <br/> |**選擇性** <br/> |
|**預防性** <br/> |高風險  <br/> |中度風險  <br/> |
|**偵測性** <br/> |中度風險  <br/> |低風險  <br/> |
|**修正性** <br/> |中度風險  <br/> |低風險  <br/> |
   
威脅是指會對基本且廣泛接受的安全性標準造成風險的任何項目，稱為資料的 CIA 三角理論：機密性、完整性和可用性：
  
- 機密性表示資訊只能由信任的授權對象閱讀及了解。
    
- 完整性表示資訊尚未由未授權的使用者修改或損毀。
    
- 可用性表示資訊隨時可供存取，並具有高品質的服務。
    
A failure of any of these characteristics is considered a compromise of the system as a whole. Threats can come from both internal and external sources, and an actor's intent can be accidental or malicious. These factors are estimated in a threat matrix that assigns threat levels of either High, Moderate, or Low to each combination of scenarios.

|<br>|**內部**<br/>|<br>|**外部**<br/>|<br>|<br>|<br>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||*惡意*<br/>|*意外*<br/>|*惡意*<br/>|*意外*<br/>|||
|**具機密性**<br/>|(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)|
|**完整性**<br/>|(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)|
|**可用性**<br/>|(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)|
   
 **外部驅動程式**
  
|**合約**|**法規**|**公開承諾**|
|:-----|:-----|:-----|
|(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |(H、M 或 L)  <br/> |
   
相關法規、合約和公開承諾等外部因素可能會影響設計用來保護資料，並避免資料入侵的控制項，這些因素每一個都會指派高、中或低的風險值。
  
在 CIA/威脅和法律/外部驅動程式代表的 15 個可能風險案例中這些高、中或低的風險值預估出現次數會加以結合來提供風險加權，將指定數值的風險出現次數和可能性視為重要的，並在計算控制項的嚴重性等級時納入考量。
  
根據控制項的嚴重性等級，控制項會被指派數字 1 (最低) 到 10 (最高) 之間的合規性分數，分成下列的風險類別：
  
|**風險層級**|**控制項的值**|
|:-----|:-----|
|低  <br/> |1-3  <br/> |
|仲裁  <br/> |6  <br/> |
|高  <br/> |8  <br/> |
|嚴重  <br/> |10  <br/> |
   
藉由透過最高合規性分數值來排列評估控制項的優先順序，組織將會集中於最高風險的項目，及接收比例較高的正面意見反應，針對每個已完成的控制項評估將更多分數新增至合規性分數總分。
  
### <a name="summary-of-scoring-methodology"></a>計分方法摘要
  
The Compliance Score is a core component of the way that Compliance Manager helps organizations understand and manage their compliance. The Compliance Score for an assessment is an expression of the company's compliance with a given standard or regulation as a number, where the higher the score (up to the maximum number of points allocated for the Assessment), the better the company's compliance posture. Understanding the compliance scoring methodology in which assessment controls are assigned risk severity values between 1- 10 (low to high), and how completed control assessments add to the total compliance score is crucial to organizations for prioritizing their actions.

## <a name="grouping-assessments"></a>群組評估

當您建立新評定時，系統會提示您建立群組以將評定指派到該群組，或是將評定指派到現有群組。 群組可讓您按照邏輯整理評定，並在有相同或相關的客戶管理控制措施之間共用通用資訊和工作流程工作。
  
For example, you could group Assessments by year or teams, departments, or agencies within your organization or group them by year. Here are some examples of groups and the Assessments they might contain.
  
- GDPR 評估 - 2018
    
  - Office 365 + GDPR
    
  - Azure + GDPR
    
  - Dynamics + GDPR
    
- Azure 評估 - 2018
    
  - Azure + GDPR
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
- 資料安全性與隱私權評估
    
  - Office 365 + ISO 27001:2013
    
  - Office 365 + ISO 27018:2014
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
> [!TIP]
> 建議您判斷貴組織的群組策略，然後再新增新的評估。 
  
以下是幾種群組評估的需求：
  
- 群組名稱 (也稱為 *群組 ID) 在貴組織中必須是唯一的。 
    
- Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair. For example, a group can't contain two Assessments for Office 365 and GDPR. Similarly, a group can contain multiple Assessments for the same cloud service as long as the corresponding certification/regulation for each one is different.
    
將評定新增到評定群組後，就無法變更該群組。 您可以重新命名評定群組，這會變更與該群組關聯的所有評定的評定群組名稱。 您可以建立評定和新評定群組，並且從現有評定複製資訊，這會在不同的評定群組中有效地建立該評定的重複項目。 封存評定會中斷該評定與評定群組之間的關係。 其他相關評定的任何進一步更新不會再反映於已封存評定中。
  
如先前所述，使用群組的一個重要優勢在於，當相同群組中的兩個不同評定共用相同的客戶管理控制措施 (每個控制措施的客戶動作因而相同)，則一個評定中的控制措施的實作詳細資料、測試資訊和狀態完成度，會同步處理到群組中任何其他評定的相同控制措施。 換句話說，如果評定共用相同的控制措施且這些評定位於相同的群組，您只須管理一個評定中的控制措施的評定程序。 該控制項的結果就會自動同步到其他評定。 例如，ISO 27001 和 ISO 27018 都包含與密碼原則相關的控制項。 如果控制項的測試狀態在一個評定中已設為 [通過]，只要兩個評定都屬於相同評定群組，則控制項在其他評定中會更新 (並標示為 [通過])。
  
作為範例，請考慮這兩個相關評定控制項，各自都與公用網路上的資料加密有關：Office 365 - GDPR 評定中的控制項 6.10.1.2，和 Office 365 - NIST 800-53 評定中的控制項 SC-13。 這些是兩個不同評定 (皆在預設群組內) 中的相關評定控制措施。 一開始，這兩個評定都未完成任何客戶控制措施評定 (如顯示這兩個評定的合規性管理員儀表板中所示)。
  
![合規性管理員儀表板 - 群組的評定 - 之前](../media/dc0126a3-415c-4fbe-a020-1806dd1caebd.png)
  
按一下 [Office 365 - GDPR]**** 評定，並使用篩選控制項，可檢視 GDPR 控制項 6.10.1.2，我們會看到 NIST 800-53 控制項 SC 13 列為相關的控制項。
  
![合規性管理員評定 - 共用控制項](../media/aafb106e-0abc-4918-8038-de11cf326dfe.png)
  
 我們在這裡顯示實作完成和測試 GDPR 控制項 6.10.1.2。 
  
![合規性管理員評定控制項 GDPR 6.10.1.2 - 通過](../media/ee9e83b6-9d51-4b3b-85eb-96bec0fef2e1.png)
  
瀏覽至群組評估中相關的控制項，我們可以看到 NIST 800-53 SC-13 也已使用相同的日期與時間標示為已完成，而無需其他實作或測試工作。
  
![合規性管理員評定 - NIST 800-53 SC(13) 已完成](../media/b5933592-db5a-4fdd-9be2-bba777646a88.png)
  
回到儀表板中，我們可以看到每個評定有 1 個控制項評定已完成，且每個評定的合規性總分增加了 8 (該共用控制項的合規性分數值)。
  
![合規性管理員儀表板 - 群組的評定程序同步處理](../media/727f1203-b98d-4a03-a7af-e9236f4c5534.png)

## <a name="administrative-functions"></a>系統管理功能

有特定的系統管理功能，僅提供給租用戶系統管理員帳戶，且僅當以全域系統管理員身分登入時才會顯示。
  
> [!NOTE]
> The Access to Restricted Documents permission in the drop-down list will allow administrators to give users access to restricted documents that Microsoft shares on the Service Trust Portal. The Restricted Documents feature isn't available, but is coming soon. 
  
### <a name="assigning-compliance-manager-roles-to-users"></a>將合規性管理員角色指派給使用者

Each Compliance Manager role has slightly different permissions. You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal by selecting the **Admin** menu item, and then choosing **Settings**. 
  
![STP 系統功能表 - 選取的設定](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
若要新增使用者或從合規性管理員角色中移除使用者。
  
1. 請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。
    
2. 使用您的 Azure Active Directory 全域系統管理員帳戶登入。
    
3. 在服務信任入口網站頂端的功能表列上，按一下 [系統管理員]****，然後選擇 [設定]****。 
    
4. 在 [選取角色]**** 下拉式清單中，按一下您想要管理的角色。 
    
5. 新增至每個角色的使用者會列在 [選取角色]**** 頁面上。 
    
6. To add users to this role, click **Add**. In the **Add Users** dialog, click the user field. You can scroll through the list of available users or begin typing the user name to filter the list based on your search term. Click the user to add that account to the **Add Users** list to be provisioned with that role. If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then click the user to add to the list. Click **Save** to provision the selected role to these users. 
    
    ![合規性管理員 - 佈建角色 - 新增使用者](../media/2f386f82-2bf8-4e95-ab41-1724b752b508.png)
  
7. 若要從此角色移除使用者，請選取使用者並按一下 [刪除]****。 
    
    ![合規性管理員 - 佈建角色 - 移除使用者](../media/17004def-604f-471d-a54d-f678fcc01c1e.png)
 
## <a name="user-privacy-settings"></a>使用者隱私權設定

Certain regulations require that an organization must be able to delete user history data. To enable this, Compliance Manager provides the **User Privacy Settings** functions, that allow administrators to: 
  
- [使用者搜尋](#search-for-a-user)

- [匯出帳戶資料歷程記錄的報告](#export-a-report-of-account-data-history)

- [重新指派動作項目](#reassign-action-items)

- [刪除使用者資料歷程記錄](#delete-user-data-history)
    
![合規性管理員管理 - 使用者隱私權設定功能](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
### <a name="search-for-a-user"></a>搜尋使用者

若要搜尋使用者帳戶：
  
1. 輸入使用者電子郵件地址的別名 (位在 @ 符號左邊的資訊)，然後按一下右邊的網域尾碼清單以選擇網域名稱。 如果這是個具有多個註冊網域的租用戶，請您仔細檢查電子郵件地址的網域名稱尾碼，以確保資訊正確。
    
2. 當您輸入正確的使用者名稱時，按一下 [搜尋]****。 
    
3. If the user account is not found, the error message 'User not found' will be displayed on the page. Check the user's email address information, make corrections as necessary and click **Search** to try again. 
    
4. 找到使用者帳戶時，按鈕的文字會從 [搜尋]**** 變更為 [清除]****，這表示傳回的使用者帳戶是額外功能的作業內容，將會顯示在下面，且執行這些功能將會套用到這個使用者帳戶。 
    
5. 若要清除搜尋結果，並搜尋不同的使用者，請按一下 [清除]****。 
    
### <a name="export-a-report-of-account-data-history"></a>匯出帳戶資料歷程記錄的報告

識別使用者帳戶之後，您可能會想要產生一份與此帳戶相關的相依性報告。 這個資訊可以讓您重新指派開放的動作項目，或是確保存取先前上傳的證明。 
  
 若要產生並匯出報告：
  
1. 按一下 [匯出]**** 以產生並下載目前指派給傳回之使用者帳戶的合規性管理員控制項動作項目報告，以及由該使用者上傳的文件清單。 如果沒有指派的動作或上傳的文件，會顯示「沒有此使用者的資料」的錯誤訊息。 
    
2. 報告會在作用中的瀏覽器視窗背景中下載 - 如果您沒有看到下載快顯功能表，可能需要檢查您的瀏覽器下載記錄。
    
3. 開啟文件以檢視報告資料。
    
> [!NOTE]
> This is not a historical report that retains and displays state changes to action item assignment history. The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report). For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user. 
  
### <a name="reassign-action-items"></a>重新指派動作項目

This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below. This action does not change document upload history for the returned user account. 
  
 若要將動作項目重新指派給其他使用者：
  
1. 按一下輸入方塊以瀏覽並選取所傳回使用者的動作項目應被指派的組織中的另一位使用者。
    
2. 選取 [取代]**** 以將所傳回使用者的所有控制項動作項目重新指派給新選取的使用者。 
    
3. 隨即顯示確認對話方塊，說明「這會把指派給目前使用者的所有控制項動作項目重新指派給選取的使用者。 這個動作無法復原。 您確定要繼續？」
    
4. 若要繼續，請按一下 [確定]****，否則請按一下 [取消]****。 
    
> [!NOTE]
> All action items (both active and completed) will be assigned to the newly selected user. However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user. 
  
Changing the document upload history to remove the previously assigned user will have to be done as a manual process. In that case, the administrator will need to:
  
1. 開啟先前已下載的 [匯出] 報告。
  
2. 找出並瀏覽至所需的控制項動作項目。
  
3. 按一下 [管理文件]**** 以瀏覽到該控制項的辨識項存放庫。 
  
4. 下載文件。
  
5. 刪除辨識存放庫中的文件。
  
6. Re-upload the document. The document will now have a new upload date, time and Uploaded By username. 
  
### <a name="delete-user-data-history"></a>刪除使用者資料歷程記錄

This sets control action items to 'unassigned' for all action items assigned to the returned user. This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user
  
 若要刪除使用者帳戶動作項目和文件上傳記錄：
  
1. 按一下 [刪除]****。 

    A confirmation dialog will be displayed, stating "This will remove all control action item assignments and the document upload history for the selected user. This action cannot be undone. Are you sure you want to continue?"
    
3. 若要繼續，請按一下 [確定]****，否則請按一下 [取消]****。 
  
## <a name="using-compliance-manager"></a>使用合規性管理員

合規性管理員會提供工具給您，可指派、追蹤及記錄合規性與評估相關的活動，從而協助貴組織跨小組障礙，達成貴組織的合規性目標。
  
![合規性管理員儀表板 - 頂端功能表 - 更新的系統管理功能表](../media/134d7577-cd70-4124-bcfd-d3feb248952b.png)

## <a name="accessing-compliance-manager"></a>存取合規性管理員

You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.
  
![合規性管理員 - 從 STP 功能表存取合規性管理員](../media/14be4cac-2380-49bc-9b36-210da8cafdfa.png)
  
1. 請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。
    
2. 使用您的 Azure Active Directory (Azure AD) 使用者帳戶登入。
    
3. 在服務信任入口網站中，按一下 [合規性管理員]****。 
    
4. When the Non-Disclosure Agreement is displayed, read it, and then click **Agree** to continue. You'll only have to do this once, and then the Compliance Manager dashboard is displayed. 

    為協助您快速上手，我們依預設新增了下列「評估」：
    
    ![合規性管理員中的預設「評估」](../media/8c59b45a-706a-4362-a7ba-2cb782931bf7.png)
    
5. 按一下![合規性管理員中的說明圖示](../media/c1b3092f-6ac7-43ab-b1c4-63a54598450c.png)[說明]****，以進行簡短的合規性管理員教學課程。 
  
## <a name="viewing-action-items"></a>檢視動作項目

合規性管理員提供您所有獲派的控制項評定動作項目的便利檢視，可讓您快速且輕鬆地執行相關動作。 您可以按一下與該評定關聯的索引標籤，以檢視所有動作項目或選取與特定認證對應的動作項目。 例如，在下列影像中，已選取 GDPR 索引標籤，顯示與 GDPR 評定有關的控制項。
  
![合規性管理員 - 動作項目清單列出多個 GDPR 已選取的索引標籤](../media/ba960f5c-becb-4d95-a000-d08ec77b7b46.png)
  
若要檢視您的動作項目：
  
1. 移至合規性管理員儀表板
    
2. 按一下 [動作項目]**** 連結，而頁面會重新整理以顯示已指派給您的動作項目。 
    
    By default, all action items are shown. If you have action items across multiple certifications, the names of the certifications will be listed in tabs across the top of the assessment control. To see the action items for a specific certification, click that tab.

## <a name="adding-an-assessment"></a>新增評估

若要將評估新增到合規性管理員：
  
1. 在合規性管理員儀表板中，按一下 [新增圖示]![](../media/ITPro-EAC-AddIcon.gif)[新增評估]****。 
    
2. In the **Add an Assessment** window, you can create a new group to add the Assessment to or you can add it to an existing group (the built-in group is named "Initial Group".) Depending on the option you choose, either type the name of a new group or select an existing group from the drop-down list. For more information, see [Grouping Assessments](#grouping-assessments).
    
    如果您建立群組，您也可以選擇從現有群組將資訊複製到新評定。 也就是說，已從您正在複製群組中的評定新增到客戶管理控制項的實作詳細資料和測試計劃和管理回應欄位的任何資訊，都會複製到新評定中的相同 (或相關) 的客戶管理控制項。 如果您正在將新評定新增到現有群組，來自該群組中的評定的通用資訊將會複製到新評定。 如需詳細資訊，請參閱[從現有的評定複製資訊](#copying-information-from-existing-assessments)。
    
3. 按 [下一步]**** 並執行下列動作：
    
    a. 從 [選取產品]**** 下拉式清單中選擇要評定合規性的 Microsoft 雲端服務。 
    
    b. 從 [選取認證]**** 下拉式清單中選擇要根據哪個認證評定選取的雲端服務。 
    
4. 按一下 [新增至儀表板]**** 來建立「評估」；評估會在現有磚的清單結尾新增至合規性管理員作為新的磚。 
    
    合規性管理員儀表板上的**評定磚**會顯示評定群組、評定的名稱 (自動建立為一組服務名稱，然後選取憑證)、建立日期和上次修改時間、合規性分數總分 (也就是所有已實作、測試及通過的指派控制項風險值的加總)，以及底部的進度列指示器，顯示已評估的控制項數目。 
    
5. 按一下「評定」的名稱即可開啟它，然後檢視「評定」的詳細資料。
    
6. 按一下 [動作]**** 功能表來檢視您指派的動作項目、重新命名評定群組、匯出評定報告，或封存評定。 
    
    ![合規性管理員 - 評定磚](../media/abf35c11-9757-45c1-aa14-91178f67a18c.png)

## <a name="copying-information-from-existing-assessments"></a>從現有「評定」複製資訊

如先前所述，當您建立評定群組時，您可以選擇從現有群組中的評定將資訊複製到新群組中的新評定。 這可讓您將已完成的評定和測試工作套用到新評定中的相同客戶管理控制項。 例如，如果您在貴組織中有一個針對所有 GDPR 相關評定的群組，在將新評定新增到群組時，您可以從現有評定工作複製通用資訊。
  
您可以將下列客戶資訊複製到新的「評估」：
  
- Assessment Users. An Assessment user is a user who the control is assigned to.
    
- 狀態、日期測試和測試結果。
    
- 實作詳細資料和測試計劃資訊。
    
同樣地，會同步處理來自相同評定群組內的共用客戶管理控制項的資訊。 而且也會同步處理相同評定內的相關客戶管理控制項中的資訊。

## <a name="viewing-assessments"></a>檢視評定

1. 找出對應到您想要檢視評定的「評定磚」，然後按一下評定名稱即可開啟，並檢視與「評定」相關的 Microsoft 和客戶管理控制項，以及一份「評定」範圍內的雲端服務清單。 以下是 Office 365 和 GDPR 的「評定」範例。
    
    ![合規性管理員評定檢視 - 全螢幕的圖說文字](../media/169a02eb-e805-412d-b9e7-89561aa7ad1d.png)
  
1. 此區段會顯示「評估」摘要資訊，包括「評估群組」的名稱、「產品」、「評估名稱」、評估控制項的數目
    
2. This section shows the Assessment Filter controls. For a more detailed explanation of how to use the Assessment Filter controls see the [Managing the assessment process](#managing-the-assessment-process) section. 
    
3. 本節會顯示評估範圍內的個別雲端服務。
    
4. 此區段包含 Microsoft 管理的控制項。 會依據控制項系列整理相關控制項。 按一下某個控制項系列以將它展開，並顯示個別控制項。
    
5. 此區段包含客戶管理的控制項，這也是依據控制項系列整理而成。 按一下某個控制項系列以將它展開，並顯示個別控制項。
    
6. 顯示控制項系列中的控制項總數，以及已存取這些控制項的數目。 追蹤貴組織評定客戶管理控制項的進度是合規性管理員的主要功能。 如需詳細資訊，請參閱[了解合規性分數](#understanding-the-compliance-score)一節。 

## <a name="managing-the-assessment-process"></a>管理評估程序

評定的建立者是一開始的唯一評定使用者。 針對每個客戶管理的控制項，您可以指派動作項目給貴組織中的某個人員，讓該人員成為可執行建議的客戶動作以及收集和上傳證據的評定使用者。 當您指派動作項目時，您可以選擇傳送含有詳細資料的電子郵件給該人員，包括建議的客戶動作和動作項目優先順序。 電子郵件通知包含 [動作項目]**** 儀表板的連結，這會列出指派給該人員的所有動作項目。 
  
以下是您可以使用合規性管理員工作流程功能執行的工作清單。
  
![合規性管理員評估工作流程的圖說文字](../media/9e5ae34d-b55e-4452-a021-e0e5b10218f5.png)
  
1. **使用篩選選項來尋找特定的評估控制項** - 合規性管理員提供 [篩選選項]****，提供您高度細微的選取範圍準則來顯示評估控制項，協助您精確將目標鎖定在特定區域以進行合規性。 
    
    按一下頁面右側的漏斗圖圖示，以顯示或隱藏 [篩選選項]**** 控制項。 這些控制項可讓您指定篩選準則，而且只有符合這些準則的評定控制項才會顯示在下方。 ![合規性管理員評定篩選控制項](../media/d44e1b4b-d928-4778-8a3a-6231edde9ca0.png)
  
    - **文章**：篩選文章名稱並傳回與該文章關聯的評定控制項。 例如，輸入「文章 (5)」會傳回其名稱包含該字串的文章選擇清單，亦即文章 (5)(1)(a)、文章 (5)(1)(b)、文章 (5)(1)(c) 等。選取文章 (5)(1)(c) 會傳回與文章 (5)(1)(c) 關聯的控制項。 這是使用 OR 運算子搭配多個值的多重選取欄位，舉例來說，如果您選取文章 (5)(1)(a)，然後新增文章 (5)(1)(c)，篩選則會傳回與文章 (5)(1)(a) 或文章 (5)(1)(c) 關聯的控制項。 
    
      ![合規性管理員評定檢視 - 篩選文章名稱](../media/8b0507a0-589d-484a-bc60-80a3debe3ddb.png)
  
    - **控制項** - 傳回名稱符合篩選的控制項清單，亦即輸入 7.3 會傳回選取項目清單項目，例如 7.3.1、7.3.4、7.3.5 等。這是多重選取欄位，會使用 OR 運算子與多個值 - 例如，如果您選取 7.3.1 然後新增 7.3.4，篩選則會傳回與 7.3.1 或 7.3.4 相關聯的控制項。 
    
      ![合規性管理員評定檢視 - 篩選控制項多重選取](../media/c4fc25e8-2376-4f2d-b605-f9c3d90413bf.png)
  
    - **指派的使用者** - 傳回指派給所選取使用者的控制項清單。 
    
    - **狀態** - 傳回所選取狀態的控制項清單。 
    
    - **測試結果** - 傳回所選取測試結果的控制項清單。 
    
    As you apply filter conditions, the view of applicable controls will change to correspond to your filter conditions. Expand the control family sections to show the control details below. 
    
    ![合規性管理員評估檢視 - 篩選文章結果](../media/e6485d45-d47f-4b25-8b1c-b3c2ee4a8328.png)
  
2. If after selecting the desired filters no results are shown, that means there are no controls that correspond to the specified filter conditions. For instance, if you select a particular **Assigned User** and then choose a **Control** name that does correspond to the control assigned to that user, no assessments will be shown in the page below. 
    
3. **Assign an Action Item to a user** - You can assign an Action Item to a person to implement the requirements of a certification/regulation, or to test, verify, and document your organization's implementation requirements. When you assign an Action Item, you can choose to send an email to the person that contains details including the recommended Customer Actions and the Action Item priority. You can also unassign or reassign an Action Item to a different person. 
    
4. **管理文件**：客戶管理的控制項也有一個管理與執行實作工作相關文件的位置，而且可用於執行測試和驗證工作。 凡是擁有合規性管理員中的資料編輯權限的任何人員，只要按一下 [管理文件]****，就可以上傳文件。 文件上傳完畢後，您可以按一下 [管理文件]**** 來檢視和下載檔案。 
    
5. **提供實作和測試詳細資料** - 每個客戶管理控制項都有可編輯的欄位，使用者可以在其中新增記錄貴組織為符合憑證/規定需求所採取步驟的實作詳細資料，並驗證及記錄貴組織符合這些需求的方式。
    
6. **Set Status** - Set the Status for each item as part of the assessment process. Available status values are **Implemented**, **Alternative Implementation**, **Planned**, and **Not in Scope**. 
    
7. **輸入測試日期和測試結果**：具有合規性管理員評估員角色的人員可以驗證是否已執行適當的測試、檢閱實作詳細資料、測試計劃、測試結果，以及任何上傳的證據，然後設定測試日期和測試結果。 可用的測試結果值包括 [通過]****、[失敗 - 低風險]****、[失敗 - 中度風險]**** 和 [失敗 - 高風險]****。 

## <a name="managing-action-items"></a>管理動作項目

貴組織中參與評定程序的人員可以從他們身為使用者的所有評定中，使用合規性管理員來檢閱客戶管理的控制項。 當使用者登入「合規性管理員」並開啟 [動作項目]**** 儀表板時，會顯示指派給他們的 [動作項目] 清單。 視使用者獲派的合規性管理員角色而定，他們可以提供實作或測試詳細資料、更新狀態，或是指派動作項目。 
  
As certification controls are generally implemented by one person and tested by another, the control action item can be initially assigned to one person for implementation, and once that is complete, that person can reassign the control action item to the next person for control testing and uploading of evidence. This assignment/reassignment of control actions can be performed by any users who have a Compliance Manager role with sufficient permissions, allowing for central management of control assignments, or decentralized routing of control action items, from implementer to tester as appropriate.
  
若要指派動作項目：
  
1. 合規性管理員儀表板，找出您想要使用之評估的評估磚，按一下評估的名稱以前往評估的詳細資料頁面。
    
2. 您可以按一下 [篩選]****，使用篩選控制項來找出您想要指派的特定評估控制項，或 
    
3. 向下捲動至 [客戶管理控制項] 區段、展開控制項系列，並捲動控制項的清單，直到您找到指派評定控制項
    
4. 在 [指派的使用者]**** 欄中，按一下 [指派]****。 
    
5. In the Assign Action Item dialog box, click the **Assign To** field to populate the list of users to whom the action can be assigned. You can scroll through the list to find the target user or start typing in the field to search for the username. 
    
6. 按一下使用者以指派此動作項目給他們。
    
7. 如果您想要傳送電子郵件通知給使用者以通知他們，請確保勾選 [傳送電子郵件通知]**** 核取方塊。 
    
8. 輸入您想要向該使用者顯示的任何附註，再按一下 [指派]****。 
 
    使用者會收到其動作項目指派的通知和任何您所提供的附註。
    
The notes that are associated with the action item are persisted in the notes section, available for the next time the action item is assigned. These notes are not read-only, can be edited, replaced or removed by the person assigning the action item.

## <a name="exporting-information-from-an-assessment"></a>從評估中匯出資訊

您可以將評定匯出到 Excel 檔案，以供貴組織中的合規性專案關係人檢閱，並提供給稽核員和監管單位。 此評定報告是建立該報告的日期與時間之際的評定快照，而且它包含該評定的 Microsoft 管理控制項和客戶管理控制項的詳細資料，包括控制項實作狀態、控制項測試日期和測試結果，並提供上傳證據文件的連結。 建議您在封存評定前匯出評定報告，因為封存的評定不會保留其上傳文件的連結。
  
若要匯出評估報告：
  
- 在合規性管理員儀表板中，在您想要匯出的評估磚上按一下 [動作]****，然後選擇 [匯出至 Excel]****

  或
    
- 如果您正在檢視 [評定詳細資料] 頁面，請按一下 [匯出至 Excel]**** 按鈕，位於評定合規性分數上方的頁面右上角。
    
The assessment report will be downloaded in your browser session. If you don't see a popup informing you of this, you may wish to check your browser's downloads folder.

## <a name="archiving-an-assessment"></a>封存評估

When you have completed an Assessment and no longer need it for compliance purposes, you can archive it. When an Assessment is archived, it is removed from Assessments dashboard.
  
> [!NOTE]
> When an Assessment is Archived, it cannot be 'unarchived' or restored to a read-write in progress state. Please note that Archived Assessments do not retain their links to uploaded evidence documents, so it is highly recommended that you perform an Export of the Assessment before archiving it, as the exported assessment report will contain links to the evidence documents, enabling you to continue to access them. 
  
若要封存評估：
  
1. 在所需評估的儀表板磚上，按一下 [動作]****。 
    
2. 選取 [封存評估]****。 
 
    [封存評估]**** 對話方塊隨即顯示，要求您確認您想要封存的評估。
    
4. 若要繼續進行封存，按一下 [封存]****，或是按一下 [取消]****。 
    
若要檢視封存的評估：
  
1. 在合規性管理員儀表板上，請勾選 [顯示已封存]**** 核取方塊。 
    
    封存的評估會出現在標題為 [封存的評估]**** 列底下其他作用中評估下的新顯示區段中。
    
3. 按一下您想要檢視的評估名稱。
    
檢視封存的評估時，通常可編輯的控制項 (也就是實作、測試結果) 都不會為使用中，且 [管理文件]**** 按鈕將不存在。

## <a name="using-search"></a>使用搜尋

![服務信任入口網站 - 搜尋輸入欄位](../media/7c5cd817-3d62-420b-adb4-76e33fef941f.png)
  
Click the magnifying glass in the upper right-hand corner of the page by to expand the Search input field, enter your search terms and press Enter. The Search control will appear, with the search term in the search pane input field, and search results will appear beneath.
  
By default, Search returns Document results, and you can use the Filter By dropdown lists to refine the list of documents displayed, to add or remove search results from view. You can use multiple filter attributes at the same time to narrow the returned documents to specific cloud services, categories of compliance or security practices, regions of the world, or industries. Click the document name link to download the document.
  
![服務信任入口網站 - 套用篩選器搜尋文件](../media/86b754e1-c63c-4514-89ac-d014bf334140.png)
  
按一下 [合規性管理員] 連結來顯示合規性管理員評定控制項的搜尋結果。 列出的搜尋結果會顯示建立評定的日期、將評定分組的名稱、適用的雲端服務，以及是否為 Microsoft 或客戶管理的控制項。
  
![服務信任入口網站 - 搜尋合規性管理員控制項](../media/bafb811a-68ce-40b5-ad16-058498fe5439.png)
  
> [!NOTE]
> 服務信任入口網站的報告和記錄在發佈之後，至少有 12 個月可供下載，直到提供新版文件為止。 
 
## <a name="localization-support"></a>當地語系化支援

Service Trust Portal enables you to view the page content in different languages. To change the page language, simply click on the globe icon in the lower left corner of the page and select the language of your choice. 
  
![服務信任入口網站 - 當地語系化的內容選項](../media/b50c677e-a886-4267-9eca-915d880ead7a.png)


## <a name="change-log-for-customer-managed-controls"></a>客戶管理控制項的變更記錄

「合規性管理員」的設計是定期更新以便與法規需求變更保持一致，以及與我們的雲端服務變更保持一致。 這些更新包括對客戶管理控制項的變更。 我們會提供變更記錄檔，協助您了解這些變更的影響，包括新增或變更內容的詳細資料，以及變更對現有評定有何影響的指導方針。 通常有兩種類型的變更：
  
- A **Major** change is a significant change to a Customer Action, such as the addition or removal of a control or specific numbered steps, or a change in the guidance around responsibilities, recommendations, or evidence. For Major changes, we recommend that you re-evaluate your implementation and/or assessment of the affected control.
    
- A **Minor** change is an insignificant change to a Customer Actions, such as fixing a typo or formatting issues, or updating or correcting hyperlinks. Minor changes generally do not require the control to be re-evaluated; however, we do recommend that you review the updated Customer Action.
  
### <a name="customer-managed-controls---change-log-for-july-2018"></a>客戶管理控制項 - 2018 年 7 月的變更記錄

|**控制項 ID**|**評估**|**變更類型**|**變更描述**|**客戶的建議動作**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|45 C.F.R. § 164.308(a)(7)(ii)(A)<br/> |Office 365：HIPAA|主要|將 HITECH 控制項新增至 Office 365 的 HIPAA 評估 |檢閱新增的控制項和建議的客戶動作<br/> |
|45 C.F.R.  164.312(a)(6)(ii)|Office 365：HIPAA|主要|將 HITECH 控制項新增至 Office 365 的 HIPAA 評估|檢閱新增的控制項和建議的客戶動作<br/>|
45 C.F.R. § 164.312(c)(1)| Office 365：HIPAA|主要| 將 HITECH 控制項新增至 Office 365 的 HIPAA 評估 |檢閱新增的控制項和建議的客戶動作<br/> |
45 C.F.R.  § 164.316(b)(2)(iii)| Office 365：HIPAA|主要|將 HITECH 控制項新增至 Office 365 的 HIPAA 評估|檢閱新增的控制項和建議的客戶動作<br/>|
|

### <a name="customer-managed-controls---change-log-for-april-2018"></a>客戶管理控制項 - 2018 年 4 月的變更記錄

|**GDPR**|**HIPAA**|**ISO 27001**|**ISO 27018**|**NIST 800-53**|**NIST 800-171**|**變更類型**|**變更描述**|**客戶的建議動作**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|6.13.2  <br/> |||C.16.1.1  <br/> |||主要  <br/> |先前編號為 6.12.1.1。  <br/> 已新增詳細資料至建議。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
||||||3.1.6  <br/> |主要  <br/> |已新增步驟至指導方針，包括啟用稽核及搜尋稽核記錄。  <br/> |檢閱客戶動作中的更新建議。  <br/> |
|6.8.2  <br/> |||A.10.2  <br/> |||主要  <br/> |先前編號為 6.7.2.9。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|6.6.4  <br/> |45 C.F.R. § 164.312(a)(2)(i)  <br/>           45 C.F.R. § 164.312(d)  <br/> |A.9.4.2  <br/> ||IA-2  <br/> |3.5.1  <br/> |主要  <br/> |先前編號為 6.5.2.3。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|6.13.1  <br/> |45 C.F.R. § 164.308(a)(1)(i)  <br/> |A.16.1  <br/> |C.16.1  <br/> |IR-4(a)  <br/> |3.6.1  <br/> |主要  <br/> |先前編號為 6.12.1。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|6.7  <br/> ||||||主要  <br/> |先前編號為 6.6.1.1。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|6.6.5  <br/> |||A.10.8  <br/> |IA-3  <br/> |3.5.2  <br/> |主要  <br/> |先前編號為 6.5.4.2。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|6.15.1  <br/> ||||||主要  <br/> |先前編號為 6.14.1.3。  <br/> 包含其他建議與動作項目的更新指導方針。  <br/> |重新評估控制項：在客戶動作中檢閱更新的指導方針，然後依照實作和評估控制項的建議步驟。  <br/> |
|||||AC-2(h)(2)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||||AC-2(7)(b)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||||AC-2(h)(1)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
||45 C.F.R. § 164.308(a)(5)(ii)(C)  <br/> |||AC-2(g)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||||AC-2(12)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
||45 C.F.R. § 164.312(b)  <br/> |A.12.4.3  <br/> ||AU-2(d)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||||AC-2(4)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
||||||3.1.7  <br/> |次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||A.16.1.7  <br/> |C.12.4.2，組件 2  <br/> |||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||||AC-2(h)(3)  <br/> ||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||A.12.4.2  <br/> ||||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗。  <br/> |不需要任何動作。  <br/> |
|||A.7.2.8  <br/> ||||次要  <br/> |已新增連結至 [內容搜尋] 刀鋒視窗，和 DSR 入口網站。  <br/> |不需要任何動作。  <br/> |
||45 C.F.R. § 164.308(a)(3)(ii)(C)  <br/> |||||次要  <br/> |已新增連結至 [啟用稽核] 刀鋒視窗和 Office 365 系統管理員角色支援主題。  <br/> |不需要任何動作。  <br/> |
|5.2.1  <br/> ||||||次要  <br/> |先前編號為 5.2.2。  <br/> 已釐清指導方針內的客戶責任。  <br/> |檢閱客戶動作中的更新建議。  <br/> |
|6.11.1  <br/> |45 C.F.R. § 164.312(e)(2)(ii)  <br/> |A.10.1.1          A.10.1.2          A.18.1.5  <br/> |C.10.1.1  <br/> |SC-13  <br/> |3.13.11  <br/> |次要  <br/> |先前編號為 6.10.1.2。  <br/> 修正拼字錯誤。  <br/> |不需要任何動作。  <br/> |
|7.5.1  <br/> ||||||次要  <br/> |先前編號為 A.7.4.1。  <br/> 修正拼字錯誤。  <br/> |不需要任何動作。  <br/> |
|||A.8.2.3  <br/> |||3.1.3  <br/> |次要  <br/> |移除不必要的句子。  <br/> |不需要任何動作。  <br/> |
||45 C.F.R. § 164.308(a)(4)(i)  <br/> |A.6.1.2  <br/> ||AC-5(a)  <br/> |3.1.2          3.1.4  <br/> |次要  <br/> |包含其他建議與動作項目的更新指導方針。  <br/> |檢閱客戶動作中的更新建議。  <br/> |
||45 C.F.R. § 164.308(a)(7)(ii)(E)  <br/> |||RA-2(a)  <br/> ||次要  <br/> |已更新使用匯入服務說明主題連結以使用 FWLink。  <br/> |不需要任何動作。  <br/> |
|

### <a name="gdpr-assessment-control-id-change-reference---change-log-for-february-2018"></a>GDPR 評估控制項 ID 變更參考 - 2018 年 2 月的變更記錄 

|**上一個控制項 ID (2017 年 11 月預覽)**|**新的控制項 ID (2018 年 2 月公開發行)**|
|:-----|:-----|
|5.2.2  <br/> |5.2.1  <br/> |
|5.2.3  <br/> |5.2.2  <br/> |
|5.2.4  <br/> |5.2.3  <br/> |
|6.1.1.1  <br/> |6.2  <br/> |
|6.10.1.2  <br/> |6.11.1  <br/> |
|6.10.2.5  <br/> |6.11.2  <br/> |
|6.11.1.2  <br/> |6.12  <br/> |
|6.12.1  <br/> |6.13.1  <br/> |
|6.12.1.1  <br/> |6.13.2  <br/> |
|6.12.1.5  <br/> |6.13.3  <br/> |
|6.14.1.3  <br/> |6.15.1  <br/> |
|6.14.2.1  <br/> |6.15.2  <br/> |
|6.14.2.3  <br/> |6.15.3  <br/> |
|6.2.1.1  <br/> |6.3  <br/> |
|6.3.2.2  <br/> |6.4  <br/> |
|6.4.3.1  <br/> |6.5.2  <br/> |
|6.4.3.2  <br/> |6.8.1  <br/> |
|6.4.3.3  <br/> |6.5.3  <br/> |
|6.5.2  <br/> |6.6.1  <br/> |
|6.5.2.1  <br/> |6.6.2  <br/> |
|6.5.2.2  <br/> |6.6.3  <br/> |
|6.5.2.3  <br/> |6.6.4  <br/> |
|6.5.4.2  <br/> |6.6.5  <br/> |
|6.6.1.1  <br/> |6.7  <br/>   |
|6.7.2.7  <br/> |6.8.1  <br/> |
|6.7.2.9  <br/> |6.8.2  <br/> |
|6.8.1.4  <br/> |6.9.1  <br/> |
|6.8.4.1  <br/> |6.9.3  <br/> |
|6.8.4.2  <br/> |6.9.4  <br/> |
|6.9.2.1  <br/> |6.10.1  <br/>|
|6.9.2.3  <br/> |6.10.2  <br/>|
|A.7.1.1  <br/> |7.2.1  <br/> |
|A.7.1.2  <br/> |7.2.2  <br/> |
|A.7.1.3  <br/> |7.2.3  <br/> |
|A.7.1.4  <br/> |7.2.4  <br/> |
|A.7.1.5  <br/> |7.2.5  <br/> |
|A.7.1.6  <br/> |7.2.6  <br/> |
|A.7.1.7  <br/> |7.2.7  <br/> |
|A.7.2.1  <br/> |7.3.1  <br/> |
|A.7.2.10 <br/> |7.3.9  <br/> |
|A.7.2.11 <br/> |7.3.10  <br/>|
|A.7.2.2  <br/> |7.3.2  <br/> |
|A.7.2.3  <br/> |7.3.3  <br/> |
|A.7.2.4  <br/> |7.3.4  <br/> |
|A.7.2.5  <br/> |7.3.5  <br/> |
|A.7.2.6  <br/> |7.3.6  <br/> |
|A.7.2.7  <br/> |7.3.7  <br/> |
|A.7.2.8  <br/> |7.3.8  <br/> |
|A.7.3.1  <br/> |7.4.1  <br/> |
|A.7.3.10 <br/> |7.4.10  <br/>|
|A.7.3.2  <br/> |7.4.2  <br/> |
|A.7.3.3  <br/> |7.4.3  <br/> |
|A.7.3.4  <br/> |7.4.4  <br/> |
|A.7.3.5  <br/> |7.4.5  <br/> |
|A.7.3.6  <br/> |7.4.6  <br/> |
|A.7.3.7  <br/> |7.4.7  <br/> |
|A.7.3.8  <br/> |7.4.8  <br/> |
|A.7.3.9  <br/> |7.4.9  <br/> |
|A.7.4.1  <br/> |7.5.1  <br/> |
|A.7.4.2  <br/> |7.5.2  <br/> |
|A.7.4.3  <br/> |7.5.3  <br/> |
|A.7.4.4  <br/> |7.5.4  <br/> |
|A.7.4.5  <br/> |7.5.5  <br/> |
|B.8.1.1  <br/> |8.2.1  <br/> |
|B.8.1.2  <br/> |8.2.2  <br/> |
|B.8.1.3  <br/> |8.2.3  <br/> |
|B.8.1.4  <br/> |8.2.4  <br/> |
|B.8.1.5  <br/> |8.2.5  <br/> |
|B.8.1.6  <br/> |8.2.6  <br/> |
|B.8.2.1  <br/> |8.3.1  <br/> |
|B.8.3.1  <br/> |8.4.1  <br/> |
|B.8.3.2  <br/> |8.4.2  <br/> |
|B.8.3.3  <br/> |8.4.3  <br/> |
|B.8.4.1  <br/> |8.5.1  <br/> |
|B.8.4.2  <br/> |8.5.2  <br/> |
|B.8.4.3  <br/> |8.5.4  <br/> |
|B.8.4.4  <br/> |8.5.5  <br/> |
|B.8.4.5  <br/> |8.5.3  <br/> |
|B.8.4.6  <br/> |8.5.6  <br/> |
|B.8.4.7  <br/> |8.5.7  <br/> |
|B.8.4.8  <br/> |8.5.8  <br/> |
|
   
## <a name="see-also"></a>另請參閱

- [合規性管理員互動指南](https://content.cloudguides.com/guides/Compliance%20Manager)

- [宣布合規性管理員正式公開上市](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Announcing-Compliance-Manager-general-availability/ba-p/161922)

- [Microsoft 365 提供資訊保護策略來協助符合 GDPR](https://blogs.office.com/2018/02/22/microsoft-365-provides-an-information-protection-strategy-to-help-with-the-gdpr)
