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
  
请求将当前邮件排队等待传递。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时控制如何提交邮件的标志的位掩码。 可以设置以下标志:
    
FORCE_SUBMIT 
  
> MAPI 应提交邮件, 即使它可能不会立即发送。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIMessageSite:: SubmitMessage**方法以请求将邮件排队等待传递。 邮件网站在提交邮件之前, 应调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。 该邮件不需要先保存, 因为如果邮件已被修改, **SubmitMessage**应会导致保存邮件。 返回**SubmitMessage**后, 该窗体必须检查当前邮件, 然后在不存在的情况下消除自己。 
  
有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: SubmitMessage  <br/> |MFCMAPI 使用**IMAPIMessageSite:: SubmitMessage**方法保存邮件。 首先, 它调用**IPersistMessage:: HandsOffMessage**方法, 然后调用**SubmitMessage**。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

