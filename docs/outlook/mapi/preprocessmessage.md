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
ms.openlocfilehash: 22562e1177c9a649bc66b25b5e8e9e6ecc8e397c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778556"
---
# <a name="preprocessmessage"></a>PreprocessMessage

  
  
**适用于**： Outlook 
  
定义预处理邮件内容或一条消息的格式的函数。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实施定义的函数：  <br/> |传输提供程序  <br/> |
|定义的函数调用：  <br/> |MAPI 后台处理程序  <br/> |
   
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
  
> [in]加入会话，从而使用指针。 
    
 _lpMessage_
  
> [in]指向预处理的消息的指针。 
    
 _lpAdrBook_
  
> [in]对通讯簿用户应从中选择的邮件收件人的指针。 
    
 _lpFolder_
  
> [传入、 传出]指向文件夹的指针。 在输入_lpFolder_参数指向包含邮件预处理的文件夹。 输出， _lpFolder_指向预处理的消息放置位置的文件夹。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存在需要时。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _lpcOutbound_
  
> [输出]指向_lpppMessage_参数指向该数组中的消息数。 
    
 _lpppMessage_
  
> [输出]为数组指向指针的指针预处理或否则生成的邮件。 
    
 _lppRecipList_
  
> [输出]为可选的指针返回[ADRLIST](adrlist.md)结构，列出其邮件是未送达的预处理器检测到的收件人。 此列表的内容的详细信息，请参阅[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 邮件内容已成功预处理。
    
## <a name="remarks"></a>说明

传输提供程序消息预处理器消息预处理期间可以演示的进度指示器。 但是，它应永远不会显示一个对话框，需要用户交互期间消息预处理。 
  
预处理器将大量数据添加到出站邮件时, 应遵循某些过程。 此类型的消息可以存储在基于服务器的邮件存储区，导致预处理器访问远程存储区，非常耗时的过程。 若要避免这样做，预处理器应具有该选项，使其以存储大量空间采用本地邮件存储区中的数据并提供对本地邮件中存储的引用。 
  
预处理器不应释放的任何最初传递给**PreprocessMessage**基于函数对象。 
  
MAPI 后台处理程序可以调用**PreprocessMessage**函数之前，必须具有传输提供程序注册[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法将调用的函数。 在调用**PreprocessMessage**函数，后台处理程序无法继续提交一条消息，直到此函数返回。 
  
MAPI 后台处理程序负责提交邮件的任务。 这意味着原始邮件永远不放置数组中的邮件指针而且**SubmitMessage**方法调用从来不是必需。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

