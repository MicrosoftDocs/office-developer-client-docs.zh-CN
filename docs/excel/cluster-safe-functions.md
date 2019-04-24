---
title: 群集安全函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 787badaf-8782-454d-a016-7eae83bbd8a9
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d32925fcd5c3be7fe3e615ee2290f25c7595911c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310974"
---
# <a name="cluster-safe-functions"></a><span data-ttu-id="df63a-103">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="df63a-103">Cluster safe functions</span></span>

<span data-ttu-id="df63a-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df63a-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="df63a-105">在 excel 2013 中, excel 可以通过专用群集连接器接口将用户定义的函数 (UDF) 调用卸载到高性能计算群集中。</span><span class="sxs-lookup"><span data-stu-id="df63a-105">In Excel 2013, Excel can offload User-Defined Function (UDF) calls to a high-performance computing cluster through a dedicated cluster connector interface.</span></span> <span data-ttu-id="df63a-106">计算群集供应商提供群集连接器。</span><span class="sxs-lookup"><span data-stu-id="df63a-106">Compute cluster vendors provide Cluster Connectors.</span></span> <span data-ttu-id="df63a-107">UDF 作者可以将其 udf 声明为群集安全的, 然后在出现群集连接器时, Excel 会将对这些 udf 的调用发送到群集连接器以进行卸载。</span><span class="sxs-lookup"><span data-stu-id="df63a-107">UDF authors can declare their UDFs as cluster safe and then, when a cluster connector is present, Excel sends calls to these UDFs to the cluster connector for offloading.</span></span>
  
<span data-ttu-id="df63a-108">当 Excel 在重新计算过程中发现群集安全 UDF 时, 它会将当前正在运行的 XLL 的名称、群集安全 udf 的名称以及群集连接器的任何参数传递给该名称。</span><span class="sxs-lookup"><span data-stu-id="df63a-108">When Excel discovers a cluster-safe UDF during recalculation, it passes the name of the XLL that is currently running, the name of the cluster-safe UDF, and any parameters to the cluster connector.</span></span> <span data-ttu-id="df63a-109">连接器远程运行 UDF 调用, 并将结果返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="df63a-109">The connector runs the UDF call remotely and returns the results to Excel.</span></span> <span data-ttu-id="df63a-110">非相关计算将继续, 并且当群集连接器运行完 UDF 后, 它会将结果传递到 Excel, 并继续进行依赖计算。</span><span class="sxs-lookup"><span data-stu-id="df63a-110">Non-dependent calculation continues and when the cluster connector has finished running the UDF, it passes the results to Excel and dependent calculations continue.</span></span> <span data-ttu-id="df63a-111">此异步行为的机制模仿异步 udf 使用的机制, 不同之处在于群集连接器管理异步方面而不是 UDF 作者。</span><span class="sxs-lookup"><span data-stu-id="df63a-111">The mechanism for this asynchronous behavior mimics the mechanism used by asynchronous UDFs, except that the cluster connector manages the asynchronous aspects instead of the UDF author.</span></span> <span data-ttu-id="df63a-112">通常, 群集连接器实现 XLL 填充程序以加载 xll 并在计算群集节点上运行 udf。</span><span class="sxs-lookup"><span data-stu-id="df63a-112">Typically, a cluster connector implements an XLL shim to load XLLs and run UDFs on compute cluster nodes.</span></span>
  
<span data-ttu-id="df63a-113">将 udf 声明为群集安全的机制类似于声明 udf 的安全进行多线程重新计算。</span><span class="sxs-lookup"><span data-stu-id="df63a-113">The mechanics of declaring UDFs as cluster-safe resemble those of declaring UDFs as safe for multi-threaded recalculation.</span></span> <span data-ttu-id="df63a-114">但是, 由于 UDF 不一定与同一 Excel 会话中的其他 udf 运行在同一台计算机上, 因此在编写群集安全 udf 时有不同的注意事项。</span><span class="sxs-lookup"><span data-stu-id="df63a-114">However, because the UDF is not necessarily running on the same computer as other UDFs from the same Excel session, there are different considerations when writing cluster-safe UDFs.</span></span>
  
