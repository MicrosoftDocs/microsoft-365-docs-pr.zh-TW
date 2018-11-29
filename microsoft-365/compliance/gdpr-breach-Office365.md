---
title: GDPR 規定的 Office 365 資料外洩通知
description: Microsoft 如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Office 365、Microsoft 365、Microsoft 365 教育版、Microsoft 365 文件、GDPR
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: c2ee959aad883516f03e903d34f517b4e76e4864
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866591"
---
# <a name="office-365-breach-notification-under-the-gdpr"></a><span data-ttu-id="e2797-104">GDPR 規定的 Office 365 資料外洩通知</span><span class="sxs-lookup"><span data-stu-id="e2797-104">Office 365 Breach Notification Under the GDPR</span></span>

<span data-ttu-id="e2797-p101">Office 365 將以資料處理者的身分，確保身為資料控制者的客戶可符合 GDPR 資料外洩通知的要求。為此，我們致力於完成以下項目：</span><span class="sxs-lookup"><span data-stu-id="e2797-p101">As a data processor, Office 365 will ensure that our customers are able to meet the GDPR’s breach notification requirements as data controllers. To that end, we are committed to the following:</span></span>

-   <span data-ttu-id="e2797-p102">讓客戶能夠指定專用的隱私權連絡人，以便在發生外洩事件時通知此連絡人。客戶可以在 Azure Active Directory (AAD) 中指定此連絡人。</span><span class="sxs-lookup"><span data-stu-id="e2797-p102">Providing customers with an ability to specify a dedicated privacy contact who will be notified in the event breach. Customers will be able to specify this contact in Azure Active Directory (AAD)</span></span>

-   <span data-ttu-id="e2797-p103">在宣告發生資料外洩的 72 小時內，向客戶發出個人資料外洩通知。通知會透過電子郵件傳送給客戶指定的連絡人</span><span class="sxs-lookup"><span data-stu-id="e2797-p103">Notifying customers of a personal data breach within 72 hours of a breach being declared. Notification will be done by e-mail to the contact specified by the customer</span></span>

-   <span data-ttu-id="e2797-p104">初次通知至少會包含外洩性質的描述、使用者的影響估計及降低風險的步驟 (如果適用的話)。如果在發出初次通知時，我們尚未完成調查，初次通知中會指出後續步驟及與您連絡的時間表</span><span class="sxs-lookup"><span data-stu-id="e2797-p104">Initial notification will include, at the least, a description of the nature of the breach, approximation of user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication in our initial notification</span></span>

<span data-ttu-id="e2797-p105">Microsoft 認可資料控制者要負責進行風險評估並判斷資料外洩是否需要通知客戶 DPA，而我們傳送給客戶的通知中會提供此評估所需的資訊。因此，Microsoft 會將所有個人資料外洩事件通知客戶，除了確定無法辨識的個人資料以外 (例如，已確認金鑰完整性的強式加密資料)。</span><span class="sxs-lookup"><span data-stu-id="e2797-p105">Microsoft recognizes that data controllers are responsible for conducting risk assessments and determining whether a breach requires notification of the customer’s DPA, and our notification to customers will provide the information needed to make that assessment. Microsoft will therefore notify customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, strongly encrypted data where integrity of the keys is confirmed).</span></span>

## <a name="office-365-investments-in-data-security"></a><span data-ttu-id="e2797-115">Office 365 在資料安全性中的投資</span><span class="sxs-lookup"><span data-stu-id="e2797-115">Office 365 Investments in Data Security</span></span>

<span data-ttu-id="e2797-116">我們除了致力於提供資料外洩的即時通知外，Office 365 在系統、處理程序及人員上也花費許多心思，為求降低個人資料外洩的可能性，以及在資料外洩發生時進行快速偵測，並降低其造成的傷害。</span><span class="sxs-lookup"><span data-stu-id="e2797-116">In addition to our commitment to provide timely notification of breach, Office 365 strongly invests in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur.</span></span>

<span data-ttu-id="e2797-117">以下是一些我們在此方面的投資說明：</span><span class="sxs-lookup"><span data-stu-id="e2797-117">Here is a description of some of our investments in this space:</span></span>

