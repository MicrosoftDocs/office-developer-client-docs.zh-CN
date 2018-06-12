---
title: PpropFindProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PpropFindProp
api_type:
- HeaderDef
ms.assetid: f23dd6f4-915b-4fe8-ab3f-6d625c7d6061
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b7755f2ec067003e47d358a9736c6d7d96ede267
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778565"
---
# <a name="ppropfindprop"></a>PpropFindProp

  
  
**适用于**： Outlook 
  
搜索属性中指定属性设置。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _rgprop_
  
> [in]定义要搜索的属性的[SPropValue](spropvalue.md)结构的数组。 
    
 _cprop_
  
> [in]设置由_rgprop_参数指示的属性中的属性的计数。 
    
 _ulPropTag_
  
> [in]要设置由_rgprop_参数指示的属性中搜索的属性的属性标记。 
    
## <a name="return-value"></a>返回值

 **PpropFindProp**返回[SPropValue](spropvalue.md)结构定义符合输入的属性标记，则为 NULL，如果没有匹配的属性。 
  
## <a name="remarks"></a>备注

如果给定的属性标记指示 PT_UNSPECIFIED 类型的属性， **PpropFindProp**函数标记中找到仅属性标识符的匹配项。 否则为它找到匹配项整个属性标记，其中包括属性类型，并返回标识的属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::BuildDataItem  <br/> |MFCMAPI 使用**PpropFindProp**方法来查找属性中的属性设置添加到列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 作为的代码示例](mfcmapi-as-a-code-sample.md)

