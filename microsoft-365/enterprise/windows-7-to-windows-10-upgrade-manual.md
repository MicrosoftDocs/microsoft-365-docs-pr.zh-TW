---
title: Windows 7 至 Windows 10 手動升級指南
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 7 至 Windows 10 手動升級指南。
ms.openlocfilehash: 13cdb56b52655ed81932601dd3ff97c90c1daad8
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033678"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a><span data-ttu-id="20e69-103">Windows 7 至 Windows 10 手動升級逐步指南</span><span class="sxs-lookup"><span data-stu-id="20e69-103">Windows 7 to Windows 10 manual upgrade step-by-step guide</span></span>

<span data-ttu-id="20e69-104">本文說明將 Windows 7 企業版電腦手動升級至 Windows 10 企業版的程序。</span><span class="sxs-lookup"><span data-stu-id="20e69-104">This article describes the process to manually upgrade a Windows 7 Enterprise PC to Windows 10 Enterprise.</span></span> <span data-ttu-id="20e69-105">其他 Windows 7 版本 (例如家用版和專業版) 的程序非常相似，但您也可以選擇使用媒體建立工具直接升級。</span><span class="sxs-lookup"><span data-stu-id="20e69-105">For other Windows 7 editions, such as Home and Professional, the process is very similar, but you also have the option to upgrade directly using the media creation tool.</span></span> <span data-ttu-id="20e69-106">從 Windows 7 任何版本升級至 Windows 10 需要有效的產品金鑰，以及相符或更高版本的 Windows，例如 Windows 7 專業版可以升級至 Windows 10 專業版，但無法升級至 Windows 10 家用版。</span><span class="sxs-lookup"><span data-stu-id="20e69-106">Upgrades for any edition of Windows 7 to Windows 10 will require a valid product key and matching or higher edition of Windows, for example Windows 7 Professional can upgrade to Windows 10 Pro, but cannot be upgraded to Windows 10 Home.</span></span> <span data-ttu-id="20e69-107">Windows 7 旗艦版必須升級至 Windows 10 專業版。</span><span class="sxs-lookup"><span data-stu-id="20e69-107">Windows 7 Ultimate will need to be upgraded to Windows 10 Pro.</span></span>

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a><span data-ttu-id="20e69-108">使用媒體建立工具或 ISO 檔案的 Windows 10 升級</span><span class="sxs-lookup"><span data-stu-id="20e69-108">Windows 10 upgrades using the media creation tool or ISO files</span></span>

