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
ms.openlocfilehash: db4b8d99c960deb3de3d228b2bf9549738501bcc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576279"
---
# <a name="imapiformcontainerresolvemessageclass"></a>IMAPIFormContainer::ResolveMessageClass

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
解析为其窗体的窗体容器中的邮件类，并返回该窗体的窗体信息对象。
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMessageClass,
  ULONG ulFlags,
  LPMAPIFORMINFO FAR * ppforminfo
);
```

## <a name="parameters"></a>参数

 _szMessageClass_
  
> [in]命名正在解析的邮件类的字符串。 邮件类名称始终都是 ANSI 字符串，从不 Unicode。
    
 _ulFlags_
  
> [in]位掩码的标志控制如何消息类已解决的。 可以设置以下标记：
    
MAPIFORM_EXACTMATCH 
  
> 应解决仅邮件类的字符串完全匹配。
    
 _ppforminfo_
  
> [输出]指向返回窗体信息对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NOT_FOUND 
  
> _SzMessageClass_参数中传递的邮件类不匹配窗体容器中的任何窗体的邮件类。 
    
## <a name="remarks"></a>注解

客户端应用程序调用**IMAPIFormContainer::ResolveMessageClass**方法解析为窗体容器内的窗体的邮件类。 返回_ppforminfo_参数中的窗体信息对象提供了进一步访问具有给定的邮件类的窗体的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要解决向窗体的邮件类，传递解析的邮件类的名称 (例如， `IPM.HelpDesk.Software`)。 强制为完全的分辨率 (即，以防止对的邮件类的基类的分辨率)，可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
解析的邮件类的类标识符返回窗体信息对象的一部分。 不要假设您调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)或[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)方法之后的类标识符存在之前 OLE 库中。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg::OnResolveMessageClass  <br/> |MFCMAPI 使用**IMAPIFormContainer::ResolveMessageClass**方法查找与邮件类关联的表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)
  
[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

