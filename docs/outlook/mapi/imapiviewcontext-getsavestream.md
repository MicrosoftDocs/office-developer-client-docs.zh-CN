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
  
检索用于保存当前邮件的流。
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a>参数

 _pulFlags_
  
> 排除指向控制应如何保存邮件文本的标志的位掩码的指针。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 邮件文本以 Unicode 格式保存。 如果未设置 MAPI_UNICODE 标志, 则文本将保存为 ANSI 格式。
    
 _pulFormat_
  
> 排除指向控制保存的文本的格式的标志位掩码的指针。 可以设置以下标志:
    
SAVE_FORMAT_RICHTEXT 
  
> 邮件文本将保存为 rtf 格式的格式文本。 
    
SAVE_FORMAT_TEXT 
  
> 邮件文本将保存为纯文本格式。 
    
 _ppstm_
  
> 排除指向指向将包含已保存邮件的流的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索流。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIViewContext:: GetSaveStream**方法以检索 stream 一个对象, 该对象实现**IStream**接口, 以支持在表单查看器中处理 "另存为" 谓词。 [IMAPIForm::D overb](imapiform-doverb.md)方法, 该方法在表单服务器中实现并由表单查看器调用以调用谓词, 在邮件完全转换为相应的文本格式并置于相应的流中之前, 不应返回。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用**GetSaveStream**之前, 请勿写入_ppstm_指向的流。 当**GetSaveStream**返回时, 请勿重置查找指针的位置。 此指针必须保留在保存的邮件文本的末尾。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)

