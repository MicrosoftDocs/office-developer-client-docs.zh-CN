---
title: MAPI 存储结构化视图
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 642a678b-4bf2-4246-85cb-c798de23e36f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f58fa70e98841db5507323a63737f1df6c1b7a6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411748"
---
# <a name="structured-storage-in-mapi"></a>MAPI 存储结构化视图

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
结构化存储是指使用 COM 引入的分层存储组织。 在结构化存储环境中，存储分为两个或三种类型的对象： 
  
- Stream 对象
    
- 锁定字节对象
    
- 存储对象
    
流和锁定字节是直接访问数据的低级别对象。 Stream 对象实现 **IStream** 接口，该接口定义读取、写入、定位和复制数据字节的方法。 锁定字节对象实现另一个 COM 接口 **ILockBytes**，以使用字节数组访问数据。 字节数组通常用于提供对基础存储的自定义访问。
  
存储对象在流顶部分层或锁定字节对象;它们可以包含一个或多个这些对象以及其他存储对象。 存储对象实现 **IStorage** 接口，该接口定义用于创建、访问和维护嵌套对象的方法。 
  
由于 **IStream、ILockBytes** 和 **IStorage** 是 COM 接口而不是 MAPI 接口，因此它们的方法返回 COM 错误值，而不是 MAPI 值。 在这些接口中调用方法的客户端和服务提供商必须使用 API 函数 **MapStorageSCode** 将这些值转换为 MAPI 错误值。 有关详细信息，请参阅 [MapStorageSCode](mapstoragescode.md)。
  
客户端和服务提供商使用结构化存储处理太大的属性，而这些属性无法通过 **IMAPIProp** 方法进行维护，通常是大型字符串和二进制属性。 客户端或服务提供商访问这些客户端或服务提供商的一种常见方法是，在 [调用 IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法时指定 **IStream** 或 **IStorage** 作为接口标识符。 例如，客户端调用 **OpenProperty，PR_ATTACH_DATA_BIN** 属性标记，IID_IStream作为接口标识符来访问邮件中的二进制附件。  
  
客户端和服务提供商可以实施自己的流和存储对象或调用 API 函数，以访问 MAPI 或 COM 提供的实现。 由于提供的实现服务于大多数目的，因此客户端和服务提供商很少需要创建自己的实现。 
  
当客户端对 MAPI 对象调用 **OpenProperty** 以通过存储对象访问其某个属性时，服务提供商通常将在直接模式下打开存储对象。 但是，这是典型行为，而不是必需的行为。 客户端应假定由服务提供商打开或创建的所有存储对象都事务处理，并且需要调用 **IStorage：：Commit**。 他们还应记住，在最终提交后调用 **IMAPIProp：：SaveChanges** 以保存 MAPI 对象之前，对存储对象的更改不会永久发生。 有关详细信息，请参阅 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)。
  
MAPI 和 COM 提供了多个 API 函数，用于定义或访问存储和流对象。 下表介绍了常用函数。
  
**用于访问 存储 和 Stream 对象的函数**

|**函数**|**说明**|
|:-----|:-----|
|[HrIStorageFromStream](hristoragefromstream.md) <br/> |创建存储对象以访问流或锁定字节对象。  <br/> |
|[OpenIMsgOnIStg](openimsgonistg.md) <br/> |创建邮件对象以访问存储对象。  <br/> |
|[OpenStreamOnFile](openstreamonfile.md) <br/> |创建流对象以访问文件。  <br/> |
|[WrapCompressedRTFStream](wrapcompressedrtfstream.md) <br/> |创建一个 stream 对象，该对象包含邮件格式文本的压缩或未压缩版本的流。  <br/> |
   
 **检索给定子存储中的流名称**
  
1. 调用 substorage 的 **IStorage：：EnumElements** 方法来获取 **IEnumSTATSTG** 接口。 
    
2. 调用 **IEnumSTATSTG：：Next，** 同时使用尽可能多的 **STATSTG** 结构。 如果一次请求 100 个 **，Next** 通常S_FALSE  _pceltFetched_ 的内容设置为实际检索到的编号。 
    
3. 检查带标记的 **STATSTG** STGTY_STREAM。 
    
4. 释放  _pwcsName_ 参数。 
    
 **创建存储对象以访问现有流或锁定字节对象**
  
- 客户端调用 [HrIStorageFromStream](hristoragefromstream.md)。 
    
 **创建邮件对象以访问现有存储对象**
  
- 服务提供商和客户端调用 [OpenIMsgOnIStg](openimsgonistg.md)。 创建的消息对象不同于邮件存储提供程序通常创建的消息对象，因为它不支持所有 [IMessage ： IMAPIProp](imessageimapiprop.md) 接口方法，如 **IMessage：：SubmitMessage**。 **OpenIMsgOnIStg** 的可选输入参数是一个符合 [MSGCALLRELEASE 原型](msgcallrelease.md)的回调函数。 当邮件的引用计数达到零时，新邮件对象将调用此函数。 在完全删除新邮件之前，实现 **MSGCALLRELEASE** 函数对于执行最终处理非常有用。 
    
[OpenStreamOnFile](openstreamonfile.md) 通常用于存储文件附件，因为它会创建从文件读取和写入文件的流。 **OpenProperty** **PR_ATTACH_DATA_BIN属性** 标记创建用于存储二进制附件数据的流。 
  
 **压缩或解压缩包含格式文本格式的邮件文本的流**
  
- 客户端调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)。 **WrapCompressedRTFStream** 创建包装 RTF 流的流。 包装流不实现所有 **IStream** 方法;排除以下方法：Seek、SetSize、Revert、LockRegion、UnlockRegion、Stat和 Clone 。      这是因为 **WrapCompressedRTFStream** 创建的流对象不支持 **SetSize** 或 **Stat，** 因此无法轻松扩展或检索它们的大小。 最佳策略是选取合理的缓冲区大小，并读取或写入循环。
    
> [!NOTE]
> COM 具有基于字节数组的存储对象实现，该数组从 **EnumElements** 方法返回存在问题的 **IEnumSTATSTG** 对象。 特别是 **，QueryInterface** 方法不能正常工作。 使用 COM 实现实现自己的存储对象的服务提供商应为 **IEnumSTATSTG** 对象创建一个精简包装，该对象将调用转发到基础 **IEnumSTATSTG** 方法，但实现自己的 **AddRef、Release、QueryInterface** 和 **Clone** 方法。   
  

