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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417082"
---
# <a name="retrieving-mapi-properties"></a>检索 MAPI 属性

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端或服务提供商从对象检索属性时，对象会提供属性的值、类型和标识符。 
  
客户端和服务提供商可以通过调用下列方法之一检索对象的属性：
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[HrGetOneProp](hrgetoneprop.md)
  
**GetProps** 方法用于检索一个或多个属性，这些属性不需要专用接口或备用接口来访问。 这意味着 **GetProps** 可用的属性较小，如整数和布尔值。 
  
 **检索多个属性**
  
1. 分配 [一个足够大的 SPropTagArray](sproptagarray.md) 结构，以容纳要检索的属性数。 
    
2. 将 **SPropTagArray** 结构的 **cValues** 成员设置为要检索的属性数，将每个 **aulPropTag** 成员设置为目标属性之一的标识符和类型（如果可能）。 如果类型未知，请设置为PT_UNSPECIFIED。 如果类型和标识符都未知，请通过调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)找到此信息。 **GetPropList** 返回一个属性标记数组，该数组包含对象的所有受支持属性。 如果只有属性名称可用，请调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 以访问关联的标识符。 
    
3. 调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 以打开属性。 
    
**OpenProperty** 方法用于打开需要备用接口（如 **IStream** 或 [IMAPITable）](imapitableiunknown.md)进行访问的较大属性。 **OpenProperty** 通常用于打开大字符串、二进制和对象属性，并且一次只能打开一个属性。 调用方将所需的其他接口的标识符作为输入参数之一进行传递。 
  
**OpenProperty** 的一些常见用途包括PR_BODY ([PidTagBody](pidtagbody-canonical-property.md)) ， 属性（包含基于文本的邮件的正文 **、PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 、保留 OLE 对象或邮件附件的属性）和 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) （保留文件夹或通讯簿容器内容表的属性）。  
  
根据 属性，从 **OpenProperty** 请求不同的接口。 **IStream** 是一个允许读取属性数据并作为字节流写入的接口，它通常用于访问 **PR_BODY。** [IMessage 或](imessageimapiprop.md) **IStream** 可用于访问PR_ATTACH_DATA_OBJ **。** 作为标准邮件的嵌入邮件附件使用 **IMessage，** 而 TNEF 格式的邮件使用 **IStream**。 由于 **PR_CONTAINER_CONTENTS** 表对象，因此它通过 [IMAPITable 访问](imapitableiunknown.md)。
  
 **检索附件的 PR_ATTACH_DATA_BIN 属性**
  
1. 调用 [OpenStreamOnFile](openstreamonfile.md) 函数以打开文件的流。 
    
2. 调用邮件的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法，以使用 **IStream** 接口检索 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。 同时设置 MAPI_MODIFY 和 MAPI_CREATE 标志。 
    
3. 分配 **STATSTG** 结构，并通过调用文件流的 **IStream：：Stat** 方法来确定其大小。 确定流大小的另一个方法为使用标志调用 **IStream：：Seek** STREAM_SEEK_END。 
    
4. 调用流的 **IStream：：CopyTo** 方法将数据从文件流复制到附件流。 
    
5. 复制操作完成后，通过调用它们的 **IUnknown：：Release** 方法释放这两个流。 
    
当 **IStream** 用于属性访问时，某些服务提供商会自动将属性的大小随流发送回。 调用具有 MAPI_DEFERRED_ERRORS 标志的 **OpenProperty** 可能会延迟属性的打开和流大小的返回。 如果在设置了 MAPI_DEFERRED_ERRORS 标志的 **OpenProperty** 之后调用 **IStream：：Stat** 以检索此大小，则性能将受到影响，因为此调用序列会强制进行额外的远程过程调用。 为了避免性能下降，客户端可以在调用 **OpenProperty** 和 **Stat** 之间调用任何 MAPI 方法。
  
[HrGetOneProp](hrgetoneprop.md)函数（如 **OpenProperty）** 一次打开一个属性。 只有当目标对象存在于本地计算机上时，才应使用 **HrGetOneProp。** 当目标对象在本地不可用时，重复使用 **HrGetOneProp** 会导致多个远程过程调用和性能下降。 
  
需要多个属性的调用方可以在循环中调用 **HrGetOneProp** 或 **OpenProperty，** 也可以对 **GetProps** 进行一次调用。 调用 **GetProps 一** 次会更有效。 
  
> [!NOTE]
> 安全属性不会自动与 **GetProps、HrGetOneProp** 或 **GetPropList** 调用中的其他属性一起提供。 必须使用安全属性的属性标识符显式请求。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

