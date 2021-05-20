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
  
创建新的子文件夹。
  
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
  
> [in]要创建的文件夹的类型。 可以设置以下标志：
    
FOLDER_GENERIC 
  
> 应创建一个泛型文件夹。
    
FOLDER_SEARCH 
  
> 应创建搜索结果文件夹。
    
 _lpszFolderName_
  
> [in]指向包含新文件夹名称的字符串的指针。 此名称是新文件夹PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的基础。 
    
 _lpszFolderComment_
  
> [in]指向包含与新文件夹关联的注释的字符串的指针。 此字符串将成为[PidTagComment](pidtagcomment-canonical-property.md) PR_COMMENT (新) 的值。  如果传递 NULL，则文件夹没有初始注释。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问新文件夹的接口。 传递 NULL 会导致邮件存储提供程序返回标准文件夹接口 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他调用方可以将  _lpInterface_ 参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。 
    
 _ulFlags_
  
> [in]控制如何创建文件夹的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **CreateFolder** 成功返回，可能在新文件夹对调用客户端完全可用之前。 如果新文件夹不可用，则后续调用它会导致错误。 
    
MAPI_UNICODE 
  
> 文件夹的名称采用 Unicode 格式。 如果未MAPI_UNICODE，文件夹名称将采用 ANSI 格式。
    
OPEN_IF_EXISTS 
  
> 通过打开具有该名称的现有文件夹，即使  _lpszFolderName_ 参数中指定的文件夹已存在，也允许该方法成功。 请注意，如果具有提供的名称存在多个现有文件夹，则允许同级文件夹具有相同的名称的邮件存储提供程序可能无法打开现有文件夹。 
    
 _lppFolder_
  
> [out]指向指向新建文件夹的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 如果设置了新文件夹标志，则已成功创建或打开OPEN_IF_EXISTS文件夹。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_COLLISION 
  
> _lpszFolderName_ 参数中提供的名称的文件夹已存在。 文件夹名称必须是唯一的。 
    
## <a name="remarks"></a>备注

**IMAPIFolder：：CreateFolder** 方法在当前文件夹中创建子文件夹，并将条目标识符分配给新文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当 **CreateFolder** 返回时，请注意新文件夹的条目标识符可能不可用。 一些邮件存储提供程序在调用新文件夹的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法以永久保存它之前，不会提供条目标识符。 如果已设置值标志，MAPI_DEFERRED_ERRORS尤其如此。 
  
请注意，某些邮件存储提供程序始终将  _lppFolder_ 参数指向文件夹的标准接口，而不考虑为  _lpInterface_ 参数传递的值。 由于返回的接口指针可能不是您预期的类型，因此请调用新文件夹的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。 如有必要，在进行其他调用之前，将指针强制转换到更合适的类型。
  
大多数邮件存储提供程序都要求新文件夹的名称对于同级文件夹的名称是唯一的。 能够处理错误MAPI_E_COLLISION，如果未遵循此规则，则返回该错误值。 
  
若要确定新创建的文件夹的条目标识符，请调用新文件夹的 **IMAPIProp：：GetProps** 方法来检索其 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnCreateSubFolder  <br/> |MFCMAPI 使用 **CMsgStoreDlg：：OnCreateSubFolder** 方法在 MFCMAPI 中创建新文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