-   <span data-ttu-id="e2797-p106">**存取控制系統：** Office 365 會持續維持「無常設存取」原則，亦即，工程師只有在回應需要提高權限的特定事件而被明確授與存取權時，才會擁有服務的存取權。無論何時授與存取權，皆須遵循最低權限原則：針對特定要求授與的權限，僅允許服務執行該要求的最小一組必要動作。為了做到這一點，Office 365 會持續嚴格地區隔「提高權限角色」，每個角色僅允許採取預先定義的特定動作。不同於其他角色，「存取客戶資料」角色通常用來管理服務，並且會在核准前進行最嚴格的檢查。綜合來看，這些在存取控制上的投資，會大幅降低工程師在 Office 365 中不當存取客戶資料的可能性。</span><span class="sxs-lookup"><span data-stu-id="e2797-p106">**Access Control Systems.** Office 365 maintains a “zero-standing access” policy, which means that engineers do not have access to the service unless it is explicitly granted in response to a specific incident that requires elevation of access. Whenever access is granted it is done under the principle of least privilege: permission granted for a specific request only allow for a minimal set of actions required to service that request. To do this, Office 365 maintains strict separation between “elevation roles”, with each role only allowing certain pre-defined actions to be taken. The “Access to Customer Data” role is distinct from other roles that are more commonly used to administer the service and is scrutinized most heavily before approval. Taken together, these investments in access control greatly reduce the likelihood that an engineer in Office 365 inappropriately accesses customer data.</span></span>

-   <span data-ttu-id="e2797-p107">**安全性監視系統與自動化：** Office 365 會持續維護穩固的即時安全性監視系統。在其他問題上，若有人試圖非法存取客戶資料，或試圖非法將我們服務的資料轉送出去時，這些系統會發出警告。對於與上述存取控制相關的部分，我們的安全性監視系統會詳細記錄提高權限的要求，及針對指定提高權限要求採取的動作，並維護這些記錄。Office 365 也會持續維護自動解決問題的能力，以針對我們偵測到的問題，在回應時自動採取動作來降低威脅，並指定團隊來回應無法自動解決的警訊。為了驗證我們的安全性監視系統，Office 365 會定期進行紅隊演練 (red-team exercises)，也就是內部滲透測試團隊會針對實際環境模擬攻擊者的行為。這些演練可讓我們的安全性監視和回應能力持續進化。</span><span class="sxs-lookup"><span data-stu-id="e2797-p107">**Security Monitoring Systems and Automation:** Office 365 maintains robust, real-time security monitoring systems. Among other issues, these systems raise alerts for attempts to illicitly access customer data, or for attempts to illicitly transfer data out of our service. Related to the points about access control mentioned above, our security monitoring systems maintain detailed records of elevation requests that are made, and the actions taken for a given elevation request. Office 365 also maintains automatic resolution investments that automatically act to mitigate threats in response to issues we detect, and dedicated teams for responding to alerts that cannot be resolved automatically. To validate our security monitoring systems, Office 365 regularly conducts red-team exercises in which an internal penetration testing team simulates attacker behavior against the live environment. These exercises lead to regular improvements to our security monitoring and response capabilities.</span></span>

-   <span data-ttu-id="e2797-p108">**人員與處理程序：** 除了上述的自動化作業，Office 365 也會持續維護處理程序和團隊，以負責較大型組織的隱私權和事件管理程序訓練，以及在資料外洩時執行這些程序。例如，維護詳細的隱私權外洩標準作業程序 (SOP)，並分享給整個組織中的團隊。此 SOP 會詳細說明 Office 365 中個別團隊與中央安全性事件回應團隊的角色與責任。這包括哪些團隊需要改善他們自己的安全性狀態 (進行安全性檢閱、與中央安全性監視系統整合和其他最佳做法)，以及哪些團隊需要在發生實際資料外洩時執行動作 (針對事件回應進行快速升級、維護並提供用來加速回應程序的特定資料來源)。團隊也須定期在資料分類及個人資料的正確處理和儲存程序上接受訓練。</span><span class="sxs-lookup"><span data-stu-id="e2797-p108">**Personnel and Processes:** In addition to the automation described above, Office 365 maintains processes and teams responsible for both educating the broader organization about privacy and incident management processes, and for executing those processes during a breach. For example, a detailed privacy breach Standard Operating Procedure (SOP) is maintained and shared with teams throughout the organization. This SOP describes in detail the roles and responsibilities both of individual teams within Office 365 and centralized security incident response teams. These span both what teams need to do to improve their own security posture (conduct security reviews, integrate with central security monitoring systems, and other best practices), and what teams would need to do in the event of an actual breach (rapid escalation to incident response, maintain and provide specific data sources that will be used to expedite the response process). Teams are also regularly trained on data classification, and correct handling and storage procedures for personal data.</span></span>

<span data-ttu-id="e2797-p109">最重要的是，Office 365 致力於降低因個人資料外洩而影響客戶的可能性與結果。如果發生個人資料外洩，我們會在確認資料外洩後盡速通知客戶。</span><span class="sxs-lookup"><span data-stu-id="e2797-p109">The major takeaway is that Office 365 strongly invests in reducing the likelihood and consequences of personal data breach impacting our customers. If personal data breach does occur, we are committed to rapidly notifying our customers once that breach is confirmed.</span></span>

## <a name="what-to-expect-in-the-event-of-breach"></a><span data-ttu-id="e2797-137">發生資料外洩時的預期行為</span><span class="sxs-lookup"><span data-stu-id="e2797-137">What to Expect in the Event of Breach</span></span>

