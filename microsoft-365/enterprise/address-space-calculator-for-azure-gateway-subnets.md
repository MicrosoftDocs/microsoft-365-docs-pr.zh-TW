---
title: Azure 閘道子網的位址空間計算機
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: 摘要：使用 C3、Python 或 PowerShell 計算 Azure 閘道子網的位址空間。
ms.openlocfilehash: d92bea5c36fde6277154d19365ed0bdaa5df4254
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780565"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a><span data-ttu-id="edca7-103">Azure 閘道子網的位址空間計算機</span><span class="sxs-lookup"><span data-stu-id="edca7-103">Address space calculator for Azure gateway subnets</span></span>

<span data-ttu-id="edca7-104">連線至其他網路之 Azure 基礎結構服務中的虛擬網路 (VNet) 必須具有閘道子網。</span><span class="sxs-lookup"><span data-stu-id="edca7-104">A virtual network (VNet) in Azure infrastructure services that is connected to other networks must have a gateway subnet.</span></span> <span data-ttu-id="edca7-105">定義閘道子網的最佳作法如下：</span><span class="sxs-lookup"><span data-stu-id="edca7-105">The best practices for defining the gateway subnet are:</span></span>

- <span data-ttu-id="edca7-106">閘道子網的前置長度可以有最大前置長度 29 (例如，10.119.255.248/29) ，但目前建議使用的前置詞長度為 27 (例如，10.119.255.224/27) 。</span><span class="sxs-lookup"><span data-stu-id="edca7-106">The prefix length of the gateway subnet can have a maximum prefix length of 29 (for example, 10.119.255.248/29), but the current recommendation is that you use a prefix length of 27 (for example, 10.119.255.224/27).</span></span>
- <span data-ttu-id="edca7-107">在定義閘道子網的位址空間時，請使用 VNet 位址空間的最後一部分。</span><span class="sxs-lookup"><span data-stu-id="edca7-107">When defining the address space of the gateway subnet, use the last part of the VNet address space.</span></span>

<span data-ttu-id="edca7-108">針對第二個建議，您可以透過將閘道子網所用的位數設定為0，以及 VNet 位址空間中的剩餘位數設定為1，以判斷閘道子網的位址空間。</span><span class="sxs-lookup"><span data-stu-id="edca7-108">For the second recommendation, you can determine the address space of the gateway subnet by setting the bits used for the gateway subnet to 0 and the remaining bits in the VNet address space to 1.</span></span> <span data-ttu-id="edca7-109">若要快速計算閘道子網位址空間，而不需要轉換成二進位及回到十進位，您可以使用以 c # 或 Python 或使用 PowerShell 命令區塊編寫的主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="edca7-109">To quickly calculate the gateway subnet address space without having to convert to binary and back to decimal, you can use a console application written in C# or Python or with a PowerShell command block.</span></span>

<span data-ttu-id="edca7-110">本文包含的 c #、Python 及 PowerShell 程式碼區塊，會根據 w.x.y.z/n 的值，計算 VNet 位址前置詞和閘道子網前置長度的閘道子網位址空間。</span><span class="sxs-lookup"><span data-stu-id="edca7-110">This article contains C#, Python, and PowerShell code blocks that calculate the gateway subnet address space based on the values of w.x.y.z/n for the VNet address prefix and the gateway subnet prefix length.</span></span>

## <a name="c-code-block"></a><span data-ttu-id="edca7-111">C # 程式碼區塊</span><span class="sxs-lookup"><span data-stu-id="edca7-111">C# code block</span></span>

<span data-ttu-id="edca7-112">使用此程式碼區塊，可在 c # 中建立主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="edca7-112">Use this code block to create a console app in C#.</span></span>

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("**_ Gateway subnet address space calculator for Azure virtual networks _*_");             
            Console.WriteLine("_*************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a><span data-ttu-id="edca7-113">Python 程式碼區塊</span><span class="sxs-lookup"><span data-stu-id="edca7-113">Python code block</span></span>

<span data-ttu-id="edca7-114">使用此程式碼區塊可在 Python 中建立主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="edca7-114">Use this code block to create a console app in Python.</span></span>

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("**_ Gateway subnet address space calculator for Azure virtual networks _*_")  
print("_*************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a><span data-ttu-id="edca7-115">PowerShell 命令區塊</span><span class="sxs-lookup"><span data-stu-id="edca7-115">PowerShell command block</span></span>

<span data-ttu-id="edca7-116">填寫值，並在 PowerShell 視窗或 PowerShell 整合式腳本環境 (ISE) 中執行所產生的命令區塊。</span><span class="sxs-lookup"><span data-stu-id="edca7-116">Fill in the values and run the resulting command block in a PowerShell window or in the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a><span data-ttu-id="edca7-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="edca7-117">Related topics</span></span>

[<span data-ttu-id="edca7-118">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="edca7-118">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)