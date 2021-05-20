---
title: 适用于开发人员的 C API 的Excel
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007]，新增功能
localization_priority: Normal
ms.assetid: f11552e1-b8ea-4933-b6fc-c452b07eb59d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 64e3933ec25f0771db5bd36bbf57f3f259cdc8a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439686"
---
# <a name="whats-new-in-the-c-api-for-excel"></a>适用于开发人员的 C API 的Excel

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
XLL Microsoft Excel 2013 Sdk Microsoft Excel 2013 SDK (SDK) 支持以下功能。
  
- **新函数**
    
    XLL SDK Microsoft Excel 2013 2013 中所有新工作表函数的Excel调用。 有关调用 2013 Excel，请参阅从 DLL 或[XLL Excel调用代码](calling-into-excel-from-the-dll-or-xll.md)。
    
- **异步用户定义函数**
    
    Excel 2013 支持异步调用 (UDF) 用户定义函数，这可以通过允许多个计算同时运行来提高性能。 有关异步 UDF 详细信息，请参阅 [Asynchronous User-Defined Functions](asynchronous-user-defined-functions.md)。
    
- **群集连接器**
    
    群集连接器使 UDF 能够运行在高性能计算群集上。 有关创建群集连接器的信息，请参阅 Developing [Excel Cluster Connectors。](developing-excel-cluster-connectors.md)
    
    > [!NOTE]
    > 打算在计算群集上运行的 XLL 加载项只能调用群集安全函数。 有关可以使用的函数详细信息，请参阅Excel [XLL SDK API 函数](excel-xll-sdk-api-function-reference.md)参考和群集[保险箱函数](cluster-safe-functions.md)。 
  
- **64 位支持**
    
    现在可以编译和链接 32 位和 64 位 XLL。 有关详细信息，请参阅创建[XLL。](creating-xlls.md)
    
## <a name="see-also"></a>另请参阅



[开发 Excel XLL](developing-excel-xlls.md)
  
[在 Excel 中使用 C API 进行编程](programming-with-the-c-api-in-excel.md)
  
[线程中的多线程和内存Excel](multithreading-and-memory-contention-in-excel.md)


[Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

