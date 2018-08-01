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
ms.openlocfilehash: 69bbed644a8173bf9291ca48a63960f693108318
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774985"
---
# <a name="fpropcompareprop"></a>FPropCompareProp

**适用于**： Outlook 
  
将使用指定的关系运算符的两个属性值进行比较。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropCompareProp(
  LPSPropValue lpSPropValue1,
  ULONG ulRelOp,
  LPSPropValue lpSPropValue2
);
```

## <a name="parameters"></a>参数

_lpSPropValue1_
  
> [in]定义用于比较的第一个属性值[SPropValue](spropvalue.md)结构的指针。 
    
_ulRelOp_
  
> [in]用于比较关系运算符。 允许的值，请参阅[SComparePropsRestriction](scomparepropsrestriction.md)结构。 
    
_lpSPropValue2_
  
> [in]定义用于比较的第二个属性值**SPropValue**结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 属性值满足指定的关系。 
    
FALSE 
  
> 属性值不满足指定的关系。
    
## <a name="remarks"></a>说明

比较方法取决于[SPropValue](spropvalue.md)属性定义中指定的属性类型。 **FPropCompareProp**和[FPropContainsProp](fpropcontainsprop.md)函数可以用于准备用于生成表的限制。 
  
_LpSPropValue1_、 _ ulRelOp _、 _ lpSPropValue2 _ 的比较的顺序。 如果进行比较的属性值的属性类型不匹配，则**FPropCompareProp**函数将返回 FALSE。 
  

