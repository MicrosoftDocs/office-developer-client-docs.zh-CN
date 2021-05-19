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
  
允许呼叫服务提供商或网关将属性添加到邮件或附件的封装中。 
  
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
  
> [in]控制如何在封装中包含或排除属性的标志的位掩码。 可以设置以下标志：
    
TNEF_PROP_ATTACHMENTS_ONLY 
  
> 仅对作为邮件附件一  _部分的 lpPropList_ 参数中的属性进行编码。 
    
TNEF_PROP_CONTAINED 
  
> 仅对  _ulElemID_ 参数指定的附件中的属性进行编码。 如果  _lpvData_ 参数不为 NULL，则指向的数据将写入 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 指示的文件中附件的封装中。
    
TNEF_PROP_CONTAINED_TNEF 
  
> 仅对  _ulElemID_ 参数指定的邮件或附件中的属性进行编码。 如果设置此标志，  _则 lpvData_ 中的值必须是 [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) 指针。 
    
TNEF_PROP_EXCLUDE 
  
> 对  _lpPropList_ 参数中未指定的所有属性进行编码。 
    
TNEF_PROP_INCLUDE 
  
> 对  _lpPropList 中指定的所有属性进行编码_。 
    
TNEF_PROP_MESSAGE_ONLY 
  
> 仅对  _lpPropList_ 中指定的属于邮件本身的这些属性进行编码。 
    
 _ulElemID_
  
> [in]附件 **的附件** PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个唯一标识其父邮件中的附件的编号。 当请求对附件进行特殊处理时，使用  _ulElemID_ 参数。 除非 _ulFlags_ 参数中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 标志，否则 ulElemID参数应为 0。 
    
 _lpvData_
  
> [in]指向用于替换  _ulElemID_ 中指定的附件数据的附件数据的指针。 _lpvData_ 参数应为 NULL，除非TNEF_PROP_CONTAINED _ulFlags_ TNEF_PROP_CONTAINED_TNEF或参数。
    
 _lpPropList_
  
> [in]指向要包含或排除在封装中的属性列表的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：AddProps** 方法来列出要包含在或排除在 Transport-Neutral 封装格式 (TNEF) 中处理邮件或附件的属性。 通过使用连续呼叫，提供商或网关可以指定要添加和编码或排除进行编码的属性列表。 提供商和网关还可使用 **AddProps** 提供有关应给定任何特殊处理附件的信息。 
  
 仅对使用 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md) TNEF_ENCODE的 TNEF_ENCODE 打开的 [TNEF](opentnefstreamex.md)对象支持 **AddProps。** 
  
请注意，在调用 [ITnef：：Finish](itnef-finish.md)方法之前 **，AddProps** 不会进行实际的 TNEF 编码。 此功能意味着传入 **AddProps** 的指针必须一直有效，直到调用 **Finish** 之后。 此时，可以释放或释放通过 **AddProps** 调用传入的所有对象和数据。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用 **ITnef：：AddProps** 方法将邮件中的属性复制到 TNEF 流。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachTransportName 规范属性](pidtagattachtransportname-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

