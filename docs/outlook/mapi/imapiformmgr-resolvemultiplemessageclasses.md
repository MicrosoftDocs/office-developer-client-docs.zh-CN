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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 968be38e794793405aac15340a92ccd6d680498d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571694"
---
# <a name="imapiformmgrresolvemultiplemessageclasses"></a>IMAPIFormMgr::ResolveMultipleMessageClasses

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将一组的邮件类解析为其的窗体中的窗体容器中，并返回这些表单的信息对象的窗体的数组。
  
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
  
> [in]一个指向数组，其中包含的邮件类来解析名称。
    
 _ulFlags_
  
> [in]位掩码的标志的控制解析的邮件类的方式。 可以设置以下标记：
    
MAPIFORM_EXACTMATCH 
  
> 应解决仅邮件类的字符串完全匹配。
    
MAPIFORM_LOCALONLY
  
> 不包括缓存窗体。
    
 _pFolderFocus_
  
> [in]一个指向包含正在解析其邮件类的窗体的文件夹。 _PFolderFocus_参数可以是 NULL。 
    
 _ppfrminfoarray_
  
> [输出]指向为数组表单信息对象的指针的指针。 如果表单查看器中_pMsgClasses_参数传递 NULL， _ppfrminfoarray_参数包含容器中的所有窗体的窗体信息对象。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormMgr::ResolveMultipleMessageClasses**方法解析为窗体容器内的窗体的邮件类的组。 窗体信息对象_ppfrminfoarray_中返回的数组进一步提供对每个窗体的属性的访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要解决窗体的邮件类的组，表单查看器将传递数组中的邮件类名称解析。 若要强制为完全的分辨率 （即，以防止解决方案时完全匹配的窗体的邮件类的基类服务器不可用） 可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
邮件类名称始终都是 ANSI 字符串，从不 Unicode。
  
如果邮件类无法解析到窗体，窗体信息数组中的邮件类将返回 NULL。 因此，即使该方法返回 S_OK，表单查看器应不工作假定已成功解析的所有邮件类。 相反，表单查看器应检查返回的数组中的值。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

