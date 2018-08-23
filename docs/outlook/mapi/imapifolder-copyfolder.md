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
ms.openlocfilehash: 134a492dbc86dd0ce6b3795d5ae40b334c14d468
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585148"
---
# <a name="imapifoldercopyfolder"></a>IMAPIFolder::CopyFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
复制或移动的子文件夹。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要复制或移动的子文件夹的项标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestFolder_参数指向的文件夹的接口的指针。 传递 NULL 将导致服务提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 _LpInterface_的有效值包括 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 和 IID_IMAPIFolder。 
    
 _lpDestFolder_
  
> [in]打开接收的复制或移动的子文件夹的文件夹指向的指针。
    
 _lpszNewFolderName_
  
> [in]一个指向其新的目标中复制或移动的文件夹的名称。 如果_lpszNewFolderName_设置为 NULL，则源子文件夹名称用于目标文件夹的名称。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 除非设置了 FOLDER_DIALOG 标志_ulFlags_参数中的，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，用于控制复制或移动操作。 可以设置以下标志：
    
COPY_SUBFOLDERS 
  
> 所有要复制的子文件夹中的子文件夹也应复制。 当 COPY_SUBFOLDERS 未设置的复制操作时，将复制仅由_lpEntryID_标识的子文件夹。 移动操作，COPY_SUBFOLDERS 行为是默认的无论是否设置了标志。 
    
FOLDER_DIALOG 
  
> 请求进度指示器的显示。
    
FOLDER_MOVE 
  
> Subfolder 是要移动而不是复制。 如果未设置 FOLDER_MOVE，复制的子文件夹。
    
MAPI_DECLINE_OK 
  
> 通知的消息存储提供程序，它通过调用其支持对象[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)或[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法实现**CopyFolder** ，如果**CopyFolder**应改为立即返回 MAPI_E_DECLINE_COPY。 
    
MAPI_UNICODE 
  
> 目标文件夹的名称为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，文件夹名称是 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动指定的文件夹。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志消息存储提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和消息存储提供程序支持仅 Unicode。
    
MAPI_E_COLLISION 
  
> 正在移动或复制的文件夹的名称为相同的目标文件夹中的子文件夹。 消息存储提供程序需要唯一文件夹名称。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序实现此方法通过调用支持对象方法，并且将呼叫者已传递 MAPI_DECLINE_OK 标志。
    
MAPI_E_FOLDER_CYCLE 
  
> 源文件夹直接或间接包含目标文件夹。 重要工作可能已执行之前已发现这种情况，因此可能部分修改源和目标文件夹。 
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有的项目复制成功。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPIFolder::CopyFolder**方法复制，或将子文件夹从一个位置移至另一个。 正在复制或移动的子文件夹为子文件夹添加到目标文件夹中。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

当复制或移动操作通过设置 COPY_SUBFOLDERS 标志指示涉及多个文件夹时，每个文件夹尽可能完整执行操作。 有时之一要移动或复制的文件夹不存在或已移动或复制到其他位置。 不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。
  
尝试保留复制邮件中的所有邮件项标识符。 您还应尝试保留项标识符，但它并不需要。 
  
## <a name="notes-to-callers"></a>给调用方的说明

希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**CopyFolder**成功复制或移动的每个邮件和子文件夹。  <br/> |S_OK  <br/> |
|**CopyFolder**程序无法成功复制或移动的每个邮件和子文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND  <br/> |
|**CopyFolder**无法完成。  <br/> |除 MAPI_E_NOT_FOUND 任何错误值  <br/> |
   
**CopyFolder**无法完成后，请假定已完成任何工时。 **CopyFolder**可能已经能够复制或移动遇到错误之前的一个或多个邮件和子文件夹。 
  
_LpEntryID_中传递的文件夹不存在的项标识符，如果**CopyFolder**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。 
  
消息存储提供程序，根据原始邮件的项标识符可能或可能不会保留复制邮件中。 您应保留项标识符，只要有可能，但它并不要求。 您通常取决于以下方案：
  
- 消息存储的两种不同类型之间移动文件夹时，项标识符保证更改。
    
- 属于同一字段类型的两个邮件存储之间移动文件夹时，始终更改的项标识符。
    
- 当将文件夹移到另一位置相同的邮件存储区中时，条目标识符可能或可能不更改，具体取决于消息存储提供程序。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnPasteFolder  <br/> |MFCMAPI 使用**IMAPIFolder::CopyFolder**方法将文件夹从一个位置复制到另一个。 MFCMAPI 复制操作期间记住源文件夹，并在粘贴操作过程中实际执行该副本。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

