---
title: 检索 MAPI 属性
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd3f9f59-9020-46e6-9560-86a7a0eeca20
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 9666c551543cefd12ee8c902db1a2372aab20632
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328642"
---
# <a name="retrieving-mapi-properties"></a>检索 MAPI 属性

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端或服务提供程序从对象中检索属性时, 该对象可提供该属性的值、类型和标识符。 
  
客户端和服务提供程序可以通过调用以下项之一来检索对象的属性:
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[HrGetOneProp](hrgetoneprop.md)
  
**GetProps**方法用于检索一个或多个不需要专用或备用接口进行访问的属性。 这意味着**GetProps**中可用的属性很小, 例如整数和布尔值。 
  
 **检索多个属性**
  
1. 分配一个足够大的[SPropTagArray](sproptagarray.md)结构, 以容纳要检索的属性的数量。 
    
2. 将**SPropTagArray**结构的**cValues**成员设置为要检索的属性的数量, 并将每个**aulPropTag**成员设置为 "标识符" 和 "类型" (如果可能) 其中一个目标属性。 如果类型未知, 请将其设置为 PT_UNSPECIFIED。 如果类型和标识符都是未知的, 则通过调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)查找此信息。 **GetPropList**返回具有对象的所有支持属性的属性标记数组。 如果仅有属性名称可用, 则调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)以访问关联的标识符。 
    
3. 调用[IMAPIProp:: GetProps](imapiprop-getprops.md)打开属性或属性。 
    
**OpenProperty**方法用于打开需要备用接口 (如**IStream**或[IMAPITable](imapitableiunknown.md) for access) 的较大属性。 **OpenProperty**通常用于打开大型字符串、二进制文件和对象属性, 并且一次只能打开一个属性。 调用方传入作为输入参数之一所需的其他接口的标识符。 
  
**OpenProperty**的一些常见用途包括打开**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、保存基于文本的邮件正文的属性、 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))、保存的属性OLE 对象或邮件附件以及**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), 它是保存文件夹或通讯簿容器内容表的属性。 
  
根据属性的不同, 从**OpenProperty**请求不同的接口。 **IStream**是一个接口, 它允许以字节流的形式读取和写入属性数据, 通常用于访问**PR_BODY**。 [IMessage](imessageimapiprop.md)或**IStream**可用于访问**PR_ATTACH_DATA_OBJ**。 作为标准邮件的嵌入邮件附件使用**IMessage** , 而 TNEF 格式的邮件使用**IStream**。 因为**PR_CONTAINER_CONTENTS**是 table 对象, 所以可以使用[IMAPITable](imapitableiunknown.md)进行访问。
  
 **检索附件的 PR_ATTACH_DATA_BIN 属性**
  
1. 调用[OpenStreamOnFile](openstreamonfile.md)函数打开文件的流。 
    
2. 调用邮件的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以检索**IStream**接口的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。 同时设置 MAPI_MODIFY 和 MAPI_CREATE 标志。 
    
3. 分配一个**STATSTG**结构, 并在调用文件流的**IStream:: Stat**方法以确定其大小时传递该结构。 确定流大小的另一种方法是调用**IStream:: Seek** with 标志 STREAM_SEEK_END。 
    
4. 调用流的**IStream:: CopyTo**方法将数据从文件的流复制到附件流。 
    
5. 复制操作完成后, 通过调用其**IUnknown:: release**方法来释放两个流。 
    
当将**IStream**用于属性访问时, 某些服务提供程序会自动将该属性的大小与流一起发送回来。 使用 MAPI_DEFERRED_ERRORS 标志调用**OpenProperty**会延迟属性的打开和流大小的返回。 如果调用**IStream:: Stat**以在使用 MAPI_DEFERRED_ERRORS 标志集的**OpenProperty**之后检索此大小, 则性能将受到影响, 因为此调用序列将强制执行额外的远程过程调用。 若要避免性能下降, 客户端可以调用对**OpenProperty**和**Stat**的调用之间的任何 MAPI 方法。
  
[HrGetOneProp](hrgetoneprop.md)函数 (如**OpenProperty**) 一次打开一个属性。 仅当本地计算机上存在目标对象时, 才应使用**HrGetOneProp** 。 如果目标对象不是本地可用的, 则重复使用**HrGetOneProp**会导致多个远程过程调用, 并导致性能下降。 
  
需要多个属性的调用方可以在循环中调用**HrGetOneProp**或**OpenProperty** , 也可以调用**GetProps**的一个调用。 调用**GetProps**一次效率更高。 
  
> [!NOTE]
> 安全属性不会自动与**GetProps**、 **HrGetOneProp**或**GetPropList**调用中的其他属性一起使用。 必须使用属性标识符显式请求安全属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

