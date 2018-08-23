---
title: IMAPIMessageSiteSubmitMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.SubmitMessage
api_type:
- COM
ms.assetid: 6b14c383-8bc6-4e86-bd92-0500272af40d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 587b8bbb7ac25a7977d8962535f1909464ffc248
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571099"
---
# <a name="imapimessagesitesubmitmessage"></a>IMAPIMessageSite::SubmitMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当前邮件在排队等待传送的请求。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何提交一条消息。 可以设置以下标记：
    
FORCE_SUBMIT 
  
> MAPI 应提交的邮件，即使它可能不立即发送。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIMessageSite::SubmitMessage**方法以请求邮件在排队等待传送。 消息网站应在提交邮件之前调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。 消息不需要已以前保存，因为**SubmitMessage**应会导致如果已修改邮件同时保存邮件。 后**SubmitMessage**返回时，窗体必须检查当前消息，然后关闭本身，如果不存在。 
  
有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::SubmitMessage  <br/> |MFCMAPI 使用**IMAPIMessageSite::SubmitMessage**方法保存邮件。 首先，它将调用**IPersistMessage::HandsOffMessage**方法，然后它调用**SubmitMessage**。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

