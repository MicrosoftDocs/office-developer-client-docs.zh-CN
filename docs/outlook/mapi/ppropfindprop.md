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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97021128f92af0486af1ba3125c7843eaa357648
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406337"
---
# <a name="ppropfindprop"></a>PpropFindProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
搜索属性集内指定的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _rgprop_
  
> [in] [定义要搜索的属性的 SPropValue](spropvalue.md) 结构数组。 
    
 _cprop_
  
> [in]  _rgprop_ 参数指示的属性集内的属性计数。 
    
 _ulPropTag_
  
> [in]在  _rgprop_ 参数指示的属性集内搜索的属性的属性标记。 
    
## <a name="return-value"></a>返回值

 **PpropFindProp** 返回 [一个 SPropValue](spropvalue.md) 结构，该结构定义与输入属性标记匹配的属性;如果没有匹配项，则返回 NULL。 
  
## <a name="remarks"></a>备注

如果给定的属性标记指示类型为 PT_UNSPECIFIED， **则 PpropFindProp** 函数将仅查找标记中属性标识符的匹配项。 否则，它将查找整个属性标记（包括属性类型）的匹配项，并返回标识的属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：：BuildDataItem  <br/> |MFCMAPI 使用 **PpropFindProp** 方法在要添加到列表中的属性集内查找属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

