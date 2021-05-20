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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428016"
---
# <a name="imapiformmgrresolvemultiplemessageclasses"></a>IMAPIFormMgr::ResolveMultipleMessageClasses

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一组邮件类解析为表单容器中的窗体，并返回这些表单的表单信息对象的数组。
  
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
  
> [in]指向包含要解析的邮件类的名称的数组的指针。
    
 _ulFlags_
  
> [in]控制邮件类解析方式的标志的位掩码。 可以设置以下标志：
    
MAPIFORM_EXACTMATCH 
  
> 仅应解析完全匹配的邮件类字符串。
    
MAPIFORM_LOCALONLY
  
> 不包括缓存的表单。
    
 _pFolderFocus_
  
> [in]指向包含正在解析其邮件类的窗体的文件夹的指针。 _pFolderFocus_ 参数可以是 NULL。 
    
 _ppfrminfoarray_
  
> [out]指向指向表单信息对象数组的指针的指针。 如果表单查看器在  _pMsgClasses_ 参数中传递 NULL，  _则 ppfrminfoarray_ 参数包含容器中所有表单的表单信息对象。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：ResolveMultipleMessageClasses** 方法，将一组邮件类解析为表单容器中的表单。 _ppfrminfoarray_ 中返回的表单信息对象数组提供对每个表单属性的进一步访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将一组邮件类解析为表单，表单查看器会传递要解析的邮件类名称数组。 若要强制使解析准确 (即当完全匹配的表单服务器不可用时，阻止解析到邮件类的基类) 可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
邮件类名称始终是 ANSI 字符串，从不为 Unicode。
  
如果无法将邮件类解析为窗体，将在窗体信息数组中为邮件类返回 NULL。 因此，即使此方法返回 S_OK，表单查看者也不应假定已成功解析所有邮件类。 相反，表单查看者应检查返回的数组中的值。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

