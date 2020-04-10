---
title: 當您的網域由 Google 管理時建立 DNS 記錄（eNom）
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: 瞭解如何透過 Google 網域頁面存取 eNom 及建立 DNS。
ms.openlocfilehash: 8fc13ea2ccc7dfee510ef7abb72f88030d048943
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210655"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="70581-103">當您的網域由 Google 管理時建立 DNS 記錄（eNom）</span><span class="sxs-lookup"><span data-stu-id="70581-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="70581-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="70581-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="70581-105">若要將您的郵件帳戶移轉到 Office 365，您需要在您的網域註冊機構建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="70581-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="70581-106">如果您在註冊**Google Apps For Work** account 時透過 google 購買網域，您的 DNS 記錄會由 google 管理，但會向 eNom 註冊。</span><span class="sxs-lookup"><span data-stu-id="70581-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="70581-107">您可以透過 Google**網域**頁面存取 eNom 及建立 DNS。</span><span class="sxs-lookup"><span data-stu-id="70581-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="70581-108">請按照本文所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="70581-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="70581-109">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="70581-109">Create the DNS record</span></span>

1. <span data-ttu-id="70581-110">在[Google 管理主控台](https://www.google.com/work/apps/business)上，選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="70581-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="70581-112">輸入您的功能變數名稱，然後選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="70581-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="70581-114">在頁面底部，選取 [**其他控制項**]。</span><span class="sxs-lookup"><span data-stu-id="70581-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="70581-116">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="70581-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="70581-118">在 [**網域**] 頁面上，選取 [**新增/移除網域**]。</span><span class="sxs-lookup"><span data-stu-id="70581-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="70581-120">在 [**網域**] 頁面上，選取 [**高級 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="70581-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70581-121">如果您在註冊**Google Apps For Work** account 時未透過 Google 購買功能變數名稱，您的**網域**頁面上將不會有**高級 DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="70581-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="70581-122">相反地，您必須直接前往您網域主機的網站以存取您的 DNS 設定，並執行此操作與下列步驟。</span><span class="sxs-lookup"><span data-stu-id="70581-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="70581-123">如需詳細資訊，請參閱[Access G Suite 網域設定](https://support.google.com/a/answer/54693?hl=en)。</span><span class="sxs-lookup"><span data-stu-id="70581-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="70581-125">在 [**高級 DNS 設定**] 頁面上，選取 [登**入 dns 主控台**]。</span><span class="sxs-lookup"><span data-stu-id="70581-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="70581-126">記下登**入名稱**和**密碼**資訊。</span><span class="sxs-lookup"><span data-stu-id="70581-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="70581-127">您在下一個步驟需要用到這些資訊。</span><span class="sxs-lookup"><span data-stu-id="70581-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="70581-129">使用 [**高級 DNS 設定**] 頁面中的登**入名稱**和**密碼**登入 Google**網域管理員**。</span><span class="sxs-lookup"><span data-stu-id="70581-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="70581-131">在 [ ***domain_name*** ] 頁面上的 [**主機記錄**] 區段中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="70581-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="70581-133">在 [**主機記錄**] 區段中，選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="70581-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="70581-135">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="70581-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="70581-136">**主機**</span><span class="sxs-lookup"><span data-stu-id="70581-136">**HOST**</span></span>|<span data-ttu-id="70581-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="70581-137">**TXT VALUE**</span></span>|<span data-ttu-id="70581-138">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="70581-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="70581-139">TXT</span><span class="sxs-lookup"><span data-stu-id="70581-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="70581-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="70581-140">This is an example.</span></span> <span data-ttu-id="70581-141">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="70581-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="70581-142">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="70581-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="70581-143">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="70581-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="70581-145">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="70581-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="70581-p105">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="70581-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
