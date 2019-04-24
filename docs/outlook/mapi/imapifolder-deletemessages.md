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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280118"
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
  
> 实时指向[ENTRYLIST](entrylist.md)结构的指针, 该结构包含要删除的邮件数以及标识这些邮件的[ENTRYID](entryid.md)结构的数组。 
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 除非在_ulFlags_参数中设置了 MESSAGE_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_参数中设置了 MESSAGE_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _ulFlags_
  
> 实时用于控制如何删除邮件的标志的位掩码。 可以设置以下标志:
    
DELETE_HARD_DELETE
  
> 永久删除所有邮件, 包括软删除的邮件。
    
MESSAGE_DIALOG 
  
> 在操作继续时显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除指定的一个或一条消息。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 呼叫成功, 但未成功删除所有邮件。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::D eletemessages**方法删除文件夹中的邮件。 不存在、已移动到其他位置、以读/写权限打开, 或当前已提交的邮件无法被删除。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当删除操作涉及多封邮件时, 应尽可能完全地对每个文件夹执行此操作, 即使无法删除一个或多个邮件也是如此。 请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。
  
## <a name="notes-to-callers"></a>给调用方的说明

在下列情况下, 需要这些返回值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**DeleteMessages**已成功删除每封邮件。  <br/> |S_OK  <br/> |
|**DeleteMessages**无法成功删除每个邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteMessages**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 外的任何错误值  <br/> |
   
当**DeleteMessages**无法完成时, 请不要假定没有任何工作已完成。 **DeleteMessages**可能已能够在遇到错误之前删除一个或多个邮件。 
  
 **DeleteMessages**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND, 具体取决于邮件存储区的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |CFolderDlg:: OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMAPIFolder::D eletemessages**方法删除指定的邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ENTRYID](entryid.md)
  
[ENTRYLIST](entrylist.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

