---
title: IMAPIFormContainerResolveMessageClass
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.ResolveMessageClass
api_type:
- COM
ms.assetid: 9ce13f11-5787-4ea5-a84f-b1e3824529ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c0954d6f8b14b4088ece2ac276b045b6c163ed98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408549"
---
# <a name="imapiformcontainerresolvemessageclass"></a>IMAPIFormContainer::ResolveMessageClass

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMessageClass,
  ULONG ulFlags,
  LPMAPIFORMINFO FAR * ppforminfo
);
```

## <a name="parameters"></a>参数

 _szMessageClass_
  
> 实时一个为要解析的邮件类别命名的字符串。 邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。
    
 _ulFlags_
  
> 实时用于控制如何解析邮件类别的标志的位掩码。 可以设置以下标志:
    
MAPIFORM_EXACTMATCH 
  
> 应解析完全匹配的邮件类字符串。
    
 _ppforminfo_
  
> 排除指向指向返回的表单信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NOT_FOUND 
  
> 在_szMessageClass_参数中传递的邮件类与表单容器中任何表单的邮件类都不匹配。 
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormContainer:: ResolveMessageClass**方法将邮件类别解析为表单容器内的窗体。 _ppforminfo_参数中返回的 form 信息对象提供了对具有给定邮件类的表单属性的进一步访问权限。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将邮件类别解析为表单, 请传入要解析的邮件类的名称 (例如, `IPM.HelpDesk.Software`)。 若要强制解决是精确的 (即, 若要防止解析邮件类的基类), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
解析的邮件类的类标识符作为表单信息对象的一部分返回。 在调用[IMAPIFormMgr::P repareform](imapiformmgr-prepareform.md)或[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)方法之后, 不要假定该类标识符存在于 OLE 库中。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg  <br/> |CFormContainerDlg:: OnResolveMessageClass  <br/> |MFCMAPI 使用**IMAPIFormContainer:: ResolveMessageClass**方法来查找与邮件类关联的窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)
  
[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

