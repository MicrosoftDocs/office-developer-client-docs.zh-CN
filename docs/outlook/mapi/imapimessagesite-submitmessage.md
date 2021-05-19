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
ms.openlocfilehash: 496732e334d2d39672048dd1a02346aaee4b70e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417026"
---
# <a name="imapimessagesitesubmitmessage"></a>IMAPIMessageSite::SubmitMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求将当前邮件排入队列进行传递。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制邮件提交方式的标志的位掩码。 可以设置以下标志：
    
FORCE_SUBMIT 
  
> MAPI 应该提交邮件，即使可能不会立即发送。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIMessageSite：：SubmitMessage** 方法，以请求将邮件排队等待传递。 邮件网站应在提交邮件之前调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法。 邮件不需要以前保存，因为 **SubmitMessage** 应在邮件已修改时导致邮件保存。 返回 **SubmitMessage** 后，表单必须检查当前邮件，然后在不存在邮件时自行消除。 
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：SubmitMessage  <br/> |MFCMAPI 使用 **IMAPIMessageSite：：SubmitMessage** 方法保存邮件。 首先，它调用 **IPersistMessage：：HandsOffMessage** 方法，然后调用 **SubmitMessage**。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

