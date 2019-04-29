---
title: ITnefSetProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.SetProps
api_type:
- COM
ms.assetid: 09e4b427-316b-4630-9f3d-81e74f040d7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f7372830624d774fb914ae956e86a9e4476cf487
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430789"
---
# <a name="itnefsetprops"></a>ITnef::SetProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置封装的邮件或附件的一个或多个属性的值, 而不修改原始邮件或附件。 
  
```cpp
HRESULT SetProps(
  ULONG ulFlags,
  ULONG ulElemID,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制属性值设置方式的标志的位掩码。 可以设置以下标志:
    
TNEF_PROP_CONTAINED 
  
> 仅对_ulElemID_参数所指定的邮件或附件中的属性进行编码。 
    
 _ulElemID_
  
> 实时附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性, 其中包含一个在其父邮件中唯一标识附件的编号。
    
 _cValues_
  
> 实时由_lpProps_参数指向的[SPropValue](spropvalue.md)结构中的属性值的数量。 
    
 _lpProps_
  
> 实时指向**SPropValue**结构的指针, 该结构包含要设置的属性的属性值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

传输提供程序、邮件存储提供程序和网关调用**ITnef:: SetProps**方法来设置要在邮件或附件的封装中包括的属性, 而不修改原始邮件或附件。 使用此调用设置的任何属性将覆盖封装的邮件中的现有属性。 
  
 仅在使用[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_ENCODE 标志打开的 TNEF 对象中支持**SetProps** 。 可以使用此调用设置任意数量的属性。 
  
> [!NOTE]
> 在调用[ITnef:: Finish](itnef-finish.md)方法之前, 不会发生**SetProps**的实际 TNEF 编码。 此功能意味着传递到**SetProps**的指针必须一直保持有效, 直到对完成的调用**完成**。 在这种情况下, 传递到**SetProps**调用中的所有对象和数据都可以释放或释放。 
  
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[ITnef : IUnknown](itnefiunknown.md)

