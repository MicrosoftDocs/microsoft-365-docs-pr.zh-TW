---
title: 自動化事件導向保留
ms.author: laurawi
author: laurawi
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本主題說明如何使用 Microsoft 365 REST API 透過事件進行自動化保留，設定您的商務程序流程。
ms.openlocfilehash: 5977b79c47166fdafc76dfdb122b4fd37b63a875
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38708062"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="ce521-103">自動化事件型保留</span><span class="sxs-lookup"><span data-stu-id="ce521-103">Automate event-based retention</span></span>

<span data-ttu-id="ce521-p101">組織中的內容量暴增，內容逐漸變得冗餘、過時且瑣碎，有關內容的各種問題已經變成一項嚴重的議題。為了持續迎接法律、商務和法規遵循方面的挑戰，組織必須具備保留和保護重要資訊、同時又能快速找出相關內容的能力。將資訊去蕪存菁，只保留重要且相關的資訊將成為企業致勝的關鍵。</span><span class="sxs-lookup"><span data-stu-id="ce521-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="ce521-p102">為此，組織可以利用 Office 365 安全規範中心的保留解決方案。保留解決方案可以使用[保留標籤](labels.md)進行觸發。保留標籤可以[根據特定事件選擇保留期間](event-driven-retention.md)。一般而言，保留期間是依據已知的日期，例如內容的建立日期或上次修改日期。然而，組織也可以要求依據事件的發生進行內容處置，例如員工離開組織 7 年後。</span><span class="sxs-lookup"><span data-stu-id="ce521-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="ce521-p103">為確保內容的處置符合規範，請務必了解事件發生的時間。隨著內容量的迅速暴增，以即時且符合規範的方法保留和處置內容已經演變成一項重大的挑戰。</span><span class="sxs-lookup"><span data-stu-id="ce521-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="ce521-p104">事件型保留可以解決這個問題。本主題說明如何使用 Microsoft 365 REST API 透過事件進行自動化保留，設定您的商務程序流程。</span><span class="sxs-lookup"><span data-stu-id="ce521-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="ce521-116">關於事件型保留</span><span class="sxs-lookup"><span data-stu-id="ce521-116">About event-based retention</span></span>

