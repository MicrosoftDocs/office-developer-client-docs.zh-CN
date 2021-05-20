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
  
> [in]要删除的附件的索引号。 这是[PidTagAttachNumber](pidtagattachnumber-canonical-property.md) PR_ATTACH_NUM (附件) 的值。 
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 ATTACH_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 ATTACH_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制用户界面显示的标志的位掩码。 可以设置以下标志：
    
ATTACH_DIALOG 
  
> 请求在操作继续时显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 附件已成功删除。
    
## <a name="remarks"></a>备注

**IMessage：:D eleteAttach** 方法从邮件中删除附件。 
  
在调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法之前，不会永久删除已删除的附件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用 **DeleteAttach** 之前，请为附件及其每个流调用 **IUnknown：：Release** 方法。 
  
由于删除附件的过程可能很长， **因此 DeleteAttach** 提供了显示进度指示器的机制。 可以通过将指针传递给 [IMAPIProgress ：IUnknown](imapiprogressiunknown.md) 实现或 NULL（如果你没有实现）来请求显示进度指示器。 还必须在  _ulUIParam_ 参数中指定窗口句柄，在  _ulFlags_ ATTACH_DIALOG指定该窗口句柄。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|AttachmentsDlg.cpp  <br/> |CAttachmentsDlg：：OnDeleteSelectedItem  <br/> |MFCMAPI 使用 **IMessage：:D eleteAttach** 方法删除选定的附件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

