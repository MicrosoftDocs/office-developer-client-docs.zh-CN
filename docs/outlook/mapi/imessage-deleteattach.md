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
ms.openlocfilehash: de5c98272c08c469acf23b0ecae7eac0a2d1bfe6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592512"
---
# <a name="imessagedeleteattach"></a>IMessage::DeleteAttach

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]若要删除的附件的索引号。 这是附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性的值。
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。 除非 ATTACH_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]对显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将显示进度指示器使用 MAPI 进度对象实现。 除非_ulFlags_中设置了 ATTACH_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，控制的用户界面的显示。 可以设置以下标记：
    
ATTACH_DIALOG 
  
> 随着操作进行请求进度指示器的显示。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除附件。
    
## <a name="remarks"></a>注解

**IMessage::DeleteAttach**方法删除从邮件中的附件。 
  
消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法被调用之前，已删除的附件未被永久删除。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**DeleteAttach**之前, 的附件和每个其流中调用**IUnknown::Release**方法。 
  
由于删除附件可能会很长时间， **DeleteAttach**提供显示进度指示器的机制。 您可以通过传递一个指向请求的进度指示器显示您[IMAPIProgress: IUnknown](imapiprogressiunknown.md)实现或 NULL，如果您没有实施。 您还必须在_ulUIParam_参数和 ATTACH_DIALOG 标志_ulFlags_参数中的指定窗口句柄。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|AttachmentsDlg.cpp  <br/> |CAttachmentsDlg::OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMessage::DeleteAttach**方法删除所选的附件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

