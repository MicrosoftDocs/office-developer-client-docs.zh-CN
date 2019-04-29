---
title: 基本和有用的 C API XLM 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 函数 [excel 2007], c api xlm
localization_priority: Normal
ms.assetid: dc80cb3d-0d7e-4cb9-9870-3acc84eeca82
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d6acd5bb171fb2494f2adb23584f4e7f088e1b83
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434513"
---
# <a name="essential-and-useful-c-api-xlm-functions"></a>基本和有用的 C API XLM 函数

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
本节中介绍的函数是 Microsoft Excel 回调函数, 对于 DLL 和 XLL 开发人员尤其有用。 在这些情况下, **xlfRegister**函数对于要注册其函数和命令的 xll 和 dll 是必需的, 以便可以直接从 Excel 中调用它们。 函数**xlfUnregister**和**xlfSetName**结合使用, 以注销 DLL 和 XLL 函数和命令。 
  
Excel 通过 C API 公开了许多函数, 这些函数在开发 xll 时非常有用。 它们对应于 XLM 宏工作表中提供的 Excel 工作表函数和函数和命令。
  
## <a name="in-this-section"></a>本节内容

[xlfCaller](xlfcaller.md)
  
[xlfEvaluate](xlfevaluate.md)
  
[xlfGetDef](xlfgetdef.md)
  
[xlfGetName](xlfgetname.md)
  
[xlfRegister（窗体 1）](xlfregister-form-1.md)
  
[xlfRegister（窗体 2）](xlfregister-form-2.md)
  
[xlfRegisterId](xlfregisterid.md)
  
[xlfUnregister（窗体 1）](xlfunregister-form-1.md)
  
[xlfUnregister（窗体 2）](xlfunregister-form-2.md)
  
[xlfSetName](xlfsetname.md)
  

