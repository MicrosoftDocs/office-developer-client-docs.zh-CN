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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 154d6e4a4e333f3a6165c3875bdcd57957ebf70c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348732"
---
# <a name="itnefopentaggedbody"></a>ITnef::OpenTaggedBody

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开封装邮件的文本上的流接口。
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向与流关联的消息的指针。 此消息不需要与调用[OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数时传递的消息[](opentnefstreamex.md)相同。 
    
 _ulFlags_
  
> [in]控制流接口打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_CREATE 
  
> 如果当前邮件中不存在属性，应创建该属性。 如果该属性存在，则属性中的当前数据应替换为 TNEF Transport-Neutral封装格式 (数据) 数据。 当实现设置MAPI_CREATE标志时，它还应设置MAPI_MODIFY标志。
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认接口是只读的。 MAPI_MODIFY设置时必须MAPI_CREATE设置。
    
 _lppStream_
  
> [out]指向流对象的指针，该对象包含传入 **封装** 邮件的 PR_BODY ([PidTagBody](pidtagbody-canonical-property.md)) 属性并支持 [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) 接口的文本。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：OpenTaggedBody** 方法来打开封装邮件的文本上的流接口 (即 TNEF 对象) 。 
  
在处理过程中 **，OpenTaggedBody** 插入或分析指示任何附件或 OLE 对象在邮件文本中的位置的附件标记。 附件标记的格式如下： 
  
 **[[**_附件名称_ **：** _n_ **in** attachment container _name_ **]]**
  
 _附件名称_ 描述附件对象; _n_ 是一个数字，标识序列的一部分的附件，从 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数的 _lpKey_ 参数中传递的值递增; [](opentnefstreamex.md)和 _附件容器名称_ 描述附件对象所在的物理组件。 
  
 **OpenTaggedBody** 会读出邮件文本，并插入附件标记，只要附件对象最初出现在文本中。 原始邮件文本未更改。 
  
当包含标记的邮件传递到流时，标记将去除，附件对象将重定位在流中标记的位置。
  
## <a name="see-also"></a>另请参阅



[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagBody 规范属性](pidtagbody-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