<span data-ttu-id="e2797-p110">上一節說明 Office 365 為降低資料外洩可能性所做的投資。但若是真的發生罕見的資料外洩事件時，客戶應預期在以下各方面有可預測的經驗：</span><span class="sxs-lookup"><span data-stu-id="e2797-p110">The section above describes the investments Office 365 makes to reduce the likelihood of data breach. In the unlikely event that breach does occur, customers should expect a predictable experience in terms of the following:</span></span>

-   <span data-ttu-id="e2797-p111">在 Office 365 中有一致的事件回應週期。如前面所述，Office 365 會維護詳細的事件回應 SOP，其中說明團隊應如何為資料外洩作好準備，以及發生資料外洩時他們應如何應對。這可確保我們的保護作業和程序可套用到整個服務。</span><span class="sxs-lookup"><span data-stu-id="e2797-p111">Consistent incident response lifecycle within Office 365. As described above, Office 365 maintains detailed incident response SOPs describing how teams should prepare for breach and how they should operate if a breach does occur. This ensures that our protections and processes apply throughout the service.</span></span>

-   <span data-ttu-id="e2797-p112">用一致的準則通知客戶。我們的通知準則著重於客戶資料的機密性、完整性和可用性。如果客戶資料的機密性和完整性受到影響，Office 365 會直接通知客戶。也就是說，當有人未經適當授權而存取客戶的資料時，或資料發生不適當的損毀或遺失時，我們會向客戶發出通知。Office 365 也會報告影響資料可用性的問題，即使這通常是透過「服務健康狀態儀表板 (SHD)」來完成。</span><span class="sxs-lookup"><span data-stu-id="e2797-p112">Consistent criteria for notifying customers. Our notification criteria focus on Confidentiality, Integrity, and Availability of customer data. Office 365 will directly notify customers if either the confidentiality or integrity of customer data is impacted. That is, we will notify customers if their data is accessed without proper authorization, or if there is inappropriate destruction or loss of data. Office 365 will also report issues impacting data availability, although this is usually done through the Service Health Dashboard (SHD).</span></span>

-   <span data-ttu-id="e2797-p113">一致的通知詳細資料。當 Office 365 因為資料外洩而發生通知時，客戶可以預期收到特定的詳細資料：至少我們會提供下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="e2797-p113">Consistent notification details. When Office 365 does communicate regarding data breach, customers can expect specific details to be communicated: at minimum, we will provide the following details:</span></span>

    -   <span data-ttu-id="e2797-150">發生資料外洩和發現資料外洩的時間</span><span class="sxs-lookup"><span data-stu-id="e2797-150">Timing of the breach and timing of breach awareness</span></span>

    -   <span data-ttu-id="e2797-151">受影響的大約使用者數目</span><span class="sxs-lookup"><span data-stu-id="e2797-151">The approximate number of users impacted</span></span>

    -   <span data-ttu-id="e2797-152">已外洩的使用者資料類型</span><span class="sxs-lookup"><span data-stu-id="e2797-152">The type of user data that was breached</span></span>

    -   <span data-ttu-id="e2797-153">降低資料外洩影響的必要動作 (由控制者或處理者執行)</span><span class="sxs-lookup"><span data-stu-id="e2797-153">Actions needed to mitigate the breach, either by the controller or by the processor</span></span>

<span data-ttu-id="e2797-p114">同時，客戶應注意作為資料處理者的 Office 365，並不會判斷資料外洩的風險。每當偵測到個人資料外洩時，我們會通知客戶並提供所需的詳細資料，讓他們正確判斷影響使用者的風險，並決定是否需要進一步向法規主管機關報告。為此，資料控制者預期可判斷以下項目：</span><span class="sxs-lookup"><span data-stu-id="e2797-p114">Customers should also note that Office 365, as a data processor, will not determine the risk of data breach. Whenever personal data breach is detected, we will notify our customers and provide them with the details they need to accurately determine risk to impacted users and to decide whether further reporting to regulatory authorities is required. To that end, data controllers are expected to determine the following:</span></span>

-   <span data-ttu-id="e2797-157">資料外洩嚴重性 (也就是風險判斷)</span><span class="sxs-lookup"><span data-stu-id="e2797-157">Breach severity (that is, risk determination)</span></span>

-   <span data-ttu-id="e2797-158">是否需要通知終端使用者</span><span class="sxs-lookup"><span data-stu-id="e2797-158">Whether end users need to be notified</span></span>

-   <span data-ttu-id="e2797-159">是否需要通知法規機構 (DPA)</span><span class="sxs-lookup"><span data-stu-id="e2797-159">Whether regulators (DPAs) need to be notified</span></span>

