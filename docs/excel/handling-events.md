---
title: 处理事件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b67fcb83-a0e2-4349-88f5-bcc181306eac
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c989bc39c22f4e566c18feb4fdeaa8582c5525f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438265"
---
# <a name="handling-events"></a>处理事件

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从 Excel 2010 开始, xll 可以接收旨在管理异步函数生命周期的事件。 这些事件如下所示:
  
- **CalculationEnded**: 在 Excel 完成计算时引发。 在此事件发生之后, 您可以释放计算过程中分配的资源。
    
- **CalculationCanceled**: 用户中断计算时引发。 XLL 将停止所有异步活动。 紧接在此事件之后, 将引发**CalculationEnded**事件。 
    
XLL 使用 C API 函数[xlEventRegister](xleventregister.md)来处理这些事件。 
  
> [!NOTE]
> 在编程重新计算过程中不会引发**CalculationEnded**和**CalculationCanceled** 。 
  

