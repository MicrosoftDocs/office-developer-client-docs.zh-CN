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
  
用于注册事件处理程序。 在 Excel 2010 中引入。
  
```vb
Excel12(xlEventRegister, LPXLOPER12 pxRes, 2, LPXLOPER12 pxProcedure, LPXLOPER12 pxEvent);
```

## <a name="parameters"></a>参数

 _pxProcedure_ （**xltypeStr**）
  
在 DLL 代码中显示的事件处理程序函数的名称。
  
 _pxEvent_ （**xltypeInt**）
  
由_pxProcedure_参数中指定的函数处理的事件。 
  
从 Excel 2010 开始，Excel 支持以下事件：
  
|**Event**|**说明**|
|:-----|:-----|
|**xleventCalculationEnded** <br/> |在 Excel 完成计算时引发。 在此事件发生之后，您可以释放在计算过程中分配的任何资源。  <br/> |
|**xleventCalculationCanceled** <br/> |当用户中断计算时引发。 XLL 应停止任何异步活动。 在此事件之后立即引发 CalculationEnded 事件。  <br/> |
   
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，pxRes （**xltypeInt**）的值 > 为0。 如果不成功，pxRes = = 0。
  
## <a name="see-also"></a>另请参阅



[用户定义异步函数](asynchronous-user-defined-functions.md)

