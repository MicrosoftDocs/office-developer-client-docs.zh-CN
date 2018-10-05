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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396314"
---
# <a name="itnefaddprops"></a>ITnef::AddProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许将属性添加到邮件或附件封装调用服务提供商或网关。 
  
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
  
> [in]位掩码的标志，控制如何中包括还是排除在封装属性。 可以设置以下标志：
    
TNEF_PROP_ATTACHMENTS_ONLY 
  
> 对仅_lpPropList_参数中的属性属于邮件中的附件进行编码。 
    
TNEF_PROP_CONTAINED 
  
> 将编码仅从附件_ulElemID_参数指定的属性。 如果_lpvData_参数不是 NULL，则指向数据写入由**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性指示文件中的附件的封装。
    
TNEF_PROP_CONTAINED_TNEF 
  
> 将编码仅从邮件或附件_ulElemID_参数指定的属性。 如果设置此标志， _lpvData_中的值必须是[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)指针。 
    
TNEF_PROP_EXCLUDE 
  
> 将编码不_lpPropList_参数中指定的所有属性。 
    
TNEF_PROP_INCLUDE 
  
> 将编码_lpPropList_中指定的所有属性。 
    
TNEF_PROP_MESSAGE_ONLY 
  
> 对仅这些属性中_lpPropList_指定消息本身的一部分进行编码。 
    
 _ulElemID_
  
> [in]附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个数字唯一地标识其父邮件中的附件。 特殊处理请求的附件时使用_ulElemID_参数。 除非_ulFlags_参数中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 标志， _ulElemID_参数应为 0。 
    
 _lpvData_
  
> [in]指向用于替换附件_ulElemID_中指定的数据的附件数据的指针。 除非 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 设置中_ulFlags_， _lpvData_参数应为 NULL。
    
 _lpPropList_
  
> [in]指向要在包含或排除封装的属性列表的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::AddProps**方法列表属性中包含或排除在邮件或附件的传输中性封装格式 (TNEF) 处理。 通过使用后续呼叫，提供程序或网关可以指定的属性添加和编码或排除要编码的列表。 提供程序和网关还可以使用**AddProps**提供，应注意任何特殊处理附件有关的信息。 
  
 **AddProps**仅支持使用 TNEF_ENCODE 标志[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的 TNEF 对象。 
  
请注意[ITnef::Finish](itnef-finish.md)方法调用之前对**AddProps**时发生的任何实际 TNEF 编码。 此功能的含义，**完成**呼叫后，指针传递给**AddProps**必须保持才有效。 此时，所有对象和传入**AddProps**呼叫数据可以发布或释放。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用**ITnef::AddProps**方法将属性从邮件复制到 TNEF 流。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::Finish](itnef-finish.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachTransportName 规范属性](pidtagattachtransportname-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

