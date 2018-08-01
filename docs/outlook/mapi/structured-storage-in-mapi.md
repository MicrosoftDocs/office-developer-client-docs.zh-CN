---
title: MAPI 中的结构化的存储
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 642a678b-4bf2-4246-85cb-c798de23e36f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 462ee84d5e9acd26f80bae6516179f21651749be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778910"
---
# <a name="structured-storage-in-mapi"></a>MAPI 中的结构化的存储

  
  
**适用于**： Outlook 
  
结构化的存储是指存储 COM.中引入的分层组织 结构化的存储环境中存储分为两个或三种类型的对象： 
  
- Stream 对象
    
- 锁定字节对象
    
- 存储对象
    
流和锁定字节是直接访问的数据的级别较低的对象。 Stream 对象实现**IStream**接口它定义用于读取、 写入、 定位、 和复制字节的数据的方法。 锁定字节对象实现其他 COM 接口， **ILockBytes**，若要访问与一个字节数组的数据。 通常，用于字节数组，以提供对基础存储的自定义的访问。
  
存储对象层叠流或锁定字节对象;它们可以包含一个或多个这些对象以及其他存储对象。 存储对象实现**IStorage**接口它定义用于创建、 访问和维护嵌套的对象的方法。 
  
由于**IStream**、 **ILockBytes**和**IStorage** COM 接口，而不是 MAPI 接口，其方法将返回 COM 错误值而不是 MAPI 值。 客户端和这些接口中调用方法的服务提供商必须使用 API 函数**MapStorageSCode**将这些值转换 MAPI 错误值。 有关详细信息，请参阅[MapStorageSCode](mapstoragescode.md)。
  
客户端和服务提供商可以用于结构化的存储使用太长维护**IMAPIProp**方法、 通常较大字符串和二进制属性的属性。 客户端或服务提供商访问它们的常用方法之一是通过作为对[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用中的接口标识符指定**IStream**或**IStorage** 。 例如，客户端调用与**PR_ATTACH_DATA_BIN** **OpenProperty**作为属性标记和接口标识 IID_IStream 访问邮件中的二进制附件。 
  
客户端和服务提供商可以实现自己流和存储的对象或调用访问实现 MAPI 或 COM.提供的 API 函数 因为提供的实现有大多数情况下，客户端和服务提供商很少需要创建自己。 
  
当客户端调用**OpenProperty** MAPI 对象上存储对象通过访问其属性之一时，服务提供程序通常将在直接模式中打开的存储对象。 但是，这是典型而不是所需行为。 客户端应假定打开或创建由服务提供商提供的所有存储对象的事务处理，并需要**IStorage::Commit**调用。 他们还应该记住存储对象更改将不进行永久他们最后一**提交**保存 MAPI 对象之后调用**IMAPIProp::SaveChanges**之前。 有关详细信息，请参阅[IMAPIProp::SaveChanges](imapiprop-savechanges.md)。
  
MAPI 和 COM 提供用于定义或访问存储和 stream 对象的几个 API 函数。 下表中介绍的常用的功能。
  
**用于访问存储和 Stream 对象的函数**

|**函数**|**说明**|
|:-----|:-----|
|[HrIStorageFromStream](hristoragefromstream.md) <br/> |创建访问流或锁定字节对象的存储对象。  <br/> |
|[OpenIMsgOnIStg](openimsgonistg.md) <br/> |创建访问存储对象的消息对象。  <br/> |
|[OpenStreamOnFile](openstreamonfile.md) <br/> |创建 stream 对象，以访问文件。  <br/> |
|[WrapCompressedRTFStream](wrapcompressedrtfstream.md) <br/> |创建一个包含保存一条消息的格式文本 stream 的压缩文件或未压缩版本的 stream 对象。  <br/> |
   
 **若要检索在给定的子存储的流的名称**
  
1. 调用子存储的**IStorage::EnumElements**方法以获取**IEnumSTATSTG**接口。 
    
2. 调用**IEnumSTATSTG::Next**尽可能多**STATSTG**结构一次，您可以。 如果每次请求的 100**下, 一步**将通常返回 S_FALSE _pceltFetched_的内容设置为实际检索到的号码。 
    
3. 检查 STGTY_STREAM 与标记的**STATSTG**结构。 
    
4. 释放_pwcsName_参数。 
    
 **若要创建存储对象，以便访问现有流或锁定字节对象**
  
- 客户端调用[HrIStorageFromStream](hristoragefromstream.md)。 
    
 **若要创建邮件对象，以便访问现有的存储对象**
  
- 服务提供商和客户端调用[OpenIMsgOnIStg](openimsgonistg.md)。 Message 对象创建不同的它不支持的所有通常由消息存储提供程序创建的消息对象[IMessage: IMAPIProp](imessageimapiprop.md)接口方法，如**IMessage::SubmitMessage**。 **OpenIMsgOnIStg**的可选输入的参数是一个符合[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数。 当邮件的引用计数为零时，由新的消息对象调用此函数。 实现**MSGCALLRELEASE**函数可用于执行最终处理之前完全删除新邮件。 
    
[OpenStreamOnFile](openstreamonfile.md)通常用于存储文件附件，因为它会创建流读取和写入文件。 与**PR_ATTACH_DATA_BIN**属性标记为**OpenProperty**创建存储二进制附件数据的流。 
  
 **压缩或解压缩包含富文本格式的消息文本的流**
  
- 客户端调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。 **WrapCompressedRTFStream**创建换行 RTF 流的流。 包装流未实现的所有**IStream**方法;排除以下方法： **Seek**、 **SetSize**、**还原**、 **LockRegion**、 **UnlockRegion**、 **Stat**和**克隆**。 这是因为由**WrapCompressedRTFStream**创建的 stream 对象不支持**SetSize**或**Stat**，不可用于扩展或检索其大小简便方法。 最佳策略是选取合理缓冲区大小和读取或写入循环。
    
> [!NOTE]
> COM 具有存储对象实现基于从有问题的**EnumElements**方法返回一个**IEnumSTATSTG**对象的字节数组。 具体而言， **QueryInterface**方法不会无法正常工作。 服务提供程序实现使用 COM 实现自己存储对象应创建精简的**IEnumSTATSTG**对象的转发到基础**IEnumSTATSTG**方法的调用，但实现包装自己**AddRef**，**发布**、 **QueryInterface**和**Clone**方法。 
  