<span data-ttu-id="ce521-p105">組織的規模可以是小型、中型或大型。每日建立和管理的商務文件、法律文件、員工檔案、合約和產品文件的數量卻是急遽增加。</span><span class="sxs-lookup"><span data-stu-id="ce521-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="ce521-p106">舉例來說，每天有數以百計的員工加入或離開組織，HR 部門依據企業要求不斷地建立、更新或刪除員工相關的文件。這個程序必須針對企業綱要遵循不同的保留原則：</span><span class="sxs-lookup"><span data-stu-id="ce521-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="ce521-p107">**內容的保留期間可以是已知的日期**，例如內容的建立日期、上次修改日期或標籤日期。例如，您可以在文件建立後保留文件七年，然後再刪除文件。</span><span class="sxs-lookup"><span data-stu-id="ce521-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="ce521-p108">**內容的保留期間也可以是未知的日期**。例如，您可以使用保留標籤，將保留期間設定成依據特定類型事件的發生時間，例如員工離開組織。</span><span class="sxs-lookup"><span data-stu-id="ce521-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="ce521-p109">事件會觸發保留期間開始進行。在加上標籤的內容中，所有適用於該事件類型的內容都會強制執行標籤的保留動作。這項功能稱為事件型保留，若要深入了解，請參閱[事件導向保留概觀](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="ce521-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="ce521-128">設定事件型保留</span><span class="sxs-lookup"><span data-stu-id="ce521-128">Set up event-based retention</span></span>

<span data-ttu-id="ce521-129">本節描述保留內容前必須完成的工作。</span><span class="sxs-lookup"><span data-stu-id="ce521-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="ce521-130">識別角色</span><span class="sxs-lookup"><span data-stu-id="ce521-130">Identify roles</span></span>

<span data-ttu-id="ce521-131">找出組織中執行記錄管理工作，負責有效且有效率地保留商務文件的各種角色。</span><span class="sxs-lookup"><span data-stu-id="ce521-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="ce521-132">**角色**</span><span class="sxs-lookup"><span data-stu-id="ce521-132">**Persona**</span></span>| <span data-ttu-id="ce521-133">**Role**</span><span class="sxs-lookup"><span data-stu-id="ce521-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="ce521-134">系統管理</span><span class="sxs-lookup"><span data-stu-id="ce521-134">Admin</span></span> | <span data-ttu-id="ce521-135">在 SharePoint 中建立保留事件類型、保留標籤和記錄存放庫</span><span class="sxs-lookup"><span data-stu-id="ce521-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="ce521-136">記錄管理員</span><span class="sxs-lookup"><span data-stu-id="ce521-136">Records Manager</span></span>                                  | <span data-ttu-id="ce521-137">提供保留原則和保留排程的指引和規範詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce521-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="ce521-138">系統管理員 (企業)</span><span class="sxs-lookup"><span data-stu-id="ce521-138">System Admin (business)</span></span>                          | <span data-ttu-id="ce521-139">設定和管理外部系統以使用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce521-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="ce521-140">資訊工作者</span><span class="sxs-lookup"><span data-stu-id="ce521-140">Information Worker</span></span>                               | <span data-ttu-id="ce521-141">管理商務程序 (HR、財務、IT 等) 的生命週期</span><span class="sxs-lookup"><span data-stu-id="ce521-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="ce521-142">設定安全規範中心</span><span class="sxs-lookup"><span data-stu-id="ce521-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="ce521-143">規範管理員建立事件類型，例如，僱用終止或合約到期或產品製造結束 (請參閱[事件導向保留](event-driven-retention.md)中的逐步程序。</span><span class="sxs-lookup"><span data-stu-id="ce521-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
1. <span data-ttu-id="ce521-144">規範管理員依據事件建立保留標籤，將標籤與事件類型建立相關聯。</span><span class="sxs-lookup"><span data-stu-id="ce521-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="ce521-145">保留標籤有 4 種類型的觸發程序：</span><span class="sxs-lookup"><span data-stu-id="ce521-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="ce521-146">建立日期</span><span class="sxs-lookup"><span data-stu-id="ce521-146">Create date</span></span>
                
    1. <span data-ttu-id="ce521-147">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="ce521-147">Last modified</span></span>
                
    1. <span data-ttu-id="ce521-148">標籤日期 (內容加上標籤的日期)</span><span class="sxs-lookup"><span data-stu-id="ce521-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="ce521-149">事件型</span><span class="sxs-lookup"><span data-stu-id="ce521-149">Event-based</span></span>
    
1. <span data-ttu-id="ce521-150">規範管理員發佈保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ce521-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="ce521-151">設定 SharePoint</span><span class="sxs-lookup"><span data-stu-id="ce521-151">Set up SharePoint</span></span>
   
<span data-ttu-id="ce521-152">若要建立記錄存放庫，規範系統管理員必須：</span><span class="sxs-lookup"><span data-stu-id="ce521-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="ce521-153">建立 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="ce521-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="ce521-154">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="ce521-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="ce521-p110">建立 SharePoint 文件庫。在文件庫層級設定事件型標籤。如需更多資訊，請參閱[將預設的保留標籤套用至 SharePoint 文件庫、資料夾或文件組的所有內容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="ce521-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="ce521-p111">在 SharePoint 中設定文件組。如需更多資訊，請參閱[文件組簡介](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)。</span><span class="sxs-lookup"><span data-stu-id="ce521-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="ce521-p112">指派資產 ID (資產 ID 是組織使用的產品名稱或代碼，例如，員工編號可以是資產 ID) 給每一個員工文件組 (透過指派資產 ID 給資料夾的方式，該資料夾內的每個項目都會自動繼承相同的資產 ID。這意味著所有的項目可以透過相同的事件觸發保留期間。</span><span class="sxs-lookup"><span data-stu-id="ce521-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="ce521-161">觸發事件型保留的方法</span><span class="sxs-lookup"><span data-stu-id="ce521-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="ce521-162">有兩種方法可以觸發事件型保留：</span><span class="sxs-lookup"><span data-stu-id="ce521-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="ce521-p113">**使用系統管理中心介面**這個程序可以用於一次保留較少的內容，或是觸發頻率不高的保留，例如每月或每年的頻率。如需更多有關此方法資訊，請參閱[事件導向保留概觀](event-driven-retention.md)。然而，這個觸發保留的方法可能非常耗時且容易發生錯誤，從而阻礙了保留的擴展性。因此，使用自動化流暢的解決方案進行觸發保留將可以增強資料的安全性與合規性。</span><span class="sxs-lookup"><span data-stu-id="ce521-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="ce521-p114">**使用 M365 REST API**這個程序可以用於一次保留大量內容的時候，和 (或) 觸發頻率高的保留，例如每日或每週的頻率。當偵測到您的商務線系統內發生事件時，流程會接著在安全規範中心內自動建立相關的事件。因此，每次發生事件時，您不需要在使用者介面手動建立事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="ce521-170">有兩個選項可以使用 REST API：</span><span class="sxs-lookup"><span data-stu-id="ce521-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="ce521-p115">**Microsoft Flow 或類似的應用程式**可以用於自動觸發事件的發生。Microsoft Flow 是連線至其他系統的協調器。使用 Microsoft Flow 不需要自訂的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ce521-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="ce521-174">**PowerShell 或 HTTP 用戶端呼叫 REST API**使用 PowerShell (6 或更新版本) 呼叫 Microsoft 365 REST API 建立事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="ce521-p116">Rest API 是支援 HTTP 操作組 (方法) 的服務端點，提供服務資源的建立、擷取、更新、刪除等存取權，如需更多資訊，請參閱 [REST API 要求/回應的元件](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。在這種情況下，透過使用 Microsoft 365 REST API，使用 POST 和 GET 操作 (方法) 可以建立和擷取事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="ce521-177">範例案例</span><span class="sxs-lookup"><span data-stu-id="ce521-177">Example scenarios</span></span>

<span data-ttu-id="ce521-178">讓我們來考慮以下案例。</span><span class="sxs-lookup"><span data-stu-id="ce521-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="ce521-179">案例 1：員工離開組織</span><span class="sxs-lookup"><span data-stu-id="ce521-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="ce521-p117">組織針對每位員工建立和儲存無數的員工相關文件。這些文件會在每位員工的僱用期間內進行管理和保留。然而，當員工離開組織或僱用終止時，組織有義務根據法律和商務要求在約定時間內保留該位員工的文件。</span><span class="sxs-lookup"><span data-stu-id="ce521-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="ce521-183">現在，如果每天有多位員工離開組織，組織每天必須觸發數以千百份文件的保留計時器。</span><span class="sxs-lookup"><span data-stu-id="ce521-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="ce521-p118">除此之外，還要根據員工記錄的類型計算每位離職員工的保留期間，即僱用終止日期加上天數、月數或年數。例如，同一位員工的薪資補償和福利申報可能需要不同的保留期間。</span><span class="sxs-lookup"><span data-stu-id="ce521-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="ce521-p119">下圖顯示多個標籤與單一事件相關聯的情況。在圖中，員工薪資補償標籤下的所有檔案與員工福利標籤下的所有檔案同時與單一事件相關聯，這個單一事件是員工離開組織。這些文件各自有不同的保留計時器。因此，當員工離開組織時，在每一個標籤內的文件會開始經歷不同的保留期間。若要針對每一位員工的每一種文件類型或標籤觸發所有不同的保留計時器，這是一項非常具有挑戰性的任務。請再想像一下，為多位員工執行這項任務的情形。</span><span class="sxs-lookup"><span data-stu-id="ce521-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![事件類型、事件和標籤的圖表](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="ce521-193">因此，以自動化程序針對多位員工觸發不同的保留計時器不僅節省時間、減少錯誤，而且非常有效率。</span><span class="sxs-lookup"><span data-stu-id="ce521-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="ce521-194">**針對這個案例設定自動化事件型保留：**</span><span class="sxs-lookup"><span data-stu-id="ce521-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![員工離開組織案例的角色和動作圖表](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="ce521-196">管理員在文件組建立員工資料夾，例如李莉華、王立民。</span><span class="sxs-lookup"><span data-stu-id="ce521-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="ce521-197">管理員將員工檔案新增至每一位員工的員工資料夾，例如福利、薪水、員工的薪資補償</span><span class="sxs-lookup"><span data-stu-id="ce521-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="ce521-198">管理員指派資產 ID 至每一個員工資料夾。</span><span class="sxs-lookup"><span data-stu-id="ce521-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="ce521-199">SCC 管理員</span><span class="sxs-lookup"><span data-stu-id="ce521-199">SCC Admin l</span></span>

  - <span data-ttu-id="ce521-200">登入安全規範中心</span><span class="sxs-lookup"><span data-stu-id="ce521-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ce521-201">SCC 管理員會建立員工相關的事件類型，例如「僱用終止」、「僱用員工」事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="ce521-202">SCC 管理員會建立「員工保留」標籤。</span><span class="sxs-lookup"><span data-stu-id="ce521-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="ce521-203">這個「員工保留」標籤可以手動或自動發佈並套用至 SharePoint 中的員工檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="ce521-204">HR 管理系統 (例如 Workday) 可以使用 Microsoft Flow 定期執行管理員工檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="ce521-205">如果員工離開組織，M365 事件型保留 REST API 將會開始特定員工檔案的保留計時器。</span><span class="sxs-lookup"><span data-stu-id="ce521-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="ce521-206">使用 Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="ce521-206">Using Microsoft Flow</span></span>

<span data-ttu-id="ce521-207">步驟 1- 建立流程以使用 Microsoft 365 REST API 建立事件</span><span class="sxs-lookup"><span data-stu-id="ce521-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![使用 Flow 建立事件](media/automate-event-driven-retention-flow-1.png)

![使用流程呼叫 REST API](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="ce521-210">建立事件</span><span class="sxs-lookup"><span data-stu-id="ce521-210">Create an event</span></span>

<span data-ttu-id="ce521-211">呼叫 REST API 的範例程式碼</span><span class="sxs-lookup"><span data-stu-id="ce521-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ce521-212">Method</span><span class="sxs-lookup"><span data-stu-id="ce521-212">Method</span></span></th>
<th><span data-ttu-id="ce521-213">POST</span><span class="sxs-lookup"><span data-stu-id="ce521-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ce521-214">URL</span><span class="sxs-lookup"><span data-stu-id="ce521-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-215">Headers</span><span class="sxs-lookup"><span data-stu-id="ce521-215">Headers</span></span></td>
<td><span data-ttu-id="ce521-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ce521-216">Content-Type</span></span></td>
<td><span data-ttu-id="ce521-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ce521-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce521-218">Body</span><span class="sxs-lookup"><span data-stu-id="ce521-218">Body</span></span></td>
<td><p><span data-ttu-id="ce521-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="ce521-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="ce521-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="ce521-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="ce521-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="ce521-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="ce521-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="ce521-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="ce521-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="ce521-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="ce521-227">&lt;d:Name&gt;僱用終止 &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="ce521-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="ce521-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="ce521-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="ce521-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="ce521-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="ce521-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-234">驗證</span><span class="sxs-lookup"><span data-stu-id="ce521-234">Authentication</span></span></td>
<td><span data-ttu-id="ce521-235">基本</span><span class="sxs-lookup"><span data-stu-id="ce521-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce521-236">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="ce521-236">Username</span></span></td>
<td><span data-ttu-id="ce521-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ce521-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-238">密碼</span><span class="sxs-lookup"><span data-stu-id="ce521-238">Password</span></span></td>
<td><span data-ttu-id="ce521-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ce521-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="ce521-240">可用的參數</span><span class="sxs-lookup"><span data-stu-id="ce521-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ce521-241"><strong>參數</strong></span><span class="sxs-lookup"><span data-stu-id="ce521-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="ce521-242"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="ce521-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="ce521-243"><strong>附註</strong></span><span class="sxs-lookup"><span data-stu-id="ce521-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ce521-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="ce521-245">提供事件的唯一名稱，</span><span class="sxs-lookup"><span data-stu-id="ce521-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="ce521-p120">結尾不可有空格以及下列字元：% \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="ce521-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="ce521-249">輸入事件類型名稱 (或 Guid)</span><span class="sxs-lookup"><span data-stu-id="ce521-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="ce521-p121">例如：「僱用終止」。事件類型必須與保留標籤相關聯。</span><span class="sxs-lookup"><span data-stu-id="ce521-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce521-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="ce521-253">輸入 ComplianceAssetId: + 員工 ID</span><span class="sxs-lookup"><span data-stu-id="ce521-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="ce521-254">例如：&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="ce521-256">事件的日期和時間</span><span class="sxs-lookup"><span data-stu-id="ce521-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="ce521-257">格式：yyyy-MM-ddTHH:mm:ssZ，例如：</span><span class="sxs-lookup"><span data-stu-id="ce521-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="ce521-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="ce521-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="ce521-259">回應碼</span><span class="sxs-lookup"><span data-stu-id="ce521-259">Response codes</span></span>

| <span data-ttu-id="ce521-260">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="ce521-260">**Response Code**</span></span> | <span data-ttu-id="ce521-261">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce521-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="ce521-262">302</span><span class="sxs-lookup"><span data-stu-id="ce521-262">302</span></span>               | <span data-ttu-id="ce521-263">重新導向</span><span class="sxs-lookup"><span data-stu-id="ce521-263">Redirect</span></span>              |
| <span data-ttu-id="ce521-264">201</span><span class="sxs-lookup"><span data-stu-id="ce521-264">201</span></span>               | <span data-ttu-id="ce521-265">建立時間</span><span class="sxs-lookup"><span data-stu-id="ce521-265">Created</span></span>               |
| <span data-ttu-id="ce521-266">403</span><span class="sxs-lookup"><span data-stu-id="ce521-266">403</span></span>               | <span data-ttu-id="ce521-267">授權失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-267">Authorization Failed</span></span>  |
| <span data-ttu-id="ce521-268">401</span><span class="sxs-lookup"><span data-stu-id="ce521-268">401</span></span>               | <span data-ttu-id="ce521-269">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="ce521-270">依據時間範圍取得事件</span><span class="sxs-lookup"><span data-stu-id="ce521-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ce521-271">Method</span><span class="sxs-lookup"><span data-stu-id="ce521-271">Method</span></span></th>
<th><span data-ttu-id="ce521-272">GET</span><span class="sxs-lookup"><span data-stu-id="ce521-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ce521-273">URL</span><span class="sxs-lookup"><span data-stu-id="ce521-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="ce521-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="ce521-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-275">Headers</span><span class="sxs-lookup"><span data-stu-id="ce521-275">Headers</span></span></td>
<td><span data-ttu-id="ce521-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ce521-276">Content-Type</span></span></td>
<td><span data-ttu-id="ce521-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ce521-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-278">驗證</span><span class="sxs-lookup"><span data-stu-id="ce521-278">Authentication</span></span></td>
<td><span data-ttu-id="ce521-279">基本</span><span class="sxs-lookup"><span data-stu-id="ce521-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce521-280">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="ce521-280">Username</span></span></td>
<td><span data-ttu-id="ce521-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ce521-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce521-282">密碼</span><span class="sxs-lookup"><span data-stu-id="ce521-282">Password</span></span></td>
<td><span data-ttu-id="ce521-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ce521-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="ce521-284">回應碼</span><span class="sxs-lookup"><span data-stu-id="ce521-284">Response codes</span></span>

| <span data-ttu-id="ce521-285">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="ce521-285">**Response Code**</span></span> | <span data-ttu-id="ce521-286">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce521-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="ce521-287">200</span><span class="sxs-lookup"><span data-stu-id="ce521-287">200</span></span>               | <span data-ttu-id="ce521-288">好的，以 atom+ xml 格式列出事件清單</span><span class="sxs-lookup"><span data-stu-id="ce521-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="ce521-289">404</span><span class="sxs-lookup"><span data-stu-id="ce521-289">404</span></span>               | <span data-ttu-id="ce521-290">找不到</span><span class="sxs-lookup"><span data-stu-id="ce521-290">Not found</span></span>                         |
| <span data-ttu-id="ce521-291">302</span><span class="sxs-lookup"><span data-stu-id="ce521-291">302</span></span>               | <span data-ttu-id="ce521-292">重新導向</span><span class="sxs-lookup"><span data-stu-id="ce521-292">Redirect</span></span>                          |
| <span data-ttu-id="ce521-293">401</span><span class="sxs-lookup"><span data-stu-id="ce521-293">401</span></span>               | <span data-ttu-id="ce521-294">授權失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-294">Authorization Failed</span></span>              |
| <span data-ttu-id="ce521-295">403</span><span class="sxs-lookup"><span data-stu-id="ce521-295">403</span></span>               | <span data-ttu-id="ce521-296">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="ce521-297">依 ID 取得事件</span><span class="sxs-lookup"><span data-stu-id="ce521-297">Get an event by ID</span></span>

| <span data-ttu-id="ce521-298">Method</span><span class="sxs-lookup"><span data-stu-id="ce521-298">Method</span></span>         | <span data-ttu-id="ce521-299">GET</span><span class="sxs-lookup"><span data-stu-id="ce521-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="ce521-300">URL</span><span class="sxs-lookup"><span data-stu-id="ce521-300">URL</span></span>            | <span data-ttu-id="ce521-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="ce521-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="ce521-302">Header</span><span class="sxs-lookup"><span data-stu-id="ce521-302">Header</span></span>         | <span data-ttu-id="ce521-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ce521-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="ce521-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ce521-304">application/atom+xml</span></span> |
| <span data-ttu-id="ce521-305">驗證</span><span class="sxs-lookup"><span data-stu-id="ce521-305">Authentication</span></span> | <span data-ttu-id="ce521-306">基本</span><span class="sxs-lookup"><span data-stu-id="ce521-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="ce521-307">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="ce521-307">Username</span></span>       | <span data-ttu-id="ce521-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ce521-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="ce521-309">密碼</span><span class="sxs-lookup"><span data-stu-id="ce521-309">Password</span></span>       | <span data-ttu-id="ce521-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ce521-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="ce521-311">回應碼</span><span class="sxs-lookup"><span data-stu-id="ce521-311">Response codes</span></span>

| <span data-ttu-id="ce521-312">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="ce521-312">**Response Code**</span></span> | <span data-ttu-id="ce521-313">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce521-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ce521-314">200</span><span class="sxs-lookup"><span data-stu-id="ce521-314">200</span></span>               | <span data-ttu-id="ce521-315">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="ce521-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ce521-316">404</span><span class="sxs-lookup"><span data-stu-id="ce521-316">404</span></span>               | <span data-ttu-id="ce521-317">找不到</span><span class="sxs-lookup"><span data-stu-id="ce521-317">Not found</span></span>                                            |
| <span data-ttu-id="ce521-318">302</span><span class="sxs-lookup"><span data-stu-id="ce521-318">302</span></span>               | <span data-ttu-id="ce521-319">重新導向</span><span class="sxs-lookup"><span data-stu-id="ce521-319">Redirect</span></span>                                             |
| <span data-ttu-id="ce521-320">401</span><span class="sxs-lookup"><span data-stu-id="ce521-320">401</span></span>               | <span data-ttu-id="ce521-321">授權失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ce521-322">403</span><span class="sxs-lookup"><span data-stu-id="ce521-322">403</span></span>               | <span data-ttu-id="ce521-323">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="ce521-324">依名稱取得事件</span><span class="sxs-lookup"><span data-stu-id="ce521-324">Get an event by name</span></span>

| <span data-ttu-id="ce521-325">Method</span><span class="sxs-lookup"><span data-stu-id="ce521-325">Method</span></span>         | <span data-ttu-id="ce521-326">GET</span><span class="sxs-lookup"><span data-stu-id="ce521-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="ce521-327">URL</span><span class="sxs-lookup"><span data-stu-id="ce521-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="ce521-328">Headers</span><span class="sxs-lookup"><span data-stu-id="ce521-328">Headers</span></span>        | <span data-ttu-id="ce521-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ce521-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="ce521-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ce521-330">application/atom+xml</span></span> |
| <span data-ttu-id="ce521-331">驗證</span><span class="sxs-lookup"><span data-stu-id="ce521-331">Authentication</span></span> | <span data-ttu-id="ce521-332">基本</span><span class="sxs-lookup"><span data-stu-id="ce521-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="ce521-333">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="ce521-333">Username</span></span>       | <span data-ttu-id="ce521-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ce521-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="ce521-335">密碼</span><span class="sxs-lookup"><span data-stu-id="ce521-335">Password</span></span>       | <span data-ttu-id="ce521-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ce521-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="ce521-337">回應碼</span><span class="sxs-lookup"><span data-stu-id="ce521-337">Response codes</span></span>

| <span data-ttu-id="ce521-338">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="ce521-338">**Response Code**</span></span> | <span data-ttu-id="ce521-339">**描述**</span><span class="sxs-lookup"><span data-stu-id="ce521-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ce521-340">200</span><span class="sxs-lookup"><span data-stu-id="ce521-340">200</span></span>               | <span data-ttu-id="ce521-341">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="ce521-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ce521-342">404</span><span class="sxs-lookup"><span data-stu-id="ce521-342">404</span></span>               | <span data-ttu-id="ce521-343">找不到</span><span class="sxs-lookup"><span data-stu-id="ce521-343">Not found</span></span>                                            |
| <span data-ttu-id="ce521-344">302</span><span class="sxs-lookup"><span data-stu-id="ce521-344">302</span></span>               | <span data-ttu-id="ce521-345">重新導向</span><span class="sxs-lookup"><span data-stu-id="ce521-345">Redirect</span></span>                                             |
| <span data-ttu-id="ce521-346">401</span><span class="sxs-lookup"><span data-stu-id="ce521-346">401</span></span>               | <span data-ttu-id="ce521-347">授權失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ce521-348">403</span><span class="sxs-lookup"><span data-stu-id="ce521-348">403</span></span>               | <span data-ttu-id="ce521-349">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="ce521-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="ce521-350">使用 PowerShell (6 或更新版本) 或任何 HTTP 用戶端</span><span class="sxs-lookup"><span data-stu-id="ce521-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="ce521-351">步驟 1：連線至 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ce521-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="ce521-352">步驟 2：執行下列指令碼。</span><span class="sxs-lookup"><span data-stu-id="ce521-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce521-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="ce521-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="ce521-354">$userName = &quot;使用者名稱&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="ce521-355">$password = &quot;密碼&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="ce521-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="ce521-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="ce521-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="ce521-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="ce521-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="ce521-359">Write-Host &quot;開始建立下列名稱的事件：$EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="ce521-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="ce521-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="ce521-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="ce521-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="ce521-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="ce521-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="ce521-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="ce521-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="ce521-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="ce521-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="ce521-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="ce521-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="ce521-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="ce521-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="ce521-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="ce521-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="ce521-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="ce521-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="ce521-374">$event = $null</span></span></p>
<p><span data-ttu-id="ce521-375">try</span><span class="sxs-lookup"><span data-stu-id="ce521-375">try</span></span></p>
<p><span data-ttu-id="ce521-376">{</span><span class="sxs-lookup"><span data-stu-id="ce521-376">{</span></span></p>
<p><span data-ttu-id="ce521-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="ce521-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="ce521-378">}</span><span class="sxs-lookup"><span data-stu-id="ce521-378">}</span></span></p>
<p><span data-ttu-id="ce521-379">catch</span><span class="sxs-lookup"><span data-stu-id="ce521-379">catch</span></span></p>
<p><span data-ttu-id="ce521-380">{</span><span class="sxs-lookup"><span data-stu-id="ce521-380">{</span></span></p>
<p><span data-ttu-id="ce521-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="ce521-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="ce521-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="ce521-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="ce521-383">{</span><span class="sxs-lookup"><span data-stu-id="ce521-383">{</span></span></p>
<p><span data-ttu-id="ce521-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="ce521-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="ce521-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="ce521-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="ce521-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="ce521-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="ce521-387">}</span><span class="sxs-lookup"><span data-stu-id="ce521-387">}</span></span></p>
<p><span data-ttu-id="ce521-388">}</span><span class="sxs-lookup"><span data-stu-id="ce521-388">}</span></span></p>
<p><span data-ttu-id="ce521-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="ce521-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="ce521-390">確認兩個選項的結果</span><span class="sxs-lookup"><span data-stu-id="ce521-390">Verify the outcome in both options</span></span>

<span data-ttu-id="ce521-391">步驟 1：前往安全規範中心</span><span class="sxs-lookup"><span data-stu-id="ce521-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="ce521-392">步驟 2：按一下 [資料控管] 下的 [事件]</span><span class="sxs-lookup"><span data-stu-id="ce521-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="ce521-393">步驟 3：確認已建立 [事件]。</span><span class="sxs-lookup"><span data-stu-id="ce521-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="ce521-394">同樣地，上述自動化事件型保留的選項也可以用於下列案例。</span><span class="sxs-lookup"><span data-stu-id="ce521-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="ce521-395">案例 2：合約到期</span><span class="sxs-lookup"><span data-stu-id="ce521-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="ce521-p122">組織與客戶、供應商和合作夥伴間的單一合約可以有多筆記錄。這些文件可以存放在如 SharePoint 的文件庫中。合約的結束決定與合約相關聯文件保留期間的開始。例如，所有與合約相關的記錄必須自合約到期日開始保留五年。觸發五年保留期間的事件就是合約到期。</span><span class="sxs-lookup"><span data-stu-id="ce521-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="ce521-401">客戶關係管理 (CRM) 系統可以使用 Microsoft 365 並觸發合約文件的保留</span><span class="sxs-lookup"><span data-stu-id="ce521-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="ce521-402">**針對這個案例設定自動化事件型保留：**</span><span class="sxs-lookup"><span data-stu-id="ce521-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![合約到期案例的角色和工作圖表](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="ce521-404">管理員針對每一種合約類型使用各種資料夾建立 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="ce521-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="ce521-405">系統管理員將合約檔案 (例如授權合約、開發合約) 新增至每一個合約資料夾</span><span class="sxs-lookup"><span data-stu-id="ce521-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="ce521-406">管理員指派資產 ID 至每一個合約資料夾</span><span class="sxs-lookup"><span data-stu-id="ce521-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="ce521-407">SCC 管理員登入安全規範中心</span><span class="sxs-lookup"><span data-stu-id="ce521-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ce521-408">SCC 管理員會建立合約相關的事件類型，例如「合約建立日」、「合約到期日」事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="ce521-409">SCC 管理員會建立「合約到期日」標籤。</span><span class="sxs-lookup"><span data-stu-id="ce521-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="ce521-410">這個「合約到期」標籤可以手動或自動發佈並套用至 SharePoint 中的合約檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="ce521-411">合約管理系統可以使用 Microsoft Flow 或類似的應用程式進行定期執行管理合約檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="ce521-412">如果合約到期，Microsoft Flow 將會觸發 M365 事件型保留 REST API，開始特定合約檔案的保留計時器。</span><span class="sxs-lookup"><span data-stu-id="ce521-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="ce521-413">案例 3：產品製造結束</span><span class="sxs-lookup"><span data-stu-id="ce521-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="ce521-p123">生產各種產品線的製造公司建立許多製造規格和價格文件。當產品不再製造時，所有連結至這個產品的規格和文件都必須在產品存留期結束後保留一段特定的時間。</span><span class="sxs-lookup"><span data-stu-id="ce521-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="ce521-416">企業資源規劃 (ERP) 系統可以使用 Microsoft 365 和 Microsoft Flow 觸發保留。</span><span class="sxs-lookup"><span data-stu-id="ce521-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="ce521-417">**針對這個案例設定自動化事件型保留：**</span><span class="sxs-lookup"><span data-stu-id="ce521-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![產品生命週期案例的角色和工作圖表](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="ce521-419">管理員在文件組建立產品資料夾，例如產品 1、產品 2 等。</span><span class="sxs-lookup"><span data-stu-id="ce521-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="ce521-420">管理員將產品檔案新增至每一個產品資料夾，例如製造規格、產品價格、產品授權</span><span class="sxs-lookup"><span data-stu-id="ce521-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="ce521-421">管理員指派資產 ID 至每一個產品資料夾。</span><span class="sxs-lookup"><span data-stu-id="ce521-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="ce521-422">SCC 管理員登入安全規範中心</span><span class="sxs-lookup"><span data-stu-id="ce521-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ce521-423">SCC 管理員會建立員工相關的事件類型，例如「產品製造開始」、「產品製造結束」事件。</span><span class="sxs-lookup"><span data-stu-id="ce521-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="ce521-424">SCC 管理員會建立「產品製造結束」標籤。</span><span class="sxs-lookup"><span data-stu-id="ce521-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="ce521-425">這個「產品製造結束」標籤可以手動或自動發佈並套用至 SharePoint 中的產品檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="ce521-426">ERP 系統可以使用 Microsoft Flow 或類似的應用程式進行定期執行管理產品檔案</span><span class="sxs-lookup"><span data-stu-id="ce521-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="ce521-427">如果產品的製造結束，Microsoft Flow 將會觸發 M365 事件型保留 REST API，開始特定產品檔案的保留計時器。</span><span class="sxs-lookup"><span data-stu-id="ce521-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="ce521-428">附錄</span><span class="sxs-lookup"><span data-stu-id="ce521-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="ce521-429">使用重新導向 302 回應結果呼叫 REST API</span><span class="sxs-lookup"><span data-stu-id="ce521-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="ce521-430">使用 REST API URL 叫用 POST 保留事件呼叫<https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (需要全域管理員權限)</span><span class="sxs-lookup"><span data-stu-id="ce521-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="ce521-p124">檢查回應碼。如果是 302，則從回應標頭的 Location 屬性取得重新導向的 URL</span><span class="sxs-lookup"><span data-stu-id="ce521-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="ce521-433">使用重新導向的 URL 再次叫用 POST 保留事件呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce521-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="ce521-434">參與名單</span><span class="sxs-lookup"><span data-stu-id="ce521-434">Credits</span></span>

<span data-ttu-id="ce521-435">本主題的檢閱者：</span><span class="sxs-lookup"><span data-stu-id="ce521-435">This topic was reviewed by:</span></span>

<span data-ttu-id="ce521-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="ce521-436">Antonio Maio</span></span><br/><span data-ttu-id="ce521-437">Microsoft Office Apps and Services MVP</span><span class="sxs-lookup"><span data-stu-id="ce521-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="ce521-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="ce521-438">Antonio.Maio@Protiviti.com</span></span>
