---
title: 搭配搭配搭配的 Microsoft Defender 防毒軟體和 Office 365 (包括 OneDrive) 來自勒索軟體和 cyberthreats 的更佳防護
description: Office 365 包括 OneDrive，與 Microsoft Defender 防毒軟體一起 wonderfully。 若要深入瞭解，請閱讀本文。
keywords: windows defender、防毒軟體、office 365、onedrive、還原、勒索軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41f22375aa117ba617eae59d4b8e9f8bb15ad4f0
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764096"
---
# <a name="better-together-microsoft-defender-antivirus-and-office-365"></a><span data-ttu-id="40c3b-105">更好搭配： Microsoft Defender 防病毒和 Office 365</span><span class="sxs-lookup"><span data-stu-id="40c3b-105">Better together: Microsoft Defender Antivirus and Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="40c3b-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="40c3b-106">**Applies to:**</span></span>
- [<span data-ttu-id="40c3b-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40c3b-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="40c3b-108">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="40c3b-108">Microsoft Defender Antivirus</span></span>
- <span data-ttu-id="40c3b-109">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="40c3b-109">Microsoft 365</span></span>

<span data-ttu-id="40c3b-110">您可能已經知道：</span><span class="sxs-lookup"><span data-stu-id="40c3b-110">You might already know that:</span></span>

- <span data-ttu-id="40c3b-111">**Microsoft Defender 防毒軟體會保護您的 Windows 10 裝置免受軟體威脅（如病毒、惡意程式碼和間諜** 軟體）的威脅。</span><span class="sxs-lookup"><span data-stu-id="40c3b-111">**Microsoft Defender Antivirus protects your Windows 10 device from software threats, such as viruses, malware, and spyware**.</span></span> <span data-ttu-id="40c3b-112">Microsoft Defender 防毒軟體是 Windows 10 中內建的完整、持續的保護，可供您開始。</span><span class="sxs-lookup"><span data-stu-id="40c3b-112">Microsoft Defender Antivirus is your complete, ongoing protection, built into Windows 10 and ready to go.</span></span> <span data-ttu-id="40c3b-113">[Microsoft Defender 防病毒是您的下一代保護](./microsoft-defender-antivirus-in-windows-10.md)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-113">[Microsoft Defender Antivirus is your next-generation protection](./microsoft-defender-antivirus-in-windows-10.md).</span></span> 

- <span data-ttu-id="40c3b-114">**Office 365 包括 antiphishing、反垃圾郵件和反惡意程式碼保護**。</span><span class="sxs-lookup"><span data-stu-id="40c3b-114">**Office 365 includes antiphishing, antispam, and antimalware protection**.</span></span> <span data-ttu-id="40c3b-115">透過 Office 365 訂閱，您可以透過 OneDrive) ，取得高品質的電子郵件和行事曆、Office app、1 TB 的雲端儲存區 (，以及跨所有裝置的高級安全性。</span><span class="sxs-lookup"><span data-stu-id="40c3b-115">With your Office 365 subscription, you get premium email and calendars, Office apps, 1 TB of cloud storage (via OneDrive), and advanced security across all your devices.</span></span> <span data-ttu-id="40c3b-116">這適用于家用和商務使用者。</span><span class="sxs-lookup"><span data-stu-id="40c3b-116">This is true for home and business users.</span></span> <span data-ttu-id="40c3b-117">而且，如果您是企業使用者，而且您的組織使用的是 Office 365 E5，您可以透過 Microsoft Defender for Office 365 來更進一步防護， [以防範 office 365 的威脅](/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-117">And if you're a business user, and your organization is using Office 365 E5, you get even more protection through Microsoft Defender for Office 365 [Protect against threats with Office 365](/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

- <span data-ttu-id="40c3b-118">**OneDrive （包含在 Office 365 中），可讓您線上儲存檔案和資料夾，並視您的顯示加以共用**。</span><span class="sxs-lookup"><span data-stu-id="40c3b-118">**OneDrive, included in Office 365, enables you to store your files and folders online, and share them as you see fit**.</span></span> <span data-ttu-id="40c3b-119">您可以搭配 (用於工作或趣味) 的人員，以及儲存在 OneDrive 中的 coauthor 檔案。</span><span class="sxs-lookup"><span data-stu-id="40c3b-119">You can work together with people (for work or fun), and coauthor files that are stored in OneDrive.</span></span> <span data-ttu-id="40c3b-120">您也可以在所有裝置中存取您的檔案， (電腦、電話及平板電腦) 。</span><span class="sxs-lookup"><span data-stu-id="40c3b-120">You can also access your files across all your devices (your PC, phone, and tablet).</span></span> <span data-ttu-id="40c3b-121">[在 OneDrive 中管理共用](/OneDrive/manage-sharing)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-121">[Manage sharing in OneDrive](/OneDrive/manage-sharing).</span></span>

<span data-ttu-id="40c3b-122">**不過，您知道使用 Microsoft Defender 防毒軟體搭配 Office 365，是否有合理的安全性理由**？</span><span class="sxs-lookup"><span data-stu-id="40c3b-122">**But did you know there are good security reasons to use Microsoft Defender Antivirus together with Office 365**?</span></span> <span data-ttu-id="40c3b-123">這裡有兩個範例︰</span><span class="sxs-lookup"><span data-stu-id="40c3b-123">Here are two:</span></span>

 1. <span data-ttu-id="40c3b-124">[您取得勒索軟體保護和](#ransomware-protection-and-recovery)復原。</span><span class="sxs-lookup"><span data-stu-id="40c3b-124">[You get ransomware protection and recovery](#ransomware-protection-and-recovery).</span></span>

 2. <span data-ttu-id="40c3b-125">[整合意味著更好的保護](#integration-means-better-protection)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-125">[Integration means better protection](#integration-means-better-protection).</span></span>

<span data-ttu-id="40c3b-126">請閱讀下列各節以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="40c3b-126">Read the following sections to learn more.</span></span>

## <a name="ransomware-protection-and-recovery"></a><span data-ttu-id="40c3b-127">勒索軟體防護和修復</span><span class="sxs-lookup"><span data-stu-id="40c3b-127">Ransomware protection and recovery</span></span>

<span data-ttu-id="40c3b-128">當您將檔案儲存為 [OneDrive](/onedrive)，而且 [Microsoft Defender 防病毒](./microsoft-defender-antivirus-in-windows-10.md) 程式會偵測裝置上的勒索軟體威脅時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="40c3b-128">When you save your files to [OneDrive](/onedrive), and [Microsoft Defender Antivirus](./microsoft-defender-antivirus-in-windows-10.md) detects a ransomware threat on your device, the following things occur:</span></span>

1. <span data-ttu-id="40c3b-129">**系統會告訴您威脅**。</span><span class="sxs-lookup"><span data-stu-id="40c3b-129">**You are told about the threat**.</span></span> <span data-ttu-id="40c3b-130"> (如果您的組織使用 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)，也會通知您的安全性作業小組。 ) </span><span class="sxs-lookup"><span data-stu-id="40c3b-130">(If your organization is using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), your security operations team is notified, too.)</span></span>

2. <span data-ttu-id="40c3b-131">**Microsoft Defender 防毒程式可協助您 (和您組織的安全性小組)** 從您的裝置) 中移除勒索軟體 (。</span><span class="sxs-lookup"><span data-stu-id="40c3b-131">**Microsoft Defender Antivirus helps you (and your organization's security team) remove the ransomware** from your device(s).</span></span> <span data-ttu-id="40c3b-132"> (如果您的組織使用 Microsoft Defender for Endpoint，您的安全性作業小組可以判斷其他裝置是否受到感染，也會採取適當的動作。 ) </span><span class="sxs-lookup"><span data-stu-id="40c3b-132">(If your organization is using Microsoft Defender for Endpoint, your security operations team can determine whether other devices are infected and take appropriate action, too.)</span></span>

3. <span data-ttu-id="40c3b-133">**您可以在 OneDrive 中取得復原** 檔案的選項。</span><span class="sxs-lookup"><span data-stu-id="40c3b-133">**You get the option to recover your files in OneDrive**.</span></span> <span data-ttu-id="40c3b-134">透過「OneDrive 檔案還原」功能，您可以將檔案從 OneDrive 復原，直到勒索軟體攻擊發生之前的狀態。</span><span class="sxs-lookup"><span data-stu-id="40c3b-134">With the OneDrive Files Restore feature, you can recover your files in OneDrive to the state they were in before the ransomware attack occurred.</span></span> <span data-ttu-id="40c3b-135">請參閱 [勒索軟體偵測和復原](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-135">See [Ransomware detection and recovering your files](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f).</span></span>

<span data-ttu-id="40c3b-136">請思考這可儲存的時間和麻煩。</span><span class="sxs-lookup"><span data-stu-id="40c3b-136">Think of the time and hassle this can save.</span></span> 

## <a name="integration-means-better-protection"></a><span data-ttu-id="40c3b-137">整合意味著更好的保護</span><span class="sxs-lookup"><span data-stu-id="40c3b-137">Integration means better protection</span></span>

<span data-ttu-id="40c3b-138">Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint 整合意味著您的組織有更好的保護。</span><span class="sxs-lookup"><span data-stu-id="40c3b-138">Microsoft Defender for Office 365 integrated with Microsoft Defender for Endpoint means better protection for your organization.</span></span> <span data-ttu-id="40c3b-139">方法如下：</span><span class="sxs-lookup"><span data-stu-id="40c3b-139">Here's how:</span></span>

- <span data-ttu-id="40c3b-140">[Microsoft Defender For Office 365](/microsoft-365/security/office-365-security/office-365-atp) 保護您的組織免受電子郵件訊息、電子郵件附件及連結 (URLs) 于 Office 檔中的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="40c3b-140">[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp) safeguards your organization against malicious threats posed in email messages, email attachments, and links (URLs) in Office documents.</span></span>

    <span data-ttu-id="40c3b-141">AND</span><span class="sxs-lookup"><span data-stu-id="40c3b-141">AND</span></span>

- <span data-ttu-id="40c3b-142">[Microsoft Defender For Endpoint](microsoft-defender-endpoint.md) 會保護您的裝置免受網路威脅、偵測高級攻擊和資料違例、自動化安全性事件，以及改善安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="40c3b-142">[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) protects your devices from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves your security posture.</span></span>

    <span data-ttu-id="40c3b-143">所以</span><span class="sxs-lookup"><span data-stu-id="40c3b-143">SO</span></span>

- <span data-ttu-id="40c3b-144">一旦啟用整合，您的安全作業小組便可看到任何偵測到的 URLs 或電子郵件訊息，以及這些裝置最近的警示（在 Microsoft Defender Security Center () 中）所使用的裝置清單 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="40c3b-144">Once integration is enabled, your security operations team can see a list of devices that are used by the recipients of any detected URLs or email messages, along with recent alerts for those devices, in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="40c3b-145">若尚未這樣做，請 [整合 Microsoft defender For Office 365 搭配 Microsoft defender For Endpoint](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="40c3b-145">If you haven't already done so, [integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="more-good-reasons-to-use-onedrive"></a><span data-ttu-id="40c3b-146">更合理的使用 OneDrive 的理由</span><span class="sxs-lookup"><span data-stu-id="40c3b-146">More good reasons to use OneDrive</span></span>

<span data-ttu-id="40c3b-147">從勒索軟體防護是將檔案放入 OneDrive 的一個極佳原因。</span><span class="sxs-lookup"><span data-stu-id="40c3b-147">Protection from ransomware is one great reason to put your files in OneDrive.</span></span> <span data-ttu-id="40c3b-148">這段影片摘要列出了一些更合理的原因：</span><span class="sxs-lookup"><span data-stu-id="40c3b-148">And there are several more good reasons, summarized in this video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/70b4d256-46fb-481f-ad9b-921ef5fd7bed]

## <a name="want-to-learn-more-see-these-resources"></a><span data-ttu-id="40c3b-149">想要深入了解？</span><span class="sxs-lookup"><span data-stu-id="40c3b-149">Want to learn more?</span></span> <span data-ttu-id="40c3b-150">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="40c3b-150">See these resources:</span></span>

- [<span data-ttu-id="40c3b-151">OneDrive</span><span class="sxs-lookup"><span data-stu-id="40c3b-151">OneDrive</span></span>](/onedrive)

- [<span data-ttu-id="40c3b-152">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40c3b-152">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

- [<span data-ttu-id="40c3b-153">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40c3b-153">Microsoft Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)