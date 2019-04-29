---
title: IMessageDeleteAttach
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.DeleteAttach
api_type:
- COM
ms.assetid: 0a5cb49f-c4f3-4893-8616-80d6332efcfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c14ccac0addbc1288e3507cf549344f75e69cc28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430705"
---
# <a name="imessagedeleteattach"></a>IMessage::DeleteAttach

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除附件。
  
```cpp
HRESULT DeleteAttach(
ULONG ulAttachmentNum,
ULONG_PTR ulUIParam,
LPMAPIPROGRESS lpProgress,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulAttachmentNum_
  
> 实时要删除的附件的索引号。 这是附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性的值。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 除非在_ulFlags_参数中设置了 ATTACH_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非在_ulFlags_中设置了 ATTACH_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制用户界面显示的标志的位掩码。 可以设置以下标志:
    
ATTACH_DIALOG 
  
> 在操作进行过程中请求显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除附件。
    
## <a name="remarks"></a>说明

**IMessage::D eleteattach**方法可从邮件中删除附件。 
  
在调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 不会永久删除已删除的附件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用**DeleteAttach**之前, 请先调用附件及其每个流的**IUnknown:: Release**方法。 
  
由于删除附件可能是一个漫长的过程, 因此**DeleteAttach**提供了显示进度指示器的机制。 您可以通过以下方式请求显示进度指示器: 将指针传递给您的[IMAPIProgress: IUnknown](imapiprogressiunknown.md)实现; 如果没有实现, 则为 NULL。 您还必须在_ulUIParam_参数中指定窗口句柄, 并在_ulFlags_参数中指定 ATTACH_DIALOG 标志。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AttachmentsDlg  <br/> |CAttachmentsDlg:: OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMessage::D eleteattach**方法删除选定附件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