<span data-ttu-id="20e69-109">您可以使用[媒體建立工具](https://www.microsoft.com/software-download/windows10ISO)直接升級至 Windows 10，或使用該工具將 Windows 10 下載為 ISO 檔案。</span><span class="sxs-lookup"><span data-stu-id="20e69-109">You can upgrade to Windows 10 directly using the [media creation tool](https://www.microsoft.com/software-download/windows10ISO) or use it to download Windows 10 as an ISO file.</span></span> <span data-ttu-id="20e69-110">您必須知道您目前的系統是 32 還是 64 位元、系統的預設語言和 Windows 7 版本 (例如家用版、專業版或企業版)。</span><span class="sxs-lookup"><span data-stu-id="20e69-110">You’ll need to note whether your current system is 32 or 64-bit, your system’s default language and edition of Windows 7 (e.g. Home, Professional, or Enterprise).</span></span> <span data-ttu-id="20e69-111">在 Windows 7 中，這項資訊位於 [控制台] \> [系統及安全性] \> [系統]。</span><span class="sxs-lookup"><span data-stu-id="20e69-111">In Windows 7, this information is located in the Control Panel \> System and Security \> System.</span></span> <span data-ttu-id="20e69-112">媒體建立工具不支援 Windows 10 企業版進行升級、建立安裝媒體，或下載 ISO 檔案。</span><span class="sxs-lookup"><span data-stu-id="20e69-112">The media creation tool does not support Windows 10 Enterprise for upgrades, creating installation media or downloading ISO files.</span></span> <span data-ttu-id="20e69-113">如果是從 Windows 7 企業版升級，您需要 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="20e69-113">Windows 10 Enterprise is required if you are upgrading from Windows 7 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-1.png)

<span data-ttu-id="20e69-114">從 Windows 7 企業版升級至 Windows 10 企業版時，您必須從[大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)下載適用於您的語言與架構 (32 位元或 64 位元) 的 ISO 檔案。</span><span class="sxs-lookup"><span data-stu-id="20e69-114">When upgrading from Windows 7 Enterprise to Windows 10 Enterprise, you’ll need to download the ISO file for your language and architecture (32-bit or 64-bit) from the [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

<span data-ttu-id="20e69-115">如果您規劃使用 ISO 檔案執行升級，您必須將 ISO 內的檔案擷取至您的本機檔案系統、卸除式磁碟機，或將 ISO 檔案燒錄至 DVD。</span><span class="sxs-lookup"><span data-stu-id="20e69-115">If you plan to perform the upgrade using an ISO file, you will need to extract the files within the ISO to either your local file system, to a removable drive, or you can burn the ISO file to a DVD.</span></span> <span data-ttu-id="20e69-116">您可以使用 Windows 8 或更新的電腦擷取 ISO 內的安裝檔案，然後將這些檔案儲存到卸除式 USB 儲存裝置，或使用應用程式 (例如 [7zip](https://www.7-zip.org/)) 將 ISO 檔案的內容解壓縮到 Windows 7 本機磁碟機上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="20e69-116">You can extract the installation files within the ISO using a Windows 8 or newer PC and save these files to removable USB storage or use an application such as [7zip](https://www.7-zip.org/) to extract the contents of your ISO file to a folder on your local drive within Windows 7.</span></span>

<span data-ttu-id="20e69-117">在 Windows 7 有了安裝媒體之後，您就可以執行 setup.exe 啟動升級程序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="20e69-117">Once you have the install media available in Windows 7, you can initiate the upgrade by running setup.exe as shown below.</span></span>

<span data-ttu-id="20e69-118">**重要提示：如果要進行就地升級 (亦即應用程式與您的資料要移轉至 Windows 10)，您必須從執行 Windows 7 的工作階段內啟動程序。從 DVD 或 USB 磁碟機開機進入安裝媒體不會提供您保留應用程式和檔案的選項，而是會執行 Windows 10 的全新安裝。**</span><span class="sxs-lookup"><span data-stu-id="20e69-118">**Important tip: For an in-place upgrade where applications and your data are migrated to Window 10, you’ll need to initiate the process from within a running Windows 7 session. Booting to install media from a DVD or USB drive will not give you the option to keep your apps and files, instead it will perform a clean install of Windows 10.**</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-2.png)

<span data-ttu-id="20e69-119">在 Windows 10 安裝程式中，程式將會引導您完成安裝程序，第一個畫面會提供下載更新、驅動程式和選擇性功能的選項。</span><span class="sxs-lookup"><span data-stu-id="20e69-119">Within Windows 10 Setup, you will be guided through the installation process and the first screen provides an option to download updates, drivers and optional features.</span></span> <span data-ttu-id="20e69-120">建議您使用此選項，協助確保升級成功</span><span class="sxs-lookup"><span data-stu-id="20e69-120">This is recommended to help ensure success with the upgrade</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-3.png)

<span data-ttu-id="20e69-121">套用更新之後，Windows 10 安裝程式會移至下一個階段：選取映像。</span><span class="sxs-lookup"><span data-stu-id="20e69-121">Once updates have been applied, Windows 10 Setup will move to the next phase, Select Image.</span></span> <span data-ttu-id="20e69-122">在這裡，您必須選取您的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="20e69-122">Here, you will need to select your edition of Windows.</span></span> <span data-ttu-id="20e69-123">在此案例中，因為電腦安裝的是 Windows 7 企業版，所以您要選取 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="20e69-123">In this case, since the PC has Windows 7 Enterprise installed, you would select Windows 10 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-4.png)

<span data-ttu-id="20e69-124">在 Windows 10 安裝程式的下一個畫面中，您會看到適用的注意事項與授權條款。</span><span class="sxs-lookup"><span data-stu-id="20e69-124">In the next screen in Windows 10 Setup, you’re presented with applicable notices and license terms.</span></span> <span data-ttu-id="20e69-125">閱讀並了解注意事項和條款之後，請按一下 [接受] 繼續，或按一下 [拒絕] 取消安裝。</span><span class="sxs-lookup"><span data-stu-id="20e69-125">Once you have read and understand the notices and terms, click “Accept” to continue or “Decline” to cancel.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-5.png)

