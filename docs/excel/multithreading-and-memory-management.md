---
title: 多线程处理和内存管理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f7e052a-4270-4b83-b1ed-feabf6dbeaa2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4f5495648c9012b0e028358037090f7e10ef5219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773800"
---
# <a name="multithreading-and-memory-management"></a>多线程处理和内存管理

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
正确处理内存至关重要的 Microsoft Excel 中创建可靠的 XLL 加载项。 未能分配相应的内存缓冲区释放它们时不再需要它们会降低性能，创建资源争用和 destabilizes Excel。
  
从 Microsoft Office Excel 2007 开始，您可以配置 Excel 重新计算时使用最多包含 1,024 并发线程。 在某些情况下，尤其是当多个处理器都可以使用或用户定义函数聚集多线程处理服务器上运行可以提高性能。
  
以下主题介绍如何管理内存和 xll （英文） 中的线程数：
  
- [Excel 中的内存管理](memory-management-in-excel.md)
    
- [Excel 中的多线程处理和内存争用](multithreading-and-memory-contention-in-excel.md)
    
- [Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
    
## <a name="see-also"></a>另请参阅



[Developing Excel XLLs](developing-excel-xlls.md)

