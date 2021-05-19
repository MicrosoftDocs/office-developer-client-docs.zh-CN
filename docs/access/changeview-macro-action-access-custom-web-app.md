---
title: 'ChangeView 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7eb20f21-0218-4a2c-9bbc-90218a1e87bc
description: 可以使用 ChangeView 操作在视图之间就地导航。
ms.openlocfilehash: 0c1e27c264a826d38ec2efbd5be9bc6237ad7437
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425356"
---
# <a name="changeview-macro-action-access-custom-web-app"></a>ChangeView 宏操作 (Access 自定义 Web 应用) 

可以使用 **ChangeView** 操作在视图之间就地导航。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**ChangeView** 操作具有下列参数。 
  
|**操作参数**|**必需**|**描述**|
|:-----|:-----|:-----|
|表格  <br/> |是  <br/> |要打开的表的名称。  <br/> |
|查看  <br/> |是  <br/> |要打开的视图的名称。  <br/> |
|其中  <br/> |否  <br/> |如果指定，则将替换对象记录源的 Where 条件。  <br/> |
|Order By  <br/> |否  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>备注

调用 **ChangeView** 操作时，将清除用户应用的任何排序或筛选。 
  
*OrderBy* 参数是您希望对记录进行排序的一个或多个字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
设置  *OrderBy 参数*  时，默认情况下记录按升序排序。 
  

