---
title: LPropCompareProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LPropCompareProp
api_type:
- COM
ms.assetid: f14ad568-fe45-4875-957d-415d39dc6f28
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7417ddeb814cafb954d5ab80a6dae771fd0f7a79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414611"
---
# <a name="lpropcompareprop"></a>LPropCompareProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个属性值以确定它们是否相等。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LONG LPropCompareProp(
  LPSPropValue lpSPropValueA,
  LPSPropValue lpSPropValueB
);
```

## <a name="parameters"></a>参数

 _lpSPropValueA_
  
> [in]指向定义要比较的第一个属性值的 [SPropValue](spropvalue.md) 结构的指针。 
    
 _lpSPropValueB_
  
> [in]指向定义要比较的第二个属性值的 **SPropValue** 结构的指针。 
    
## <a name="return-value"></a>返回值

 **LPropCompareProp** 返回大多数属性类型的以下值之一： 
  
- 如果  _lpSPropValueA_ 参数指示的值小于  _lpSPropValueB_ 参数指示的值，则小于零。 
    
- 如果  _lpSPropValueA_ 指示的值大于  _lpSPropValueB_ 指示的值，则大于零。
    
- 零如果  _lpSPropValueA_ 指示的值等于  _lpSPropValueB_ 指示的值。 
    
对于没有固有顺序的属性类型（如 Boolean 或错误类型）来说，如果两个属性值不相等 **，LPropCompareProp** 函数将返回未定义值。 此未定义值是非零值，并且跨调用保持一致。 
  
## <a name="remarks"></a>备注

只有在要比较的两个属性的类型相同时，才使用 **LPropCompareProp** 函数。 
  
在调用 **LPropCompareProp** 之前，客户端应用程序或服务提供商必须先检索属性，以与 [对 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法的调用进行比较。 当客户端或提供程序调用 **LPropCompareProp** 时，该函数首先检查属性标记以确保属性值的比较有效。 然后，该函数将比较属性值，并返回相应的值。 
  
如果属性值为默认值 **，LPropCompareProp** 将确定哪个属性值更大。 **LPropCompareProp** 比较的属性不一定属于同一对象。 
  

