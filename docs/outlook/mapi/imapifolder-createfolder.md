---
title: IMAPIFolderCreateFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CreateFolder
api_type:
- COM
ms.assetid: 39d07fc8-09aa-4122-af32-b02f2c893d29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 606d780aa59e363c30ddc7a5b562db64d845ccb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436760"
---
# <a name="imapifoldercreatefolder"></a>IMAPIFolder::CreateFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个新的子文件夹。
  
```cpp
HRESULT CreateFolder(
  ULONG ulFolderType,
  LPSTR lpszFolderName,
  LPSTR lpszFolderComment,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMAPIFOLDER FAR * lppFolder
);
```

## <a name="parameters"></a>参数

 _ulFolderType_
  
> 实时要创建的文件夹的类型。 可以设置以下标志:
    
FOLDER_GENERIC 
  
> 应创建一个常规文件夹。
    
FOLDER_SEARCH 
  
> 应创建搜索结果文件夹。
    
 _lpszFolderName_
  
> 实时指向包含新文件夹名称的字符串的指针。 此名称是新文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的基础。
    
 _lpszFolderComment_
  
> 实时指向包含与新文件夹相关联的注释的字符串的指针。 此字符串将成为新文件夹的**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性的值。 如果传递了 NULL, 则文件夹没有初始注释。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问新文件夹的接口。 传递 NULL 将导致邮件存储提供程序返回标准文件夹接口[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他调用方可以将_lpInterface_参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。 
    
 _ulFlags_
  
> 实时用于控制文件夹创建方式的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 允许**CreateFolder**成功返回, 可能在新文件夹完全提供给呼叫客户端之前。 如果新文件夹不可用, 则对其进行后续调用可能会导致出错。 
    
MAPI_UNICODE 
  
> 该文件夹的名称采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则该文件夹名称为 ANSI 格式。
    
OPEN_IF_EXISTS 
  
> 通过打开具有该名称的现有文件夹, 允许该方法成功, 即使在_lpszFolderName_参数中指定的文件夹已经存在。 请注意, 如果存在多个具有所提供名称的现有文件夹, 则允许同级文件夹具有相同名称的邮件存储提供程序可能无法打开现有文件夹。 
    
 _lppFolder_
  
> 排除指向新创建的文件夹的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 如果设置了 OPEN_IF_EXISTS 标志, 则已成功创建或打开新文件夹。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_COLLISION 
  
> 具有_lpszFolderName_参数中给定名称的文件夹已存在。 文件夹名称必须是唯一的。 
    
## <a name="remarks"></a>说明

**IMAPIFolder:: CreateFolder**方法在当前文件夹中创建一个子文件夹, 并将条目标识符分配给新文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**CreateFolder**返回时, 请注意新文件夹的条目标识符可能不可用。 在您调用了新文件夹的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以永久保存它之前, 某些邮件存储提供程序不会使条目标识符可用。 如果您已设置 MAPI_DEFERRED_ERRORS 标志, 则更是如此。 
  
请注意, 某些邮件存储提供程序始终将_lppFolder_参数指向文件夹的标准接口, 而不考虑您传递给_lpInterface_参数的值。 由于返回的接口指针可能不是您所需的类型, 因此请调用新文件夹的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。 如有必要, 请在进行其他调用之前, 将指针转换为更合适的类型。
  
大多数邮件存储提供程序要求新文件夹的名称相对于其同辈文件夹的名称是唯一的。 能够处理 MAPI_E_COLLISION 错误值, 如果未遵循此规则, 将返回此值。 
  
若要确定新创建的文件夹的条目标识符, 请调用新文件夹的**IMAPIProp:: GetProps**方法以检索其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg  <br/> |CMsgStoreDlg:: OnCreateSubFolder  <br/> |MFCMAPI 使用**CMsgStoreDlg:: OnCreateSubFolder**方法在 MFCMAPI 中创建新文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

