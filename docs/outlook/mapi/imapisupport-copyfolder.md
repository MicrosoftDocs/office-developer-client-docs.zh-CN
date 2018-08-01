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
ms.openlocfilehash: 0b079b311a68459a43b0a7659ddfbe94d96d7f9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775590"
---
# <a name="imapisupportcopyfolder"></a>IMAPISupport::CopyFolder

  
  
**适用于**： Outlook 
  
复制或移动到另一个父文件夹的从其当前的父文件夹的文件夹。
  
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
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问复制或移动的文件夹的父文件夹的接口的指针。
    
 _lpSrcFolder_
  
> [in]指向要复制或移动的文件夹的父文件夹的指针。 
    
 _cbEntryID_
  
> [in]由_lpEntryID_指向该条目标识符中字节数。
    
 _lpEntryID_
  
> [in]指向要复制或移动的文件夹的项标识符的指针。 
    
 _lpInterface_
  
> [in]保留;必须为 NULL。
    
 _lpDestFolder_
  
> [in]指向接收复制或移动的文件夹的文件夹的指针。
    
 _lpszNewFolderName_
  
> [in]一个指向复制或移动的文件夹; 的名称否则，为 NULL，表示复制或移动文件夹应与源文件夹 （由_lpEntryID_指向的文件夹） 中具有相同的名称。
    
 _ulUIParam_
  
> [in]的进度指示器对话框中窗口和相关的窗口的句柄。 除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何完成复制或移动操作。 可以设置以下标志：
    
COPY_SUBFOLDERS 
  
> 应复制或移动所有文件夹的子文件夹。 当 COPY_SUBFOLDERS 未设置的复制操作时，将复制仅由_lpEntryID_标识的文件夹。 移动操作，COPY_SUBFOLDERS 行为是默认的无论是否设置了标志。 
    
FOLDER_DIALOG 
  
> 请求进度指示器的显示。
    
FOLDER_MOVE 
  
> 应移动文件夹而不是复制。 如果未设置 FOLDER_MOVE，复制该文件夹。
    
MAPI_UNICODE 
  
> Unicode 格式的文件夹的名称。 如果未设置 MAPI_UNICODE 标志，文件夹的名称是 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动的文件夹。
    
MAPI_E_COLLISION 
  
> 正在移动或复制的文件夹的名称为相同的目标文件夹中的子文件夹。 消息存储提供程序需要唯一文件夹名称。 操作停止不完成。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有的项目复制成功。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

消息存储提供程序支持对象的实现**IMAPISupport::CopyFolder**方法。 消息存储提供程序可以调用**IMAPISupport::CopyFolder**其实现[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)复制或移动到另一个父文件夹中的单个文件夹中。 
  
 **IMAPISupport::CopyFolder**将复制或移动文件夹添加为目标文件夹的子文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **IMAPISupport::CopyFolder**允许同时重命名或移动的文件夹和复制或移动的受影响的文件夹的子文件夹。 若要复制或移动嵌套在复制或移动的文件夹中的所有子文件夹，请在_ulFlags_传递 COPY_SUBFOLDERS 标志。 
  
预期以下返回值在下列情况下：
  
|**条件**|**返回值**|
|:-----|:-----|
|**CopyFolder**成功复制或移动的文件夹和所有子文件夹，如果适用。  <br/> |S_OK  <br/> |
|**CopyFolder**程序无法成功复制或移动的所有文件夹。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**CopyFolder**无法完成。  <br/> |任何错误值  <br/> |
   
**CopyFolder**返回错误值，如果不继续执行假设不完成了任何工作中。 一个或多个文件夹可能已复制或移动之前**CopyFolder**遇到故障。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

