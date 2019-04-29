---
title: MAPI 服务提供程序对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f8ade454-2450-49e6-a76f-93801055a7e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0976e986a33d8b96366a84527f227bd05ef7845e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432266"
---
# <a name="mapi-service-provider-objects"></a>MAPI 服务提供程序对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
服务提供程序实现许多对象。 一些主要由 MAPI 使用, 一些由客户端应用程序使用。 一些对象由所有类型的服务提供程序实现;其余内容特定于单个提供程序类型。 下表介绍了所有服务提供程序对象。
  
|**服务提供程序对象**|**说明**|
|:-----|:-----|
|通讯簿容器  <br/> |包含活动配置文件中一个通讯簿提供程序的收件人信息;通讯簿提供程序可以有一个或多个通讯簿容器。  <br/> |
|Attachment  <br/> |包含要与邮件相关联的其他数据 (如文件或 OLE 对象)。  <br/> |
|Control  <br/> |启用或禁用按钮, 并在单击按钮时启动处理。  <br/> |
|通讯组列表  <br/> |描述单个邮件收件人的分组。  <br/> |
|Folder  <br/> |包含邮件和其他消息容器。  <br/> |
|登录  <br/> |处理服务提供程序事件通知和客户端请求。  <br/> |
|邮件用户  <br/> |描述邮件的单个收件人。  <br/> |
|邮件  <br/> |包含可发送给一个或多个收件人的信息。  <br/> |
|邮件存储  <br/> |充当以分层方式组织的邮件数据库。  <br/> |
|提供程序  <br/> |处理服务提供程序启动和关闭。  <br/> |
|后台打印程序挂钩  <br/> |对入站和出站邮件执行特殊处理。  <br/> |
|状态  <br/> |提供对服务提供程序状态的访问权限。  <br/> |
|Table  <br/> |提供对行和列格式的对象数据的摘要视图, 与数据库表类似。  <br/> |
   
所有服务提供程序都实现一个提供程序对象和一个登录对象。 提供程序对象完全用于簿记;MAPI 使用它们来控制启动和关闭进程。 登录对象间接服务一些客户端请求。 例如, 邮件存储提供程序的登录对象处理通知注册和打开邮件存储对象的请求。 
  
提供程序和登录对象实现不同的接口, 具体取决于提供实现的服务提供程序的类型。 邮件存储提供程序在其提供程序和登录对象中实现[IMSProvider: iunknown](imsprovideriunknown.md)和[IMSLogon: iunknown](imslogoniunknown.md)接口, 通讯簿提供程序实现[IABProvider: iunknown](iabprovideriunknown.md)和[IABLogon: iunknown](iablogoniunknown.md)接口, 传输提供程序实现[IXPProvider: iunknown](ixpprovideriunknown.md)和[IXPLogon: iunknown](ixplogoniunknown.md)接口。 
  
消息挂钩提供程序实现假脱机处理程序挂钩对象或筛选入站和出站邮件的对象。
  
服务提供商通常仅使用少数几个对象。 通常, 它们使用 MAPI 提供的支持对象来帮助实现客户端请求。 支持对象是针对使用它的提供程序的类型进行自定义的。 对于所有服务提供程序, 支持对象包括处理事件通知、显示配置属性、打开对象和错误处理的方法。 其余方法特定于其用途;通讯簿、邮件存储和传输提供程序以及配置支持的自定义版本。 例如, 通讯簿支持对象显示详细信息和自定义收件人对话框。 邮件存储区支持对象支持文件夹和邮件的复制和移动操作。 传输提供程序支持对象包括用于促进与 MAPI 后台处理程序的交互的方法。 
  
某些服务提供程序使用表数据和属性数据对象, 即 MAPI 实现的实用工具对象。 表数据对象使服务提供程序可以管理表的基础数据。 使用属性数据对象, 服务提供程序可以设置对象和属性访问。 
  
支持传输中性封装格式 (TNEF) 以传输属性的传输提供程序使用 MAPI 实现的 TNEF 对象来支持[ITnef: IUnknown](itnefiunknown.md)接口。 有关详细信息, 请参阅[开发启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。 
  
## <a name="see-also"></a>另请参阅



[ITnef : IUnknown](itnefiunknown.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)
  
[IABProvider : IUnknown](iabprovideriunknown.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)


[开发启用了 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)

