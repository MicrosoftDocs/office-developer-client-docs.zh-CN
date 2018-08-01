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
ms.openlocfilehash: 860b0150fd1ec66fa8fee387d8d4a96e8bb79761
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779101"
---
# <a name="writing-form-server-code"></a>编写表单服务器代码

  
  
**适用于**： Outlook 
  
您可以将窗体服务器如下： 
  
- Win32 程序显示一个接口，并处理 windows 消息通过标准 Windows 消息抽取机制。
    
- OLE 中注册其类中心，并通过 OLE 自动化方法激活一个对象。
    
- 按照与其他 MAPI 组件交互的 MAPI 规则 MAPI 对象。
    
 您的代码必须同时处理所有这三个这些广泛的要求。 
  
请参阅 Windows SDK 有关注册窗体服务器的类工厂的详细信息中的 COM 和 ActiveX 对象服务部分。 处理 windows 消息和显示接口是没有任何特殊要求 MAPI 窗体的标准 Windows 编程技术。 同样，Windows SDK 包含有关 Windows 编程的详细信息。 本文档包含您需要知道实现的必需的和可选的 MAPI 表单接口，以便在与其他 MAPI 组件交互的 MAPI 规则 — 主要的 MAPI 窗体管理器和消息客户端应用程序。
  
所有实现表单服务器时，可以使用的接口派生 — 直接或间接 — 从 OLE 基类[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)。 这意味着所有您实现这些接口需要具有**QueryInterface**、 **AddRef**和**Release**的方法。 您可以保存自己大量工作如果您使用多个继承，以便您使用的所有接口可以都共享单个所需的**IUnknown**方法的实现，在您自己的一个新的类中实现所有所需的接口。 有关详细信息，请参阅[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)、 [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)和[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 没有与 MAPI 表单服务器时的特殊注意事项这些方法。 
  
而不是所有的 MAPI 表单接口是必需的窗体的所有服务器，则任何给定接口中的方法是必需的。 也就是说，如果您选择实现特定的接口，您必须实现的所有方法界面中。 这一点不同于与其他 MAPI 组件，如邮件传输的情况。 幸运的是，MAPI 表单接口中的方法是相对简单，因此实现所有这些不会在开发人员将绝佳负担。
  
MAPI 表单接口是类型的独立的开发工具，用于创建窗体服务器。 这样，通过使用不同的开发工具创建的表单。 唯一的要求是窗体的所有服务器都必须都支持所需的 MAPI 表单接口。
  
不是所有与表单相关的 MAPI 接口所需窗体的所有服务器。 可选接口，可以实现不需要的大多数窗体服务器的一些高级的表单功能。 下表列出接口、 什么是，内容和是否必须实现它们。
  
|**接口**|**说明**|**Status**|
|:-----|:-----|:-----|
|[IMAPIForm : IUnknown](imapiformiunknown.md) <br/> |客户端用于加载窗体服务器的主要接口执行窗体动作，并关闭窗体服务器。 这也是派生自用于通知有关哪些 form 对象实现的接口其他 OLE 组件 OLE **IUnknown**接口。  <br/> |必需  <br/> |
|[IPersistMessage : IUnknown](ipersistmessageiunknown.md) <br/> |加载和保存来自窗体对象的邮件的邮件时使用。  <br/> |必需  <br/> |
|[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md) <br/> |由表单对象以跟踪消息客户端状态，并以找出 form 对象是否能够在文件夹中显示的下一页或上一页消息。  <br/> |可选  <br/> |
|[IClassFactory](http://msdn.microsoft.com/library/f624f833-2b69-43bc-92cd-c4ecbe6051c5%28Office.15%29.aspx) <br/> |使用窗体对象的合规性的 OLE 类工厂机制 OLE 类工厂接口。  <br/> |必需  <br/> |
|[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md) <br/> |如果您的窗体服务器支持多个类型的窗体，使用。 在这种情况下， **IMAPIFormFactory**界面允许客户端应用程序访问多个**IClassFactory**接口 （每种窗体的窗体服务器支持一个） 窗体服务器还必须实现。  <br/> |可选  <br/> |
   
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

