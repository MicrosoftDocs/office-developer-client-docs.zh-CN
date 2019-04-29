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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aeb8b090997bd0c4f51f872b36d6520547846f7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429998"
---
# <a name="imapimessagesitecopymessage"></a>IMAPIMessageSite::CopyMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将当前邮件复制到一个文件夹中。
  
```cpp
HRESULT CopyMessage(
  LPMAPIFOLDER pFolderDestination
);
```

## <a name="parameters"></a>参数

 _pFolderDestination_
  
> 实时指向要将邮件复制到的文件夹的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_SUPPORT 
  
> 此邮件网站不支持该操作。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIMessageSite:: CopyMessage**方法将当前邮件复制到新文件夹。 **CopyMessage**不会更改当前向用户显示的邮件, 并且不会将新创建的邮件的任何界面返回到表单。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**CopyMessage**方法的典型实现将执行以下任务: 
  
1. 为要复制到的当前邮件创建一个新邮件。
    
2. 调用[IPersistMessage:: Save](ipersistmessage-save.md)方法, 并将指针指向_pMessage_参数中的新邮件, 并调用_fSameAsLoad_参数中的 FALSE。 
    
3. 调用[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)方法, 并在_pMessage_参数中传递 NULL。 
    
4. 对新邮件调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 
    
有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: CopyMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

