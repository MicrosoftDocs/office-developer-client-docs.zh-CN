---
title: IMAPIViewContextGetSaveStream
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetSaveStream
api_type:
- COM
ms.assetid: 8316bfa1-3077-401f-aa1e-e9492aca12a8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 47ea122fce7969b326dbd48f875696b91de464f5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568572"
---
# <a name="imapiviewcontextgetsavestream"></a>IMAPIViewContext::GetSaveStream

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索用于保存当前消息流。
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a>参数

 _pulFlags_
  
> [输出]指向控制应如何保存消息文本的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> Unicode 格式保存的消息文本。 如果未设置 MAPI_UNICODE 标志，文本将保存在 ANSI 格式。
    
 _pulFormat_
  
> [输出]指向控制的已保存的文本的格式的标志位掩码。 可以设置以下标志：
    
SAVE_FORMAT_RICHTEXT 
  
> 消息文本是保存为带格式文本中富文本格式 (RTF)。 
    
SAVE_FORMAT_TEXT 
  
> 消息文本是保存为纯文本。 
    
 _ppstm_
  
> [输出]为将包含已保存的邮件流指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功检索的流。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIViewContext::GetSaveStream**方法检索流实现表单查看器中支持的另存为谓词处理的**IStream**接口的对象。 [IMAPIForm::DoVerb](imapiform-doverb.md)方法，这是在窗体服务器中实现，并调用表单查看器调用一个谓词，不应该返回直到邮件是完全转换为相应的文本格式，并放入适当的流。 
  
## <a name="notes-to-callers"></a>给调用方的说明

不写入由指向_ppstm_调用**GetSaveStream**之前的流。 **GetSaveStream**返回时，不要重置 seek 指针的位置。 此指针必须保持已保存的消息文本的结尾处。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)

