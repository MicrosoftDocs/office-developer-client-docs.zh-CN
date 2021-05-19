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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425657"
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要复制或移动的子文件夹的条目标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识符 (IID) 表示用于访问  _lpDestFolder_ 参数指向的文件夹的接口的指针。 传递 NULL 会导致服务提供商返回标准文件夹接口 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。 _lpInterface_ 的有效值包括 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 和 IID_IMAPIFolder。 
    
 _lpDestFolder_
  
> [in]一个指向打开文件夹的指针，用于接收复制或移动的子文件夹。
    
 _lpszNewFolderName_
  
> [in]指向新目标中复制或移动的文件夹的名称的指针。 如果  _lpszNewFolderName_ 设置为 NULL，则源子文件夹的名称将用于目标文件夹的名称。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 除非  _设置了 ulFlags_ 参数中的 FOLDER_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 FOLDER_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制复制或移动操作的标志的位掩码。 可以设置以下标志：
    
COPY_SUBFOLDERS 
  
> 还应复制要复制的子文件夹内的所有子文件夹。 当COPY_SUBFOLDERS复制操作时，只会复制  _由 lpEntryID_ 标识的子文件夹。 使用移动操作时，COPY_SUBFOLDERS行为是默认行为，而不管是否已设置标志。 
    
FOLDER_DIALOG 
  
> 请求进度指示器的显示。
    
FOLDER_MOVE 
  
> 要移动而不是复制子文件夹。 如果未FOLDER_MOVE，将复制子文件夹。
    
MAPI_DECLINE_OK 
  
> 通知邮件存储提供程序，如果它通过调用其支持对象的 [IMAPISupport：:D oCopyTo](imapisupport-docopyto.md)或 [IMAPISupport：:D oCopyProps](imapisupport-docopyprops.md)方法来实现 **CopyFolder，****则 CopyFolder** 应立即返回 MAPI_E_DECLINE_COPY。 
    
MAPI_UNICODE 
  
> 目标文件夹的名称采用 Unicode 格式。 如果未MAPI_UNICODE，文件夹名称将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 指定的文件夹已成功复制或移动。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE，并且邮件存储提供程序不支持 Unicode，或者未MAPI_UNICODE邮件存储提供程序仅支持 Unicode。
    
MAPI_E_COLLISION 
  
> 要移动或复制的文件夹的名称与目标文件夹中子文件夹的名称相同。 邮件存储提供程序需要唯一的文件夹名称。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序通过调用支持对象方法来实现此方法，并且调用方已传递MAPI_DECLINE_OK标志。
    
MAPI_E_FOLDER_CYCLE 
  
> 源文件夹直接或间接包含目标文件夹。 在发现此条件之前，可能执行了大量工作，因此可能会部分修改源和目标文件夹。 
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有条目都已成功复制。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：CopyFolder** 方法将子文件夹从一个位置复制或移动到另一个位置。 复制或移动的子文件夹作为子文件夹添加到目标文件夹。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当复制或移动操作涉及多个文件夹（如设置 COPY_SUBFOLDERS 标志所指示）时，请尽可能完全地执行每个文件夹的操作。 有时，要移动或复制的文件夹之一不存在，或者已移动到其他位置或已复制到其他位置。 除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。
  
尝试在复制的邮件中保留所有邮件条目标识符。 您还应尝试保留条目标识符，但不是必需的。 
  
## <a name="notes-to-callers"></a>给调用方的说明

预计以下情况下会返回这些值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**CopyFolder** 已成功复制或移动每封邮件和子文件夹。  <br/> |S_OK  <br/> |
|**CopyFolder** 无法成功复制或移动每封邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**CopyFolder** 无法完成。  <br/> |任何错误值（MAPI_E_NOT_FOUND  <br/> |
   
当 **CopyFolder** 无法完成时，不要假定未完成任何工作。 **CopyFolder** 可能能够在遇到错误之前复制或移动一个或多个邮件和子文件夹。 
  
如果不存在的文件夹的条目标识符在  _lpEntryID_ 中传递， **则 CopyFolder** 将返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。 
  
根据邮件存储提供程序，原始邮件的条目标识符可能在复制的邮件中保留，也可能不保留。 应尽可能保留条目标识符，但这不是一项要求。 通常，您可以依赖以下方案：
  
- 在两种不同类型的邮件存储之间移动文件夹时，保证条目标识符会更改。
    
- 当您在同一类型的两个邮件存储之间移动文件夹时，条目标识符几乎始终会更改。
    
- 将文件夹移动到同一邮件存储中的另一个位置时，条目标识符可能会更改，也可能不变，具体取决于邮件存储提供程序。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnPasteFolder  <br/> |MFCMAPI 使用 **IMAPIFolder：：CopyFolder** 方法将文件夹从一个位置复制到另一个位置。 MFCMAPI 在复制操作期间记住源文件夹，并实际执行粘贴操作期间的副本。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

