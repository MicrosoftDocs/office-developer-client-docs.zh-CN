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
  
定义预处理邮件内容或邮件格式的函数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|定义的函数实现者:  <br/> |传输提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI 后台处理程序  <br/> |
   
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
  
> 实时指向要使用的会话的指针。 
    
 _lpMessage_
  
> 实时指向要进行预处理的邮件的指针。 
    
 _lpAdrBook_
  
> 实时指向用户应从中选择邮件收件人的通讯簿的指针。 
    
 _lpFolder_
  
> [in, out]指向文件夹的指针。 在输入时, _lpFolder_参数指向包含要进行预处理的邮件的文件夹。 在输出时, _lpFolder_指向已放置预处理邮件的文件夹。 
    
 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 用于在需要时分配更多内存。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _lpcOutbound_
  
> 排除一个指针, 指向由_lpppMessage_参数指向的数组中的邮件数。 
    
 _lpppMessage_
  
> 排除指向指向经过预处理或以其他方式生成的邮件的指针数组的指针。 
    
 _lppRecipList_
  
> 排除指向可选的返回[ADRLIST](adrlist.md)结构的指针, 其中列出了预处理器检测到的无法传递邮件的收件人。 有关此列表内容的详细信息, 请参阅[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 邮件内容已成功预处理。
    
## <a name="remarks"></a>说明

传输提供程序消息预处理器可在邮件预处理过程中显示进度指示器。 但是, 它决不应显示在邮件预处理过程中需要用户交互的对话框。 
  
当预处理器向出站邮件中添加大量数据时, 应遵循某些过程。 这种类型的邮件可以存储在基于服务器的邮件存储中, 从而导致预处理器访问远程存储, 这是一种耗时的过程。 若要避免这种情况, 预处理器应具有一个选项, 使其能够存储在本地邮件存储区中占用大量空间的数据, 并在邮件中提供对该本地存储区的引用。 
  
预处理器不应释放最初传递到基于**PreprocessMessage**的函数的任何对象。 
  
在 MAPI 后台处理程序可以调用**PreprocessMessage**函数之前, 传输提供程序必须已在对[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法的调用中注册了函数。 调用**PreprocessMessage**函数后, 后台打印程序将无法继续提交邮件, 直到函数返回为止。 
  
MAPI 后台处理程序拥有提交邮件的任务。 这意味着原始邮件从不放置在邮件指针的数组中, 并且从不需要对**SubmitMessage**方法的调用。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

