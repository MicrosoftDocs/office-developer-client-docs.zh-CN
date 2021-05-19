---
title: 'OR (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: 组合两个条件。 当两个条件之一为 true 时，返回 TRUE。
ms.openlocfilehash: ffa605d2403c5aa8396d89f78d0bb7dd11343540
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414758"
---
# <a name="or-access-custom-web-app"></a>OR (Access 自定义 Web 应用) 

组合两个条件。 当两个条件之一为 true 时，返回 TRUE。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *BooleanExpression* **或** *BooleanExpression* 
  
Or 运算符使用下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *BooleanExpression*  <br/> |返回 TRUE 或 FALSE 的任何有效表达式。  <br/> |
   
## <a name="remarks"></a>备注

在语句中使用多个逻辑运算符时 **，Or** 运算符在 **And** 运算符之后求值。 但是，您可以使用括号更改计算顺序。 
  
下表显示 **Or** 运算符的结果。 
  
||**TRUE**|**FALSE**|
|:-----|:-----|:-----|
|**TRUE** <br/> |TRUE  <br/> |TRUE  <br/> |
|**FALSE** <br/> |TRUE  <br/> |FALSE  <br/> |
   