<span data-ttu-id="20e69-126">現在 Windows 10 安裝程式會尋找其他更新。</span><span class="sxs-lookup"><span data-stu-id="20e69-126">Now Windows 10 Setup will look for additional updates.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-6.png)

<span data-ttu-id="20e69-127">完成之後，Windows 10 安裝程式就可以開始安裝，而且依預設是設定為安裝 Windows 10，並且保留您的個人檔案和已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e69-127">Once complete, Windows 10 Setup is ready to install and by default is configured to install Windows 10 and keep your personal files and apps installed.</span></span> <span data-ttu-id="20e69-128">此為建議選項。</span><span class="sxs-lookup"><span data-stu-id="20e69-128">This is the recommended option.</span></span> <span data-ttu-id="20e69-129">按一下 [變更要保留的項目]，您會發現其他選項。</span><span class="sxs-lookup"><span data-stu-id="20e69-129">By clicking, “Change what to keep,” you’ll find additional options.</span></span> <span data-ttu-id="20e69-130">否則，請按一下 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="20e69-130">Otherwise, click “Install.”</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-7.png)

<span data-ttu-id="20e69-131">如果您選取 [變更要保留的項目]，您會看到下列選項：</span><span class="sxs-lookup"><span data-stu-id="20e69-131">If you select “Change what to keep”, you’ll be presented with these options:</span></span>

<span data-ttu-id="20e69-132">[只保留個人檔案] 不會從 Windows 7 將您已安裝的應用程式或設定移動到 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="20e69-132">“Keep personal files only” will not move your installed apps or settings from Windows 7 to Windows 10.</span></span> <span data-ttu-id="20e69-133">只會將您的檔案和使用者帳戶移動到 Windows。</span><span class="sxs-lookup"><span data-stu-id="20e69-133">Instead it will only move your files and user accounts to Windows.</span></span> <span data-ttu-id="20e69-134">使用此選項，您之後必須重新安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e69-134">Apps will need to be reinstalled later with this option.</span></span> <span data-ttu-id="20e69-135">只有當您確定在 Windows 安裝之後，您可以重新安裝或設定需要的應用程式時，才使用此選項，否則請維持預設的 [保留個人檔案與應用程式] 選項。</span><span class="sxs-lookup"><span data-stu-id="20e69-135">Only use this option if you are confident you can reinstall and configure the apps you will need after Windows is installed, otherwise stick with the default “Keep personal files and apps” option.</span></span>

<span data-ttu-id="20e69-136">[不保留任何項目] 會刪除您的檔案、應用程式及設定，並執行 Windows 的全新安裝。</span><span class="sxs-lookup"><span data-stu-id="20e69-136">“Nothing” will delete your files, apps and settings and perform a clean install of Windows.</span></span> <span data-ttu-id="20e69-137">只有當您先前已經備份想要保留的資料，而且能夠重新安裝您的應用程式時，才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="20e69-137">Use this option only if you have previously backed up the data you want to keep and you are able to reinstall your apps.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-8.png)

<span data-ttu-id="20e69-138">現在 Windows 10 安裝程式會根據您在上一個畫面中選取的項目再次取得更新。</span><span class="sxs-lookup"><span data-stu-id="20e69-138">Now Windows 10 Setup will get updates again based on what you selected in the previous screen.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-9.png)

