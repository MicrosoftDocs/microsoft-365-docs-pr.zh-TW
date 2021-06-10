---
title: 偵測並修復 Outlook 規則和自訂表單注入攻擊。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203653"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="694f8-103">偵測和修正 Outlook 規則和自訂表單注入攻擊</span><span class="sxs-lookup"><span data-stu-id="694f8-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="694f8-104">**摘要** 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊。</span><span class="sxs-lookup"><span data-stu-id="694f8-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="694f8-105">Outlook 規則和自訂表單植入攻擊是什麼？</span><span class="sxs-lookup"><span data-stu-id="694f8-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="694f8-106">在攻擊者取得組織的存取權之後，他們會嘗試建立 foothold，以在發現之後繼續進行，或回復。</span><span class="sxs-lookup"><span data-stu-id="694f8-106">After an attacker gains access to your organization, they'll try to establish a foothold to stay in or get back in after they've been discovered.</span></span> <span data-ttu-id="694f8-107">此活動稱為 *建立持續性機制*。</span><span class="sxs-lookup"><span data-stu-id="694f8-107">This activity is called *establishing a persistence mechanism*.</span></span> <span data-ttu-id="694f8-108">攻擊者可使用 Outlook 建立持續性機制的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="694f8-108">There are two ways that an attacker can use Outlook to establish a persistence mechanism:</span></span>

- <span data-ttu-id="694f8-109">利用 Outlook 規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-109">By exploiting Outlook rules.</span></span>
- <span data-ttu-id="694f8-110">將自訂表單插入 Outlook。</span><span class="sxs-lookup"><span data-stu-id="694f8-110">By injecting custom forms into Outlook.</span></span>

<span data-ttu-id="694f8-111">重新安裝 Outlook，或甚至為受影響的人員提供新電腦將不會有説明。</span><span class="sxs-lookup"><span data-stu-id="694f8-111">Reinstalling Outlook, or even giving the affected person a new computer won't help.</span></span> <span data-ttu-id="694f8-112">Outlook 的全新安裝會連接至信箱時，所有的規則和表單都會從雲端進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="694f8-112">When the fresh installation of Outlook connects to the mailbox, all rules and forms are synchronized from the cloud.</span></span> <span data-ttu-id="694f8-113">規則或表單通常是用來執行遠端程式碼，並在本機電腦上安裝惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="694f8-113">The rules or forms are typically designed to run remote code and install malware on the local machine.</span></span> <span data-ttu-id="694f8-114">惡意程式碼會竊取認證或執行其他非法活動。</span><span class="sxs-lookup"><span data-stu-id="694f8-114">The malware steals credentials or performs other illicit activity.</span></span>

