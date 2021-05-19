---
title: xlfRegister（窗体 2）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfRegister
keywords:
- xlfregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 3ebbd775-f3d2-4ba7-8835-a5b38ad2267a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66af741456ab763ef346a8777429f0ae1be77c11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416039"
---
# <a name="xlfregister-form-2"></a>xlfRegister（窗体 2）

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。 这相当于从 **XLM** 宏表Excel REGISTER。 
  
**xlfRegister** 函数可以两种形式调用： 
  
- [xlfRegister (Form 1) ](xlfregister-form-1.md)：注册单个命令或函数。
    
- xlfRegister (表单 2) ：加载并激活 XLL。
    
此函数在窗体 2 中调用，只能用于加载和激活包含 [xlAutoOpen](xlautoopen.md) 过程 XLL。 
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a>参数

 _pxModuleText_ (**xltypeStr**) 
  
要加载和激活的 DLL 的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，这将返回 **xltypeStr** (DLL) 。 否则，它将返回#VALUE！ error。
  
## <a name="see-also"></a>另请参阅



[实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

