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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 68eb74f53d6cee4661c98604ec2ea37609e20ab5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408423"
---
# <a name="imapiviewcontextgetsavestream"></a>IMAPIViewContext::GetSaveStream

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索用于保存当前消息的流。
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a>参数

 _将标记_
  
> [out]指向控制邮件文本保存方式的标志的位掩码的指针。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 邮件文本以 Unicode 格式保存。 如果未MAPI_UNICODE，文本将保存为 ANSI 格式。
    
 _将format_
  
> [out]指向控制已保存文本格式的标志的位掩码的指针。 可以设置以下标志：
    
SAVE_FORMAT_RICHTEXT 
  
> 邮件文本将保存为 RTF 格式 (格式) 。 
    
SAVE_FORMAT_TEXT 
  
> 邮件文本将另存为纯文本。 
    
 _ppstm_
  
> [out]指向将包含已保存消息的流的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索流。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIViewContext：：GetSaveStream** 方法以检索实现 **IStream** 接口的对象的流，以支持在表单查看器中处理"另存为"动词。 [IMAPIForm：:D oVerb](imapiform-doverb.md)方法在表单服务器中实现，并且由表单查看器调用以调用动词，在邮件完全转换为适当的文本格式并放入适当的流中之前，不应返回此方法。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用 **GetSaveStream** 之前，不要写入 _ppstm_ 指向的流。 当 **GetSaveStream** 返回时，不要重置查找指针的位置。 此指针必须保留在保存的邮件文本的末尾。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)

