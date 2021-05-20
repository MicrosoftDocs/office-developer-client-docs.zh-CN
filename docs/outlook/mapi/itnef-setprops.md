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
  
在不修改原始邮件或附件的情况下设置封装邮件或附件的一个或多个属性的值。 
  
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
  
> [in]控制属性值设置方式的标志位掩码。 可以设置以下标志：
    
TNEF_PROP_CONTAINED 
  
> 仅对  _ulElemID_ 参数指定的邮件或附件中的属性进行编码。 
    
 _ulElemID_
  
> [in]附件 **的附件** PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个唯一标识其父邮件中的附件的编号。
    
 _cValues_
  
> [in]_lpProps_ 参数指向 [的 SPropValue](spropvalue.md)结构中属性值的数量。 
    
 _lpProps_
  
> [in]指向包含要设置的属性的属性值的 **SPropValue** 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：SetProps** 方法来设置要包括在邮件或附件封装中的属性，而无需修改原始邮件或附件。 通过此调用设置的任何属性将覆盖封装邮件中的现有属性。 
  
 **SetProps** 仅受使用 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md) TNEF_ENCODE的 TNEF_ENCODE 打开的 [TNEF](opentnefstreamex.md) 对象的支持。 此调用可以设置任意数目的属性。 
  
> [!NOTE]
> 在调用 [ITnef：：Finish](itnef-finish.md)方法之前，不会为 **SetProps** 进行实际的 TNEF 编码。 此功能意味着传递到 **SetProps** 的指针必须一直有效，直到调用 **Finish** 之后。 此时，可以释放或释放传递到 **SetProps** 调用的所有对象和数据。 
  
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[ITnef : IUnknown](itnefiunknown.md)

