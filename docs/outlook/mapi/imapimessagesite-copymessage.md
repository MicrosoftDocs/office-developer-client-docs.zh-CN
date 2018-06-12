---
title: IMAPIMessageSiteCopyMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.CopyMessage
api_type:
- COM
ms.assetid: d4e18483-409a-4d81-91dc-f4aec29a82bb
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5bf2ff74f6cda01608efd4b372aa4b03468c820f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775450"
---
# <a name="imapimessagesitecopymessage"></a>IMAPIMessageSite::CopyMessage

  
  
**适用于**： Outlook 
  
将当前的邮件复制到一个文件夹。
  
```cpp
HRESULT CopyMessage(
  LPMAPIFOLDER pFolderDestination
);
```

## <a name="parameters"></a>参数

 _pFolderDestination_
  
> [in]一个指向邮件后要复制的文件夹。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_SUPPORT 
  
> 该操作不受此消息网站。
    
## <a name="remarks"></a>备注

表单对象调用**IMAPIMessageSite::CopyMessage**方法将当前的邮件复制到新文件夹。 **CopyMessage**不会更改当前正在显示给用户的邮件和新创建的邮件没有接口返回到表单。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**CopyMessage**方法的典型实现执行以下任务： 
  
1. 创建一个新邮件以复制到的当前消息。
    
2. 调用[IPersistMessage::Save](ipersistmessage-save.md)方法与指向_pMessage_参数和 FALSE _fSameAsLoad_参数中的新消息的指针。 
    
3. 调用[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法， _pMessage_参数中传递 NULL。 
    
4. 在新邮件上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 
    
向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::CopyMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 作为的代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

