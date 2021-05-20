---
title: 'Exp 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09385b75-ec0e-4dde-b9c3-9ade4a7a2b74
description: 返回指定表达式的指数值。
ms.openlocfilehash: 30777c41005dfcf1caad896e9e60f0bcfd9d4361
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436410"
---
# <a name="exp-function-access-custom-web-app"></a>Exp 函数 (Access 自定义 Web 应用) 

返回指定表达式的指数值。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Exp** (*NumericExpression)* 
  
**Exp** 函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *NumericExpression*  <br/> |Double 类型的表达式或可隐式转换为 Double 的类型的表达式。  <br/> |
   
## <a name="remarks"></a>备注

常量 **e (** 2.718281...) 是自然对数的基础。 
  
数字的指数是提升为数字的电源的常量 **e。** 例如 **Exp** (1.0) = e^1.0 = 2.71828182845905，Exp (10) = e^10 = 22026.4657948067。  
  
数字的自然对数的指数是数字本身 **：Exp** (LOG (n) ) = n。 数字指数的自然对数是数字本身：LOG (**Exp** (n) ) = n。 
  

