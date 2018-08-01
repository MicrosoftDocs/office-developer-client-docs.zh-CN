---
title: 适用于 Excel 的 C API 中的新增功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007]，新增功能
localization_priority: Normal
ms.assetid: f11552e1-b8ea-4933-b6fc-c452b07eb59d
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e80b667296af59f4d3f18238cd498830fcdc35a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19773817"
---
# <a name="whats-new-in-the-c-api-for-excel"></a>适用于 Excel 的 C API 中的新增功能

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
与 Microsoft Excel 2013 一起使用，Microsoft Excel 2013 XLL 软件开发工具包 (SDK) 包括支持以下功能。
  
- **新功能**
    
    Microsoft Excel 2013 XLL SDK 支持 Excel 2013 中的新工作表功能的所有回调。 有关调用 Excel 2013 函数的详细信息，请参阅[Excel 从 DLL 或 XLL 调用](calling-into-excel-from-the-dll-or-xll.md)。
    
- **异步的用户定义函数**
    
    Excel 2013 支持异步调用用户定义函数 (UDF) 通过启用多个计算同时运行这可以提高性能。 有关异步 Udf 的详细信息，请参阅[Asynchronous User-Defined 函数](asynchronous-user-defined-functions.md)。
    
- **群集连接器**
    
    群集连接器启用 Udf 高性能计算群集上运行。 有关创建群集连接器的详细信息，请参阅[开发 Excel 群集连接器](developing-excel-cluster-connectors.md)。
    
    > [!NOTE]
    > XLL 加载项您打算在计算群集上运行的必须调用仅群集安全函数。 有关功能的详细信息，您可以使用，请参阅[Excel XLL SDK API 函数参考](excel-xll-sdk-api-function-reference.md)和[群集安全函数](cluster-safe-functions.md)。 
  
- **64 位支持**
    
    您现在可以编译并链接 32 位和 64 位 xll （英文）。 有关详细信息，请参阅[创建 xll （英文）](creating-xlls.md)。
    
## <a name="see-also"></a>另请参阅



[Developing Excel XLLs](developing-excel-xlls.md)
  
[�� Excel ��ʹ�� C API ���б��](programming-with-the-c-api-in-excel.md)
  
[Excel 中的多线程处理和内存争用](multithreading-and-memory-contention-in-excel.md)


[Excel XLL SDK 入门](getting-started-with-the-excel-xll-sdk.md)

