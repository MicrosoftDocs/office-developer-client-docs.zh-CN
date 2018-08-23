---
title: IMAPIFolderEmptyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.EmptyFolder
api_type:
- COM
ms.assetid: 4cfcb498-9182-4906-bd6f-d9bc387bc88b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 287577babc9a40b771aa9917211ba5dcbf8190ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584938"
---
# <a name="imapifolderemptyfolder"></a>IMAPIFolder::EmptyFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
删除所有消息和子文件夹从文件夹而不删除该文件夹本身。
  
```cpp
HRESULT EmptyFolder(
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何清空文件夹。 可以设置以下标志：
    
DEL_ASSOCIATED 
  
> 删除所有子文件夹，包括子文件夹包含具有关联的内容的消息。 只对该呼叫会影响的顶级文件夹已 DEL_ASSOCIATED 标志。
    
DELETE_HARD_DELETE
  
> 永久删除所有邮件，包括软删除的。
    
FOLDER_DIALOG 
  
> 时需执行的操作，则显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功清空文件夹。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但不是完全清空文件夹。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::EmptyFolder**方法将删除所有文件夹的内容而不删除该文件夹本身。 
  
**EmptyFolder**呼叫期间，不会删除提交的邮件。 
  
文件夹关联的内容包括消息，用于描述视图、 规则、 自定义表单和自定义解决方案存储区，并且还可以包含表单定义。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

不要调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法的文件夹中的已提交的邮件。 不会删除提交的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**EmptyFolder**已成功清空文件夹。  <br/> |S_OK  <br/> |
|**EmptyFolder**无法完全清空文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**EmptyFolder**无法完成。  <br/> |任何错误值  <br/> |
   
无法完成**EmptyFolder**时，不假定任何工作已完成。 **EmptyFolder**可能已经能够删除该文件夹的内容的一些前遇到错误。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnEmptyFolder  <br/> |MFCMAPI 使用**IMAPIFolder::EmptyFolder**方法删除指定的文件夹中的内容。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

