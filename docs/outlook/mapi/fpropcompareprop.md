---
title: FPropCompareProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropCompareProp
api_type:
- COM
ms.assetid: 17cb53c4-7154-4a4e-b4ec-de720fa055cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7726811467324242037ec11a69ae0b1b123d7f21
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427155"
---
# <a name="fpropcompareprop"></a>FPropCompareProp

**适用于**：Outlook 2013 | Outlook 2016 
  
使用指定的关系运算符比较两个属性值。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropCompareProp(
  LPSPropValue lpSPropValue1,
  ULONG ulRelOp,
  LPSPropValue lpSPropValue2
);
```

## <a name="parameters"></a>参数

_lpSPropValue1_
  
> [in]指向定义第一个属性值进行比较的 [SPropValue](spropvalue.md) 结构的指针。 
    
_ulRelOp_
  
> [in]要用于比较的关系运算符。 有关允许的值，请参阅 [SComparePropsRestriction](scomparepropsrestriction.md) 结构。 
    
_lpSPropValue2_
  
> [in]指向定义第二个属性值进行比较的 **SPropValue** 结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 属性值满足指定的关系。 
    
FALSE 
  
> 属性值不满足指定关系。
    
## <a name="remarks"></a>备注

比较方法取决于 [SPropValue](spropvalue.md) 属性定义中指定的属性类型。 **FPropCompareProp** 和 [FPropContainsProp](fpropcontainsprop.md)函数可用于准备生成表的限制。 
  
比较顺序为  _lpSPropValue1_、 _ ulRelOp _， _ lpSPropValue2 _。 如果要比较的属性值的属性类型不匹配， **则 FPropCompareProp** 函数将返回 FALSE。 
  

