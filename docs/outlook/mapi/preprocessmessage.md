---
title: PreprocessMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PreprocessMessage
api_type:
- COM
ms.assetid: dda50325-74b3-445e-986e-115f6536561f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a3982520cb1c745874a938962ece075a294b6257
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437243"
---
# <a name="preprocessmessage"></a>PreprocessMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个预处理邮件内容或邮件格式的函数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
|定义的函数实现方：  <br/> |传输提供程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI 后台处理程序  <br/> |
   
```cpp
HRESULT PreprocessMessage(
  LPVOID lpvSession,
  LPMESSAGE lpMessage,
  LPADRBOOK lpAdrBook,
  LPMAPIFOLDER lpFolder,
  LPALLOCATEBUFFER AllocateBuffer,
  LPALLOCATEMORE AllocateMore,
  LPFREEBUFFER FreeBuffer,
  ULONG FAR * lpcOutbound,
  LPMESSAGE FAR * FAR * lpppMessage,
  LPADRLIST FAR * lppRecipList
);
```

## <a name="parameters"></a>参数

 _lpvSession_
  
> [in]指向要使用的会话的指针。 
    
 _lpMessage_
  
> [in]指向要预处理的消息的指针。 
    
 _lpAdrBook_
  
> [in]指向用户应从中选择邮件收件人的通讯簿的指针。 
    
 _lpFolder_
  
> [in， out]指向文件夹的指针。 在输入时  _，lpFolder_ 参数指向包含要预处理的邮件的文件夹。 在输出时  _，lpFolder_ 指向放置预处理邮件的文件夹。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配所需的额外内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _lpcOutbound_
  
> [out]指向  _lpppMessage_ 参数指向的数组中的邮件数的指针。 
    
 _lpppMessage_
  
> [out]指向指向指针数组的指针的指针，指向预处理或以其他方式生成的消息。 
    
 _lppRecipList_
  
> [out]指向可选返回的 [ADRLIST](adrlist.md) 结构的指针，列出邮件无法送达的预处理器检测到的收件人。 有关此列表的内容详细信息，请参阅 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 邮件内容已成功预处理。
    
## <a name="remarks"></a>备注

传输提供程序邮件预处理器可以在邮件预处理期间显示进度指示器。 但是，它永远不应在消息预处理期间显示需要用户交互的对话框。 
  
当预处理器向出站邮件添加大量数据时，应执行某些过程。 此类消息可以存储在基于服务器的邮件存储中，从而导致预处理器访问远程存储，这是一个耗时的过程。 为了避免必须这样做，预处理器应具有一个选项，使预处理器能够将占用大量空间的数据存储在本地邮件存储中，并提供对邮件中该本地存储的引用。 
  
预处理器不应释放最初传递给基于 **PreprocessMessage** 的函数的任何对象。 
  
在 MAPI 后台处理程序可以调用 **PreprocessMessage** 函数之前，传输提供程序必须在 [对 IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md) 方法的调用中注册该函数。 调用 **PreprocessMessage** 函数后，后台处理程序无法继续提交邮件，直到函数返回。 
  
MAPI 后台处理程序拥有提交邮件的任务。 这意味着原始邮件永远不会放置在消息指针数组中，并且从不需要调用 **SubmitMessage** 方法。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

