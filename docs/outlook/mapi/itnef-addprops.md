---
title: ITnefAddProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.AddProps
api_type:
- COM
ms.assetid: e85641fb-6d3c-494a-981c-01781c7bf5bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a7bb7265d29d2acfce17a1a09c95f7f7b539064
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348620"
---
# <a name="itnefaddprops"></a>ITnef::AddProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启用呼叫服务提供程序或网关以将属性添加到邮件或附件的封装。 
  
```cpp
HRESULT AddProps(
  ULONG ulFlags,
  ULONG ulElemID,
  LPVOID lpvData,
  LPSPropTagArray lpPropList
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制如何在封装中包含或排除属性的标志的位掩码。 可以设置以下标志:
    
TNEF_PROP_ATTACHMENTS_ONLY 
  
> 仅对_lpPropList_参数中作为邮件附件的一部分的属性进行编码。 
    
TNEF_PROP_CONTAINED 
  
> 仅对_ulElemID_参数所指定的附件中的属性进行编码。 如果_lpvData_参数不为 NULL, 则指向的数据将写入到附件在**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性指示的文件中的封装中。
    
TNEF_PROP_CONTAINED_TNEF 
  
> 仅对_ulElemID_参数所指定的邮件或附件中的属性进行编码。 如果设置了此标志, 则_lpvData_中的值必须是[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)指针。 
    
TNEF_PROP_EXCLUDE 
  
> 对未在_lpPropList_参数中指定的所有属性进行编码。 
    
TNEF_PROP_INCLUDE 
  
> 对在_lpPropList_中指定的所有属性进行编码。 
    
TNEF_PROP_MESSAGE_ONLY 
  
> 仅对在_lpPropList_中指定的那些属于邮件本身的属性进行编码。 
    
 _ulElemID_
  
> 实时附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性, 其中包含一个在其父邮件中唯一标识附件的编号。 当请求附件的特殊处理时, 使用_ulElemID_参数。 除非在_ulFlags_参数中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 标志, 否则_ulElemID_参数应为0。 
    
 _lpvData_
  
> 实时指向用于替换在_ulElemID_中指定的附件数据的附件数据的指针。 除非在_ulFlags_中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF, 否则_lpvData_参数应为 NULL。
    
 _lpPropList_
  
> 实时指向要包含在封装中或从封装中排除的属性列表的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

传输提供程序、邮件存储提供程序和网关调用**ITnef:: AddProps**方法, 以列出要包含或排除在邮件或附件的传输中性封装格式 (TNEF) 处理中的属性。 通过使用连续调用, 提供程序或网关可以指定要添加和编码或从编码中排除的属性的列表。 提供程序和网关也可以使用**AddProps**提供有关应提供的任何特殊处理附件的信息。 
  
 仅在使用[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_ENCODE 标志打开的 TNEF 对象中支持**AddProps** 。 
  
请注意, 在调用[ITnef:: Finish](itnef-finish.md)方法之前, 不会对**AddProps**进行实际的 TNEF 编码。 此功能意味着传递到**AddProps**的指针必须一直保持有效, 直到对完成的调用**完成**。 在这种情况下, 可以释放或释放使用**AddProps**调用传入的所有对象和数据。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用**ITnef:: AddProps**方法将邮件中的属性复制到 TNEF 流。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachTransportName 规范属性](pidtagattachtransportname-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

