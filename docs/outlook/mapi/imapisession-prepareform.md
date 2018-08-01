---
title: IMAPISessionPrepareForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.PrepareForm
api_type:
- COM
ms.assetid: 98c0eab1-fd7e-46c3-8619-ccd6dc7cf8f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 026a120406b714a50a9191e4761021693a250b94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775565"
---
# <a name="imapisessionprepareform"></a>IMAPISession::PrepareForm

  
  
**适用于**： Outlook 
  
创建数值令牌[IMAPISession::ShowForm](imapisession-showform.md)方法用来访问的消息。 
  
```cpp
HRESULT PrepareForm(
  LPCIID lpInterface,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMessageToken
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问邮件的接口的指针。 传递**null**将导致标准界面或[IMessage](imessageimapiprop.md)，正在使用。 _LpInterface_参数必须为**null**或 IID_IMessage。 
    
 _lpMessage_
  
> [in]一个指向窗体中显示的消息。
    
 _lpulMessageToken_
  
> [输出]指向**IMAPISession::ShowForm**方法用于访问由_lpMessage_指向邮件消息令牌的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 窗体准备已成功。
    
## <a name="remarks"></a>说明

**IMAPISession::PrepareForm**方法创建邮件标记为_lpMessage_参数指向邮件，并调用消息的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法。 此标记_ulMessageToken_参数中传递给**IMAPISession::ShowForm**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**PrepareForm**调用成功，请通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法之前调用**ShowForm** _lpMessage_指向将邮件释放。 未能将邮件释放调用**ShowForm**之前可能会导致内存泄漏。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageModal  <br/> |MFCMAPI 使用**IMAPISession::PrepareForm**方法，以及**IMAPISession::ShowForm**，窗体模式中显示一条消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::ShowForm](imapisession-showform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

