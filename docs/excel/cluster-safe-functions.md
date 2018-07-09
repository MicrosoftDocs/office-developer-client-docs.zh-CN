---
title: 群集安全函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 787badaf-8782-454d-a016-7eae83bbd8a9
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: f73f49e4d76a8545399eede283b70551ee6569f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773629"
---
# <a name="cluster-safe-functions"></a><span data-ttu-id="6aba5-103">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="6aba5-103">Cluster safe functions</span></span>

<span data-ttu-id="6aba5-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6aba5-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6aba5-105">Excel 2013 中 Excel 可以卸载到通过专用的群集连接器接口的高性能计算群集的用户定义函数 (UDF) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6aba5-105">In Excel 2013, Excel can offload User-Defined Function (UDF) calls to a high-performance computing cluster through a dedicated cluster connector interface.</span></span> <span data-ttu-id="6aba5-106">计算群集供应商提供群集连接器。</span><span class="sxs-lookup"><span data-stu-id="6aba5-106">Compute cluster vendors provide Cluster Connectors.</span></span> <span data-ttu-id="6aba5-107">UDF 作者可以将声明其 Udf 为群集安全，然后存在群集连接器时，Excel 将发送这些 Udf 调用到卸载的群集连接器。</span><span class="sxs-lookup"><span data-stu-id="6aba5-107">UDF authors can declare their UDFs as cluster safe and then, when a cluster connector is present, Excel sends calls to these UDFs to the cluster connector for offloading.</span></span>
  
<span data-ttu-id="6aba5-108">当 Excel 重新计算过程中发现的群集安全 UDF 时，它将传递当前正在运行，群集安全 UDF 和任何参数的名称到群集连接器的 XLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="6aba5-108">When Excel discovers a cluster-safe UDF during recalculation, it passes the name of the XLL that is currently running, the name of the cluster-safe UDF, and any parameters to the cluster connector.</span></span> <span data-ttu-id="6aba5-109">连接器在远程运行 UDF 调用，并将结果返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="6aba5-109">The connector runs the UDF call remotely and returns the results to Excel.</span></span> <span data-ttu-id="6aba5-110">独立计算继续完成群集连接器之后运行 UDF，请将结果传递到 Excel 和依赖计算继续。</span><span class="sxs-lookup"><span data-stu-id="6aba5-110">Non-dependent calculation continues and when the cluster connector has finished running the UDF, it passes the results to Excel and dependent calculations continue.</span></span> <span data-ttu-id="6aba5-111">此异步行为的机制之处在于群集连接器管理而不是 UDF 作者的异步方面模拟使用异步 Udf 的机制。</span><span class="sxs-lookup"><span data-stu-id="6aba5-111">The mechanism for this asynchronous behavior mimics the mechanism used by asynchronous UDFs, except that the cluster connector manages the asynchronous aspects instead of the UDF author.</span></span> <span data-ttu-id="6aba5-112">通常，群集连接器实现 XLL 填充码加载 xll 和群集节点上 compute 运行 Udf。</span><span class="sxs-lookup"><span data-stu-id="6aba5-112">Typically, a cluster connector implements an XLL shim to load XLLs and run UDFs on compute cluster nodes.</span></span>
  
<span data-ttu-id="6aba5-113">将 Udf 声明为群集安全的机制类似的 Udf 声明为可安全编写多线程的重新计算。</span><span class="sxs-lookup"><span data-stu-id="6aba5-113">The mechanics of declaring UDFs as cluster-safe resemble those of declaring UDFs as safe for multi-threaded recalculation.</span></span> <span data-ttu-id="6aba5-114">但是，因为其他 Udf 从同一个 Excel 会话在同一台计算机上没有一定运行 UDF，也会不同注意事项编写群集安全 Udf。</span><span class="sxs-lookup"><span data-stu-id="6aba5-114">However, because the UDF is not necessarily running on the same computer as other UDFs from the same Excel session, there are different considerations when writing cluster-safe UDFs.</span></span>
  
