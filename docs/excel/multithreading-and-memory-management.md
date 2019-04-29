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
  
正确处理内存对于创建适用于 Microsoft Excel 的可靠 XLL 外接程序至关重要。 如果无法分配适当的内存缓冲区, 并在不再需要它们时释放它们, 则会降低性能, 创建资源争用和 destabilizes Excel。
  
从 Microsoft Office Excel 2007 开始, 可以将 Excel 配置为在重新计算时最长可使用1024个并发线程。 在某些情况下, 尤其是当多个处理器可用或在群集服务器上运行的用户定义的函数时, 多线程处理可以提高性能。
  
以下主题介绍如何在 xll 中管理内存和线程:
  
- [Excel 中的内存管理](memory-management-in-excel.md)
    
- [Excel 中的多线程和内存争用](multithreading-and-memory-contention-in-excel.md)
    
- [Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
    
## <a name="see-also"></a>另请参阅



[开发 Excel XLL](developing-excel-xlls.md)

