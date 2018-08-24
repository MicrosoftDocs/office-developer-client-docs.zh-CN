---
title: IMAPIFolderDeleteMessages
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.DeleteMessages
api_type:
- COM
ms.assetid: 5a16e62b-9d33-41cd-af2b-9abd403b6f2e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd0439c71df7083e3c4787a5d317fa11d2b99c61
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578631"
---
# <a name="imapifolderdeletemessages"></a>IMAPIFolder::DeleteMessages

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除一个或多个邮件。
  
```cpp
HRESULT DeleteMessages(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpMsgList_
  
> [in]一个指向[ENTRYLIST](entrylist.md)结构，其中包含要删除的消息的数目和确定邮件的[ENTRYID](entryid.md)结构的数组。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何删除邮件。 可以设置以下标志：
    
DELETE_HARD_DELETE
  
> 永久删除所有邮件，包括软删除的。
    
MESSAGE_DIALOG 
  
> 随着进行操作，则显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的邮件或消息已成功删除。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但不是所有的邮件已成功删除。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::DeleteMessages**方法从文件夹中删除邮件。 无法删除的邮件的不存在、 已在其他地方移动的、 具有读/写权限打开或当前提交。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

时删除操作涉及多个邮件，执行操作完全尽可能对于每个文件夹中，即使不能删除一个或多条消息。 不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。
  
## <a name="notes-to-callers"></a>给调用方的说明

希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**DeleteMessages**已成功删除每条消息。  <br/> |S_OK  <br/> |
|**DeleteMessages**程序无法成功删除每封邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteMessages**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 任何错误值  <br/> |
   
无法完成**DeleteMessages**时，不假定任何工作已完成。 **DeleteMessages**可能已经能够删除一个或多条消息，然后再遇到错误。 
  
 **DeleteMessages**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg::OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMAPIFolder::DeleteMessages**方法删除指定的邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ENTRYID](entryid.md)
  
[ENTRYLIST](entrylist.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

