---
title: 在 IIS 上指定每个处理器的线程数
TOCTitle: Specifying Threads Per Processor on IIS
ms:assetid: 12889d7b-5415-8077-2ca0-1c3a96fb89ec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248898(v=office.15)
ms:contentKeyID: 48543344
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: de3c8c99c7f615928ea0a0f1e15171cc90b25f3d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466111"
---
# <a name="specifying-threads-per-processor-on-iis"></a><span data-ttu-id="6b9b8-102">在 IIS 上指定每个处理器的线程数</span><span class="sxs-lookup"><span data-stu-id="6b9b8-102">Specifying Threads Per Processor on IIS</span></span>


<span data-ttu-id="6b9b8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6b9b8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6b9b8-p101">当在 Internet 信息服务 4.0 或更高版本中使用 RDS 时，可以通过操作 Web 服务器上的注册表来控制在每个处理器上创建的线程数。在高通讯量或者通讯量虽小但查询较大的情况下，每处理器的线程数可能会影响性能。用户应进行试验以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-p101">When using RDS with Internet Information Services 4.0 or later, the number of threads created per processor can be controlled by manipulating the registry on the Web server. The number of threads per processor can affect performance in a high traffic situation, or in low traffic situations with large query sizes. The user should experiment for best results.</span></span>

<span data-ttu-id="6b9b8-107">用来确定和更改此设置默认值的方法取决于 IIS 4.0 服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-107">The method used to determine and change the default value for this setting depends upon the configuration of the IIS 4.0 server.</span></span>

<span data-ttu-id="6b9b8-p102">如果 IIS 服务器上装有 MDAC 2.1.2.4202.3 (GA) 或更高版本，RDS 将与 ASP 脚本使用相同的组件服务（如果您使用的是 Windows NT，则为 Microsoft Transaction Services）线程池。每处理器线程数的默认值是 10。若要更改该默认值，必须向服务器注册表中添加以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="6b9b8-p102">With MDAC 2.1.2.4202.3 (GA) or later installed on the IIS server, RDS uses the same Component Services (or Microsoft Transaction Services, if you are using Windows NT) thread pool as ASP scripts use. The default value for the number of threads per processor is 10. To change the default, you must add the following key to the server registry:</span></span>

```vb 
 
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\MaxPoolThreads
```

<span data-ttu-id="6b9b8-111">其中*MaxPoolThreads*是注册表\_DWORD。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-111">where *MaxPoolThreads* is a REG\_DWORD.</span></span> <span data-ttu-id="6b9b8-112">除非明确添加到注册表中未显示*MaxPoolThreads* 。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-112">*MaxPoolThreads* does not appear in the Registry unless it is specifically added.</span></span> <span data-ttu-id="6b9b8-113">有效值的范围是从 5 到建议的最大值 20。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-113">Valid values range from 5 to a recommended maximum of 20.</span></span> <span data-ttu-id="6b9b8-114">如果指定的注册表项的值大于*PoolThreadLimit*项 （位于同一路径下） 的值，则使用*PoolThreadLimit*值。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-114">If the value specified by the registry key is greater than the value of the *PoolThreadLimit* key (located under the same path), then *PoolThreadLimit* value is used.</span></span>

<span data-ttu-id="6b9b8-p104">或者，如果在 IIS 服务器上装有 MDAC 2.1 2.1.1.3711.11 (GA) 或更低版本，则每处理器线程数的默认值为 6。若要更改该默认值，则必须向 IIS 服务器上的注册表中添加以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="6b9b8-p104">Alternatively, if MDAC 2.1 2.1.1.3711.11 (GA) or earlier is installed on the IIS server, the default value for the number of threads per processor is 6. To change the default, you must add the following key to the registry on the IIS server:</span></span>

```vb 
 
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W3SVC\Parameters\ADCThreads
```

<span data-ttu-id="6b9b8-117">其中*ADCThreads*是注册表\_DWORD。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-117">where *ADCThreads* is a REG\_DWORD.</span></span> <span data-ttu-id="6b9b8-118">除非明确添加到注册表中未显示*ADCThreads* 。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-118">*ADCThreads* does not appear in the Registry unless it is specifically added.</span></span> <span data-ttu-id="6b9b8-119">有效值的范围是从 1 到 50。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-119">The range of valid values is 1 to 50.</span></span> <span data-ttu-id="6b9b8-120">如果由注册表项指定的值大于 50，则将使用最大值 (50)。</span><span class="sxs-lookup"><span data-stu-id="6b9b8-120">If the value specified by the registry key is greater than 50, then the maximum value is used (50).</span></span>

