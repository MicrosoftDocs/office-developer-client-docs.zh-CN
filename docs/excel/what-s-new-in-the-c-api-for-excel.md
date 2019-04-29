---
title: 适用于 Excel 的 C API 中的新增功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007], 新增功能
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
# <a name="whats-new-in-the-c-api-for-excel"></a>适用于 Excel 的 C API 中的新增功能

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
microsoft excel 2013 XLL 软件开发工具包 (SDK) 与 microsoft excel 2013 联合提供了对以下功能的支持。
  
- **新函数**
    
    Microsoft excel 2013 XLL SDK 支持回调到 Excel 2013 中的所有新工作表函数。 有关调用 excel 2013 函数的详细信息, 请参阅[从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)。
    
- **异步用户定义函数**
    
    Excel 2013 支持异步调用用户定义的函数 (UDF), 这可以通过启用多个计算同时运行来提高性能。 有关异步 udf 的详细信息, 请参阅[异步用户定义函数](asynchronous-user-defined-functions.md)。
    
- **群集连接器**
    
    群集连接器使 udf 能够在高性能计算群集上运行。 有关创建群集连接器的详细信息, 请参阅[开发 Excel 群集连接器](developing-excel-cluster-connectors.md)。
    
    > [!NOTE]
    > 您打算在计算群集上运行的 XLL 加载项必须仅调用群集安全函数。 有关可以使用的函数的详细信息, 请参阅[Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)和[群集安全函数](cluster-safe-functions.md)。 
  
- **64位支持**
    
    现在可以编译和链接32位和64位 xll。 有关详细信息, 请参阅[创建 xll](creating-xlls.md)。
    
## <a name="see-also"></a>另请参阅



[开发 Excel XLL](developing-excel-xlls.md)
  
[在 Excel 中使用 C API 进行编程](programming-with-the-c-api-in-excel.md)
  
[Excel 中的多线程和内存争用](multithreading-and-memory-contention-in-excel.md)


[Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

