---
title: Excel XLL SDK API Function Reference
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- api 函数参考 [excel 2007，] 函数 [Excel 2007]、 引用 [Excel 2007]，Excel 2007 XLL 软件开发工具包，参考 （英文）
localization_priority: Normal
api_type:
- COM
ms.assetid: 2f6df879-7546-4ac0-a4e3-6b009aee9463
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2bb0a57ebcae618c8e921135b2bd4c50e8adf751
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773743"
---
# <a name="excel-xll-sdk-api-function-reference"></a>Excel XLL SDK API Function Reference

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013 XLL SDK 包含用于加快 xll （英文），以及两个示例项目，示例和泛型编写 Framework 库的源文件。 
  
本节提供有关以下函数引用：
  
- Excel XLL 可以调用的回调。
    
- 查找 Microsoft Excel 的 XLL 回调。
    
- 示例和框架项目中的主要功能。
    
## <a name="sample-projects"></a>示例项目

Excel 2013 XLL SDK 提供源文件和 Microsoft Visual Studio 项目文件的以下示例项目：
  
- **框架**项目 (`SAMPLES\FRAMEWRK\`) 包含可生成到库，FRAMEWRK.lib，然后可链接到其他 XLL 项目的项目。 库包含许多函数和进行编写 Xll 更轻松的工具。 此库用于在这两个一起使用的其他项目的头文件 FRAMEWRK.h。
    
- **示例**项目 (`SAMPLES\EXAMPLE\`) 包含可以对 XLL，EXAMPLE.xll 生成的项目。 XLL 包含 Framework 库中，使用和如**xlAutoOpen**的 XLL 加载项界面功能的示例实现的多个示例。
    
- **通用**项目 (`SAMPLES\GENERIC\`) 包含可以对 XLL，GENERIC.xll 生成的项目。 XLL 演示几个示例函数和命令和是编写您自己的 Xll 的良好起始点。
    
## <a name="in-this-section"></a>本节内容

- [加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
  
- [C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md)
  
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)
  
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
- [框架库中的函数](functions-in-the-framework-library.md)
  
- [通用 DLL 中的函数](functions-in-the-generic-dll.md)
  
- [Excel 群集连接器函数](excel-cluster-connector-functions.md)
  
## <a name="see-also"></a>另请参阅

- [�� Excel ��ʹ�� C API ���б��](programming-with-the-c-api-in-excel.md)
  
- [Developing Excel XLLs](developing-excel-xlls.md)

