---
title: MAPI 服务提供商对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f8ade454-2450-49e6-a76f-93801055a7e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85a67216822360bcaf9544389f79980891951757
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584854"
---
# <a name="mapi-service-provider-objects"></a>MAPI 服务提供商对象

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
服务提供程序实现多个对象。 某些使用 MAPI 的主要和一些使用客户端应用程序。 所有类型的服务提供商; 由实现几个对象rest 是特定于单个提供程序类型。 下表介绍的所有服务提供商对象。
  
|**服务提供商对象**|**说明**|
|:-----|:-----|
|通讯簿容器  <br/> |包含一个通讯簿提供程序中的活动配置文件; 收件人信息通讯簿提供程序可以具有一个或多个地址簿容器。  <br/> |
|附件  <br/> |包含其他数据，如文件或 OLE 对象，与邮件相关联。  <br/> |
|Control  <br/> |启用或禁用按钮并启动处理单击按钮时。  <br/> |
|通讯组列表  <br/> |描述单个邮件的收件人的分组。  <br/> |
|Folder  <br/> |包含消息以及其他消息容器。  <br/> |
|登录  <br/> |处理服务提供程序的事件通知和客户端请求。  <br/> |
|邮件用户  <br/> |描述单个收件人的邮件。  <br/> |
|Message  <br/> |包含可被发送到一个或多个收件人的信息。  <br/> |
|消息存储库  <br/> |用作按层次结构组织的数据库的消息。  <br/> |
|提供程序  <br/> |处理服务提供程序启动和关机。  <br/> |
|后台处理程序挂接  <br/> |对入站和出站邮件执行特殊处理。  <br/> |
|Status  <br/> |提供对服务提供商的状态的访问。  <br/> |
|Table  <br/> |提供对行和列的格式，类似于数据库表中的对象数据的摘要视图访问。  <br/> |
   
所有服务提供商都实现提供程序对象和登录对象。 提供商对象仅限用于记帐;他们使用 MAPI 控制启动和关机进程。 登录对象间接某些客户端请求提供服务。 例如，消息存储提供程序的登录对象处理通知注册和请求以打开消息存储对象。 
  
提供程序和登录对象实现不同的接口，具体取决于服务提供程序提供实现的类型。 消息存储提供程序实现[IMSProvider: IUnknown](imsprovideriunknown.md)和[IMSLogon: IUnknown](imslogoniunknown.md)接口在其提供程序和登录对象中，通讯簿提供程序实现[IABProvider: IUnknown](iabprovideriunknown.md)和[IABLogon: IUnknown](iablogoniunknown.md)接口和传输提供程序实现[IXPProvider: IUnknown](ixpprovideriunknown.md)和[IXPLogon: IUnknown](ixplogoniunknown.md)接口。 
  
消息挂接提供程序实现后台处理程序挂接对象或筛选入站和出站邮件的对象。
  
服务提供商通常使用只有少数对象。 通常，它们使用 MAPI 提供可帮助实现客户端请求的支持对象。 正在使用它的提供程序的类型为自定义的支持对象。 对于所有服务提供程序，支持对象包含用于处理事件通知，并显示配置属性、 打开对象和错误处理方法。 其余方法是特定于其使用;有自定义的通讯簿、 消息存储和传输提供程序和配置支持的版本。 例如，通讯簿支持对象显示详细信息和收件人的自定义对话框。 消息存储库支持对象支持复制和移动的文件夹和邮件的操作。 传输提供程序支持对象包含用于简化 MAPI 后台处理程序的交互的方法。 
  
某些服务提供商使用表数据和属性数据对象 — MAPI 实现的实用程序对象。 表格数据对象启用服务提供商管理基础表的数据。 属性数据对象启用服务提供商设置对象和属性的访问。 
  
传输提供程序支持传输中性封装格式 (TNEF) 用于转接属性使用 TNEF 对象 MAPI 实现支持的[ITnef: IUnknown](itnefiunknown.md)接口。 有关详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。 
  
## <a name="see-also"></a>另请参阅



[ITnef : IUnknown](itnefiunknown.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)
  
[IABProvider : IUnknown](iabprovideriunknown.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)


[开发已启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)

