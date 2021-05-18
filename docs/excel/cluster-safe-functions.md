---
title: 群集安全函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 787badaf-8782-454d-a016-7eae83bbd8a9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d32925fcd5c3be7fe3e615ee2290f25c7595911c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409298"
---
# <a name="cluster-safe-functions"></a><span data-ttu-id="96edb-103">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="96edb-103">Cluster safe functions</span></span>

<span data-ttu-id="96edb-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96edb-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="96edb-105">在 Excel 2013 Excel，User-Defined Function (UDF) 通过专用群集连接器接口卸载对高性能计算群集的调用。</span><span class="sxs-lookup"><span data-stu-id="96edb-105">In Excel 2013, Excel can offload User-Defined Function (UDF) calls to a high-performance computing cluster through a dedicated cluster connector interface.</span></span> <span data-ttu-id="96edb-106">计算群集供应商提供群集连接器。</span><span class="sxs-lookup"><span data-stu-id="96edb-106">Compute cluster vendors provide Cluster Connectors.</span></span> <span data-ttu-id="96edb-107">UDF 作者可以将其 UDF 声明为群集安全，然后，当群集连接器存在时，Excel将调用发送到群集连接器进行卸载。</span><span class="sxs-lookup"><span data-stu-id="96edb-107">UDF authors can declare their UDFs as cluster safe and then, when a cluster connector is present, Excel sends calls to these UDFs to the cluster connector for offloading.</span></span>
  
<span data-ttu-id="96edb-108">当Excel发现群集安全的 UDF 时，它会将当前运行的 XLL 的名称、群集安全 UDF 的名称以及任何参数传递给群集连接器。</span><span class="sxs-lookup"><span data-stu-id="96edb-108">When Excel discovers a cluster-safe UDF during recalculation, it passes the name of the XLL that is currently running, the name of the cluster-safe UDF, and any parameters to the cluster connector.</span></span> <span data-ttu-id="96edb-109">连接器远程运行 UDF 调用，并返回结果以Excel。</span><span class="sxs-lookup"><span data-stu-id="96edb-109">The connector runs the UDF call remotely and returns the results to Excel.</span></span> <span data-ttu-id="96edb-110">非从属计算将继续，当群集连接器运行完 UDF 后，它会将结果传递给Excel计算继续进行。</span><span class="sxs-lookup"><span data-stu-id="96edb-110">Non-dependent calculation continues and when the cluster connector has finished running the UDF, it passes the results to Excel and dependent calculations continue.</span></span> <span data-ttu-id="96edb-111">此异步行为的机制模拟异步 UDF 使用的机制，只是群集连接器管理异步方面而不是 UDF 作者。</span><span class="sxs-lookup"><span data-stu-id="96edb-111">The mechanism for this asynchronous behavior mimics the mechanism used by asynchronous UDFs, except that the cluster connector manages the asynchronous aspects instead of the UDF author.</span></span> <span data-ttu-id="96edb-112">通常，群集连接器实现 XLL 填充程序，以加载 XLL 并运行计算群集节点上的 UDF。</span><span class="sxs-lookup"><span data-stu-id="96edb-112">Typically, a cluster connector implements an XLL shim to load XLLs and run UDFs on compute cluster nodes.</span></span>
  
<span data-ttu-id="96edb-113">将 UDF 声明为群集安全的机制类似于将 UDF 声明为多线程重新计算安全的机制。</span><span class="sxs-lookup"><span data-stu-id="96edb-113">The mechanics of declaring UDFs as cluster-safe resemble those of declaring UDFs as safe for multi-threaded recalculation.</span></span> <span data-ttu-id="96edb-114">但是，由于 UDF 不一定与来自同一 Excel 会话的其他 UDF 运行在同一计算机上，因此编写群集安全的 UDF 时有不同的注意事项。</span><span class="sxs-lookup"><span data-stu-id="96edb-114">However, because the UDF is not necessarily running on the same computer as other UDFs from the same Excel session, there are different considerations when writing cluster-safe UDFs.</span></span>
  
