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
  
将文件夹从其当前父文件夹复制或移动到另一个父文件夹。
  
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
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问要复制或移动的文件夹的父文件夹的接口。
    
 _lpSrcFolder_
  
> 实时指向要复制或移动的文件夹的父文件夹的指针。 
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_指向的字节数。
    
 _lpEntryID_
  
> 实时指向要复制或移动的文件夹的条目标识符的指针。 
    
 _lpInterface_
  
> 实时保留必须为 NULL。
    
 _lpDestFolder_
  
> 实时指向接收要复制或移动的文件夹的文件夹的指针。
    
 _lpszNewFolderName_
  
> 实时指向已复制或已移动文件夹的名称的指针;否则为 NULL, 表示复制或移动的文件夹应具有与源文件夹相同的名称 (由_lpEntryID_指向的文件夹)。
    
 _ulUIParam_
  
> 实时进度指示器对话框和相关窗口的窗口句柄。 除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 FOLDER_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制如何完成复制或移动操作的标志的位掩码。 可以设置以下标志:
    
COPY_SUBFOLDERS 
  
> 应复制或移动文件夹的所有子文件夹。 如果没有为复制操作设置 COPY_SUBFOLDERS, 则仅复制由_lpEntryID_标识的文件夹。 通过移动操作, 无论是否设置了标志, COPY_SUBFOLDERS 行为都是默认行为。 
    
FOLDER_DIALOG 
  
> 请求显示进度指示器。
    
FOLDER_MOVE 
  
> 应移动而不是复制文件夹。 如果未设置 FOLDER_MOVE, 则复制文件夹。
    
MAPI_UNICODE 
  
> 该文件夹的名称采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则该文件夹的名称为 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动文件夹。
    
MAPI_E_COLLISION 
  
> 要移动或复制的文件夹的名称与目标文件夹中的子文件夹的名称相同。 邮件存储区提供程序要求文件夹名称是唯一的。 操作在未完成的情况下停止。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 呼叫成功, 但未成功复制所有条目。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

为邮件存储提供程序支持对象实现了**IMAPISupport:: CopyFolder**方法。 邮件存储提供程序可以在其[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)的实现中调用**IMAPISupport::** , 将单个文件夹从一个父文件夹复制或移动到另一个文件夹。 
  
 **IMAPISupport:: CopyFolder**将已复制或移动的文件夹添加为目标文件夹的子文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPISupport:: CopyFolder**允许同时重命名和移动文件夹以及受影响文件夹的子文件夹的复制或移动。 若要复制或移动嵌套在复制或移动的文件夹中的所有子文件夹, 请在_ulFlags_中传递 COPY_SUBFOLDERS 标志。 
  
在下列情况下, 预期以下返回值:
  
|**条件**|**返回值**|
|:-----|:-----|
|**CopyFolder**成功复制或移动文件夹及其所有子文件夹 (如果适用)。  <br/> |S_OK  <br/> |
|**CopyFolder**无法成功复制或移动所有文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**CopyFolder**无法完成。  <br/> |任何错误值  <br/> |
   
如果**CopyFolder**返回一个错误值, 请勿在假设尚未完成任何工作的情况下继续进行。 在**CopyFolder**遇到故障之前, 一个或多个文件夹可能已被复制或移动。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

