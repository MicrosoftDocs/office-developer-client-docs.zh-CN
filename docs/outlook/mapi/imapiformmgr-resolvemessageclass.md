---
title: IMAPIFormMgrResolveMessageClass
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.ResolveMessageClass
api_type:
- COM
ms.assetid: c2af7516-3a97-4422-874d-b1e3a0d4f316
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a84698ccc132c750cbd071c05160117c40e352a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775456"
---
# <a name="imapiformmgrresolvemessageclass"></a>IMAPIFormMgr::ResolveMessageClass

  
  
**适用于**： Outlook 
  
将邮件类解析为其表单中的窗体容器中，并返回该窗体的窗体信息对象。
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMsgClass,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPMAPIFORMINFO FAR * ppResult
);
```

## <a name="parameters"></a>参数

 _szMsgClass_
  
> [in]命名正在解析的邮件类的字符串。
    
 _ulFlags_
  
> [in]位掩码的标志控制如何消息类已解决的。 可以设置以下标记：
    
MAPIFORM_EXACTMATCH 
  
> 应解决仅邮件类的字符串完全匹配。
    
 _pFolderFocus_
  
> [in]一个指向的文件夹，包含要解析的消息。 _PFolderFocus_参数可以是 NULL。 
    
 _ppResult_
  
> [输出]指向返回窗体信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NOT_FOUND 
  
> _SzMsgClass_参数中传递的邮件类不匹配的邮件类的窗体库中的任何表单。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::ResolveMessageClass**方法解析为其表单窗体容器内的邮件类。 返回_ppResult_参数中的窗体信息对象提供了进一步访问具有给定的邮件类的窗体的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要解决向窗体的邮件类，表单查看器，将传递名称解析，如的邮件类" `IPM.HelpDesk.Software`"。 若要强制为完全的分辨率 （即，以防止解决方案时完全匹配的窗体的邮件类的基类服务器不可用），可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 如果_pFolderFocus_参数为 NULL，则邮件类解析过程不搜索的文件夹的容器。 
  
搜索的容器的顺序取决于窗体库提供程序的实现。 默认窗体库提供程序先搜索本地的容器，然后为传入的文件夹，个人窗体容器和组织容器，最后，文件夹容器。
  
邮件类名称始终都是 ANSI 字符串，从不 Unicode。
  
解析的邮件类的类标识符返回窗体信息对象的一部分。 假定 OLE 库之前中存在的类标识符的表单查看器具有调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)方法或[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)方法后，表单查看器应不起作用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)
  
[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

