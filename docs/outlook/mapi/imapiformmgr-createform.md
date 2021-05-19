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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419847"
---
# <a name="imapiformmgrcreateform"></a>IMAPIFormMgr::CreateForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开窗体以基于窗体的邮件类创建新邮件。
  
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
  
> [in]打开窗体时显示的进度指示器的父窗口句柄。 除非  _在 ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _ulFlags_
  
> [in]控制表单打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示用户界面以提供状态或提示用户输入详细信息。 如果未设置此标志，则不显示用户界面。
    
 _pfrminfoToActivate_
  
> [in]指向用于打开窗体的窗体信息对象的指针。
    
 _refiidToAsk_
  
> [in]指向接口标识符的 (IID) ，用于为创建的表单对象返回接口。 _refiidToAsk_ 参数不能为 NULL。 
    
 _ppvObj_
  
> [out]指向返回接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_INTERFACE 
  
> 请求的接口不受 form 对象支持。
    
## <a name="remarks"></a>备注

表单查看者调用 **IMAPIFormMgr：：CreateForm** 方法以打开表单以基于表单的邮件类创建新邮件。 **CreateForm** 通过创建该窗体的窗体服务器实例来打开该窗体，如给定窗体信息对象中所述。 如果需要 **，CreateForm** 将调用 [IMAPIFormMgr：:P repareForm](imapiformmgr-prepareform.md) 方法将表单服务器代码下载到用户的磁盘。 
  
_pfrminfoToActivate_ 参数必须指向已正确解析的表单信息对象。 
  
打开表单后，调用表单查看器必须使用 [IPersistMessage](ipersistmessageiunknown.md) 接口设置邮件，并且可以选择为表单设置视图上下文。 有关详细信息，请参阅 [启动窗体服务器](launching-a-form-server.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：CreateForm** 方法在显示表单之前创建表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[启动表单服务器](launching-a-form-server.md)

