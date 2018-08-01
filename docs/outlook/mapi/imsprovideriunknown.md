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
ms.openlocfilehash: 9444806347c97077b03922b116e2ed7f61665cc1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775923"
---
# <a name="imsprovider--iunknown"></a>IMSProvider : IUnknown

  
  
**适用于**： Outlook 
  
提供对通过消息存储提供程序对象的消息存储提供程序的访问。 此消息存储提供程序对象由消息存储提供程序的[MSProviderInit](msproviderinit.md)入口点函数返回在提供程序登录。 消息存储提供程序对象主要由客户端应用程序和 MAPI 后台处理程序用于打开消息存储库。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|由公开：  <br/> |消息存储提供程序对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |MAPI 和 MAPI 后台处理程序  <br/> |
|接口标识符：  <br/> |IID_IMSProvider  <br/> |
|指针类型：  <br/> |LPMSPROVIDER  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[关闭](imsprovider-shutdown.md) <br/> |关闭中有序的方式的消息存储提供程序。  <br/> |
|[登录](imsprovider-logon.md) <br/> |日志 MAPI 到消息存储提供程序的一个实例。  <br/> |
|[SpoolerLogon](imsprovider-spoolerlogon.md) <br/> |记录到的消息存储 MAPI 后台处理程序。  <br/> |
|[CompareStoreIDs](imsprovider-comparestoreids.md) <br/> |比较两个邮件存储条目标识符，以确定它们是否引用同一个 store 对象。  <br/> |
   
## <a name="remarks"></a>说明

MAPI 使用一个每个会话的消息存储提供程序对象，无论多少消息存储打开存储提供程序。 如果第二个 MAPI 会话登录到任何打开的存储，MAPI 调用**MSProviderInit**第二次创建该会话中使用新的消息存储提供程序对象。 
  
消息存储提供程序对象必须包含以下内容以正常运行：
  
- _LpMalloc_内存分配例行指针以供使用此提供商对象打开的所有存储区。 
    
- _LpfAllocateBuffer_、 _ lpfAllocateMore _ 和_lpfFreeBuffer_例行指针[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)内存分配功能。 
    
- 使用此提供商对象打开并且尚未关闭的所有存储的链接的列表。
    
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

