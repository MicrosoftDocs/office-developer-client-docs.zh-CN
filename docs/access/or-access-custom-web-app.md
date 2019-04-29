---
title: 或 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: 组合了两个条件。 如果两个条件中的任何一个为 true, 则返回 true。
ms.openlocfilehash: ffa605d2403c5aa8396d89f78d0bb7dd11343540
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414758"
---
# <a name="or-access-custom-web-app"></a>或 (Access 自定义 web 应用程序)

组合了两个条件。 如果两个条件中的任何一个为 true, 则返回 true。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *BooleanExpression***或***BooleanExpression* 
  
**Or**运算符使用以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *BooleanExpression*  <br/> |返回 TRUE 或 FALSE 的任何有效表达式。  <br/> |
   
## <a name="remarks"></a>说明

当在一个语句中使用多个逻辑运算符时,**或**在**And**运算符之后计算运算符。 不过, 您可以使用括号更改求值的顺序。 
  
下表显示了**Or**运算符的结果。 
  
||**TRUE**|**该值**|
|:-----|:-----|:-----|
|**TRUE** <br/> |TRUE  <br/> |TRUE  <br/> |
|**该值** <br/> |TRUE  <br/> |FALSE  <br/> |
   

