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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426392"
---
# <a name="imapiformmgrresolvemessageclass"></a>IMAPIFormMgr::ResolveMessageClass

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件类解析为窗体容器内的窗体，并返回该窗体的窗体信息对象。
  
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
  
> [in]一个字符串，用于命名要解析的邮件类。
    
 _ulFlags_
  
> [in]控制如何解析邮件类的标志的位掩码。 可以设置以下标志：
    
MAPIFORM_EXACTMATCH 
  
> 仅应解析完全匹配的邮件类字符串。
    
 _pFolderFocus_
  
> [in]指向包含要解析的邮件的文件夹的指针。 _pFolderFocus_ 参数可以是 NULL。 
    
 _ppResult_
  
> [out]指向返回的表单信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NOT_FOUND 
  
> _在 szMsgClass_ 参数中传递的邮件类与表单库中任何窗体的邮件类不匹配。 
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：ResolveMessageClass** 方法，将邮件类解析为表单容器中的表单。 _ppResult_ 参数中返回的表单信息对象提供对具有给定邮件类的表单属性的进一步访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将邮件类解析为窗体，窗体查看器会传递要解析的邮件类的名称，例如" `IPM.HelpDesk.Software` "。 若要强制使解析准确 (即当完全匹配的表单服务器不可用时，阻止解析到邮件类的基类) ，可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。 如果  _pFolderFocus_ 参数为 NULL，则邮件类解析过程不会搜索文件夹容器。 
  
搜索的容器的顺序取决于表单库提供程序的实现。 默认表单库提供程序首先搜索本地容器，然后搜索传入文件夹的文件夹容器、个人表单容器，最后搜索组织容器。
  
邮件类名称始终是 ANSI 字符串，从不为 Unicode。
  
已解析的邮件类的类标识符作为表单信息对象的一部分返回。 在表单查看器调用 [IMAPIFormMgr：:P repareForm](imapiformmgr-prepareform.md) 方法或 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 方法之前，表单查看器不应在 OLE 库中存在类标识符的假设下工作。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)
  
[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

