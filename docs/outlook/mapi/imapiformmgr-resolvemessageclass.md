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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e99cff77fe872018722395c53c605e4d8fabfdde
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321607"
---
# <a name="imapiformmgrresolvemessageclass"></a>IMAPIFormMgr::ResolveMessageClass

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。
  
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
  
> 实时一个为要解析的邮件类别命名的字符串。
    
 _ulFlags_
  
> 实时用于控制如何解析邮件类别的标志的位掩码。 可以设置以下标志:
    
MAPIFORM_EXACTMATCH 
  
> 应解析完全匹配的邮件类字符串。
    
 _pFolderFocus_
  
> 实时指向包含正在解析的邮件的文件夹的指针。 _pFolderFocus_参数可以为 NULL。 
    
 _ppResult_
  
> 排除指向返回的表单信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NOT_FOUND 
  
> 在_szMsgClass_参数中传递的邮件类与表单库中任何表单的邮件类都不匹配。 
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: ResolveMessageClass**方法将邮件类别解析为表单容器中的表单。 _ppResult_参数中返回的 form 信息对象提供了对具有给定邮件类的表单的属性的进一步访问权限。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将邮件类别解析为表单, 表单查看器将传入要解析的邮件类的名称, 如 " `IPM.HelpDesk.Software`"。 若要强制解决完全相同 (即, 在完全匹配的窗体服务器不可用时, 阻止对邮件类的基类的解析), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 如果_pFolderFocus_参数为 NULL, 则邮件类解析过程不会搜索文件夹容器。 
  
搜索容器的顺序取决于表单库提供程序的实现。 默认表单库提供程序先搜索本地容器, 然后搜索传入文件夹的文件夹容器、个人表单容器, 最后搜索组织容器。
  
邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。
  
解析的邮件类的类标识符作为表单信息对象的一部分返回。 在表单查看器调用[IMAPIFormMgr::P repareform](imapiformmgr-prepareform.md)方法或[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)方法之前, 表单查看器不应假定在 OLE 库中存在类标识符。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)
  
[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

