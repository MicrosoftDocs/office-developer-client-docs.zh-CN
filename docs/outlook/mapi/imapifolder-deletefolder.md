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
ms.openlocfilehash: 02815c60b6bfc9809871af19e922913622588fc9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584315"
---
# <a name="imapifolderdeletefolder"></a>IMAPIFolder::DeleteFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要删除的子文件夹的项标识符的指针。
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志控制删除的子文件夹。 可以设置以下标志：
    
DEL_FOLDERS 
  
> 应删除的子文件夹指向的_lpEntryID_的所有子文件夹。 
    
DEL_MESSAGES 
  
> 应删除指向_lpEntryID_的子文件夹中的所有邮件。 
    
FOLDER_DIALOG 
  
> 继续操作时，应显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除指定的文件夹。
    
MAPI_E_HAS_FOLDERS 
  
> 正在删除的子文件夹包含子文件夹，并且未设置 DEL_FOLDERS 标志。 子文件夹未被删除。
    
MAPI_E_HAS_MESSAGES 
  
> 正在删除的子文件夹包含邮件和未设置 DEL_MESSAGES 标志。 未删除子文件夹。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但不是所有项都已成功删除。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::DeleteFolder**方法删除子文件夹。 默认情况下**DeleteFolder**运行只能在空文件夹，但您可以使用它成功对非空文件夹通过设置两个标志： DEL_FOLDERS 和 DEL_MESSAGES。 可以删除仅空文件夹或**DeleteFolder**呼叫的设置的 DEL_FOLDERS 和 DEL_MESSAGES 标志设置的文件夹。 DEL_FOLDERS 使所有文件夹的子文件夹要删除;DEL_MESSAGES 启用的所有文件夹的邮件中删除。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

当删除操作涉及多个文件夹时，每个文件夹尽可能完整执行操作。 有时之一要删除的文件夹不存在或已移动或复制到其他位置。 不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。
  
## <a name="notes-to-callers"></a>给调用方的说明

希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**DeleteFolder**已成功删除每封邮件和子文件夹。  <br/> |S_OK  <br/> |
|**DeleteFolder**程序无法成功删除每封邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**DeleteFolder**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 任何错误值  <br/> |
   
**DeleteFolder**无法完成后，请假定已完成任何工时。 **DeleteFolder**可能已经能够删除一个或多个邮件和子文件夹，然后再遇到错误。 
  
如果不能删除一个或多个子文件夹， **DeleteFolder**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于消息存储提供程序的实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMAPIFolder::DeleteFolder**方法删除文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

