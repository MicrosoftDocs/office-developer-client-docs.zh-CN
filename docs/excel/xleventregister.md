---
title: xlEventRegister
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b98637d4-02e3-4dbd-8be5-6b46d32980c6
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d837d87c479f70f0184a7cf1612dea5ab8c99e6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773844"
---
# <a name="xleventregister"></a>xlEventRegister

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于注册事件处理程序。 在 Excel 2010 中引入。
  
```vb
Excel12(xlEventRegister, LPXLOPER12 pxRes, 2, LPXLOPER12 pxProcedure, LPXLOPER12 pxEvent);
```

## <a name="parameters"></a>参数

 _pxProcedure_(**xltypeStr**)
  
在 DLL 的代码中显示它的事件处理程序函数的名称。
  
 _pxEvent_(**xltypeInt**)
  
通过_pxProcedure_参数中指定的函数处理的事件。 
  
Excel 启动 Excel 2010 中支持以下事件：
  
|"事件"|**说明**|
|:-----|:-----|
|**xleventCalculationEnded** <br/> |Excel 完成计算时引发。 您可以释放分配此事件后在计算过程中的任何资源。  <br/> |
|**xleventCalculationCanceled** <br/> |当用户中断计算时引发。 XLL 应停止任何异步活动。 紧跟此事件时引发 CalculationEnded 事件。  <br/> |
   
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回**TRUE** (**xltypeBool**)。 如果不成功，则返回**FALSE**。
  
## <a name="see-also"></a>另请参阅



[用户定义的异步函数](asynchronous-user-defined-functions.md)

