---
title: xlfRegister (窗体 2)
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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: a535018e2b644966d183ba9ae862ce83670c9231
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773842"
---
# <a name="xlfregister-form-2"></a>xlfRegister (窗体 2)

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。 这是等效于从 Excel XLM 宏工作表调用**注册**。 
  
可在两个窗体中调用**xlfRegister**函数： 
  
- [xlfRegister (窗体 1)](xlfregister-form-1.md): 注册单个命令或函数。
    
- xlfRegister (窗体 2): 加载并激活 XLL。
    
调用窗体 2 中，此函数可以仅用于加载和激活包含[xlAutoOpen](xlautoopen.md)过程 XLL。 
  
```cs
Excel12(xlfRegister, LPXLOPER12 pxRes, 1, LPXLOPER12 pxModuleText);
```

## <a name="parameters"></a>参数

 _pxModuleText_(**xltypeStr**)
  
要加载并激活的 dll 名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，这将返回 DLL (**xltypeStr**) 的名称。 否则，它返回 #VALUE ！ 错误。
  
## <a name="see-also"></a>另请参阅



[关键及有用的 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

