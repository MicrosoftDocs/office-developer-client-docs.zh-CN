---
title: FBadSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadSortOrderSet
api_type:
- COM
ms.assetid: b7f80e0a-8ddd-4b24-ab63-2078a8152058
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b3f88495cafbd6ea764ca8901ac67c23749aebe
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578575"
---
# <a name="fbadsortorderset"></a>FBadSortOrderSet

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证排序顺序设置通过验证其内存分配。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
ULONG FBadSortOrderSet(
  LPSSortOrderSet lpsos
);
```

## <a name="parameters"></a>参数

 _lpsos_
  
> [in]指向标识设置要验证的排序次序[SSortOrderSet](ssortorderset.md)结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 设置指定的排序顺序无效。 
    
FALSE 
  
> 有效设置的指定的排序顺序。
    
## <a name="remarks"></a>注解

**FBadSortOrderSet**函数可用于准备 sort 方法，如[IMAPITable::SortTable](imapitable-sorttable.md)方法调用。 
  