<span data-ttu-id="df63a-115">若要将 UDF 注册为群集安全, 必须通过**Excel12**或**Excel12v**接口调用[xlfRegister (Form 1)](xlfregister-form-1.md)回调函数。</span><span class="sxs-lookup"><span data-stu-id="df63a-115">To register a UDF as cluster-safe, you must call the [xlfRegister (Form 1)](xlfregister-form-1.md) callback function through the **Excel12** or **Excel12v** interface.</span></span> <span data-ttu-id="df63a-116">有关这些接口的详细信息, 请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v](excel4v-excel12v.md)。</span><span class="sxs-lookup"><span data-stu-id="df63a-116">For more information about these interfaces, see the [Excel4/Excel12](excel4-excel12.md) and [Excel4v/Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="df63a-117">不支持通过**Excel4**或**Excel4v**接口将 UDF 注册为群集安全的。</span><span class="sxs-lookup"><span data-stu-id="df63a-117">Registering a UDF as cluster-safe through the **Excel4** or **Excel4v** interface is not supported.</span></span> 
  
<span data-ttu-id="df63a-118">如果将某个函数注册为群集安全的, 则必须确保该函数以群集安全方式行为。</span><span class="sxs-lookup"><span data-stu-id="df63a-118">If you register a function as cluster-safe, you must ensure that the function behaves in a cluster-safe way.</span></span> <span data-ttu-id="df63a-119">尽管群集连接器的确切行为是特定于实现的, 但您应将 UDF 设计为在分布式计算机系统上运行, 并具有以下特征:</span><span class="sxs-lookup"><span data-stu-id="df63a-119">Although the exact behavior of the cluster connector is implementation-specific, you should design your UDF to run on a distributed computer system and to have the following characteristics:</span></span>
  
- <span data-ttu-id="df63a-120">UDF 不应依赖于任何内存状态。</span><span class="sxs-lookup"><span data-stu-id="df63a-120">A UDF should not rely on any memory state.</span></span> <span data-ttu-id="df63a-121">例如, UDF 不应依赖于现有内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="df63a-121">For example, a UDF should not rely on an existing in-memory cache.</span></span>
    
- <span data-ttu-id="df63a-122">UDF 不应执行群集连接器提供程序不支持的 Excel 回调。</span><span class="sxs-lookup"><span data-stu-id="df63a-122">A UDF should not perform Excel callbacks that the cluster connector provider does not support.</span></span>
    
<span data-ttu-id="df63a-123">除了群集安全的行为之外, 群集安全 udf 还提供以下技术限制:</span><span class="sxs-lookup"><span data-stu-id="df63a-123">In addition to cluster-safe behavior, there are the following technical restrictions on cluster-safe UDFs:</span></span>
  
1. <span data-ttu-id="df63a-124">没有 XLOPER 参数 (类型为 ' P ', ' R ')。</span><span class="sxs-lookup"><span data-stu-id="df63a-124">No XLOPER arguments (types 'P', 'R').</span></span>
    
2. <span data-ttu-id="df63a-125">没有支持区域引用的 XLOPER12 参数 (类型为 "U")。</span><span class="sxs-lookup"><span data-stu-id="df63a-125">No XLOPER12 arguments that support range references (type 'U').</span></span>
    
3. <span data-ttu-id="df63a-126">不能是宏表等效函数 ("#" 和 "&amp;" 不能组合)。</span><span class="sxs-lookup"><span data-stu-id="df63a-126">Cannot be a macro sheet equivalent function ('#' and '&amp;' cannot be combined).</span></span>
    
<span data-ttu-id="df63a-127">对于执行时间较短的 udf, 分担的开销可能大于执行 UDF 所需的时间, negating 使用此基础结构的许多好处。</span><span class="sxs-lookup"><span data-stu-id="df63a-127">For UDFs with shorter execution times, the overhead of offloading may be larger than the time it takes the UDF to execute, negating many of the benefits of using this infrastructure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df63a-128">不能将群集安全 udf 声明为异步 udf。</span><span class="sxs-lookup"><span data-stu-id="df63a-128">You cannot declare a cluster-safe UDF as an asynchronous UDF.</span></span> 
  
<span data-ttu-id="df63a-129">UDF 可以通过调用[xlRunningOnCluster](xlrunningoncluster.md)回调函数来确定它是否正在使用群集连接器运行。</span><span class="sxs-lookup"><span data-stu-id="df63a-129">A UDF can determine whether it is being run using a cluster connector by calling the [xlRunningOnCluster](xlrunningoncluster.md) callback function.</span></span> 
  

