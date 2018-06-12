---
title: 处理事件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b67fcb83-a0e2-4349-88f5-bcc181306eac
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: c5508df8466932b6fb5c7e04164aa00a5ea31a8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773746"
---
# <a name="handling-events"></a>处理事件

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
启动在 Excel 2010 xll （英文） 可以接收旨在管理的异步函数生命周期的事件。 事件如下所示：
  
- **CalculationEnded**： 引发完成 Excel 计算。 此事件之后，您可以释放计算过程中分配资源。
    
- **CalculationCanceled**： 用户中断计算时引发。 XLL 停止任何异步活动。 紧接此事件， **CalculationEnded**引发该事件。 
    
若要处理这些事件，XLL，请使用 C API 函数[xlEventRegister](xleventregister.md)。 
  
> [!NOTE]
> **CalculationEnded**和**CalculationCanceled**不会引发编程重新计算过程中。 
  

