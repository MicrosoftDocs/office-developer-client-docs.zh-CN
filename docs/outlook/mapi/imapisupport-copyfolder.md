---
title: IMAPISupportCopyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CopyFolder
api_type:
- COM
ms.assetid: c2e0939f-0668-473f-856c-a27af094070b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 11ee944a14f8c9bd881b9c79a4ce66817275e73a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420883"
---
# <a name="imapisupportcopyfolder"></a>IMAPISupport::CopyFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将文件夹从当前父文件夹复制或移动到另一个父文件夹。
  
```cpp
HRESULT CopyFolder(
  LPCIID lpSrcInterface,
  LPVOID lpSrcFolder,
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

 _lpSrcInterface_
  
> [in]指向接口标识符 (IID) 表示用于访问要复制或移动的文件夹的父文件夹的接口。
    
 _lpSrcFolder_
  
> [in]指向要复制或移动的文件夹的父文件夹的指针。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 指向的条目标识符中的字节计数。
    
 _lpEntryID_
  
> [in]指向要复制或移动的文件夹的条目标识符的指针。 
    
 _lpInterface_
  
> [in]保留;必须为 NULL。
    
 _lpDestFolder_
  
> [in]指向用于接收要复制或移动的文件夹的文件夹的指针。
    
 _lpszNewFolderName_
  
> [in]指向复制或移动的文件夹的名称的指针;否则为 NULL，指示复制或移动的文件夹的名称应该与  _lpEntryID_ (指向的源文件夹同名) 。
    
 _ulUIParam_
  
> [in]进度指示器对话框和相关窗口的窗口句柄。 除非  _在 ulFlags_ 参数中设置了 FOLDER_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 FOLDER_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制复制或移动操作完成方式的标志的位掩码。 可以设置以下标志：
    
COPY_SUBFOLDERS 
  
> 应复制或移动文件夹的所有子文件夹。 当COPY_SUBFOLDERS复制操作时，仅复制  _由 lpEntryID_ 标识的文件夹。 使用移动操作时，COPY_SUBFOLDERS行为是默认行为，而不管是否已设置标志。 
    
FOLDER_DIALOG 
  
> 请求进度指示器的显示。
    
FOLDER_MOVE 
  
> 应移动文件夹而不是复制文件夹。 如果未FOLDER_MOVE，将复制该文件夹。
    
MAPI_UNICODE 
  
> 文件夹的名称采用 Unicode 格式。 如果未MAPI_UNICODE，文件夹的名称将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动文件夹。
    
MAPI_E_COLLISION 
  
> 要移动或复制的文件夹的名称与目标文件夹中子文件夹的名称相同。 邮件存储提供程序要求文件夹名称是唯一的。 该操作在未完成的情况下停止。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有条目都已成功复制。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISupport：：CopyFolder** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序可以在 **IMAPIFolder：：CopyFolder 的实现中调用 IMAPISupport：：CopyFolder，** 以将单个文件夹从一个父文件夹复制或移动到另一个父文件夹。 [](imapifolder-copyfolder.md) 
  
 **IMAPISupport：：CopyFolder** 将复制或移动的文件夹添加为目标文件夹的子文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPISupport：：CopyFolder** 允许同时重命名和移动文件夹，以及复制或移动受影响文件夹的子文件夹。 若要复制或移动所有嵌套在复制或移动的文件夹中的子文件夹，请传递  _ulFlags_ COPY_SUBFOLDERS标记。 
  
预计以下情况下返回值：
  
|**Condition**|**返回值**|
|:-----|:-----|
|**CopyFolder** 已成功复制或移动文件夹及其所有子文件夹（如果适用）。  <br/> |S_OK  <br/> |
|**CopyFolder** 无法成功复制或移动所有文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**CopyFolder** 无法完成。  <br/> |任何错误值  <br/> |
   
如果 **CopyFolder** 返回错误值，请不要继续假定未完成任何工作。 在 CopyFolder 遇到故障之前，可能复制 **或移动了** 一个或多个文件夹。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

