---
title: 雙重金鑰加密 (DKE)
description: DKE 可讓您保護高度機密的資料，同時維持機碼的完整控制權。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 9607b095ba073229edae43c1d2f0e893db07c634
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663088"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="4f98d-103">Microsoft 365 的雙金鑰加密</span><span class="sxs-lookup"><span data-stu-id="4f98d-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="4f98d-104">*適用于：針對 Microsoft 365 的雙金鑰加密， [microsoft 365 相容性](https://www.microsoft.com/microsoft-365/business/compliance-management)， [Azure 資訊保護](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="4f98d-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="4f98d-105">*相關指示： [Azure 資訊保護統一標籤用戶端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="4f98d-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="4f98d-106">*服務說明： [Microsoft 365 合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="4f98d-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="4f98d-107">雙金鑰加密 (DKE) 會同時使用兩個按鍵來存取受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="4f98d-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="4f98d-108">Microsoft 會在 Microsoft Azure 中儲存一個金鑰，並保留另一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="4f98d-109">您可以使用 Double 金鑰加密服務，保留其中一個按鍵的「完全控制」。</span><span class="sxs-lookup"><span data-stu-id="4f98d-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="4f98d-110">您可以使用 Azure 資訊保護整合標籤用戶端，套用至高度機密內容的保護。</span><span class="sxs-lookup"><span data-stu-id="4f98d-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="4f98d-111">雙金鑰加密可同時支援雲端和內部部署。</span><span class="sxs-lookup"><span data-stu-id="4f98d-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="4f98d-112">這些部署可協助確保在任何儲存受保護的資料時，加密的資料都保持不透明。</span><span class="sxs-lookup"><span data-stu-id="4f98d-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="4f98d-113">如需預設的雲端型租使用者超級機碼的詳細資訊，請參閱 [規劃及執行 Azure 資訊保護租使用者金鑰](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="4f98d-114">您的組織應採用 DKE</span><span class="sxs-lookup"><span data-stu-id="4f98d-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="4f98d-115">雙金鑰加密是針對最嚴格的保護需求所需的最敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="4f98d-116">DKE 並非適用于所有的資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-116">DKE is not intended for all data.</span></span> <span data-ttu-id="4f98d-117">一般來說，您會使用雙金鑰加密來保護您整體資料中非常小的部分。</span><span class="sxs-lookup"><span data-stu-id="4f98d-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="4f98d-118">您應在部署之前，依照此解決方案識別要涵蓋的適當資料，以進行一定的努力。</span><span class="sxs-lookup"><span data-stu-id="4f98d-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="4f98d-119">在某些情況下，您可能需要縮小您的範圍，並使用其他的解決方案來處理大部分的資料，例如 Microsoft 資訊保護與 Microsoft 管理的金鑰或 BYOK。</span><span class="sxs-lookup"><span data-stu-id="4f98d-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="4f98d-120">這些解決方案已足以滿足不受增強保護和法規需求的檔。</span><span class="sxs-lookup"><span data-stu-id="4f98d-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="4f98d-121">此外，這些解決方案可讓您使用最強大的 Office 365 服務;您無法與 DKE 加密內容搭配使用的服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="4f98d-122">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-122">For example:</span></span>

- <span data-ttu-id="4f98d-123">傳輸規則包括需要附件查看的反惡意程式碼和垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="4f98d-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="4f98d-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="4f98d-124">Microsoft Delve</span></span>
- <span data-ttu-id="4f98d-125">電子文件探索</span><span class="sxs-lookup"><span data-stu-id="4f98d-125">eDiscovery</span></span>
- <span data-ttu-id="4f98d-126">內容搜尋和索引</span><span class="sxs-lookup"><span data-stu-id="4f98d-126">Content search and indexing</span></span>
- <span data-ttu-id="4f98d-127">Office Web Apps （包括共同撰寫功能）</span><span class="sxs-lookup"><span data-stu-id="4f98d-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="4f98d-128">任何未透過 MIP SDK 與 DKE 整合的外部應用程式或服務，都無法在加密的資料上執行動作。</span><span class="sxs-lookup"><span data-stu-id="4f98d-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="4f98d-129">Microsoft 資訊保護 SDK 1.7 + 支援雙金鑰加密;與我們的 SDK 整合的應用程式，將能夠透過適當的許可權和整合，在此資料上造成原因。</span><span class="sxs-lookup"><span data-stu-id="4f98d-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="4f98d-130">我們建議組織使用 Microsoft 資訊保護功能 (分類及標籤) ，保護其大部分的機密資料，並只對其重要的資料使用 DKE。</span><span class="sxs-lookup"><span data-stu-id="4f98d-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="4f98d-131">雙金鑰加密特別適用于高度管制行業（如金融服務和醫療保健）中極其敏感的資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="4f98d-132">如果您的組織有下列任何一個需求，您可以使用 DKE 來保護您的內容：</span><span class="sxs-lookup"><span data-stu-id="4f98d-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="4f98d-133">您想要確保 *只有您* 在所有情況下都能解密受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="4f98d-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="4f98d-134">您不想讓 Microsoft 自行存取受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="4f98d-135">您有法規需求，可在地理界限內保留金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="4f98d-136">您在資料中心維護所有保留用於資料加密和解密的機碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="4f98d-137">DKE 的系統和授權需求</span><span class="sxs-lookup"><span data-stu-id="4f98d-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="4f98d-138">**Microsoft 365 的雙金鑰加密** 與 Microsoft 365 E5 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4f98d-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="4f98d-139">如果您沒有 Microsoft 365 E5 授權，您可以註冊 [試用版](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="4f98d-140">如需這些授權的相關資訊，請參閱 [Microsoft 365 授權指南以取得安全性 & 合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="4f98d-141">**Azure 資訊保護**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-141">**Azure Information Protection**.</span></span> <span data-ttu-id="4f98d-142">DKE 與敏感度標籤搭配運作，需要 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="4f98d-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="4f98d-143">DKE 敏感度標籤可以透過 Office 桌面應用程式中的靈敏度功能區供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4f98d-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="4f98d-144">在您要保護和使用受保護檔的每一部用戶端電腦上安裝這些必要條件。</span><span class="sxs-lookup"><span data-stu-id="4f98d-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="4f98d-145">**適用于企業的 Microsoft Office 應用程式** 版本12711或更新版本 (Word PowerPoint 的桌上出版本，以及 Windows 上的 Excel) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="4f98d-146">**Azure 資訊保護統一標籤用戶端** 版本2.7.93.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4f98d-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="4f98d-147">從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載並安裝統一的標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="4f98d-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="4f98d-148">支援儲存及查看 DKE 保護內容的環境</span><span class="sxs-lookup"><span data-stu-id="4f98d-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="4f98d-149">**支援的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-149">**Supported applications**.</span></span> <span data-ttu-id="4f98d-150">Windows 上[的 Microsoft 365 應用程式](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)（包括 Word、Excel 及 PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="4f98d-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="4f98d-151">**線上內容支援**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-151">**Online content support**.</span></span> <span data-ttu-id="4f98d-152">支援在 Microsoft SharePoint 和商務 OneDrive 中線上儲存的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="4f98d-153">您可以透過電子郵件共用加密內容，但無法在線上查看加密的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="4f98d-154">相反地，您必須使用本機電腦上的桌面應用程式來查看受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="4f98d-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="4f98d-155">部署 DKE 的概述</span><span class="sxs-lookup"><span data-stu-id="4f98d-155">Overview of deploying DKE</span></span>

<span data-ttu-id="4f98d-156">您將遵循下列一般步驟來設定 DKE。</span><span class="sxs-lookup"><span data-stu-id="4f98d-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="4f98d-157">當您完成這些步驟之後，您的使用者就可以使用雙金鑰加密來保護高度機密的資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="4f98d-158">如本文所述，部署 DKE 服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="4f98d-159">建立具有雙按鍵加密的標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="4f98d-160">流覽至 [Microsoft 365 規範中心](https://compliance.microsoft.com) 底下的資訊保護，並建立具有雙金鑰加密的新標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="4f98d-161">請參閱 [使用敏感度標籤限制存取內容以套用加密](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="4f98d-162">使用雙金鑰加密標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="4f98d-163">從 Microsoft Office 中的 [敏感度] 功能區中，選取雙機碼加密標籤，以保護資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="4f98d-164">您可以透過幾種方式完成一些部署雙按鍵加密的步驟。</span><span class="sxs-lookup"><span data-stu-id="4f98d-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="4f98d-165">本文提供詳細指示，使系統管理員無法順利部署服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="4f98d-166">如果您很舒適，可以選擇使用您自己的方法。</span><span class="sxs-lookup"><span data-stu-id="4f98d-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="4f98d-167">部署 DKE</span><span class="sxs-lookup"><span data-stu-id="4f98d-167">Deploy DKE</span></span>

<span data-ttu-id="4f98d-168">本文和部署影片使用 Azure 作為 DKE 服務的部署目的地。</span><span class="sxs-lookup"><span data-stu-id="4f98d-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="4f98d-169">如果您要部署至其他位置，您必須提供您自己的值。</span><span class="sxs-lookup"><span data-stu-id="4f98d-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="4f98d-170">觀賞 [雙重金鑰加密部署影片](https://youtu.be/vDWfHN_kygg) ，以查看本文中概念的逐步綜述。</span><span class="sxs-lookup"><span data-stu-id="4f98d-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="4f98d-171">影片大約需要18分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="4f98d-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="4f98d-172">您將遵循下列一般步驟為您的組織設定雙金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="4f98d-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="4f98d-173">安裝 DKE 服務的必備軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="4f98d-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="4f98d-174">複製雙金鑰加密 GitHub 存放庫</span><span class="sxs-lookup"><span data-stu-id="4f98d-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="4f98d-175">修改應用程式設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="4f98d-176">產生測試機碼</span><span class="sxs-lookup"><span data-stu-id="4f98d-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="4f98d-177">建立專案</span><span class="sxs-lookup"><span data-stu-id="4f98d-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="4f98d-178">部署 DKE 服務併發布金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="4f98d-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="4f98d-179">驗證您的部署</span><span class="sxs-lookup"><span data-stu-id="4f98d-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="4f98d-180">註冊金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="4f98d-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="4f98d-181">使用 DKE 建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4f98d-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="4f98d-182">在用戶端啟用 DKE</span><span class="sxs-lookup"><span data-stu-id="4f98d-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="4f98d-183">將受保護的檔案從 HYOK 標籤遷移至 DKE 標籤</span><span class="sxs-lookup"><span data-stu-id="4f98d-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="4f98d-184">完成後，您可以使用 DKE 加密檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="4f98d-185">如需詳細資訊，請參閱 [將敏感度標籤套用至檔案和 Office 中的電子郵件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="4f98d-186">安裝 DKE 服務的必備軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="4f98d-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="4f98d-187">在您想要安裝 DKE 服務的電腦上安裝這些必要條件。</span><span class="sxs-lookup"><span data-stu-id="4f98d-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="4f98d-188">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="4f98d-189">從 [下載 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下載並安裝 SDK。</span><span class="sxs-lookup"><span data-stu-id="4f98d-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="4f98d-190">**Visual Studio 程式碼**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-190">**Visual Studio Code**.</span></span> <span data-ttu-id="4f98d-191">從下載 Visual Studio 程式碼 [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="4f98d-192">安裝之後，請執行 Visual Studio 程式碼並選取 [ **View** \> **extension**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="4f98d-193">安裝這些分機號碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-193">Install these extensions.</span></span>

- <span data-ttu-id="4f98d-194">Visual Studio 程式碼的 c #</span><span class="sxs-lookup"><span data-stu-id="4f98d-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="4f98d-195">NuGet 套件管理員</span><span class="sxs-lookup"><span data-stu-id="4f98d-195">NuGet Package Manager</span></span>

<span data-ttu-id="4f98d-196">**Git 資源**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-196">**Git resources**.</span></span> <span data-ttu-id="4f98d-197">下載並安裝下列其中一個。</span><span class="sxs-lookup"><span data-stu-id="4f98d-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="4f98d-198">Git</span><span class="sxs-lookup"><span data-stu-id="4f98d-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="4f98d-199">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="4f98d-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="4f98d-200">GitHub 企業版</span><span class="sxs-lookup"><span data-stu-id="4f98d-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="4f98d-201">**OpenSSL** 您必須安裝 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才可在部署 DKE 之後 [產生測試機碼](#generate-test-keys) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="4f98d-202">請確認您已從環境變數路徑正確呼叫它。</span><span class="sxs-lookup"><span data-stu-id="4f98d-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="4f98d-203">例如，如需詳細資訊，請參閱「將安裝目錄新增至路徑」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="4f98d-204">複製 DKE GitHub 存放庫</span><span class="sxs-lookup"><span data-stu-id="4f98d-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="4f98d-205">Microsoft 會在 GitHub 存放庫中提供 DKE 來源檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="4f98d-206">您可以複製存放庫，以在本機為組織使用建立專案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="4f98d-207">DKE GitHub 存放庫位於 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="4f98d-208">下列指示適用于未經驗的 git 或 Visual Studio 程式碼使用者：</span><span class="sxs-lookup"><span data-stu-id="4f98d-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="4f98d-209">在您的瀏覽器中，移至： [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="4f98d-210">在螢幕右側，選取 [程式 **代碼**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="4f98d-211">您的 UI 版本可能會顯示 [ **複製] 或 [下載** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4f98d-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="4f98d-212">然後，在出現的下拉式清單中，選取複製圖示，將 URL 複製到您的剪貼簿。</span><span class="sxs-lookup"><span data-stu-id="4f98d-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="4f98d-213">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-213">For example:</span></span>

   ![從 GitHub 複製 Double 金鑰加密服務存放庫](../media/dke-clone.png)

3. <span data-ttu-id="4f98d-215">在 Visual Studio 程式碼中，選取 [ **View** \> **Command 調板** ]，然後選取 [ **Git：複本**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="4f98d-216">若要跳到清單中的選項，請開始輸入 `git: clone` 以篩選項目，然後從下拉式清單中選取。</span><span class="sxs-lookup"><span data-stu-id="4f98d-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="4f98d-217">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-217">For example:</span></span>

   ![Visual Studio 程式碼 GIT：仿製選項](../media/dke-vscode-clone.png)

4. <span data-ttu-id="4f98d-219">在文字方塊中，粘貼您從 Git 複製的 URL，並 **從 GitHub** 選取 [複製]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="4f98d-220">在出現的 [ **選取資料夾** ] 對話方塊中，流覽至儲存存放庫的位置並加以選取。</span><span class="sxs-lookup"><span data-stu-id="4f98d-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="4f98d-221">在提示中，選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="4f98d-222">會在 Visual Studio 程式碼中開啟存放庫，並在左下方顯示目前的 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="4f98d-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="4f98d-223">分支應為 **master**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-223">The branch should be **master**.</span></span>

    <span data-ttu-id="4f98d-224">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-224">For example:</span></span>

   ![Visual Studio 程式碼主分支](../media/dke-vscode-master.png)

6. <span data-ttu-id="4f98d-226">從分支清單中選取 word **主** 圖形。</span><span class="sxs-lookup"><span data-stu-id="4f98d-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4f98d-227">選取 [主分支] 可確保您具有正確的檔案來建立專案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="4f98d-228">如果您未選擇正確的分支，您的部署將會失敗。</span><span class="sxs-lookup"><span data-stu-id="4f98d-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="4f98d-229">您現在已設定本機的 DKE 來源存放庫。</span><span class="sxs-lookup"><span data-stu-id="4f98d-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="4f98d-230">接下來，修改組織的 [應用程式設定](#modify-application-settings) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="4f98d-231">修改應用程式設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-231">Modify application settings</span></span>

<span data-ttu-id="4f98d-232">若要部署 DKE 服務，您必須修改下列類型的應用程式設定：</span><span class="sxs-lookup"><span data-stu-id="4f98d-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="4f98d-233">主要存取設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="4f98d-234">租使用者和主要設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="4f98d-235">您可以在 [檔案] 中的 [appsettings.js修改應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="4f98d-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="4f98d-236">此檔案位於您在本機上複製的 DoubleKeyEncryptionService 存放庫中 DoubleKeyEncryptionService\src\customer-key-store。</span><span class="sxs-lookup"><span data-stu-id="4f98d-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="4f98d-237">例如，在 Visual Studio 程式碼中，您可以流覽至檔案，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="4f98d-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![在 DKE 的檔案中尋找 appsettings.js。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="4f98d-239">主要存取設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-239">Key access settings</span></span>

<span data-ttu-id="4f98d-240">選擇是否要使用電子郵件或角色授權。</span><span class="sxs-lookup"><span data-stu-id="4f98d-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="4f98d-241">DKE 一次只支援其中一種驗證方法。</span><span class="sxs-lookup"><span data-stu-id="4f98d-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="4f98d-242">**電子郵件授權**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-242">**Email authorization**.</span></span> <span data-ttu-id="4f98d-243">可讓您的組織僅根據電子郵件地址來授權存取機碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="4f98d-244">**角色授權**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-244">**Role authorization**.</span></span> <span data-ttu-id="4f98d-245">可讓您的組織授權以 Active Directory 群組為基礎的金鑰存取權，且要求 web 服務可以查詢 LDAP。</span><span class="sxs-lookup"><span data-stu-id="4f98d-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="4f98d-246">**使用電子郵件授權設定 DKE 的主要存取設定**</span><span class="sxs-lookup"><span data-stu-id="4f98d-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="4f98d-247">開啟檔案 **上的appsettings.js** ，並找到 `AuthorizedEmailAddress` 設定。</span><span class="sxs-lookup"><span data-stu-id="4f98d-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="4f98d-248">新增您要授權的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4f98d-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="4f98d-249">使用雙引號和逗號來分隔多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4f98d-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="4f98d-250">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="4f98d-251">找到 `LDAPPath` 設定，然後 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 在雙引號之間移除文字。</span><span class="sxs-lookup"><span data-stu-id="4f98d-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="4f98d-252">將雙引號保留在原處。</span><span class="sxs-lookup"><span data-stu-id="4f98d-252">Leave the double quotes in place.</span></span> <span data-ttu-id="4f98d-253">當您完成時，此設定應該如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f98d-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="4f98d-254">找到 `AuthorizedRoles` 設定，並刪除整行。</span><span class="sxs-lookup"><span data-stu-id="4f98d-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="4f98d-255">此影像顯示檔的 **appsettings.js** 的電子郵件授權格式設定正確。</span><span class="sxs-lookup"><span data-stu-id="4f98d-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![檔上顯示電子郵件授權方法的 appsettings.js](../media/dke-email-accesssetting.png)

<span data-ttu-id="4f98d-257">**使用角色授權設定 DKE 的主要存取設定**</span><span class="sxs-lookup"><span data-stu-id="4f98d-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="4f98d-258">開啟檔案 **上的appsettings.js** ，並找到 `AuthorizedRoles` 設定。</span><span class="sxs-lookup"><span data-stu-id="4f98d-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="4f98d-259">新增您要授權的 Active Directory 群組名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="4f98d-260">使用雙引號和逗號來分隔多個組名。</span><span class="sxs-lookup"><span data-stu-id="4f98d-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="4f98d-261">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="4f98d-262">找到 `LDAPPath` 設定並新增 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="4f98d-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="4f98d-263">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="4f98d-264">找到 `AuthorizedEmailAddress` 設定，並刪除整行。</span><span class="sxs-lookup"><span data-stu-id="4f98d-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="4f98d-265">此影像顯示針對角色授權，正確設定檔案格式的 **appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![檔顯示角色授權方法的 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="4f98d-267">租使用者和主要設定</span><span class="sxs-lookup"><span data-stu-id="4f98d-267">Tenant and key settings</span></span>

<span data-ttu-id="4f98d-268">DKE 租使用者和 key settings 位於檔案中的 **appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="4f98d-269">**設定 DKE 的承租人和主要設定**</span><span class="sxs-lookup"><span data-stu-id="4f98d-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="4f98d-270">開啟檔 **上的appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="4f98d-271">找到 `ValidIssuers` 設定，並 `<tenantid>` 將其取代為您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="4f98d-272">您可以移至 Azure 入口網站並查看 [租使用者屬性](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)，以找出您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="4f98d-273">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="4f98d-274">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="4f98d-275">取代 `<yourhostname>` DKE 服務將執行的機器的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="4f98d-276">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4f98d-277">的值 `JwtAudience` 必須與您的主機名稱稱 *完全* 相符。</span><span class="sxs-lookup"><span data-stu-id="4f98d-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="4f98d-278">您可以在調試時使用 **localhost： 5001** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="4f98d-279">不過，當您完成調試時，請務必將此值更新為伺服器的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="4f98d-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="4f98d-280">`TestKeys:Name`.</span></span> <span data-ttu-id="4f98d-281">輸入機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-281">Enter a name for your key.</span></span> <span data-ttu-id="4f98d-282">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="4f98d-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="4f98d-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="4f98d-283">`TestKeys:Id`.</span></span> <span data-ttu-id="4f98d-284">建立 GUID 並輸入為 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="4f98d-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="4f98d-285">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="4f98d-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="4f98d-286">您可以使用像是 [線上 GUID 發生器](https://guidgenerator.com/) 的網站，以隨機產生 GUID。</span><span class="sxs-lookup"><span data-stu-id="4f98d-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="4f98d-287">這個圖像會顯示 **appsettings.js** 中的承租人和機碼設定的正確格式。</span><span class="sxs-lookup"><span data-stu-id="4f98d-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="4f98d-288">`LDAPPath` 設定角色授權。</span><span class="sxs-lookup"><span data-stu-id="4f98d-288">`LDAPPath` is configured for role authorization.</span></span>

![在檔案 appsettings.js中顯示 DKE 的正確租使用者和重要設定。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="4f98d-290">產生測試機碼</span><span class="sxs-lookup"><span data-stu-id="4f98d-290">Generate test keys</span></span>

<span data-ttu-id="4f98d-291">定義應用程式設定之後，即可開始產生公用和私人測試金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="4f98d-292">若要產生機碼：</span><span class="sxs-lookup"><span data-stu-id="4f98d-292">To generate keys:</span></span>

1. <span data-ttu-id="4f98d-293">在 Windows [開始] 功能表中，執行 OpenSSL 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="4f98d-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="4f98d-294">變更至您要儲存測試機碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4f98d-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="4f98d-295">您完成此工作中的步驟所建立的檔案會儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="4f98d-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="4f98d-296">產生新的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="4f98d-297">產生私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="4f98d-298">產生公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="4f98d-299">在文字編輯器中，開啟 **pubkeyonly**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="4f98d-300">將 **pubkeyonly** 檔案中的所有內容（第一行及最後一列除外）複製到檔案中 `PublicPem` **appsettings.js** 區段。</span><span class="sxs-lookup"><span data-stu-id="4f98d-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="4f98d-301">在文字編輯器中，開啟 **privkeynopass**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="4f98d-302">將 **privkeynopass** 檔案中的所有內容（第一行及最後一列除外）複製到檔案中 `PrivatePem` **appsettings.js** 區段。</span><span class="sxs-lookup"><span data-stu-id="4f98d-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="4f98d-303">移除及區段中的所有空格和分行符號 `PublicPem` `PrivatePem` 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4f98d-304">當您複製此內容時，請勿刪除任何 PEM 資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="4f98d-305">在 Visual Studio 程式碼中，流覽至 **Startup.cs** 檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="4f98d-306">此檔案位於您在本機上複製的 DoubleKeyEncryptionService 存放庫中 DoubleKeyEncryptionService\src\customer-key-store\。</span><span class="sxs-lookup"><span data-stu-id="4f98d-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="4f98d-307">找到下列行：</span><span class="sxs-lookup"><span data-stu-id="4f98d-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="4f98d-308">請使用下列文字取代這些行：</span><span class="sxs-lookup"><span data-stu-id="4f98d-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="4f98d-309">結束結果應如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f98d-309">The end results should look similar to the following.</span></span>

   ![公開預覽的 startup.cs 檔案](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="4f98d-311">現在您已經準備好 [建立 DKE 專案](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="4f98d-312">建立專案</span><span class="sxs-lookup"><span data-stu-id="4f98d-312">Build the project</span></span>

<span data-ttu-id="4f98d-313">使用下列指示在本機建立 DKE 專案：</span><span class="sxs-lookup"><span data-stu-id="4f98d-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="4f98d-314">在 Visual Studio 程式碼的 DKE 服務存放庫中，選取 [ **View** \> **Command 調板** ]，然後在提示中輸入 **build** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="4f98d-315">從清單中選擇 [ **任務：執行建立任務**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="4f98d-316">如果找不到任何建立工作，請選取 [ **設定建立** 工作] 並為 .net core 建立一個工作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f98d-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![設定 .NET 的遺失組建工作](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="4f98d-318">選擇 [ **從範本建立 tasks.js**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-318">Choose **Create tasks.json from template**.</span></span>

      ![在 DKE 的檔案從範本建立 tasks.js](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="4f98d-320">從範本類型清單中，選取 [ **.Net Core**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-320">From the list of template types, select **.NET Core**.</span></span>

      ![為 DKE 選取正確的範本](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="4f98d-322">在 [建立] 區段中，找到 customerkeystore 之 **.csproj** 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="4f98d-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="4f98d-323">如果沒有的話，請新增下列一行：</span><span class="sxs-lookup"><span data-stu-id="4f98d-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="4f98d-324">再次執行組建。</span><span class="sxs-lookup"><span data-stu-id="4f98d-324">Run the build again.</span></span>

3. <span data-ttu-id="4f98d-325">確認 [輸出] 視窗中沒有紅色的錯誤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="4f98d-326">如果有紅色錯誤，請檢查主控台輸出。</span><span class="sxs-lookup"><span data-stu-id="4f98d-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="4f98d-327">確定您已正確完成上述所有步驟，且有正確的版本。</span><span class="sxs-lookup"><span data-stu-id="4f98d-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="4f98d-328">選取 [ **執行** \> **開始調試** ] 以調試處理常式。</span><span class="sxs-lookup"><span data-stu-id="4f98d-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="4f98d-329">如果系統提示您選取環境，請選取 [ **.net core**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="4f98d-330">.NET 核心偵錯工具通常會啟動至 `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="4f98d-331">若要查看測試機碼，請移至 `https://localhost:5001` 並追加一個正斜線 (/) 和您的金鑰名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="4f98d-332">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="4f98d-333">該項應該會以 JSON 格式顯示。</span><span class="sxs-lookup"><span data-stu-id="4f98d-333">The key should display in JSON format.</span></span>

<span data-ttu-id="4f98d-334">您的設定現在已完成。</span><span class="sxs-lookup"><span data-stu-id="4f98d-334">Your setup is now complete.</span></span> <span data-ttu-id="4f98d-335">在您發佈金鑰庫之前 appsettings.js開啟] 中的 JwtAudience 設定，請確定主機名稱的值完全符合您的應用程式服務主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="4f98d-336">您可能已將其變更為 localhost 以進行組建疑難排解。</span><span class="sxs-lookup"><span data-stu-id="4f98d-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="4f98d-337">部署 DKE 服務併發布金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="4f98d-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="4f98d-338">若為生產部署，請在協力廠商雲端部署服務，或 [發佈至內部部署系統](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="4f98d-339">您可以選擇使用其他方法來部署金鑰。</span><span class="sxs-lookup"><span data-stu-id="4f98d-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="4f98d-340">選取最適合您組織的方法。</span><span class="sxs-lookup"><span data-stu-id="4f98d-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="4f98d-341">在試驗部署中，您可以在 Azure 中部署，並立即開始快速入門。</span><span class="sxs-lookup"><span data-stu-id="4f98d-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="4f98d-342">**建立 Azure Web 應用程式實例以主控您的 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="4f98d-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="4f98d-343">若要發佈機碼存放區，您將會建立 Azure 應用程式服務實例，以裝載您的 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="4f98d-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="4f98d-344">接下來，您會將所產生的金鑰發佈到 Azure。</span><span class="sxs-lookup"><span data-stu-id="4f98d-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="4f98d-345">在您的瀏覽器中，登入 [Microsoft Azure 入口網站](https://ms.portal.azure.com)，然後移至 [**應用程式服務**] [  >  **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="4f98d-346">選取您的訂閱和資源群組，然後定義您的實例詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4f98d-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="4f98d-347">輸入您要安裝 DKE 服務之電腦的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="4f98d-348">請確定其名稱與 [**appsettings.json**](#tenant-and-key-settings) file 中的 JwtAudience 設定所定義的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="4f98d-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="4f98d-349">您為此名稱提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="4f98d-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="4f98d-350">在 [ **發佈**]、[程式 **代碼**] 及 [ **執行時間堆疊**] 中，選取 [ **.net Core 3.1**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="4f98d-351">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-351">For example:</span></span>

   ![新增應用程式服務](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="4f98d-353">在頁面底部，選取 [ **複查 + 建立**]，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="4f98d-354">請執行下列其中一項動作來發佈您產生的機碼：</span><span class="sxs-lookup"><span data-stu-id="4f98d-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="4f98d-355">透過 ZipDeployUI 發佈</span><span class="sxs-lookup"><span data-stu-id="4f98d-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="4f98d-356">透過 FTP 發佈</span><span class="sxs-lookup"><span data-stu-id="4f98d-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="4f98d-357">透過 Visual Studio 2019 或更新版本發行</span><span class="sxs-lookup"><span data-stu-id="4f98d-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="4f98d-358">透過 ZipDeployUI 發佈</span><span class="sxs-lookup"><span data-stu-id="4f98d-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="4f98d-359">移至`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="4f98d-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="4f98d-360">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4f98d-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="4f98d-361">在金鑰存放區的基本代碼中，移至 [ **customer-key-store\src\customer-key-store** ] 資料夾，然後確認此資料夾包含 **customerkeystore 的 .csproj** 檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="4f98d-362">執行： **dotnet 發佈**</span><span class="sxs-lookup"><span data-stu-id="4f98d-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="4f98d-363">[輸出] 視窗會顯示部署發佈所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="4f98d-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4f98d-364">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4f98d-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="4f98d-365">將發行目錄中的所有檔案傳送至 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="4f98d-366">建立 .zip 檔時，請確定目錄中的所有檔案都位於 .zip 檔案的根層級。</span><span class="sxs-lookup"><span data-stu-id="4f98d-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="4f98d-367">將您建立的 .zip 檔案拖放至您在上面開啟的 ZipDeployUI 網站。</span><span class="sxs-lookup"><span data-stu-id="4f98d-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="4f98d-368">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4f98d-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="4f98d-369">已部署 DKE，您可以流覽至您建立的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="4f98d-370">繼續 [驗證您的部署](#validate-your-deployment) 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="4f98d-371">透過 FTP 發佈</span><span class="sxs-lookup"><span data-stu-id="4f98d-371">Publish via FTP</span></span>

1. <span data-ttu-id="4f98d-372">連線至您在 [上述](#deploy-the-dke-service-and-publish-the-key-store)建立的 App 服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="4f98d-373">在您的瀏覽器中，移至： **Azure 入口** 網站  >  **應用程式服務**  >  **部署中心**  >  **手動部署**  >  **FTP**  >  **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="4f98d-374">複製顯示至本機檔案的連接字串。</span><span class="sxs-lookup"><span data-stu-id="4f98d-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="4f98d-375">您將使用這些字串連線到 Web App 服務，並透過 FTP 上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="4f98d-376">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-376">For example:</span></span>

   ![從 FTP 儀表板複製連接字串](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="4f98d-378">在金鑰儲存的基本代碼中，移至 **customer-key-store\src\customer-key-store 目錄**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="4f98d-379">請確認此目錄包含 **customerkeystore （.csproj** ）檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="4f98d-380">執行： **dotnet 發佈**</span><span class="sxs-lookup"><span data-stu-id="4f98d-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="4f98d-381">輸出包含部署發佈所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="4f98d-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4f98d-382">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4f98d-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="4f98d-383">將發行目錄中的所有檔案傳送至 zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="4f98d-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="4f98d-384">建立 .zip 檔時，請確定目錄中的所有檔案都位於 .zip 檔案的根層級。</span><span class="sxs-lookup"><span data-stu-id="4f98d-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="4f98d-385">您可以從您的 FTP 用戶端，使用複製的連線資訊連線至應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="4f98d-386">將您在上一個步驟中建立的 .zip 檔案上傳至 Web 應用程式的根目錄。</span><span class="sxs-lookup"><span data-stu-id="4f98d-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="4f98d-387">已部署 DKE，您可以流覽至您所建立的測試機碼。</span><span class="sxs-lookup"><span data-stu-id="4f98d-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="4f98d-388">接下來， [驗證您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="4f98d-389">驗證您的部署</span><span class="sxs-lookup"><span data-stu-id="4f98d-389">Validate your deployment</span></span>

<span data-ttu-id="4f98d-390">使用上述其中一種方法來部署 DKE 之後，請驗證部署及主要儲存區設定。</span><span class="sxs-lookup"><span data-stu-id="4f98d-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="4f98d-391">運行：</span><span class="sxs-lookup"><span data-stu-id="4f98d-391">Run:</span></span>

<span data-ttu-id="4f98d-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="4f98d-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="4f98d-393">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-393">For example:</span></span>

<span data-ttu-id="4f98d-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="4f98d-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="4f98d-395">確定輸出中未顯示任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="4f98d-396">當您準備好時，請 [註冊金鑰存放區](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="4f98d-397">註冊金鑰存放區</span><span class="sxs-lookup"><span data-stu-id="4f98d-397">Register your key store</span></span>

<span data-ttu-id="4f98d-398">下列步驟可讓您註冊 DKE 服務。</span><span class="sxs-lookup"><span data-stu-id="4f98d-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="4f98d-399">註冊 DKE 服務是部署 DKE 的最後一個步驟，您才可以開始建立標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="4f98d-400">若要註冊 DKE 服務：</span><span class="sxs-lookup"><span data-stu-id="4f98d-400">To register the DKE service:</span></span>

1. <span data-ttu-id="4f98d-401">在您的瀏覽器中，開啟 [Microsoft Azure 入口網站](https://ms.portal.azure.com/)，然後移至 **所有服務** 身分 \> **識別** \> **應用程式註冊**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="4f98d-402">選取 [ **新增註冊**]，然後輸入有意義的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="4f98d-403">從顯示的選項中選取帳戶類型。</span><span class="sxs-lookup"><span data-stu-id="4f98d-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="4f98d-404">如果您使用的是非自訂網域（例如 **onmicrosoft.com**）的 Microsoft Azure，請選取 [ **此組織目錄中的帳戶]，只 (僅限 Microsoft 單一租使用者) 。**</span><span class="sxs-lookup"><span data-stu-id="4f98d-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="4f98d-405">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-405">For example:</span></span>

   ![新的應用程式註冊](../media/dke-app-registration.png)

4. <span data-ttu-id="4f98d-407">在頁面底部，選取 [ **註冊** ] 以建立新的應用程式註冊。</span><span class="sxs-lookup"><span data-stu-id="4f98d-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="4f98d-408">在新的應用程式註冊的左窗格中，按一下 [ **管理**] 下的 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="4f98d-409">選取 [ **新增平臺**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="4f98d-410">在 [ **設定平臺** ] 快顯功能表上，選取 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="4f98d-411">在 [重新 **導向 URIs**] 底下，輸入您的雙金鑰加密服務 URI。</span><span class="sxs-lookup"><span data-stu-id="4f98d-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="4f98d-412">輸入應用程式服務 URL，包括主機名稱和網域。</span><span class="sxs-lookup"><span data-stu-id="4f98d-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="4f98d-413">例如：https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="4f98d-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="4f98d-414">您輸入的 URL 必須符合部署 DKE 服務的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="4f98d-415">如果您要在本機上使用 Visual Studio 進行測試，請使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="4f98d-416">在所有情況下，此配置必須是 **HTTPs**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="4f98d-417">確定主機名稱完全符合您的應用程式服務主機名稱。</span><span class="sxs-lookup"><span data-stu-id="4f98d-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="4f98d-418">您可能已經將其變更為 `localhost` 疑難排解組建。</span><span class="sxs-lookup"><span data-stu-id="4f98d-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="4f98d-419">在 **appsettings.js開啟**] 中，這個值是您為設定的主機名稱 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="4f98d-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="4f98d-420">在 **[隱含授** 與] 底下，選取 [ **識別碼標記** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f98d-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="4f98d-421">選取 **[儲存]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="4f98d-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="4f98d-422">在左窗格中，選取 [ **公開 API**]，然後選取 [應用程式識別碼 URI] 旁的 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="4f98d-423">在 [ **公開 API** ] 頁面上，選取 [ **此 api** 區域所定義的範圍] 中的 [ **新增範圍**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="4f98d-424">在 [新增] 範圍中：</span><span class="sxs-lookup"><span data-stu-id="4f98d-424">In the new scope:</span></span>

    1. <span data-ttu-id="4f98d-425">將範圍名稱定義為 **user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="4f98d-426">選取可同意的系統管理員和使用者。</span><span class="sxs-lookup"><span data-stu-id="4f98d-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="4f98d-427">定義任何其他必要的值。</span><span class="sxs-lookup"><span data-stu-id="4f98d-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="4f98d-428">選取 [ **新增範圍**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="4f98d-429">選取頂端的 [ **儲存** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="4f98d-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="4f98d-430">仍在 **公開 API** 頁面上，選取 [ **授權用戶端應用程式** ] 區域中的 [ **新增用戶端應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="4f98d-431">在新的用戶端應用程式中：</span><span class="sxs-lookup"><span data-stu-id="4f98d-431">In the new client application:</span></span>

    1. <span data-ttu-id="4f98d-432">將用戶端識別碼定義為 **d3590ed6-52b3-4102-aeff-aad2292ab01c**。</span><span class="sxs-lookup"><span data-stu-id="4f98d-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="4f98d-433">這個值是 Microsoft Office 用戶端識別碼，可讓 Office 取得金鑰存放區的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="4f98d-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="4f98d-434">在 [ **授權範圍**] 底下，選取 [ **user_impersonation** ] 範圍。</span><span class="sxs-lookup"><span data-stu-id="4f98d-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="4f98d-435">選取 [ **新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="4f98d-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="4f98d-436">選取頂端的 [ **儲存** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="4f98d-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="4f98d-437">您的 DKE 服務現在已註冊。</span><span class="sxs-lookup"><span data-stu-id="4f98d-437">Your DKE service is now registered.</span></span> <span data-ttu-id="4f98d-438">[使用 DKE 建立標籤](#create-sensitivity-labels-using-dke)以繼續。</span><span class="sxs-lookup"><span data-stu-id="4f98d-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="4f98d-439">使用 DKE 建立敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="4f98d-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="4f98d-440">在 Microsoft 365 規範中心中，建立新的靈敏度標籤，並依照您的需要套用加密。</span><span class="sxs-lookup"><span data-stu-id="4f98d-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="4f98d-441">選取 [ **使用雙重金鑰加密** ]，然後輸入機碼的端點 URL。</span><span class="sxs-lookup"><span data-stu-id="4f98d-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="4f98d-442">例如：</span><span class="sxs-lookup"><span data-stu-id="4f98d-442">For example:</span></span>

![選取 [Microsoft 365 規範中心] 中的 [使用雙重金鑰加密]](../media/dke-use-dke.png)

<span data-ttu-id="4f98d-444">在最新版本的 Microsoft 365 應用程式中，您新增的任何 DKE 標籤都會開始顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="4f98d-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="4f98d-445">最多可能需要24小時的時間，讓用戶端重新整理新的標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="4f98d-446">在用戶端啟用 DKE</span><span class="sxs-lookup"><span data-stu-id="4f98d-446">Enable DKE in your client</span></span>

<span data-ttu-id="4f98d-447">如果您是 Office 有問必答，已為您啟用 DKE。</span><span class="sxs-lookup"><span data-stu-id="4f98d-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="4f98d-448">否則，請新增下列登錄機碼，為您的用戶端啟用 DKE：</span><span class="sxs-lookup"><span data-stu-id="4f98d-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="4f98d-449">將受保護的檔案從 HYOK 標籤遷移至 DKE 標籤</span><span class="sxs-lookup"><span data-stu-id="4f98d-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="4f98d-450">當您完成 DKE 的設定之後，您可以使用 HYOK 標籤將已保護的內容遷移至 DKE 標籤。</span><span class="sxs-lookup"><span data-stu-id="4f98d-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="4f98d-451">若要進行遷移，您會使用 AIP 掃描器。</span><span class="sxs-lookup"><span data-stu-id="4f98d-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="4f98d-452">若要開始使用掃描器，請參閱 [Azure 資訊保護統一標記掃描器的功能？](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。</span><span class="sxs-lookup"><span data-stu-id="4f98d-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="4f98d-453">如果您不遷移內容，您的 HYOK 受保護內容將保持不受影響。</span><span class="sxs-lookup"><span data-stu-id="4f98d-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
