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
ms.openlocfilehash: 0f0523c01e163b57d9ed37d9b324ec858adbd685
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426070"
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
  
> [in]指向包含要删除的消息数的 [ENTRYLIST](entrylist.md) 结构的指针，以及标识这些邮件的 [ENTRYID](entryid.md) 结构的数组。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。 
    
 _ulFlags_
  
> [in]控制邮件删除方式的标志的位掩码。 可以设置以下标志：
    
DELETE_HARD_DELETE
  
> 永久删除所有邮件，包括软删除的邮件。
    
MESSAGE_DIALOG 
  
> 在操作继续时显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的一个或多个邮件已成功删除。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有邮件都已成功删除。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIFolder：:D eleteMessages** 方法从文件夹中删除邮件。 无法删除不存在、已移动到其他位置、具有读/写权限打开或当前已提交的邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当删除操作涉及多封邮件时，请尽可能完全地执行每个文件夹的操作，即使一个或多个邮件无法删除。 除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。
  
## <a name="notes-to-callers"></a>给调用方的说明

预计以下情况下会返回这些值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**DeleteMessages** 已成功删除每封邮件。  <br/> |S_OK  <br/> |
|**DeleteMessages** 无法成功删除每封邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteMessages** 无法完成。  <br/> |任何错误值（MAPI_E_NOT_FOUND  <br/> |
   
当 **DeleteMessages** 无法完成时，不要假定未完成任何工作。 **DeleteMessages** 可能能够在遇到错误之前删除一个或多个邮件。 
  
 **DeleteMessages** MAPI_W_PARTIAL_COMPLETION或MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolderDlg：：OnDeleteSelectedItem  <br/> |MFCMAPI 使用 **IMAPIFolder：:D eleteMessages** 方法删除指定的邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ENTRYID](entryid.md)
  
[ENTRYLIST](entrylist.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[使用宏处理错误](using-macros-for-error-handling.md)

