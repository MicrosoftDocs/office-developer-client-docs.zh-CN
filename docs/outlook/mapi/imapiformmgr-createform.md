---
title: IMAPIFormMgrCreateForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.CreateForm
api_type:
- COM
ms.assetid: 7d4d50f8-3904-4e93-a535-ac7decceb1a3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c6e18ee9f8ea1d7dc6592d576c5a1163db526639
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321663"
---
# <a name="imapiformmgrcreateform"></a>IMAPIFormMgr::CreateForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开一个窗体, 以根据窗体的邮件类创建新邮件。
  
```cpp
HRESULT CreateForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  IMAPIFormInfo pfrminfoToActivate,
  REFIID refiidToAsk,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时在打开表单时显示的进度指示器的父窗口的句柄。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _ulFlags_
  
> 实时用于控制表单打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示一个用户界面, 以提供状态或提示用户详细信息。 如果未设置此标志, 则不会显示任何用户界面。
    
 _pfrminfoToActivate_
  
> 实时指向表单信息对象的指针, 该对象用于打开表单。
    
 _refiidToAsk_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符将为所创建的 form 对象返回。 _refiidToAsk_参数不能为 NULL。 
    
 _ppvObj_
  
> 排除指向指向返回的接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_INTERFACE 
  
> 表单对象不支持所请求的接口。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: CreateForm**方法打开一个窗体, 以根据窗体的邮件类创建新邮件。 **CreateForm**通过为该窗体创建窗体服务器的一个实例来打开该窗体, 如给定的窗体信息对象中所述。 如果需要, **CreateForm**调用[IMAPIFormMgr::P repareform](imapiformmgr-prepareform.md)方法将表单服务器代码下载到用户磁盘。 
  
_pfrminfoToActivate_参数必须指向已正确解析的表单信息对象。 
  
打开窗体后, 调用表单查看器必须使用[IPersistMessage](ipersistmessageiunknown.md)接口设置邮件, 并且可以选择设置窗体的视图上下文。 有关详细信息, 请参阅[启动表单服务器](launching-a-form-server.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 使用**IMAPIFormMgr:: CreateForm**方法在显示窗体之前创建窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[启动表单服务器](launching-a-form-server.md)

