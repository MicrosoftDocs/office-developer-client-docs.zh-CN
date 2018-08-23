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
ms.openlocfilehash: e86c3d9678739c09024c0655cbbbb702749a53f0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586163"
---
# <a name="imapiformmgrcreateform"></a>IMAPIFormMgr::CreateForm

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开一个窗体创建新邮件基于窗体的邮件类别。
  
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
  
> [in]打开表单时显示进度指示器的父窗口句柄。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开表单。 可以设置以下标记：
    
MAPI_DIALOG 
  
> 显示用户界面，以提供状态或提示用户输入的详细信息。 如果未设置此标志，将显示没有用户界面。
    
 _pfrminfoToActivate_
  
> [in]指向用于打开窗体的窗体信息对象的指针。
    
 _refiidToAsk_
  
> [in]指向要为已创建的窗体对象返回的接口的界面标识符 (IID) 的指针。 _RefiidToAsk_参数不能为 NULL。 
    
 _ppvObj_
  
> [输出]指向返回的接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_INTERFACE 
  
> 通过 form 对象不支持所请求的接口。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormMgr::CreateForm**方法打开要创建新邮件窗体的邮件类所基于的表单。 **CreateForm**通过给定窗体信息对象中所述创建该窗体的窗体服务器实例中打开该窗体。 如果需要， **CreateForm**调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)方法下载到用户的磁盘的窗体服务器代码。 
  
_PfrminfoToActivate_参数必须指向窗体信息对象中已正确解析。 
  
在打开窗体后，调用表单查看器必须设置使用[IPersistMessage](ipersistmessageiunknown.md)界面的一条消息，并且可以根据需要设置表单视图上下文。 有关详细信息，请参阅[启动窗体服务器](launching-a-form-server.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 使用**IMAPIFormMgr::CreateForm**方法显示之前创建的表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[启动表单服务器](launching-a-form-server.md)

