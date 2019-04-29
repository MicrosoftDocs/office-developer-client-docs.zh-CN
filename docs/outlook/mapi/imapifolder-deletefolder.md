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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要删除的子文件夹的条目标识符的指针。
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 FOLDER_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制删除子文件夹的标志的位掩码。 可以设置以下标志:
    
DEL_FOLDERS 
  
> 应删除_lpEntryID_指向的子文件夹的所有子文件夹。 
    
DEL_MESSAGES 
  
> 应删除由_lpEntryID_指向的子文件夹中的所有邮件。 
    
FOLDER_DIALOG 
  
> 操作继续时应显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除指定的文件夹。
    
MAPI_E_HAS_FOLDERS 
  
> 要删除的子文件夹包含子文件夹, 且未设置 DEL_FOLDERS 标志。 子文件夹未被删除。
    
MAPI_E_HAS_MESSAGES 
  
> 要删除的子文件夹包含邮件, 且未设置 DEL_MESSAGES 标志。 未删除子文件夹。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 呼叫成功, 但未成功删除所有条目。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIFolder::D eletefolder**方法删除子文件夹。 默认情况下, **DeleteFolder**仅对空文件夹进行操作, 但您可以通过设置两个标志: DEL_FOLDERS 和 DEL_MESSAGES, 在非空文件夹上成功地使用它。 只能删除在**DeleteFolder**调用中设置 DEL_FOLDERS 和 DEL_MESSAGES 标志的空文件夹或文件夹。 DEL_FOLDERS 启用要删除的文件夹的所有子文件夹。DEL_MESSAGES 启用要删除的所有文件夹的邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果删除操作涉及多个文件夹, 请尽可能完全地对每个文件夹执行此操作。 有时要删除的一个文件夹不存在或已移动或复制到其他位置。 请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。
  
## <a name="notes-to-callers"></a>给调用方的说明

在下列情况下, 需要这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**DeleteFolder**已成功删除每个邮件和子文件夹。  <br/> |S_OK  <br/> |
|**DeleteFolder**无法成功删除每个邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteFolder**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 外的任何错误值  <br/> |
   
当**DeleteFolder**无法完成时, 请不要假定没有任何工作已完成。 **DeleteFolder**可能已能够在遇到错误之前删除一个或多个邮件和子文件夹。 
  
如果无法删除一个或多个子文件夹, **DeleteFolder**将返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND, 具体取决于邮件存储提供程序的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg  <br/> |CMsgStoreDlg:: OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMAPIFolder::D eletefolder**方法删除文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

