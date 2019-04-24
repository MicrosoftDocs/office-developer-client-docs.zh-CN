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
ms.openlocfilehash: 3d8b1901123743b25b5bb9df174b297398c953b8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335760"
---
# <a name="imapisessionprepareform"></a>IMAPISession::PrepareForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建[IMAPISession:: ShowForm](imapisession-showform.md)方法用于访问邮件的数字标记。 
  
```cpp
HRESULT PrepareForm(
  LPCIID lpInterface,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMessageToken
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问邮件的接口。 在使用的标准接口或[IMessage](imessageimapiprop.md)中传递**null**结果。 _lpInterface_参数必须为**null**或 IID_IMessage。 
    
 _lpMessage_
  
> 实时指向要在表单中显示的邮件的指针。
    
 _lpulMessageToken_
  
> 排除指向邮件令牌的指针, **IMAPISession:: ShowForm**方法使用该指针访问_lpMessage_指向的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单准备成功。
    
## <a name="remarks"></a>注解

**IMAPISession::P repareform**方法为_lpMessage_参数所指向的邮件创建一个邮件令牌, 并调用邮件的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法。 此令牌在_ulMessageToken_参数中传递到**IMAPISession:: ShowForm**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果对**PrepareForm**的调用成功, 请通过在调用**ShowForm**之前调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来释放_lpMessage_所指向的消息。 调用**ShowForm**之前无法释放邮件可能会导致内存泄漏。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |OpenMessageModal  <br/> |MFCMAPI 使用**IMAPISession::P repareform**方法以及**IMAPISession:: ShowForm**在模式窗体中显示消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::ShowForm](imapisession-showform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

