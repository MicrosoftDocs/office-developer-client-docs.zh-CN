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
ms.openlocfilehash: 694f7ec5715a7348c9bd90c28d14f30d43d19974
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581781"
---
# <a name="imapifoldercreatefolder"></a>IMAPIFolder::CreateFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]若要创建的文件夹的类型。 可以设置以下标志：
    
FOLDER_GENERIC 
  
> 应创建一个通用的文件夹。
    
FOLDER_SEARCH 
  
> 应创建一个搜索结果文件夹。
    
 _lpszFolderName_
  
> [in]一个指向一个字符串，包含新的文件夹的名称。 此名称是新文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的基础。
    
 _lpszFolderComment_
  
> [in]一个指向一个字符串，包含与新的文件夹关联的注释。 此字符串将成为新文件夹的**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性的值。 如果传递 NULL，则文件夹具有没有初始的注释。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问新文件夹的接口的指针。 传递 NULL 将导致消息存储提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他呼叫者可以设置为 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 或 IID_IMAPIFolder _lpInterface_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何创建文件夹。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**CreateFolder**返回成功，原因可能是新文件夹之前调用客户端对完全可用。 如果新文件夹不可用，进行后续呼叫到它会导致出错。 
    
MAPI_UNICODE 
  
> Unicode 格式的文件夹的名称。 如果未设置 MAPI_UNICODE 标志，文件夹名称是 ANSI 格式。
    
OPEN_IF_EXISTS 
  
> 允许方法成功，即使已_lpszFolderName_参数中名为文件夹存在通过打开具有该名称的现有文件夹。 请注意，是否多个存在具有所提供的名称，允许同级文件夹具有相同名称的消息存储提供程序可能不打开现有文件夹。 
    
 _lppFolder_
  
> [输出]为指向新创建的文件夹的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建或打开，如果设置了 OPEN_IF_EXISTS 标志新文件夹。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_COLLISION 
  
> 存在具有已_lpszFolderName_参数中指定的名称的文件夹。 文件夹名称必须是唯一的。 
    
## <a name="remarks"></a>注解

**IMAPIFolder::CreateFolder**方法在当前文件夹中创建子文件夹，并将条目标识符分配给新文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**CreateFolder**返回时，都可以识别新文件夹的条目标识符可能不可用。 某些消息存储提供程序后，不要做出条目标识符可用直到以前呼叫过该新文件夹的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，若要永久保存它。 这是尤为如果您已设置 MAPI_DEFERRED_ERRORS 标志。 
  
请注意，某些消息存储提供程序始终指向_lppFolder_参数文件夹的标准接口，而不考虑为_lpInterface_参数中传递的值。 返回的接口指针可能不是您预期的类型，因为调用该新文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。 如有必要，进行其他呼叫之前强制转换该指针指向更适合的类型。
  
大多数消息存储提供程序需要是唯一的相对于其同级文件夹的名称的新文件夹的名称。 能够处理 MAPI_E_COLLISION 错误值，如果不遵循此规则，则返回的。 
  
若要确定新创建的文件夹的条目标识符，请调用新文件夹的**IMAPIProp::GetProps**方法来检索其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnCreateSubFolder  <br/> |MFCMAPI 使用**CMsgStoreDlg::OnCreateSubFolder**方法在 MFCMAPI 中创建新文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