<span data-ttu-id="20e69-139">現在 Windows 10 會花幾分鐘的時間安裝，如果您選擇保留您的個人檔案和應用程式，所有項目都會在相同的檔案位置，您的應用程式現在會出現在 Windows 10 中。</span><span class="sxs-lookup"><span data-stu-id="20e69-139">Now Windows 10 will install for several minutes and if you chose to keep your personal files and apps, everything will be in the same file locations and your apps will now be available in Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-10.png)

## 

## <a name="recovery-in-windows-10"></a><span data-ttu-id="20e69-140">在 Windows 10 中復原</span><span class="sxs-lookup"><span data-stu-id="20e69-140">Recovery in Windows 10</span></span>

<span data-ttu-id="20e69-141">安裝 Windows 10 之後，Windows 10 中的 [復原] 選項提供您最多 10 天的時間可以回復到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="20e69-141">After Windows 10 is installed, the Recovery option in Windows 10 gives you up to 10 days to go back to Windows 7.</span></span> <span data-ttu-id="20e69-142">如果裝置或您系統上的應用程式無法正常執行，使得您必須回復到先前的 Windows 7 安裝，這個選項很好用。</span><span class="sxs-lookup"><span data-stu-id="20e69-142">This is useful if a device or app on your system does not function properly and you need to go back to your previous Windows 7 installation.</span></span> <span data-ttu-id="20e69-143">10 天之後，依預設 Windows 10 會釋出您硬碟上由 Windows 7 復原檔案所使用的空間，然後刪除先前安裝的檔案。</span><span class="sxs-lookup"><span data-stu-id="20e69-143">After 10 days, by default Windows 10 will free up the space consumed by your Windows 7 recovery files on your hard drive and delete files from the previous installation.</span></span> <span data-ttu-id="20e69-144">在這之後，雖然 Windows 7 已刪除，您也無法還原成 Windows 7，但是您的應用程式和個人檔案仍會保留在 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="20e69-144">Although Windows 7 after this time is deleted and you won’t be able to revert Windows 7, your apps and personal files will remain in Windows 10.</span></span>

<span data-ttu-id="20e69-145">若要啟動「回復到 Windows 7」程序，請瀏覽至 [設定] \> [更新與安全性] \> [復原]。</span><span class="sxs-lookup"><span data-stu-id="20e69-145">To start the Go back to Windows 7 process, navigate to Settings \> Update & Security \> Recovery.</span></span> <span data-ttu-id="20e69-146">在 [回到 Windows 7] 下，選取 [開始]。</span><span class="sxs-lookup"><span data-stu-id="20e69-146">Under Go back to Windows 7, select “Get started.”</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-11.png)

<span data-ttu-id="20e69-147">現在，Windows 10 會詢問您為什麼要回復。</span><span class="sxs-lookup"><span data-stu-id="20e69-147">Now, Windows 10 will ask why you are going back.</span></span> <span data-ttu-id="20e69-148">如果有技術方面的原因，填寫內容有助於推動解決方案，確保其他人可以從您的經驗中獲益。</span><span class="sxs-lookup"><span data-stu-id="20e69-148">If there is a technical reason, this is useful to fill out in order to help drive resolution and ensure others can benefit from your experience.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-12.png)

<span data-ttu-id="20e69-149">很多時候，您的 Windows 10 版本會有更新，或許可以解決技術性問題。</span><span class="sxs-lookup"><span data-stu-id="20e69-149">In many cases, your version of Windows 10 will have had updates issued, which may resolve technical issues.</span></span> <span data-ttu-id="20e69-150">建議您檢查是否有更新，如果找到並安裝更新，請檢查是否能夠修正您遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="20e69-150">It is encouraged that you check for updates and if found and installed, then check if that fixes the problems you have experienced.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-13.png)

