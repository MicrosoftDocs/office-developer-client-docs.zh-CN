---
title: 多线程和内存管理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f7e052a-4270-4b83-b1ed-feabf6dbeaa2
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f387d5ddb184c681ab5e005a6eb24058f6f52f9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414464"
---
# <a name="multithreading-and-memory-management"></a>多线程和内存管理

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
正确处理内存对于为用户创建可靠的 XLL 加载项Microsoft Excel。 分配适当的内存缓冲区并释放这些缓冲区（如果不再需要）失败，将降低性能、导致资源争用并破坏Excel。
  
从 2007 Microsoft Office Excel开始，你可以将Excel配置为在重新计算时最多使用 1，024 个并发线程。 在某些情况下，尤其是当多个处理器可用或在群集服务器上运行的用户定义函数时，多线程可以提高性能。
  
以下主题介绍如何在 XLL 中管理内存和线程：
  
- [Excel 中的内存管理](memory-management-in-excel.md)
    
- [线程中的多线程和内存Excel](multithreading-and-memory-contention-in-excel.md)
    
- [Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
    
## <a name="see-also"></a>另请参阅



[开发 Excel XLL](developing-excel-xlls.md)

