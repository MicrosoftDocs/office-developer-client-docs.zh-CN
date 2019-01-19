---
title: Excel XLL SDK API 函数引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- api 函数引用 [excel 2007], 函数 [Excel 2007], 引用 [Excel 2007], Excel 2007 XLL 软件开发工具包, 引用
api_type:
- COM
ms.assetid: 2f6df879-7546-4ac0-a4e3-6b009aee9463
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: e116021a3dc24de7decbe0dad76cc762cd66d032
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715954"
---
# <a name="excel-xll-sdk-api-function-reference"></a>Excel XLL SDK API 函数引用

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013 XLL SDK 包含适用于专为加速 XLL 编写而设计的框架库的源文件和两个示例项目：示例项目和常规项目。 
  
本节提供了以下函数引用：
  
- XLL 可调用的 Excel 回调。
    
- Microsoft Excel 可查找的 XLL 回调。
    
- 示例和框架项目中的关键函数。
    
## <a name="sample-projects"></a>示例项目

Excel 2013 XLL SDK 提供适用于以下示例项目的源文件和 Microsoft Visual Studio 项目文件：
  
- **框架**项目 (`SAMPLES\FRAMEWRK\`) 包含可生成到库的项目 FRAMEWRK.lib，该项目随后可链接至其他 XLL 项目。 库中包含多个可以简化 XLL 编写的函数和工具。 此库可以在两个其他项目中与头文件 FRAMEWRK.h 结合使用。
    
- **示例**项目 (`SAMPLES\EXAMPLE\`) 包含可生成到 XLL 的项目 EXAMPLE.xll。 XLL 包含多个使用框架库的示例以及 XLL 加载项接口函数（如 **xlAutoOpen**）的示例实施。
    
- **常规**项目 (`SAMPLES\GENERIC\`) 包含可生成到 XLL 的项目 GENERIC.xll。 XLL 演示了多个实例函数和命令，是编写你自己的 XLL 的一个很好起点。
    
## <a name="in-this-section"></a>本节内容

- [加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
  
- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md)
  
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)
  
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
- [框架库中的函数](functions-in-the-framework-library.md)
  
- [通用 DLL 中的函数](functions-in-the-generic-dll.md)
  
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)
  
## <a name="see-also"></a>另请参阅

- [在 Excel 中使用 C API 进行编程](programming-with-the-c-api-in-excel.md)
  
- [开发 Excel XLL](developing-excel-xlls.md)

