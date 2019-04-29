---
title: IMAPIFormAdviseSinkOnActivateNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink.OnActivateNext
api_type:
- COM
ms.assetid: db621dfd-c6ad-42d2-8089-db40a63cab36
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d647b41018afbade91dffb2818b48b0738148855
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411762"
---
# <a name="imapiformadvisesinkonactivatenext"></a>IMAPIFormAdviseSink::OnActivateNext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示表单是否可以处理要显示的下一封邮件的邮件类。
  
```cpp
HRESULT OnActivateNext(
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPPERSISTMESSAGE FAR * ppPersistMessage
);
```

## <a name="parameters"></a>参数

 _lpszMessageClass_
  
> 实时指向下一封邮件的邮件类的指针。
    
 _ulMessageStatus_
  
> 实时客户端定义或提供程序定义的标志的位掩码, 从下一条消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制到显示, 提供有关邮件包含的内容表的状态信息实时.
    
 _ulMessageFlags_
  
> 实时一个指针, 指向从下一个要显示的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中复制的标志位掩码, 该消息表示邮件的当前状态。
    
 _ppPersistMessage_
  
> 排除一个指针, 指向一个指向用于新表单的 form 对象的[IPersistMessage](ipersistmessageiunknown.md)实现的指针 (如果需要新表单)。 如果当前窗体对象可用于显示并保存下一封邮件, 则可以返回指向 NULL 的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功, 表单可以处理下一封邮件。
    
S_FALSE 
  
> 表单不处理下一封邮件的邮件类。
    
## <a name="remarks"></a>说明

表单查看者调用**IMAPIFormAdviseSink:: OnActivateNext**方法, 以帮助表单确定是否可以在文件夹中显示下一封邮件。 下一封邮件可能是任何类的消息, 但通常是同一个类或相关类。 这样, 客户端应用程序可以尽可能重用表单对象, 从而使读取相同类的多个邮件的过程更为有效。 
  
大多数窗体对象将使用由_lpszMessageClass_参数指向的邮件类来确定它们是否可以处理下一封邮件。 通常情况下, 窗体不仅可以处理属于窗体的默认类的类的邮件, 还可以处理属于默认类的邮件的子类。 但是, 窗体可以使用其他因素来确定是否可以处理邮件, 例如下一封邮件的已发送或未发送状态。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果窗体可以处理邮件类, 则在_ppPersistMessage_参数中返回 S_OK 和 NULL。 如果表单可以创建可处理表单无法处理的邮件的新表单, 请按照以下步骤操作: 
  
1. 调用表单的类工厂以创建新表单对象的实例。
    
2. 将该实例存储在_ppPersistMessage_指针参数的内容中。 
    
3. 返回 S_OK。
    
表单查看器将使用[IPersistMessage:: load](ipersistmessage-load.md)方法加载邮件, 该对象属于_ppPersistMessage_指向的对象。
  
如果既不能创建的窗体也不能处理下一封邮件, 则返回 S_FALSE。 不过, 通常情况下, 窗体不应返回此值, 因为它会导致表单查看器中的性能下降。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |CMyMAPIFormViewer:: ActivateNext  <br/> |MFCMAPI 使用**IMAPIFormAdviseSink:: OnActivateNext**方法实现[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

