---
title: FBadColumnSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadColumnSet
api_type:
- HeaderDef
ms.assetid: 15be5a8c-4299-4434-b521-c901215b9dda
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4e5f19258fb7716e741928f02a0a87f3939c74e0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575096"
---
# <a name="fbadcolumnset"></a>FBadColumnSet

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置表格列的有效性测试使用后续调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法中的服务提供商。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
ULONG FBadColumnSet(
  LPSPropTagArray lpptaCols
);
```

## <a name="parameters"></a>参数

 _lpptaCols_
  
> [in]指向包含属性标记定义要验证的表格列的数组[SPropTagArray](sproptagarray.md)结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的列集无效。 
    
FALSE 
  
> 指定的列集才有效。
    
## <a name="remarks"></a>注解

**FBadColumnSet**函数处理无效 PT_ERROR 类型的列和有效 PT_NULL 类型的列。 
  

