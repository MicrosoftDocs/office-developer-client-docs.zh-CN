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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66af741456ab763ef346a8777429f0ae1be77c11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310120"
---
# <a name="xlfregister-form-2"></a>xlfRegister（窗体 2）

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从 DLL 或 XLL 命令调用, 该命令本身已由 Microsoft Excel 调用。 这相当于从 Excel XLM 宏表调用**REGISTER** 。 
  
可以在两种形式中调用**xlfRegister**函数: 
  
- [xlfRegister (窗体 1)](xlfregister-form-1.md): 注册单个命令或函数。
    
- xlfRegister (窗体 2): 加载并激活 XLL。
    
在表单2中调用, 此函数仅可用于加载和激活包含[xlAutoOpen](xlautoopen.md)过程的 XLL。 
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a>参数

 _pxModuleText_(**xltypeStr**)
  
要加载并激活的 DLL 的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功, 则返回 DLL 的名称 (**xltypeStr**)。 否则, 它将返回一个 #VALUE! 误差.
  
## <a name="see-also"></a>另请参阅



[实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

