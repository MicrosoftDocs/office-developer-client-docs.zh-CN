---
title: IMAPIFormMgrResolveMultipleMessageClasses
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.ResolveMultipleMessageClasses
api_type:
- COM
ms.assetid: d3cc6658-e46d-42dd-b1ac-65c88cfef8ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 515061c6c208008c4752e5ff2f23933a4c259c00
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321866"
---
# <a name="imapiformmgrresolvemultiplemessageclasses"></a>IMAPIFormMgr::ResolveMultipleMessageClasses

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一组消息类解析为表单容器中的表单, 并返回这些表单的表单信息对象的数组。
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClasses,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a>参数

 _pMsgClasses_
  
> 实时指向包含要解析的邮件类的名称的数组的指针。
    
 _ulFlags_
  
> 实时用于控制如何解析邮件类别的标志的位掩码。 可以设置以下标志:
    
MAPIFORM_EXACTMATCH 
  
> 应解析完全匹配的邮件类字符串。
    
MAPIFORM_LOCALONLY
  
> 不包含缓存的窗体。
    
 _pFolderFocus_
  
> 实时指向文件夹的指针, 该文件夹包含要解析其邮件类的窗体。 _pFolderFocus_参数可以为 NULL。 
    
 _ppfrminfoarray_
  
> 排除指向指向表单信息对象数组的指针的指针。 如果表单查看器在_pMsgClasses_参数中传递了 NULL, 则_ppfrminfoarray_参数将包含容器中所有表单的表单信息对象。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: ResolveMultipleMessageClasses**方法将一组邮件类解析为表单容器中的表单。 _ppfrminfoarray_中返回的表单信息对象的数组提供了对每个表单属性的进一步访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将一组邮件类解析为表单, 表单查看器将传入要解析的邮件类名称的数组。 若要强制解决方法是否完全 (即, 若要在完全匹配的窗体服务器不可用时防止解析为邮件类的基类), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。
  
如果无法将邮件类别解析为表单, 则在表单信息数组中返回该邮件类别的 NULL。 因此, 即使该方法返回 S_OK, 表单查看器也不应假设已成功解决所有邮件类。 相反, 表单查看器应检查返回的数组中的值。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

