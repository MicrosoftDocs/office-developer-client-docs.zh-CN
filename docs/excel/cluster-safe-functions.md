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
# <a name="cluster-safe-functions"></a>群集安全函数

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
Excel 2013 中 Excel 可以卸载到通过专用的群集连接器接口的高性能计算群集的用户定义函数 (UDF) 呼叫。 计算群集供应商提供群集连接器。 UDF 作者可以将声明其 Udf 为群集安全，然后存在群集连接器时，Excel 将发送这些 Udf 调用到卸载的群集连接器。
  
当 Excel 重新计算过程中发现的群集安全 UDF 时，它将传递当前正在运行，群集安全 UDF 和任何参数的名称到群集连接器的 XLL 的名称。 连接器在远程运行 UDF 调用，并将结果返回到 Excel。 独立计算继续完成群集连接器之后运行 UDF，请将结果传递到 Excel 和依赖计算继续。 此异步行为的机制之处在于群集连接器管理而不是 UDF 作者的异步方面模拟使用异步 Udf 的机制。 通常，群集连接器实现 XLL 填充码加载 xll （英文） 和群集节点上 compute 运行 Udf。
  
将 Udf 声明为群集安全的机制类似的 Udf 声明为可安全编写多线程的重新计算。 但是，因为其他 Udf 从同一个 Excel 会话在同一台计算机上没有一定运行 UDF，也会不同注意事项编写群集安全 Udf。
  
若要注册为群集安全 UDF，必须通过**Excel12**或**Excel12v**界面调用[xlfRegister (窗体 1)](xlfregister-form-1.md)回调函数。 有关这些接口的详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)和[Excel4v/Excel12v](excel4v-excel12v.md)。 注册为 UDF 不支持通过**Excel4**或**Excel4v**界面群集安全。 
  
如果您在注册为群集安全函数，则必须确保函数行为群集安全方式。 尽管群集连接器的具体行为是特定于实现的您应设计您的 UDF 的分布式的计算机系统上运行并具有以下特征：
  
- UDF 不应依赖于任何内存状态。 例如，UDF 应不依赖于现有内存中缓存。
    
- UDF 不应执行的群集连接器提供程序不支持的 Excel 回调。
    
群集安全行为，除了有群集安全 Udf 的以下技术限制：
  
1. 没有 XLOPER 参数 （类型 P，R）。
    
2. 支持范围引用 （类型 U） 没有 XLOPER12 参数。
    
3. 不能为等效宏工作表函数 (# 和&amp;不能组合)。
    
对于较短的执行时间较 Udf，卸载开销可能大于所用来执行，UDF 的时间绝对值的许多使用此基础结构的好处。
  
> [!NOTE]
> 不能作为异步 UDF 声明群集安全 UDF。 
  
UDF 可以确定是否正在运行通过调用[xlRunningOnCluster](xlrunningoncluster.md)回调函数中使用群集连接器。 
  

