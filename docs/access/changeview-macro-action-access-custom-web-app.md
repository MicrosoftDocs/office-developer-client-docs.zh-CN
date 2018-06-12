---
title: ChangeView 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7eb20f21-0218-4a2c-9bbc-90218a1e87bc
description: 您可以使用 ChangeView 操作就地视图之间导航。
ms.openlocfilehash: c420846074ef362d3388d40ed8700db0739b7ce0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773454"
---
# <a name="changeview-macro-action-access-custom-web-app"></a>ChangeView 宏操作 （访问自定义 web 应用程序）

您可以使用**ChangeView**操作就地视图之间导航。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**ChangeView**操作具有下列参数。 
  
|**操作参数**|**必需**|**说明**|
|:-----|:-----|:-----|
|Table  <br/> |是  <br/> |要打开的表的名称。  <br/> |
|视图  <br/> |是  <br/> |要打开的视图的名称。  <br/> |
|其中  <br/> |否  <br/> |如果指定，则将替换对象记录源的 Where 条件。  <br/> |
|Order By  <br/> |否  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>备注

调用**ChangeView**操作时，会清除任何排序或筛选用户应用的。 
  
*OrderBy*参数是在您要对记录进行排序的字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
当设置*OrderBy*参数时，记录将默认情况下按升序排序。 
  

