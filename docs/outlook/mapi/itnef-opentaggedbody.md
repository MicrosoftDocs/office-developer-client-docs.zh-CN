---
title: ITnefOpenTaggedBody
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.OpenTaggedBody
api_type:
- COM
ms.assetid: 70d5b34c-85b3-4d1f-860e-2838947ba428
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ed433dc1fcf2a366d2ece07ac06d4e12558e4aa7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776098"
---
# <a name="itnefopentaggedbody"></a>ITnef::OpenTaggedBody

  
  
**适用于**： Outlook 
  
打开上封装的消息的文本的流接口。
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向与 stream 所关联的消息的指针。 此消息不需要为相同的邮件传递对[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的调用中。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开的 stream 接口。 可以设置以下标志：
    
MAPI_CREATE 
  
> 如果属性不存在当前消息中，应创建它。 如果该属性不存在，应使用传输中性封装格式 (TNEF) 用于将 stream 中的数据更换中属性的当前数据。 当实现设置 MAPI_CREATE 标志时，它也应设置 MAPI_MODIFY 标志。
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认接口是只读的。 必须设置 MAPI_MODIFY，只要 MAPI_CREATE 设置。
    
 _lppStream_
  
> [输出]指向到包含传入的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的文本 stream 对象的指针的指针封装消息和支持[IStream](http://msdn.microsoft.com/library/stg.istream%28Office.15%29.aspx)接口的。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>说明

传输提供程序、 消息存储提供程序，和网关调用**ITnef::OpenTaggedBody**方法打开上封装的消息的文本的流接口 （即上 TNEF, 对象中）。 
  
作为其处理的一部分， **OpenTaggedBody**插入或分析附件标记指示消息文本中的任何附件或 OLE 对象的位置。 附件标记是采用以下格式： 
  
 **[[** **_附件名称_ **:** _n_ _附件容器名称_** **]]**
  
 _附件名称_介绍 attachment 对象中; _n_是从[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数; 的_lpKey_参数中传递的值递增的数字标识的序列的一部分附件和_附件容器名称_介绍 attachment 对象所在的物理组件。 
  
 **OpenTaggedBody**读取出消息文本，并应 attachment 对象最初出现在文本中插入某个附件标记。 原始消息文本不会更改。 
  
当已标记邮件传递到流时，标记都将去除和流中的标记的位置中重新定位的 attachment 对象。
  
## <a name="see-also"></a>另请参阅



[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagBody 规范属性](pidtagbody-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

