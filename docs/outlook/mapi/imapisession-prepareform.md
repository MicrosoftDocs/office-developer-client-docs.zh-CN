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
  
创建 [IMAPISession：：ShowForm](imapisession-showform.md) 方法用于访问消息的数字令牌。 
  
```cpp
HRESULT PrepareForm(
  LPCIID lpInterface,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMessageToken
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]一个指向接口标识符 (IID) 表示用于访问邮件的接口的 IID 标识符。 传递 **null** 会导致使用标准接口或 [IMessage。](imessageimapiprop.md) _lpInterface_ 参数必须为空 **或** IID_IMessage。 
    
 _lpMessage_
  
> [in]指向要显示在窗体中的消息的指针。
    
 _lpulMessageToken_
  
> [out]指向消息令牌的指针 **，IMAPISession：：ShowForm** 方法使用它访问  _lpMessage 指向的消息_。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单准备成功。
    
## <a name="remarks"></a>备注

**IMAPISession：:P repareForm** 方法为 _lpMessage_ 参数指向的消息创建消息令牌，并调用消息的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法。 此令牌在  _ulMessageToken_ 参数中传递到 **IMAPISession：：ShowForm**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 **对 PrepareForm** 的调用成功，在调用 **ShowForm** 之前，通过调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法释放 _lpMessage_ 指向的消息。 调用 **ShowForm** 之前释放消息失败可能会导致内存泄漏。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageModal  <br/> |MFCMAPI 使用 **IMAPISession：:P repareForm** 方法以及 **IMAPISession：：ShowForm** 在模式表单中显示消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::ShowForm](imapisession-showform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

