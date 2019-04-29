---
title: IMSProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider
api_type:
- COM
ms.assetid: 0f17aa44-abcb-4732-b013-d91652847cf6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5305ddd20b690f5c2e5807fb7ce2410549f7124
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412861"
---
# <a name="imsprovider--iunknown"></a>IMSProvider : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过邮件存储提供程序对象提供对邮件存储区提供程序的访问。 在提供程序登录时, 通过邮件存储提供程序的[MSProviderInit](msproviderinit.md)入口点函数返回此邮件存储区提供程序对象。 邮件存储提供程序对象主要用于客户端应用程序和 MAPI 后台处理程序, 以打开邮件存储区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |邮件存储提供程序对象  <br/> |
|实现者：  <br/> |邮件存储区提供程序  <br/> |
|调用者：  <br/> |mapi 和 mapi 后台处理程序  <br/> |
|接口标识符:  <br/> |IID_IMSProvider  <br/> |
|指针类型:  <br/> |LPMSPROVIDER  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[关闭](imsprovider-shutdown.md) <br/> |以有序的方式关闭邮件存储提供程序。  <br/> |
|[登录](imsprovider-logon.md) <br/> |将 MAPI 记录到邮件存储提供程序的一个实例上。  <br/> |
|[SpoolerLogon](imsprovider-spoolerlogon.md) <br/> |将 MAPI 后台处理程序记录到邮件存储区。  <br/> |
|[CompareStoreIDs](imsprovider-comparestoreids.md) <br/> |比较两个邮件存储区条目标识符, 以确定它们是否引用同一个存储对象。  <br/> |
   
## <a name="remarks"></a>说明

无论由存储提供程序打开多少个邮件存储区, MAPI 都会对每个会话使用一个邮件存储提供程序对象。 如果第二个 mapi 会话登录到任何打开的存储, 则 MAPI 会再次调用**MSProviderInit**以创建一个新的邮件存储提供程序对象, 以供该会话使用。 
  
若要正确运行, 邮件存储提供程序对象必须包含以下内容:
  
- 一个_lpMalloc_内存分配例程指针, 可供使用此 provider 对象打开的所有存储使用。 
    
- _lpfAllocateBuffer_、_ lpfAllocateMore _ 和_lpfFreeBuffer_例程指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)内存分配函数的指针。 
    
- 使用此提供程序对象打开且尚未关闭的所有存储的链接列表。
    
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

