---
title: IMAPIFolderCopyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyFolder
api_type:
- COM
ms.assetid: 2c1c25c6-1aec-4d9e-a2a3-bf1b4a2908b8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d9c1e88b12baf50593212a3ae3c02907ce6617b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280176"
---
# <a name="imapifoldercopyfolder"></a>IMAPIFolder::CopyFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动子文件夹。
  
```cpp
HRESULT CopyFolder(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  LPVOID lpDestFolder,
  LPSTR lpszNewFolderName,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要复制或移动的子文件夹的条目标识符的指针。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问_lpDestFolder_参数所指向的文件夹的接口。 传递 NULL 将导致服务提供程序返回标准文件夹接口[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 _lpInterface_的有效值包括 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 和 IID_IMAPIFolder。 
    
 _lpDestFolder_
  
> 实时指向用于接收复制或移动的子文件夹的打开文件夹的指针。
    
 _lpszNewFolderName_
  
> 实时一个指针, 指向其新目标中复制或移动的文件夹的名称。 如果将_lpszNewFolderName_设置为 NULL, 则源子文件夹的名称将用于目标文件夹的名称。 
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 除非设置_ulFlags_参数中的 FOLDER_DIALOG 标记, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 FOLDER_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制复制或移动操作的标志的位掩码。 可以设置以下标志:
    
COPY_SUBFOLDERS 
  
> 还应复制子文件夹中要复制的所有子文件夹。 如果 COPY_SUBFOLDERS 不是为复制操作设置的, 则仅复制由_lpEntryID_标识的子文件夹。 通过移动操作, 无论是否设置了标志, COPY_SUBFOLDERS 行为都是默认行为。 
    
FOLDER_DIALOG 
  
> 请求显示进度指示器。
    
FOLDER_MOVE 
  
> 移动子文件夹, 而不是复制。 如果未设置 FOLDER_MOVE, 则复制子文件夹。
    
MAPI_DECLINE_OK 
  
> 通过调用其支持对象的 IMAPISupport 来实现**CopyFolder** , 通知邮件存储提供程序[::D ocopyto](imapisupport-docopyto.md)或[IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法, **CopyFolder**应立即返回 MAPI_E_DECLINE_COPY。 
    
MAPI_UNICODE 
  
> 目标文件夹的名称采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则该文件夹名称为 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动指定的文件夹。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且邮件存储区提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 且邮件存储区提供程序仅支持 UNICODE。
    
MAPI_E_COLLISION 
  
> 要移动或复制的文件夹的名称与目标文件夹中的子文件夹的名称相同。 邮件存储区提供程序需要唯一的文件夹名称。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序通过调用支持对象方法来实现此方法, 并且调用方已传递 MAPI_DECLINE_OK 标志。
    
MAPI_E_FOLDER_CYCLE 
  
> 源文件夹直接或间接包含目标文件夹。 在发现此条件之前, 可能已经执行了大量的工作, 因此源文件夹和目标文件夹可能被部分修改。 
    
MAPI_W_PARTIAL_COMPLETION 
  
> 呼叫成功, 但未成功复制所有条目。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder:: CopyFolder**方法将子文件夹从一个位置复制或移动到另一个位置。 要复制或移动的子文件夹作为子文件夹添加到目标文件夹中。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当复制或移动操作涉及多个文件夹 (如设置 COPY_SUBFOLDERS 标志) 时, 请尽可能为每个文件夹完全执行该操作。 有时, 要移动或复制的一个文件夹不存在, 或者已将其移动或复制到其他位置。 请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。
  
尝试将所有邮件条目标识符保留在复制的邮件中。 您还应尝试保留条目标识符, 但这并不是必需的。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在下列情况下, 需要这些返回值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**CopyFolder**已成功复制或移动每个邮件和子文件夹。  <br/> |S_OK  <br/> |
|**CopyFolder**无法成功复制或移动每个邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**CopyFolder**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 外的任何错误值  <br/> |
   
当**CopyFolder**无法完成时, 请不要假定没有任何工作已完成。 在遇到此错误之前, **CopyFolder**可能已能够复制或移动一个或多个邮件和子文件夹。 
  
如果在_lpEntryID_中传递了不存在的文件夹的条目标识符, 则**CopyFolder**将返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND, 具体取决于邮件存储的实现。 
  
根据邮件存储提供程序, 原始邮件的条目标识符可能会保留在复制的邮件中, 也可能不会保留。 应尽可能保留条目标识符, 但这并不是必需的。 您通常可以依赖于以下方案:
  
- 在两种不同类型的邮件存储之间移动文件夹时, 可保证条目标识符的变化。
    
- 当您在两个相同类型的邮件存储库之间移动文件夹时, 条目标识符几乎总是发生变化。
    
- 将文件夹移动到同一邮件存储区中的其他位置时, 条目标识符可能会更改, 也可能不会更改, 具体取决于邮件存储提供程序。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg  <br/> |CMsgStoreDlg:: OnPasteFolder  <br/> |MFCMAPI 使用**IMAPIFolder:: CopyFolder**方法将文件夹从一个位置复制到另一个位置。 MFCMAPI 在复制操作过程中记住源文件夹, 并在粘贴操作过程中实际执行复制操作。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

