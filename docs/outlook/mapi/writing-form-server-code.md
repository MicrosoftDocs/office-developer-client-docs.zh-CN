---
title: 编写表单服务器代码
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ff33badc-ceed-4364-b99c-8af3af83ceb6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a93e53261d56e452f38e38da427585cecccba405
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325790"
---
# <a name="writing-form-server-code"></a>编写表单服务器代码

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您可以将窗体服务器视为以下内容: 
  
- 一个 Win32 程序, 它显示一个接口并通过标准 windows 消息泵机制处理 windows 消息。
    
- 一个对象, 用于将其类工厂注册为 ole 并由 ole 自动化方法激活。
    
- 遵循 mapi 规则的 mapi 对象与其他 MAPI 组件的交互。
    
 您的代码必须同时处理所有这三个这些广泛的要求。 
  
有关注册表单服务器的类工厂的详细信息, 请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。 处理 windows 消息和显示接口是标准的 windows 编程技术, 它们对 MAPI 表单没有任何特殊的要求。 此外, windows SDK 还提供了有关 Windows 编程的详细信息。 本文档包含为实现必需和可选 mapi 表单接口而需要了解的内容, 以便它们遵循与其他 mapi 组件 (主要是 mapi 表单管理器和邮件客户端应用程序) 进行交互的 mapi 规则。
  
在实现窗体服务器时可使用的所有接口都是从 OLE 基类[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)直接或间接地派生而来的。 这意味着, 这些接口的所有实现都需要使用**QueryInterface**、 **AddRef**和**Release**方法。 如果您使用多重继承在自己的一个新类中实现所有必需的接口, 以便您使用的所有接口都可以共享所需**IUnknown**方法的单个实现, 则可以节省大量工作。 有关详细信息, 请参阅[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)、 [IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)和[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 对于这些方法的 MAPI 表单服务器, 没有特殊的注意事项。 
  
虽然并非所有的 MAPI 表单接口对于所有表单服务器都是必需的, 但任何给定接口中的方法都是必需的。 也就是说, 如果您选择实现特定接口, 则必须实现接口中的所有方法。 这与其他一些 MAPI 组件 (如邮件传输) 的情况不同。 幸运的是, MAPI 表单接口中的方法相对简单, 因此实现所有这些方法不会给开发人员带来极大的负担。
  
MAPI 表单接口与用于创建表单服务器的开发工具的类型无关。 这样, 就可以使用不同的开发工具创建表单。 唯一的要求是所有表单服务器都必须支持所需的 MAPI 表单接口。
  
并非所有表单服务器都需要与表单相关的所有 MAPI 接口。 可选接口允许您实现大多数表单服务器不需要的一些高级表单功能。 下表列出了接口、它们的用途以及是否必须实现这些接口。
  
|**接口**|**说明**|**状态**|
|:-----|:-----|:-----|
|[IMAPIForm : IUnknown](imapiformiunknown.md) <br/> |客户端用于加载表单服务器、执行表单谓词和关闭表单服务器的主接口。 这也是从 OLE **IUnknown**派生的接口, 用于通知其他 ole 组件有关 form 对象实现的接口。  <br/> |必需  <br/> |
|[IPersistMessage : IUnknown](ipersistmessageiunknown.md) <br/> |在将邮件加载到表单对象中并保存邮件时使用。  <br/> |必需  <br/> |
|[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md) <br/> |由 form 对象用来跟踪邮件客户端状态, 并确定 form 对象是否能够显示文件夹中的下一封或上一封邮件。  <br/> |可选  <br/> |
|[IClassFactory](https://msdn.microsoft.com/library/f624f833-2b69-43bc-92cd-c4ecbe6051c5%28Office.15%29.aspx) <br/> |form 对象使用的 ole 类工厂接口, 用于符合 OLE 类工厂机制。  <br/> |必需  <br/> |
|[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md) <br/> |如果窗体服务器支持多种类型的窗体, 则使用此项。 在这种情况下, **IMAPIFormFactory**接口允许客户端应用程序访问您的表单服务器还必须实现的多个**IClassFactory**接口 (每种类型的表单服务器支持一个表单)。  <br/> |可选  <br/> |
   
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