<span data-ttu-id="6aba5-115">若要注册为群集安全 UDF，必须通过**Excel12**或**Excel12v**界面调用[xlfRegister (窗体 1)](xlfregister-form-1.md)回调函数。</span><span class="sxs-lookup"><span data-stu-id="6aba5-115">To register a UDF as cluster-safe, you must call the [xlfRegister (Form 1)](xlfregister-form-1.md) callback function through the **Excel12** or **Excel12v** interface.</span></span> <span data-ttu-id="6aba5-116">有关这些接口的详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v](excel4v-excel12v.md)。</span><span class="sxs-lookup"><span data-stu-id="6aba5-116">For more information about these interfaces, see the [Excel4/Excel12](excel4-excel12.md) and [Excel4v/Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="6aba5-117">注册为 UDF 不支持通过**Excel4**或**Excel4v**界面群集安全。</span><span class="sxs-lookup"><span data-stu-id="6aba5-117">Registering a UDF as cluster-safe through the **Excel4** or **Excel4v** interface is not supported.</span></span> 
  
<span data-ttu-id="6aba5-118">如果您在注册为群集安全函数，则必须确保函数行为群集安全方式。</span><span class="sxs-lookup"><span data-stu-id="6aba5-118">If you register a function as cluster-safe, you must ensure that the function behaves in a cluster-safe way.</span></span> <span data-ttu-id="6aba5-119">尽管群集连接器的具体行为是特定于实现的您应设计您的 UDF 的分布式的计算机系统上运行并具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="6aba5-119">Although the exact behavior of the cluster connector is implementation-specific, you should design your UDF to run on a distributed computer system and to have the following characteristics:</span></span>
  
- <span data-ttu-id="6aba5-120">UDF 不应依赖于任何内存状态。</span><span class="sxs-lookup"><span data-stu-id="6aba5-120">A UDF should not rely on any memory state.</span></span> <span data-ttu-id="6aba5-121">例如，UDF 应不依赖于现有内存中缓存。</span><span class="sxs-lookup"><span data-stu-id="6aba5-121">For example, a UDF should not rely on an existing in-memory cache.</span></span>
    
- <span data-ttu-id="6aba5-122">UDF 不应执行的群集连接器提供程序不支持的 Excel 回调。</span><span class="sxs-lookup"><span data-stu-id="6aba5-122">A UDF should not perform Excel callbacks that the cluster connector provider does not support.</span></span>
    
<span data-ttu-id="6aba5-123">群集安全行为，除了有群集安全 Udf 的以下技术限制：</span><span class="sxs-lookup"><span data-stu-id="6aba5-123">In addition to cluster-safe behavior, there are the following technical restrictions on cluster-safe UDFs:</span></span>
  
1. <span data-ttu-id="6aba5-124">没有 XLOPER 参数 （类型 P，R）。</span><span class="sxs-lookup"><span data-stu-id="6aba5-124">No XLOPER arguments (types 'P', 'R').</span></span>
    
2. <span data-ttu-id="6aba5-125">支持范围引用 （类型 U） 没有 XLOPER12 参数。</span><span class="sxs-lookup"><span data-stu-id="6aba5-125">No XLOPER12 arguments that support range references (type 'U').</span></span>
    
3. <span data-ttu-id="6aba5-126">不能为等效宏工作表函数 (# 和&amp;不能组合)。</span><span class="sxs-lookup"><span data-stu-id="6aba5-126">Cannot be a macro sheet equivalent function ('#' and '&amp;' cannot be combined).</span></span>
    
<span data-ttu-id="6aba5-127">对于较短的执行时间较 Udf，卸载开销可能大于所用来执行，UDF 的时间绝对值的许多使用此基础结构的好处。</span><span class="sxs-lookup"><span data-stu-id="6aba5-127">For UDFs with shorter execution times, the overhead of offloading may be larger than the time it takes the UDF to execute, negating many of the benefits of using this infrastructure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6aba5-128">不能作为异步 UDF 声明群集安全 UDF。</span><span class="sxs-lookup"><span data-stu-id="6aba5-128">You cannot declare a cluster-safe UDF as an asynchronous UDF.</span></span> 
  
<span data-ttu-id="6aba5-129">UDF 可以确定是否正在运行通过调用[xlRunningOnCluster](xlrunningoncluster.md)回调函数中使用群集连接器。</span><span class="sxs-lookup"><span data-stu-id="6aba5-129">A UDF can determine whether it is being run using a cluster connector by calling the [xlRunningOnCluster](xlrunningoncluster.md) callback function.</span></span> 
  

