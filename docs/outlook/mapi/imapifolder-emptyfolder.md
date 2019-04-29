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
ms.openlocfilehash: 4ca828c3e03cbff886230f2af63485f7b15e8b35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416781"
---
# <a name="imapifolderemptyfolder"></a>IMAPIFolder::EmptyFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除文件夹中的所有邮件和子文件夹, 而不删除该文件夹本身。
  
```cpp
HRESULT EmptyFolder(
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _ulFlags_
  
> 实时用于控制文件夹如何清空的标志的位掩码。 可以设置以下标志:
    
DEL_ASSOCIATED 
  
> 删除所有子文件夹, 包括包含相关内容的邮件的子文件夹。 DEL_ASSOCIATED 标志仅对调用操作所针对的顶级文件夹有意义。
    
DELETE_HARD_DELETE
  
> 永久删除所有邮件, 包括软删除的邮件。
    
FOLDER_DIALOG 
  
> 在操作继续时显示进度指示器。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功清空该文件夹。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功, 但未完全清空该文件夹。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIFolder:: EmptyFolder**方法删除文件夹中的所有内容, 而不删除文件夹本身。 
  
在**EmptyFolder**呼叫过程中, 不会删除已提交的邮件。 
  
文件夹的关联内容包括用于描述视图、规则、自定义表单和自定义解决方案存储的邮件, 还可以包括表单定义。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

请勿为已提交的文件夹中的邮件调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法。 已提交的邮件不会被删除。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在下列情况下, 需要这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**EmptyFolder**已成功清空文件夹。  <br/> |S_OK  <br/> |
|**EmptyFolder**无法完全清空文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**EmptyFolder**无法完成。  <br/> |任何错误值  <br/> |
   
当**EmptyFolder**无法完成时, 请不要假定没有任何工作已完成。 **EmptyFolder**可能已能够在遇到此错误之前删除部分文件夹内容。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg  <br/> |CMsgStoreDlg:: OnEmptyFolder  <br/> |MFCMAPI 使用**IMAPIFolder:: EmptyFolder**方法删除指定文件夹的内容。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

