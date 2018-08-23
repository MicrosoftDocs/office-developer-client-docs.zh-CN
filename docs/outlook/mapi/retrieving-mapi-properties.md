---
title: 检索 MAPI 属性
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd3f9f59-9020-46e6-9560-86a7a0eeca20
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 1404239a54f9b8991099a66831e3364d9a683d1d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566332"
---
# <a name="retrieving-mapi-properties"></a>检索 MAPI 属性

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当客户端或服务提供程序检索的对象的属性时，该对象可提供，该属性的值、 类型和标识符。 
  
客户端和服务提供商可以检索对象的属性，通过调用下列选项之一：
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[HrGetOneProp](hrgetoneprop.md)
  
**GetProps**方法用于检索一个或多个不需要专门或备用界面进行访问的属性。 这意味着提供**GetProps**属性也小，如整数和布尔值。 
  
 **若要检索多个属性**
  
1. 分配[SPropTagArray](sproptagarray.md)结构足以容纳要检索的属性的数目。 
    
2. 设置为属性可检索和如果可能，之一的目标属性设置为标识符和类型，每个**aulPropTag**成员数量**cValues** **SPropTagArray**结构的成员。 如果类型是未知，则将其设置为 PT_UNSPECIFIED。 如果类型和标识符是未知，通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)查找此信息。 **GetPropList**返回所有对象的支持属性的属性标记数组。 如果只有属性名称，则调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)访问关联的标识符。 
    
3. 调用[IMAPIProp::GetProps](imapiprop-getprops.md)打开或多个属性。 
    
**OpenProperty**方法用于打开较大访问需要如**IStream**或[IMAPITable](imapitableiunknown.md)备用接口的属性。 **OpenProperty**通常用于将打开大型字符串、 二进制、 和对象的属性和一次只能打开一个属性。 呼叫者传入的其他接口所需的输入参数之一的标识符。 
  
一些**OpenProperty**的常见用途包括打开**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))，包含**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 的属性包含基于文本的邮件正文的属性OLE 对象或邮件附件，并**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))，包含文件夹或通讯簿容器内容表的属性。 
  
具体取决于该属性，从**OpenProperty**请求时使用不同的接口。 **IStream**，一个接口，允许属性数据读取和写入的字节流的形式通常用于访问**PR_BODY**。 [IMessage](imessageimapiprop.md)或**IStream**可用于访问**PR_ATTACH_DATA_OBJ**。 嵌入的邮件附件的标准的邮件使用**IMessage**而 TNEF 格式中的邮件使用**IStream**。 由于**PR_CONTAINER_CONTENTS** table 对象，它是使用[IMAPITable](imapitableiunknown.md)进行访问。
  
 **若要检索的附件 PR_ATTACH_DATA_BIN 属性**
  
1. 调用[OpenStreamOnFile](openstreamonfile.md)函数打开的文件流。 
    
2. 调用消息的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法来检索**IStream**接口的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。 设置的 MAPI_MODIFY 和 MAPI_CREATE 标志。 
    
3. 分配**STATSTG**结构并将其传递中调用的文件流**IStream::Stat**方法以确定其大小。 另一种方法确定流大小是与标志 STREAM_SEEK_END 调用**IStream::Seek** 。 
    
4. 调用的流**IStream::CopyTo**方法将数据从该文件流复制到附件流。 
    
5. 完成复制操作后，通过调用其**IUnknown::Release**方法释放两个流。 
    
当**IStream**用于属性访问时，某些服务提供程序将自动发送流后的属性的大小。 调用**OpenProperty** MAPI_DEFERRED_ERRORS 与打开的属性和流大小的返回可以延迟标志。 如果**IStream::Stat**调用来检索此大小与 MAPI_DEFERRED_ERRORS **OpenProperty**标记设置后，将会影响性能，因为此的调用序列强制额外远程过程调用。 若要避免性能下降，客户端可以调用之间**OpenProperty**和**Stat**的调用任何 MAPI 方法。
  
[HrGetOneProp](hrgetoneprop.md)函数，如**OpenProperty**，每次打开一个属性。 在本地计算机上存在目标对象时，应仅使用**HrGetOneProp** 。 不本地可用目标对象时，使用**HrGetOneProp**反复会导致多个远程过程调用和性能下降。 
  
需要多个属性的呼叫者可以在一个循环呼叫**HrGetOneProp**或**OpenProperty**或进行一次调用**GetProps**。 一次调用**GetProps**是更有效。 
  
> [!NOTE]
> 安全属性不是自动提供**GetProps**、 **HrGetOneProp**或**GetPropList**呼叫中的其他属性。 必须使用及其属性标识符显式请求安全属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

