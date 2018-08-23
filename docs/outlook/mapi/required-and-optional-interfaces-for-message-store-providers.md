---
title: 邮件存储区提供程序的必需和可选接口
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc62e57e-82a4-4f37-8d1b-7cdf828b951e
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 3305aaadbcf7d53b801ddaf7e31a0d63145fc7ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586961"
---
# <a name="required-and-optional-interfaces-for-message-store-providers"></a>邮件存储区提供程序的必需和可选接口

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 定义一组与消息存储提供程序相关的接口。 由于广泛的消息存储可以选择实现的功能，这些接口一些需要和某些不是。 下表列出了对消息存储提供程序相关的 MAPI 接口，指定是否接口是必需或可选的并描述及其用途。
  
|**接口**|**Status**|**说明**|
|:-----|:-----|:-----|
|[IMSProvider](imsprovideriunknown.md) <br/> |必需  <br/> |登录到移开的消息存储。  <br/> |
|[IMSLogon](imslogoniunknown.md) <br/> |必需  <br/> |打开文件夹或消息，验证的消息存储的标识，并处理通知。  <br/> |
|[IMsgStore](imsgstoreimapiprop.md) <br/> |必需  <br/> |打开文件夹或消息，找到特殊文件夹，并处理的邮件提交。  <br/> |
|[IMAPIFolder](imapifolderimapicontainer.md) <br/> |必需  <br/> |查找和处理消息和子文件夹。  <br/> |
|[IMessage](imessageimapiprop.md) <br/> |必需  <br/> |处理附件，并设置的一些消息的属性。  <br/> |
|[IMAPITable](imapitableiunknown.md) <br/> |必需  <br/> |允许其他对象来提供与各种 MAPI 组件的数据的集合。  <br/> |
|[IMAPIStatus](imapistatusimapiprop.md) <br/> |必需  <br/> |使客户端验证的消息存储的状态和执行一些配置任务。  <br/> |
|[IAttach](iattachimapiprop.md) <br/> |可选  <br/> |如果存储提供程序支持的文件附件，则访问邮件附件属性。  <br/> |
|**IStorage** <br/> |可选  <br/> |如果存储提供程序支持 OLE 对象附件，管理结构化的存储对象。  <br/> |
|**IStream** <br/> |可选  <br/> |启用邮件和附件对象以读取和写入 stream 对象的数据。  <br/> |
|**IStreamDocfile** <br/> |可选  <br/> |使某些服务提供商，以打开存储对象，例如复合文件中的 OLE 2.0 文件格式。  <br/> |
   
您需要实现**IMAPIFolder**、 **IMessage**、 **IMAPIStatus**和**IMAPITable**的基本信息介绍了这些接口的参考主题。 本节包含与消息存储提供程序更直接相关的补充信息。 MAPI 接口的其余部分应实现根据本节中和相应的参考主题中的信息。 请参阅有关实施**IStorage**、 **IStream**和**IStreamDocFile**Windows SDK 中的 COM 和 ActiveX 对象服务部分。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

