---
title: MAPI 中的结构化存储
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 642a678b-4bf2-4246-85cb-c798de23e36f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f58fa70e98841db5507323a63737f1df6c1b7a6d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327431"
---
# <a name="structured-storage-in-mapi"></a>MAPI 中的结构化存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
结构化存储指随 COM 引入的存储的分层组织。 在结构化存储环境中, 将存储组织为两种或三种类型的对象: 
  
- Stream 对象
    
- 锁定字节对象
    
- 存储对象
    
流和锁定字节是可直接访问数据的较低级别对象。 Stream 对象实现**IStream**接口, 该接口定义用于读取、写入、定位和复制数据字节的方法。 Lock bytes 对象实现另一个 COM 接口**ILockBytes**, 以使用字节数组访问数据。 字节数组通常用于提供对基础存储的自定义访问。
  
存储对象在 stream 或 lock bytes 对象的上方分层;它们可以包含一个或多个这些对象以及其他存储对象。 Storage 对象实现**IStorage**接口, 该接口定义用于创建、访问和维护嵌套对象的方法。 
  
由于**IStream**、 **ILockBytes**和**IStorage**是 com 接口而不是 mapi 接口, 因此它们的方法返回 com 错误值而不是 mapi 值。 客户端和服务提供程序调用这些接口中的方法时, 必须使用 API 函数**MapStorageSCode**将这些值转换为 MAPI 错误值。 有关详细信息, 请参阅[MapStorageSCode](mapstoragescode.md)。
  
客户端和服务提供程序使用结构化存储来处理因过大而无法使用**IMAPIProp**方法维护的属性, 通常是大型字符串和二进制属性。 客户端或服务提供程序访问它们的常用方法之一是, 在对[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用中将**IStream**或**IStorage**指定为接口标识符。 例如, 客户端将**PR_ATTACH_DATA_BIN**作为属性标记, 并将 IID_IStream 作为接口标识符调用, 以访问邮件中的二进制附件的**OpenProperty** 。 
  
客户端和服务提供程序可以实现自己的 stream 和 storage 对象或调用 API 函数, 以访问 MAPI 或 COM 提供的实现。 由于提供的实现为大多数目的提供服务, 因此客户端和服务提供程序很少需要创建自己的实现。 
  
当客户端对 MAPI 对象调用**OpenProperty**以通过存储对象访问其属性之一时, 服务提供程序通常会在直接模式下打开存储对象。 但是, 这是典型行为, 而不是必需的行为。 客户端应假定服务提供程序打开或创建的所有存储对象都进行了事务处理, 并且需要调用**IStorage:: Commit**。 此外, 还应注意, 对存储对象所做的更改在其调用**IMAPIProp:: SaveChanges**之后将不会**** 永久生效, 以保存 MAPI 对象。 有关详细信息, 请参阅[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)。
  
MAPI 和 COM 提供了用于定义或访问存储和流对象的几个 API 函数。 下表描述了常用函数。
  
**用于访问存储和 Stream 对象的函数**

|**函数**|**说明**|
|:-----|:-----|
|[HrIStorageFromStream](hristoragefromstream.md) <br/> |创建存储对象以访问 stream 或 lock bytes 对象。  <br/> |
|[OpenIMsgOnIStg](openimsgonistg.md) <br/> |创建一个 message 对象以访问存储对象。  <br/> |
|[OpenStreamOnFile](openstreamonfile.md) <br/> |创建 stream 对象以访问文件。  <br/> |
|[WrapCompressedRTFStream](wrapcompressedrtfstream.md) <br/> |创建一个 stream 对象, 该对象包含包含邮件的格式文本的流的压缩版本或未压缩版本。  <br/> |
   
 **检索给定 substorage 中的流的名称**
  
1. 调用 substorage 的**IStorage:: EnumElements**方法以获取**IEnumSTATSTG**接口。 
    
2. **IEnumSTATSTG:: 下一**次使用任意数量的**STATSTG**结构的调用。 [! 注意] 如果一次请求 100, 则**Next**通常会返回 S_FALSE, 并将_pceltFetched_的内容设置为实际检索的编号。 
    
3. 检查使用 STGTY_STREAM 标记的**STATSTG**结构。 
    
4. 释放_pwcsName_参数。 
    
 **创建存储对象以访问现有的 stream 或 lock bytes 对象**
  
- 客户端调用[HrIStorageFromStream](hristoragefromstream.md)。 
    
 **创建邮件对象以访问现有存储对象**
  
- 服务提供商和客户端调用[OpenIMsgOnIStg](openimsgonistg.md)。 创建的 message 对象不同于通常由邮件存储提供程序创建的邮件对象, 因为它不支持所有[IMessage: IMAPIProp](imessageimapiprop.md)接口方法, 如**IMessage:: SubmitMessage**。 **OpenIMsgOnIStg**的可选输入参数是符合[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数。 当邮件的引用计数达到零时, 新的 message 对象调用此函数。 在完全删除新邮件之前, 实现**MSGCALLRELEASE**函数可用于执行最终处理。 
    
[OpenStreamOnFile](openstreamonfile.md)通常用于存储文件附件, 因为它会创建一个从文件中读取和写入文件的流。 **OpenProperty** with **PR_ATTACH_DATA_BIN**作为属性标记创建用于存储二进制附件数据的流。 
  
 **压缩或解压缩包含 rtf 格式的邮件文本的流**
  
- 客户端调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。 **WrapCompressedRTFStream**创建一个包装 RTF 流的流。 包装流不实现所有的**IStream**方法;排除了以下方法: **Seek**、 **SetSize**、 **Revert**、 **LockRegion**、 **UnlockRegion**、 **Stat**和**Clone**。 这是因为**WrapCompressedRTFStream**创建的 stream 对象不支持**SetSize**或**Stat**, 不是扩展或检索其大小的简单方法。 最佳策略是选择合理的缓冲区大小, 并在循环中进行读取或写入。
    
> [!NOTE]
> COM 具有一个基于字节数组的存储对象实现, 该数组从有问题的**EnumElements**方法返回一个**IEnumSTATSTG**对象。 具体说来, **QueryInterface**方法无法正常工作。 使用 COM 实现来实现其自己的存储对象的服务提供程序应为**IEnumSTATSTG**对象创建一个瘦包装, 该包装会将呼叫转发到基础**IEnumSTATSTG**方法, 但却实现了自己的**AddRef**、 **Release**、 **QueryInterface**和**Clone**方法。 
  