<span data-ttu-id="20e69-151">如果更新無法解決問題，您還是需要還原到先前安裝的 Windows 7，您可能必須重新安裝某些應用程式 (例如您在執行 Windows 10 期間安裝的任何應用程式)，也可能會遺失某些設定。</span><span class="sxs-lookup"><span data-stu-id="20e69-151">If the updates do not resolve issues and you do need to revert to your previous installation of Windows 7, there is a chance that some apps will need to be reinstalled – such as any app that installed during the time you were running Windows 10 – and some settings may be lost.</span></span> <span data-ttu-id="20e69-152">重要的是，您在使用 Windows 10 時儲存在本機的檔案和文件都會保留，當您回到 Windows 7 之後，就能使用。</span><span class="sxs-lookup"><span data-stu-id="20e69-152">Importantly, files and docs you’ve saved locally while using Windows 10 will remain and be available for you once you’re back in Windows 7.</span></span> 

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-14.png)

<span data-ttu-id="20e69-153">在您開始之前，請確認您已經準備好先前 Windows 7 安裝的本機或網域帳戶和密碼。</span><span class="sxs-lookup"><span data-stu-id="20e69-153">Before you get started, make sure you have a local or domain account and password ready from the previous Windows 7 installation.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-15.png)

<span data-ttu-id="20e69-154">在這裡，您可以啟動回到 Windows 7 的程序。</span><span class="sxs-lookup"><span data-stu-id="20e69-154">From here you can initiate the process to go back to Windows 7.</span></span> <span data-ttu-id="20e69-155">幾分鐘之後，電腦會開機回到 Windows 7，您的體驗就會與升級到 Windows 10 之前相同。</span><span class="sxs-lookup"><span data-stu-id="20e69-155">After a few minutes, your PC will boot back into Windows 7 with the same experience prior to upgrading to Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-16.png)

## <a name="moving-to-windows-10-on-a-new-pc"></a><span data-ttu-id="20e69-156">在新電腦上移至 Windows 10</span><span class="sxs-lookup"><span data-stu-id="20e69-156">Moving to Windows 10 on a new PC</span></span>

<span data-ttu-id="20e69-157">另外一個建議的方法是在新電腦上移至 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="20e69-157">Another recommended option is to move to Windows 10 on a new PC.</span></span> <span data-ttu-id="20e69-158">如果您偏好這麼做，可以使用 [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) 備份、[內建於 Windows 的備份與還原](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10)、手動使用[外部儲存裝置](https://support.microsoft.com/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10)，或使用像 [Laplink 的 PCmover Express](https://www.microsoft.com/windows/transfer-your-data) 的工具，轉移舊電腦的檔案。</span><span class="sxs-lookup"><span data-stu-id="20e69-158">If this is your preference, you can transfer your files from your old computer using [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) backup, [Backup and Restore built into Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manually using an [external storage device](https://support.microsoft.com/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10), or tools like [Laplink’s PCmover Express](https://www.microsoft.com/windows/transfer-your-data).</span></span> <span data-ttu-id="20e69-159">如果使用上述任何一種選項，您還是必須重新安裝未隨附於 Windows 10 的所有必要應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e69-159">With any of these options, you will still need to re-install any required applications not included with Windows 10.</span></span> <span data-ttu-id="20e69-160">若要深入了解從執行 Windows 7 的現有電腦手動移至 Windows 10 新電腦的選項，請參閱 Windows 支援中的[移至 Windows 10 電腦](https://support.microsoft.com/help/4229823?ocid=MoveToWindows10)。</span><span class="sxs-lookup"><span data-stu-id="20e69-160">To learn more about your options for manually moving from an existing PC running Windows 7 to a new PC with Windows 10, see [Moving to a Windows 10 PC](https://support.microsoft.com/help/4229823?ocid=MoveToWindows10) in Windows Support.</span></span>

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[<span data-ttu-id="20e69-161">桌面部署中心</span><span class="sxs-lookup"><span data-stu-id="20e69-161">Desktop Deployment Center</span></span>](https://aka.ms/howtoshift)