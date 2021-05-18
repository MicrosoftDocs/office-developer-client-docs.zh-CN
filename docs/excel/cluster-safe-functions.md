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
# <a name="cluster-safe-functions"></a>群集安全函数

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
在 Excel 2013 Excel，User-Defined Function (UDF) 通过专用群集连接器接口卸载对高性能计算群集的调用。 计算群集供应商提供群集连接器。 UDF 作者可以将其 UDF 声明为群集安全，然后，当群集连接器存在时，Excel将调用发送到群集连接器进行卸载。
  
当Excel发现群集安全的 UDF 时，它会将当前运行的 XLL 的名称、群集安全 UDF 的名称以及任何参数传递给群集连接器。 连接器远程运行 UDF 调用，并返回结果以Excel。 非从属计算将继续，当群集连接器运行完 UDF 后，它会将结果传递给Excel计算继续进行。 此异步行为的机制模拟异步 UDF 使用的机制，只是群集连接器管理异步方面而不是 UDF 作者。 通常，群集连接器实现 XLL 填充程序，以加载 XLL 并运行计算群集节点上的 UDF。
  
将 UDF 声明为群集安全的机制类似于将 UDF 声明为多线程重新计算安全的机制。 但是，由于 UDF 不一定与来自同一 Excel 会话的其他 UDF 运行在同一计算机上，因此编写群集安全的 UDF 时有不同的注意事项。
  
若要将 UDF 注册为群集安全，必须通过 **Excel12 或 Excel12v**) 调用 [xlfRegister](xlfregister-form-1.md) (Form **1**) 回调函数。 有关这些接口详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v。](excel4v-excel12v.md) 不支持通过 Excel4 或 **Excel4v** 接口将UDF 注册为群集安全。 
  
如果将函数注册为群集安全函数，则必须确保该函数以群集安全方式运行。 尽管群集连接器的确切行为特定于实现，但您应该设计 UDF 以在分布式计算机系统上运行，并具有以下特征：
  
- UDF 不应依赖任何内存状态。 例如，UDF 不应依赖现有的内存中缓存。
    
- UDF 不应执行Excel连接器提供程序不支持的回调。
    
除了群集安全行为之外，群集安全 UDF 还具有以下技术限制：
  
1. 没有 XLOPER 参数 (类型"P"，"R") 。
    
2. 没有支持区域引用的 XLOPER12 参数 (类型"U") 。
    
3. 不能是宏表等效函数 ('#'和 &amp; '' 不能合并) 。
    
对于执行时间较短的 UDF，卸载的开销可能大于执行 UDF 所花的时间，这将抵消使用此基础结构的许多好处。
  
> [!NOTE]
> 无法将群集安全 UDF 声明为异步 UDF。 
  
UDF 可以通过调用 [xlRunningOnCluster](xlrunningoncluster.md) 回调函数来确定它是否正在使用群集连接器运行。 
  