<span data-ttu-id="694f8-115">好消息是：如果您將 Outlook 用戶端保持在最新版本的狀態，您就不會受到威脅成為目前的威脅 Outlook 用戶端預設會封鎖這兩種機制。</span><span class="sxs-lookup"><span data-stu-id="694f8-115">The good news is: if you keep your Outlook clients patched to the latest version, you aren't vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="694f8-116">攻擊通常遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="694f8-116">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="694f8-117">**規則會利用** 下列專案：</span><span class="sxs-lookup"><span data-stu-id="694f8-117">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="694f8-118">攻擊者竊取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="694f8-118">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="694f8-119">攻擊者會登入該使用者的 Exchange 信箱 (Exchange Online 或內部部署 Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="694f8-119">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="694f8-120">攻擊者會在信箱中建立轉接收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-120">The attacker creates a forwarding Inbox rule in the mailbox.</span></span> <span data-ttu-id="694f8-121">當信箱收到符合規則條件的特定郵件時，就會觸發轉寄規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-121">The forwarding rule is triggered when the mailbox receives a specific message from the attacker that matches the conditions of the rule.</span></span> <span data-ttu-id="694f8-122">規則條件和郵件格式是針對彼此進行量身定制的。</span><span class="sxs-lookup"><span data-stu-id="694f8-122">The rule conditions and message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="694f8-123">攻擊者會將觸發器電子郵件傳送至已遭破壞的信箱，而該信箱仍是由使用者無意中使用。</span><span class="sxs-lookup"><span data-stu-id="694f8-123">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="694f8-124">當信箱收到符合規則條件的郵件時，就會套用規則的動作。</span><span class="sxs-lookup"><span data-stu-id="694f8-124">When the mailbox receives a message that matches the conditions of rule, the action of the rule is applied.</span></span> <span data-ttu-id="694f8-125">一般來說，規則動作是要在遠端 (WebDAV) 伺服器上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="694f8-125">Typically, the rule action is to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="694f8-126">通常，應用程式會在使用者的電腦上安裝惡意程式碼 (例如， [PowerShell Empire](https://www.powershellempire.com/)) 。</span><span class="sxs-lookup"><span data-stu-id="694f8-126">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="694f8-127">惡意程式碼可讓攻擊者) 使用者的使用者名稱和密碼或本機電腦上的其他認證，以及執行其他惡意活動，以竊取 (或竊取。</span><span class="sxs-lookup"><span data-stu-id="694f8-127">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="694f8-128">**表單利用** 方式：</span><span class="sxs-lookup"><span data-stu-id="694f8-128">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="694f8-129">攻擊者竊取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="694f8-129">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="694f8-130">攻擊者會登入該使用者的 Exchange 信箱 (Exchange Online 或內部部署 Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="694f8-130">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="694f8-131">攻擊者會將自訂的郵件表單範本插入使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="694f8-131">The attacker inserts a custom mail form template into the user's mailbox.</span></span> <span data-ttu-id="694f8-132">當信箱從需要信箱載入自訂表單的攻擊者接收特定郵件時，就會觸發自訂表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-132">The custom form is triggered when the mailbox receives a specific message from the attacker that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="694f8-133">自訂表單和郵件格式是針對彼此進行量身定制。</span><span class="sxs-lookup"><span data-stu-id="694f8-133">The custom form and the message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="694f8-134">攻擊者會將觸發器電子郵件傳送至已遭破壞的信箱，而該信箱仍是由使用者無意中使用。</span><span class="sxs-lookup"><span data-stu-id="694f8-134">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="694f8-135">當信箱收到郵件時，信箱會載入所需的表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-135">When the mailbox receives the message, the mailbox loads the required form.</span></span> <span data-ttu-id="694f8-136">表單會在遠端 (WebDAV) 伺服器上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="694f8-136">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="694f8-137">通常，應用程式會在使用者的電腦上安裝惡意程式碼 (例如， [PowerShell Empire](https://www.powershellempire.com/)) 。</span><span class="sxs-lookup"><span data-stu-id="694f8-137">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="694f8-138">惡意程式碼可讓攻擊者) 使用者的使用者名稱和密碼或本機電腦上的其他認證，以及執行其他惡意活動，以竊取 (或竊取。</span><span class="sxs-lookup"><span data-stu-id="694f8-138">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="694f8-139">規則和自訂表單植入攻擊的外觀可能如 Office 365 所示？</span><span class="sxs-lookup"><span data-stu-id="694f8-139">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="694f8-140">您的使用者可能會注意到這些持續性機制，但在某些情況下，您可能會看不到這些功能。</span><span class="sxs-lookup"><span data-stu-id="694f8-140">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="694f8-141">本文將告訴您如何在下面列出的任何 (的威脅) 中尋找7號徵兆。</span><span class="sxs-lookup"><span data-stu-id="694f8-141">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="694f8-142">如果您找到上述任一項，您必須採取補救步驟。</span><span class="sxs-lookup"><span data-stu-id="694f8-142">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="694f8-143">**規則受損的** 指標：</span><span class="sxs-lookup"><span data-stu-id="694f8-143">**Indicators of the Rules compromise**:</span></span>
  - <span data-ttu-id="694f8-144">規則動作是要啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="694f8-144">Rule Action is to start an application.</span></span>
  - <span data-ttu-id="694f8-145">規則參照 EXE、ZIP 或 URL。</span><span class="sxs-lookup"><span data-stu-id="694f8-145">Rule References an EXE, ZIP, or URL.</span></span>
  - <span data-ttu-id="694f8-146">在本機電腦上，尋找來自 Outlook PID 的新進程開始。</span><span class="sxs-lookup"><span data-stu-id="694f8-146">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="694f8-147">**自訂表單受損的** 指標：</span><span class="sxs-lookup"><span data-stu-id="694f8-147">**Indicators of the Custom forms compromise**:</span></span>
  - <span data-ttu-id="694f8-148">顯示的自訂表單會另存為自己的郵件類別。</span><span class="sxs-lookup"><span data-stu-id="694f8-148">Custom forms present saved as their own message class.</span></span>
  - <span data-ttu-id="694f8-149">郵件類別包含可執行程式碼。</span><span class="sxs-lookup"><span data-stu-id="694f8-149">Message class contains executable code.</span></span>
  - <span data-ttu-id="694f8-150">通常，惡意表單會儲存在個人表單文件庫或 [收件匣] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="694f8-150">Typically, malicious forms are stored in Personal Forms Library or Inbox folders.</span></span>
  - <span data-ttu-id="694f8-151">表單命名為 IPM。注意。[custom name]。</span><span class="sxs-lookup"><span data-stu-id="694f8-151">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="694f8-152">尋找此攻擊之徵兆及確認的步驟</span><span class="sxs-lookup"><span data-stu-id="694f8-152">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="694f8-153">您可以使用下列其中一種方法來確認攻擊：</span><span class="sxs-lookup"><span data-stu-id="694f8-153">You can use either of the following methods to confirm the attack:</span></span>

- <span data-ttu-id="694f8-154">使用 Outlook 用戶端，手動檢查每個信箱的規則和表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-154">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="694f8-155">這個方法是完整的，但是您一次只能檢查一個信箱。</span><span class="sxs-lookup"><span data-stu-id="694f8-155">This method is thorough, but you can only check one mailbox at a time.</span></span> <span data-ttu-id="694f8-156">如果您有許多使用者要檢查，而且也可能會感染您所使用的電腦，則此方法可能會非常耗時。</span><span class="sxs-lookup"><span data-stu-id="694f8-156">This method can be very time consuming if you have many users to check, and might also infect the computer that you're using.</span></span>

- <span data-ttu-id="694f8-157">使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 腳本自動為您租使用者中的所有使用者轉儲所有的郵件轉寄規則和自訂表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-157">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="694f8-158">這是最快且最安全的方法，最少量的開銷。</span><span class="sxs-lookup"><span data-stu-id="694f8-158">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="694f8-159">使用 Outlook 用戶端確認規則攻擊</span><span class="sxs-lookup"><span data-stu-id="694f8-159">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="694f8-160">以使用者身分開啟使用者 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="694f8-160">Open the users Outlook client as the user.</span></span> <span data-ttu-id="694f8-161">使用者可能需要協助您檢查其信箱上的規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-161">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="694f8-162">如需如何在 Outlook 中開啟規則介面的程式，請參閱[使用規則文章管理電子郵件訊息](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="694f8-162">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="694f8-163">尋找使用者未建立的規則，或任何未預期的規則或具有可疑名稱的規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-163">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="694f8-164">請參閱規則描述，以取得啟動和應用程式的規則動作，或參考 .EXE、.ZIP 檔案或啟動 URL。</span><span class="sxs-lookup"><span data-stu-id="694f8-164">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="694f8-165">尋找任何開始使用 Outlook 進程識別碼的新程式。</span><span class="sxs-lookup"><span data-stu-id="694f8-165">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="694f8-166">請參閱 [尋找進程識別碼](/windows-hardware/drivers/debugger/finding-the-process-id)。</span><span class="sxs-lookup"><span data-stu-id="694f8-166">Refer to [Find the Process ID](/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="694f8-167">使用 Outlook 用戶端確認表單攻擊的步驟</span><span class="sxs-lookup"><span data-stu-id="694f8-167">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="694f8-168">以使用者身分開啟使用者 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="694f8-168">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="694f8-169">遵循中的步驟，顯示使用者 Outlook 版本的[[開發人員]](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)索引標籤。</span><span class="sxs-lookup"><span data-stu-id="694f8-169">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the user's version of Outlook.</span></span>

3. <span data-ttu-id="694f8-170">在 Outlook 中開啟 [目前可見的開發人員] 索引標籤，然後按一下 [**設計表單**]</span><span class="sxs-lookup"><span data-stu-id="694f8-170">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="694f8-171">從 [**查找範圍**] 清單中選取 [**收件** 匣]。</span><span class="sxs-lookup"><span data-stu-id="694f8-171">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="694f8-172">尋找任何自訂表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-172">Look for any custom forms.</span></span> <span data-ttu-id="694f8-173">自訂表單非常少見，如果您有任何自訂表單，則需要更深入的外觀。</span><span class="sxs-lookup"><span data-stu-id="694f8-173">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="694f8-174">調查任何自訂表單，尤其是標示為隱藏的表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-174">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="694f8-175">開啟任何自訂表單，然後在 **表單** 群組中按一下 [ **View Code** ] （查看表單載入時執行的功能）。</span><span class="sxs-lookup"><span data-stu-id="694f8-175">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="694f8-176">使用 PowerShell 確認規則和表單攻擊的步驟</span><span class="sxs-lookup"><span data-stu-id="694f8-176">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="694f8-177">驗證規則或自訂表單攻擊的最簡單方法，就是執行 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script。</span><span class="sxs-lookup"><span data-stu-id="694f8-177">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="694f8-178">此腳本會連接至您租使用者中的每個信箱，並將所有規則和表單轉儲成兩個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="694f8-178">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="694f8-179">先決條件</span><span class="sxs-lookup"><span data-stu-id="694f8-179">Pre-requisites</span></span>

<span data-ttu-id="694f8-180">您必須具有全域系統管理員許可權，才能執行腳本，因為腳本會連接到租用中的每個信箱，以讀取規則和表單。</span><span class="sxs-lookup"><span data-stu-id="694f8-180">You will need to have global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="694f8-181">以本機系統管理員許可權登入您將執行腳本的電腦。</span><span class="sxs-lookup"><span data-stu-id="694f8-181">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="694f8-182">將 Get-AllTenantRulesAndForms.ps1 腳本從 GitHub 下載或複製到要從中執行它的資料夾。</span><span class="sxs-lookup"><span data-stu-id="694f8-182">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="694f8-183">腳本會為此資料夾建立兩個日期戳檔案，MailboxFormsExport-yyyy-mm-dd.csv 和 MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="694f8-183">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="694f8-184">以系統管理員身分開啟 PowerShell 實例，然後開啟您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="694f8-184">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="694f8-185">依下列方式執行此 PowerShell 命令列 `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="694f8-185">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="694f8-186">解讀輸出</span><span class="sxs-lookup"><span data-stu-id="694f8-186">Interpreting the output</span></span>

- <span data-ttu-id="694f8-187">**MailboxRulesExport-*年月*.csv**：檢查每個資料列 (一個規則，) 包含應用程式或可執行檔的動作條件：</span><span class="sxs-lookup"><span data-stu-id="694f8-187">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="694f8-188">**ActionType (欄位 A)**：如果看到值 "ID_ACTION_CUSTOM"，該規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="694f8-188">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="694f8-189">**IsPotentiallyMalicious (欄)**：如果此值為 "TRUE"，則此規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="694f8-189">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="694f8-190">**ActionCommand (Column G)**：如果此欄列出的應用程式或任何具有 .exe 或 .zip 副檔名的檔案，或是參照 URL 的未知專案，則該規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="694f8-190">**ActionCommand (column G)**: If this column lists an application or any file with .exe or .zip extensions, or an unknown entry that refers to a URL, the rule is likely malicious.</span></span>

- <span data-ttu-id="694f8-191">**MailboxFormsExport-*yyyy*.csv**：一般說來，使用自訂表單非常少見。</span><span class="sxs-lookup"><span data-stu-id="694f8-191">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is rare.</span></span> <span data-ttu-id="694f8-192">如果您在此活頁簿中找到任何的，請開啟該使用者的信箱，並檢查該表單本身。</span><span class="sxs-lookup"><span data-stu-id="694f8-192">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="694f8-193">如果您的組織未有意放入該組織，可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="694f8-193">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="694f8-194">如何停止和修正 Outlook 規則和表單攻擊</span><span class="sxs-lookup"><span data-stu-id="694f8-194">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="694f8-195">如果您發現其中任何一種攻擊的證據，修正很簡單，只需要從信箱中刪除規則或表單即可。</span><span class="sxs-lookup"><span data-stu-id="694f8-195">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="694f8-196">您可以使用 Outlook 用戶端或使用遠端 PowerShell 來移除規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-196">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="694f8-197">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="694f8-197">Using Outlook</span></span>

1. <span data-ttu-id="694f8-198">識別使用者與 Outlook 搭配使用的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="694f8-198">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="694f8-199">所有的潛在惡意程式碼都必須清除。</span><span class="sxs-lookup"><span data-stu-id="694f8-199">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="694f8-200">不允許使用者登入並使用電子郵件，直到所有裝置都已清除為止。</span><span class="sxs-lookup"><span data-stu-id="694f8-200">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="694f8-201">依照刪除每個裝置的 [規則](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="694f8-201">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="694f8-202">如果您不確定是否存在其他惡意程式碼，您可以格式化及重新安裝裝置上的所有軟體。</span><span class="sxs-lookup"><span data-stu-id="694f8-202">If you are unsure about the presence of other malware, you can format and reinstall all the software on the device.</span></span> <span data-ttu-id="694f8-203">若為行動裝置，您可以依照製造商的步驟，將裝置重設為出廠影像。</span><span class="sxs-lookup"><span data-stu-id="694f8-203">For mobile devices, you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="694f8-204">安裝最新版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="694f8-204">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="694f8-205">請記住，目前的 Outlook 版本會封鎖這兩種攻擊類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="694f8-205">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="694f8-206">移除信箱的所有離線副本之後，請重設使用者的密碼 (使用高品質的) ，然後在 [未啟用 MFA 的情況下，依照 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) ] 中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="694f8-206">Once all offline copies of the mailbox have been removed, reset the user's password (use a high quality one) and follow the steps in [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled.</span></span> <span data-ttu-id="694f8-207">這可確保使用者的認證不會透過其他方式公開 (例如網路釣魚或密碼重複使用) 。</span><span class="sxs-lookup"><span data-stu-id="694f8-207">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="694f8-208">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="694f8-208">Using PowerShell</span></span>

<span data-ttu-id="694f8-209">您可以使用兩個遠端 PowerShell Cmdlet 來移除或停用危險的規則。</span><span class="sxs-lookup"><span data-stu-id="694f8-209">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="694f8-210">只需遵循步驟。</span><span class="sxs-lookup"><span data-stu-id="694f8-210">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="694f8-211">Exchange server 上之信箱的步驟</span><span class="sxs-lookup"><span data-stu-id="694f8-211">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="694f8-212">使用遠端 PowerShell 連線至 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="694f8-212">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="694f8-213">遵循[連線 Exchange 使用遠端 PowerShell 來伺服器](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)的步驟。</span><span class="sxs-lookup"><span data-stu-id="694f8-213">Follow the steps in [Connect to Exchange servers using remote PowerShell](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="694f8-214">如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="694f8-214">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="694f8-215">如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="694f8-215">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="694f8-216">信箱在 Exchange Online 中的步驟</span><span class="sxs-lookup"><span data-stu-id="694f8-216">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="694f8-217">遵循[連線 Exchange Online 使用 PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="694f8-217">Follow the steps in [Connect to Exchange Online using PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="694f8-218">如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [ [移除收件匣規則](/powershell/module/exchange/Remove-InboxRule) ] Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="694f8-218">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="694f8-219">如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="694f8-219">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="694f8-220">如何最小化未來的攻擊</span><span class="sxs-lookup"><span data-stu-id="694f8-220">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="694f8-221">第一種：保護您的帳戶</span><span class="sxs-lookup"><span data-stu-id="694f8-221">First: protect your accounts</span></span>

<span data-ttu-id="694f8-222">只有在竊取或破壞使用者的帳戶之後，攻擊者才會使用這些規則和表單攻擊。</span><span class="sxs-lookup"><span data-stu-id="694f8-222">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="694f8-223">因此，避免對您的組織使用這些入侵的第一步，是要積極保護您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="694f8-223">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="694f8-224">一些最常見的帳戶破壞方式是透過網路釣魚或 [密碼噴塗攻擊](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。</span><span class="sxs-lookup"><span data-stu-id="694f8-224">Some of the most common ways that accounts are breached are through phishing or [password spray attacks](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/).</span></span>

<span data-ttu-id="694f8-225">保護使用者帳戶的最佳方法（特別是管理員帳戶）是為 [使用者設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="694f8-225">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="694f8-226">您也應該：</span><span class="sxs-lookup"><span data-stu-id="694f8-226">You should also:</span></span>

- <span data-ttu-id="694f8-227">監視如何 [存取及使用](/azure/active-directory/active-directory-view-access-usage-reports)您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="694f8-227">Monitor how your user accounts are [accessed and used](/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="694f8-228">您可能不會防止初始遭到破壞，但是您會儘早偵測，以縮短破壞的持續時間和破壞影響。</span><span class="sxs-lookup"><span data-stu-id="694f8-228">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="694f8-229">您可以使用這些[Office 365 雲端 App 安全性原則](/cloud-app-security/what-is-cloud-app-security)，在不尋常的活動上監視帳戶及警示：</span><span class="sxs-lookup"><span data-stu-id="694f8-229">You can use these [Office 365 Cloud App Security policies](/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="694f8-230">**多個失敗的登入嘗試**：這個原則設定檔您的環境，當使用者在與所學的基準相關的單一會話中執行多個失敗的登入活動時，便會觸發警示，這可能表示企圖遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="694f8-230">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="694f8-231">不 **可能的旅行**：這項原則會在不同位置的相同使用者中偵測到活動時，在兩個位置之間的時間範圍內，以短于預期的旅行時間。</span><span class="sxs-lookup"><span data-stu-id="694f8-231">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="694f8-232">這可能表示不同的使用者使用相同的認證。</span><span class="sxs-lookup"><span data-stu-id="694f8-232">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="694f8-233">偵測到這種反常行為時，會有七天的初始學習週期，以瞭解新使用者的活動模式。</span><span class="sxs-lookup"><span data-stu-id="694f8-233">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="694f8-234">**由使用者) 所 (的特殊模擬活動**：此原則設定檔您的環境，當使用者在與基線獲知相關的單一會話中執行多個類比活動時，便會觸發警示，這可能表示企圖遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="694f8-234">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="694f8-235">使用類似[Office 365 安全評分](https://securescore.office.com/)的工具來管理帳戶安全性設定和行為。</span><span class="sxs-lookup"><span data-stu-id="694f8-235">Use a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="694f8-236">第二：讓 Outlook 的用戶端保持在最新</span><span class="sxs-lookup"><span data-stu-id="694f8-236">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="694f8-237">完全更新及修補的 Outlook 2013 版本，2016預設會停用「啟動應用程式」規則/表單動作。</span><span class="sxs-lookup"><span data-stu-id="694f8-237">Fully updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="694f8-238">這可確保即使攻擊者破壞帳戶，規則和表單動作也會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="694f8-238">This will ensure that even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="694f8-239">您可以遵循[安裝 Office 更新](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)中的步驟，安裝最新的更新及安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="694f8-239">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="694f8-240">以下是 Outlook 2013 和2016用戶端的修補程式版本：</span><span class="sxs-lookup"><span data-stu-id="694f8-240">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="694f8-241">**Outlook 2016**：16.0.4534.1001 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="694f8-241">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="694f8-242">**Outlook 2013**：15.0.4937.1000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="694f8-242">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="694f8-243">如需個別安全性修補程式的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="694f8-243">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="694f8-244">Outlook 2016安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="694f8-244">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="694f8-245">Outlook 2013 安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="694f8-245">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="694f8-246">第三：監視您的 Outlook 用戶端</span><span class="sxs-lookup"><span data-stu-id="694f8-246">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="694f8-247">請注意，即使已安裝修補程式和更新，攻擊者還是可以變更本機電腦設定，以重新啟用「啟動應用程式」行為。</span><span class="sxs-lookup"><span data-stu-id="694f8-247">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="694f8-248">您可以使用 [高級群組原則管理](/microsoft-desktop-optimization-pack/agpm/) ，在用戶端上監視及強制執行本機電腦原則。</span><span class="sxs-lookup"><span data-stu-id="694f8-248">You can use [Advanced Group Policy Management](/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="694f8-249">您可以使用[64 位版本的 Windows](https://support.microsoft.com/help/305097)，查看是否已透過登錄中的覆寫重新啟用「啟動應用程式」的資訊。</span><span class="sxs-lookup"><span data-stu-id="694f8-249">You can see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="694f8-250">請檢查下列子項：</span><span class="sxs-lookup"><span data-stu-id="694f8-250">Check these subkeys:</span></span>

- <span data-ttu-id="694f8-251">**Outlook 2016**：`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="694f8-251">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="694f8-252">**Outlook 2013**：`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="694f8-252">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="694f8-253">尋找機碼 EnableUnsafeClientMailRules。</span><span class="sxs-lookup"><span data-stu-id="694f8-253">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="694f8-254">如果已存在，且已設定為1，則 Outlook 的安全性修補程式已被取代，且電腦受到表單/規則攻擊的影響。</span><span class="sxs-lookup"><span data-stu-id="694f8-254">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="694f8-255">如果值為0，就會停用「啟動應用程式」動作。</span><span class="sxs-lookup"><span data-stu-id="694f8-255">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="694f8-256">如果已安裝更新及修補的 Outlook 版本，但此登錄機碼不存在，系統就不會受到這些攻擊。</span><span class="sxs-lookup"><span data-stu-id="694f8-256">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="694f8-257">使用內部部署 Exchange 安裝的客戶應考慮封鎖沒有可用修補程式的舊 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="694f8-257">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="694f8-258">有關此程式的詳細資訊，請參閱[設定 Outlook 用戶端封鎖](/exchange/configure-outlook-client-blocking-exchange-2013-help)的文章。</span><span class="sxs-lookup"><span data-stu-id="694f8-258">Details on this process can be found in the article [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="694f8-259">像網路安全專業人員一般保護 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="694f8-259">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="694f8-260">您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="694f8-260">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="694f8-261">使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="694f8-261">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="694f8-262">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="694f8-262">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="694f8-263">這類功能會立即生效，對您的使用者影響很小。</span><span class="sxs-lookup"><span data-stu-id="694f8-263">These have immediate effect and are low-impact to your users.</span></span>

- <span data-ttu-id="694f8-264">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="694f8-264">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="694f8-265">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="694f8-265">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="694f8-266">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="694f8-266">Beyond 90 days.</span></span> <span data-ttu-id="694f8-267">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="694f8-267">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="694f8-268">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="694f8-268">See also:</span></span>

- <span data-ttu-id="694f8-269">[惡意 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)SilentBreak 的安全性公告關於規則向量可提供 Outlook 規則的詳細評論。</span><span class="sxs-lookup"><span data-stu-id="694f8-269">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="694f8-270">[MAPI over HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog on Mailrule Pwnage 討論稱為尺規的工具，可讓您透過 Outlook 規則來利用信箱。</span><span class="sxs-lookup"><span data-stu-id="694f8-270">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="694f8-271">Sensepost 博客上有關表單威脅向量的[Outlook 表單和外殼](https://sensepost.com/blog/2017/outlook-forms-and-shells/)。</span><span class="sxs-lookup"><span data-stu-id="694f8-271">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="694f8-272">尺規基本代碼</span><span class="sxs-lookup"><span data-stu-id="694f8-272">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="694f8-273">尺規指標洩露</span><span class="sxs-lookup"><span data-stu-id="694f8-273">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)