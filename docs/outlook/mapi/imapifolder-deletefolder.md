---
title: IMAPIFolderDeleteFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.DeleteFolder
api_type:
- COM
ms.assetid: 6c3e883c-80c0-4eda-8f81-8277d933a74b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a476607927f3563ede94a04ccfe4f7a3749c978e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417404"
---
# <a name="imapifolderdeletefolder"></a>IMAPIFolder::DeleteFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除子文件夹。
  
```cpp
HRESULT DeleteFolder(
  ULONG_PTR cbEntryID,
  LPENTRYID lpEntryID,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要删除的子文件夹的条目标识符的指针。
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 FOLDER_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 FOLDER_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制子文件夹删除的标记位掩码。 可以设置以下标志：
    
DEL_FOLDERS 
  
> 应删除  _lpEntryID_ 指向的子文件夹的所有子文件夹。 
    
DEL_MESSAGES 
  
> 应删除  _lpEntryID_ 指向的子文件夹内的所有邮件。 
    
FOLDER_DIALOG 
  
> 在操作进行时，应显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的文件夹已成功删除。
    
MAPI_E_HAS_FOLDERS 
  
> 要删除的子文件夹包含子文件夹，并且未DEL_FOLDERS子文件夹标记。 未删除子文件夹。
    
MAPI_E_HAS_MESSAGES 
  
> 要删除的子文件夹包含邮件，并且未DEL_MESSAGES子文件夹标记。 未删除子文件夹。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有条目都已成功删除。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIFolder：:D eleteFolder** 方法删除子文件夹。 默认情况下 **，DeleteFolder** 仅对空文件夹运行，但您可以通过设置两个标志成功在非空文件夹上使用它：DEL_FOLDERS 和 DEL_MESSAGES。 只有在 **DeleteFolder** 调用上同时设置 DEL_FOLDERS 和 DEL_MESSAGES 标记的空文件夹或文件夹才能删除。 DEL_FOLDERS可删除文件夹的所有子文件夹;DEL_MESSAGES可删除文件夹的所有邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当删除操作涉及多个文件夹时，请尽可能完全地执行每个文件夹的操作。 有时，要删除的文件夹之一不存在，或者已移动到其他位置或已将其复制。 除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。
  
## <a name="notes-to-callers"></a>给调用方的说明

预计以下情况下会返回这些值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**DeleteFolder** 已成功删除每封邮件和子文件夹。  <br/> |S_OK  <br/> |
|**DeleteFolder** 无法成功删除每封邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteFolder** 无法完成。  <br/> |任何错误值（MAPI_E_NOT_FOUND  <br/> |
   
当 **DeleteFolder** 无法完成时，不要假定未完成任何工作。 **DeleteFolder** 可能能够在遇到错误之前删除一个或多个邮件和子文件夹。 
  
如果无法删除一个或多个子文件夹 **，DeleteFolder** MAPI_W_PARTIAL_COMPLETION或MAPI_E_NOT_FOUND，具体取决于邮件存储提供程序的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnDeleteSelectedItem  <br/> |MFCMAPI 使用 **IMAPIFolder：:D eleteFolder** 方法删除文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

