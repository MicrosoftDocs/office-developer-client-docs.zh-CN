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
ms.openlocfilehash: b0260ffe5dc4806cb627fd71c78866bf96796455
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434716"
---
# <a name="fbadcolumnset"></a>FBadColumnSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
测试供服务提供商在后续调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法时使用的表列集的有效性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadColumnSet(
  LPSPropTagArray lpptaCols
);
```

## <a name="parameters"></a>参数

 _lpptaCols_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含定义要验证的表列的属性标记数组。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的列集无效。 
    
FALSE 
  
> 指定的列集有效。
    
## <a name="remarks"></a>备注

**FBadColumnSet** 函数将类型为PT_ERROR的列视为无效，而类型为 PT_NULL列则视为有效。 
  

