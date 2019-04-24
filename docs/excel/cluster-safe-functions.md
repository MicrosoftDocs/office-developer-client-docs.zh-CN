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
# <a name="cluster-safe-functions"></a>群集安全函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
在 excel 2013 中, excel 可以通过专用群集连接器接口将用户定义的函数 (UDF) 调用卸载到高性能计算群集中。 计算群集供应商提供群集连接器。 UDF 作者可以将其 udf 声明为群集安全的, 然后在出现群集连接器时, Excel 会将对这些 udf 的调用发送到群集连接器以进行卸载。
  
当 Excel 在重新计算过程中发现群集安全 UDF 时, 它会将当前正在运行的 XLL 的名称、群集安全 udf 的名称以及群集连接器的任何参数传递给该名称。 连接器远程运行 UDF 调用, 并将结果返回到 Excel。 非相关计算将继续, 并且当群集连接器运行完 UDF 后, 它会将结果传递到 Excel, 并继续进行依赖计算。 此异步行为的机制模仿异步 udf 使用的机制, 不同之处在于群集连接器管理异步方面而不是 UDF 作者。 通常, 群集连接器实现 XLL 填充程序以加载 xll 并在计算群集节点上运行 udf。
  
将 udf 声明为群集安全的机制类似于声明 udf 的安全进行多线程重新计算。 但是, 由于 UDF 不一定与同一 Excel 会话中的其他 udf 运行在同一台计算机上, 因此在编写群集安全 udf 时有不同的注意事项。
  
若要将 UDF 注册为群集安全, 必须通过**Excel12**或**Excel12v**接口调用[xlfRegister (Form 1)](xlfregister-form-1.md)回调函数。 有关这些接口的详细信息, 请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v](excel4v-excel12v.md)。 不支持通过**Excel4**或**Excel4v**接口将 UDF 注册为群集安全的。 
  
如果将某个函数注册为群集安全的, 则必须确保该函数以群集安全方式行为。 尽管群集连接器的确切行为是特定于实现的, 但您应将 UDF 设计为在分布式计算机系统上运行, 并具有以下特征:
  
- UDF 不应依赖于任何内存状态。 例如, UDF 不应依赖于现有内存中的缓存。
    
- UDF 不应执行群集连接器提供程序不支持的 Excel 回调。
    
除了群集安全的行为之外, 群集安全 udf 还提供以下技术限制:
  
1. 没有 XLOPER 参数 (类型为 ' P ', ' R ')。
    
2. 没有支持区域引用的 XLOPER12 参数 (类型为 "U")。
    
3. 不能是宏表等效函数 ("#" 和 "&amp;" 不能组合)。
    
对于执行时间较短的 udf, 分担的开销可能大于执行 UDF 所需的时间, negating 使用此基础结构的许多好处。
  
> [!NOTE]
> 不能将群集安全 udf 声明为异步 udf。 
  
UDF 可以通过调用[xlRunningOnCluster](xlrunningoncluster.md)回调函数来确定它是否正在使用群集连接器运行。 
  