<span data-ttu-id="96edb-115">若要将 UDF 注册为群集安全，必须通过 **Excel12 或 Excel12v**) 调用 [xlfRegister](xlfregister-form-1.md) (Form **1**) 回调函数。</span><span class="sxs-lookup"><span data-stu-id="96edb-115">To register a UDF as cluster-safe, you must call the [xlfRegister (Form 1)](xlfregister-form-1.md) callback function through the **Excel12** or **Excel12v** interface.</span></span> <span data-ttu-id="96edb-116">有关这些接口详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v。](excel4v-excel12v.md)</span><span class="sxs-lookup"><span data-stu-id="96edb-116">For more information about these interfaces, see the [Excel4/Excel12](excel4-excel12.md) and [Excel4v/Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="96edb-117">不支持通过 Excel4 或 **Excel4v** 接口将UDF 注册为群集安全。</span><span class="sxs-lookup"><span data-stu-id="96edb-117">Registering a UDF as cluster-safe through the **Excel4** or **Excel4v** interface is not supported.</span></span> 
  
<span data-ttu-id="96edb-118">如果将函数注册为群集安全函数，则必须确保该函数以群集安全方式运行。</span><span class="sxs-lookup"><span data-stu-id="96edb-118">If you register a function as cluster-safe, you must ensure that the function behaves in a cluster-safe way.</span></span> <span data-ttu-id="96edb-119">尽管群集连接器的确切行为特定于实现，但您应该设计 UDF 以在分布式计算机系统上运行，并具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="96edb-119">Although the exact behavior of the cluster connector is implementation-specific, you should design your UDF to run on a distributed computer system and to have the following characteristics:</span></span>
  
- <span data-ttu-id="96edb-120">UDF 不应依赖任何内存状态。</span><span class="sxs-lookup"><span data-stu-id="96edb-120">A UDF should not rely on any memory state.</span></span> <span data-ttu-id="96edb-121">例如，UDF 不应依赖现有的内存中缓存。</span><span class="sxs-lookup"><span data-stu-id="96edb-121">For example, a UDF should not rely on an existing in-memory cache.</span></span>
    
- <span data-ttu-id="96edb-122">UDF 不应执行Excel连接器提供程序不支持的回调。</span><span class="sxs-lookup"><span data-stu-id="96edb-122">A UDF should not perform Excel callbacks that the cluster connector provider does not support.</span></span>
    
<span data-ttu-id="96edb-123">除了群集安全行为之外，群集安全 UDF 还具有以下技术限制：</span><span class="sxs-lookup"><span data-stu-id="96edb-123">In addition to cluster-safe behavior, there are the following technical restrictions on cluster-safe UDFs:</span></span>
  
1. <span data-ttu-id="96edb-124">没有 XLOPER 参数 (类型"P"，"R") 。</span><span class="sxs-lookup"><span data-stu-id="96edb-124">No XLOPER arguments (types 'P', 'R').</span></span>
    
2. <span data-ttu-id="96edb-125">没有支持区域引用的 XLOPER12 参数 (类型"U") 。</span><span class="sxs-lookup"><span data-stu-id="96edb-125">No XLOPER12 arguments that support range references (type 'U').</span></span>
    
3. <span data-ttu-id="96edb-126">不能是宏表等效函数 ('#'和 &amp; '' 不能合并) 。</span><span class="sxs-lookup"><span data-stu-id="96edb-126">Cannot be a macro sheet equivalent function ('#' and '&amp;' cannot be combined).</span></span>
    
<span data-ttu-id="96edb-127">对于执行时间较短的 UDF，卸载的开销可能大于执行 UDF 所花的时间，这将抵消使用此基础结构的许多好处。</span><span class="sxs-lookup"><span data-stu-id="96edb-127">For UDFs with shorter execution times, the overhead of offloading may be larger than the time it takes the UDF to execute, negating many of the benefits of using this infrastructure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96edb-128">无法将群集安全 UDF 声明为异步 UDF。</span><span class="sxs-lookup"><span data-stu-id="96edb-128">You cannot declare a cluster-safe UDF as an asynchronous UDF.</span></span> 
  
<span data-ttu-id="96edb-129">UDF 可以通过调用 [xlRunningOnCluster](xlrunningoncluster.md) 回调函数来确定它是否正在使用群集连接器运行。</span><span class="sxs-lookup"><span data-stu-id="96edb-129">A UDF can determine whether it is being run using a cluster connector by calling the [xlRunningOnCluster](xlrunningoncluster.md) callback function.</span></span> 
  

