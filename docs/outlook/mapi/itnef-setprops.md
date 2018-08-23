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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 81f9388b67d3194fe1442091b9f4f75a7671cb6d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579646"
---
# <a name="itnefsetprops"></a>ITnef::SetProps

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置用于封装的邮件或附件的一个或多个属性的值，而无需修改原始邮件或附件。 
  
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
  
> [in]位掩码的标志的控制设置属性值的方式。 可以设置以下标记：
    
TNEF_PROP_CONTAINED 
  
> 将编码仅从邮件或附件_ulElemID_参数指定的属性。 
    
 _ulElemID_
  
> [in]附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个数字唯一地标识其父邮件中的附件。
    
 _cValues_
  
> [in]_LpProps_参数指向[SPropValue](spropvalue.md)结构中的属性值的数目。 
    
 _lpProps_
  
> [in]一个指向**SPropValue**结构，其中包含要设置的属性的属性值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>注解

传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::SetProps**方法可设置属性包括在邮件或附件封装而无需修改的原始邮件或附件。 与此呼叫设置的所有属性重都写封装的消息中的现有属性。 
  
 **SetProps**仅支持使用 TNEF_ENCODE 标志[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的 TNEF 对象。 与此呼叫，可以设置任意数量的属性。 
  
> [!NOTE]
> 无实际 TNEF 编码的**SetProps**直到调用[ITnef::Finish](itnef-finish.md)方法后会发生的情况。 此功能的含义，**完成**呼叫后，指针传递给**SetProps**必须保持才有效。 此时，所有对象和数据传递到**SetProps**呼叫可以发布或释放。 
  
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[ITnef : IUnknown](itnefiunknown.md)