-   <span data-ttu-id="e2797-160">控制者為降低資料外洩產生的影響，而採取的特定動作</span><span class="sxs-lookup"><span data-stu-id="e2797-160">Specific steps that will be taken by the controller to mitigate the consequences of breach</span></span>

## <a name="contacting-microsoft"></a><span data-ttu-id="e2797-161">連絡 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2797-161">Contacting Microsoft</span></span>

<span data-ttu-id="e2797-p115">在某些情況下，客戶可能會發現資料外洩，而想要通知 Microsoft。目前的通訊協定是讓客戶可通知 Microsoft 支援服務，然後其與工程團隊連絡以取得詳細資訊。在此狀況下，Microsoft 工程團隊會即時且竭盡所能地提供客戶所需的資訊 (透過支援連絡方式)。</span><span class="sxs-lookup"><span data-stu-id="e2797-p115">In some scenarios, a customer may become aware of a breach and may wish to notify Microsoft. The current protocol is for customers to notify Microsoft Support, which will then interface with engineering teams for more information. In this scenario, Microsoft engineering teams are similarly committed to providing the information customers need, through their support contact, in a timely fashion.</span></span>

## <a name="call-to-action-for-customers"></a><span data-ttu-id="e2797-165">建議客戶執行的動作</span><span class="sxs-lookup"><span data-stu-id="e2797-165">Call to Action for Customers</span></span>

<span data-ttu-id="e2797-p116">如上所述，Office 365 會盡力在宣告資料外洩後的 72 小時內通知客戶。客戶的租用戶系統管理員將會收到通知。此外，Office 365 建議客戶透過 Azure Active Directory (AAD) 入口網站指定「全域隱私權連絡人」別名。發生個人資料外洩時，除了系統管理員外，此別名也可以收到以電子郵件傳送的通知。</span><span class="sxs-lookup"><span data-stu-id="e2797-p116">As noted above, Office 365 is committed to notifying customers within 72 hours of breach declaration. The customer’s tenant administrator will be notified. Additionally, Office 365 recommends that customers designate a Global Privacy Contact alias, which can be done in the Azure Active Directory (AAD) portal. In the event of personal data breach, this alias may be e-mailed in addition to the notification that will be sent to administrators.</span></span>

<span data-ttu-id="e2797-p117">客戶的隱私權連絡人可以是組織內的個人、通訊群組清單 (DL)，或是完全與組織沒關係的某人。Office 365 只會要求客戶提供此連絡人的電子郵件地址，而且客戶可以在 AAD 入口網站中的 [全域隱私權連絡人] 欄位下，指定此連絡人。請注意，此欄位與 AAD 中的「技術連絡人」欄位相關 (但不同)。如果客戶選擇指定 DL 作為此連絡人，應確認 DL 是否已設定為可接收來自外部寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="e2797-p117">The customer’s privacy contact can be an individual within the organization, a distribution list (DL), or someone entirely outside of the organization. Office 365 only asks that customers provide an e-mail address for this contact, and customers will be able to specify this in the AAD portal, under the “Global Privacy Contact” field. Note that this field is related to, but distinct from, the existing “Technical Contact” field in AAD. If customers choose to specify a DL for this contact, they should ensure that the DL is configured to enable receipt of messages from external senders.</span></span>

<span data-ttu-id="e2797-174">總之，Office 365 會要求客戶執行下列項目，以享有資料外洩通知程序的好處：</span><span class="sxs-lookup"><span data-stu-id="e2797-174">To summarize, Office 365 asks customers to do the following to receive the benefits of our breach notification processes:</span></span>

-   <span data-ttu-id="e2797-p118">決定在發生個人資料外洩時接收電子郵件通知的連絡人。連絡人應了解 GDPR 規定中的控制者需求，並準備好在收到通知的短時間內，與組織的 DPO 或可能是 DPA 進行通訊。租用戶系統管理員也會收到資料外洩通知，同樣地，他也應了解 GDPR 規定中的控制者需求。</span><span class="sxs-lookup"><span data-stu-id="e2797-p118">Decide on a contact to receive e-mail notifications regarding personal data breach. This contact should be aware of the controller’s requirements under GDPR and should be prepared to interface with the organization’s DPO and potentially the DPA shortly after receiving notification. Tenant administrators will also receive breach notifications and should similarly be aware of the controller’s requirements under GDPR.</span></span>

-   <span data-ttu-id="e2797-p119">在 AAD 入口網站中輸入隱私權連絡人的電子郵件地址。如果未提供「全域隱私權連絡人」資訊，則 Microsoft 只會通知租用戶系統管理員</span><span class="sxs-lookup"><span data-stu-id="e2797-p119">Enter the privacy contact’s e-mail address into the AAD portal. If no Global Privacy Contact information is provided, Microsoft will only notify the tenant administrator</span></span>
- <!-- note that there is missing text clipped from the original Word doc -->
