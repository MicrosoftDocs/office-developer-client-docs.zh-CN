---
title: xlEventRegister
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b98637d4-02e3-4dbd-8be5-6b46d32980c6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 00c222efce6925c3f691eb2b799adf687c22082c
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160277"
---
# <a name="xleventregister"></a>xlEventRegister

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于注册事件处理程序。 2010 Excel引入。
  
```vb
Excel12(xlEventRegister, LPXLOPER12 pxRes, 2, LPXLOPER12 pxProcedure, LPXLOPER12 pxEvent);
```

## <a name="parameters"></a>参数

 _pxProcedure_ (**xltypeStr**) 
  
出现在 DLL 代码中的事件处理程序函数的名称。
  
 _pxEvent_ (**xltypeInt**) 
  
由  _pxProcedure_ 参数中指定的函数处理的事件。 
  
从 Excel 2010 开始，Excel支持以下事件：
  
|**Event**|**说明**|
|:-----|:-----|
|**xleventCalculationEnded** <br/> |在Excel时引发。 您可以在此事件后释放计算期间分配的任何资源。  <br/> |
|**xleventCalculationCanceled** <br/> |在用户中断计算时引发。 XLL 应停止任何异步活动。 CalculationEnded 事件在此事件后立即引发。  <br/> |
   
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，pxRes (**xltypeInt**) 值为 0 >。 如果失败，则 pxRes ==0。
  
## <a name="see-also"></a>另请参阅



[用户定义异步函数](asynchronous-user-defined-functions.md)

