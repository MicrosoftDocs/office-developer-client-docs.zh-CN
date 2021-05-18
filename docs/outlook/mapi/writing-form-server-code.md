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
  
您可以将表单服务器视为以下服务器： 
  
- 一个 Win32 程序，它通过标准邮件Windows处理窗口消息。
    
- 一个使用 OLE 注册其类工厂并且由 OLE 自动化方法激活的对象。
    
- 遵循 MAPI 规则与其他 MAPI 组件的交互的 MAPI 对象。
    
 代码必须同时处理这三个广泛要求。 
  
有关注册表单服务器的类工厂的详细信息，请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。 处理窗口消息和显示接口是Windows编程技术的标准方法，这些编程技术对 MAPI 表单没有任何特殊要求。 同样，Windows SDK 具有有关编程Windows的详细信息。 本文档包含实现必需和可选的 MAPI 表单接口所需的内容，以便它们遵循 MAPI 规则与其他 MAPI 组件（主要是 MAPI 表单管理器和消息客户端应用程序）交互。
  
实现表单服务器时可以使用的所有接口都直接或间接派生自 OLE 基类 [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)。 这意味着这些接口的所有实现都需要具有 **QueryInterface、AddRef** 和 **Release** 方法。 如果使用多个继承在您自己的一个新类中实现所有必需的接口，那么您可以为自己节省大量工作，以便你使用的所有接口可以共享所需 **IUnknown** 方法的单个实现。 有关详细信息，请参阅[IUnknown：：AddRef、IUnknown：：QueryInterface](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)和[IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 [](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 对于这些方法，对于 MAPI 表单服务器没有特殊的注意事项。 
  
虽然并非所有 MAPI 表单接口对于所有表单服务器都是强制性的，但任何给定接口中的方法都是强制性的。 也就是说，如果选择实现特定接口，则必须在接口中实现所有方法。 这不同于其他一些 MAPI 组件（如邮件传输）的情况。 幸运的是，MAPI 表单接口中的方法相对简单，因此实现所有这些方法不会给开发人员带来极大负担。
  
MAPI 表单接口与用于创建表单服务器的开发工具类型无关。 这允许使用不同的开发工具创建表单。 唯一的要求是，所有表单服务器都必须支持所需的 MAPI 表单接口。
  
并非所有表单服务器都需要与表单相关的所有 MAPI 接口。 可选接口允许您实现大多数表单服务器不需要的一些高级表单函数。 下表列出了接口、接口用于哪些内容以及是否必须实现这些接口。
  
|**接口**|**说明**|**状态**|
|:-----|:-----|:-----|
|[IMAPIForm : IUnknown](imapiformiunknown.md) <br/> |客户端用于加载表单服务器、执行表单谓词和关闭表单服务器的主接口。 这也是从 OLE **IUnknown** 派生的接口，用于通知其他 OLE 组件有关表单对象实现哪些接口。  <br/> |必需  <br/> |
|[IPersistMessage : IUnknown](ipersistmessageiunknown.md) <br/> |在将邮件加载到表单对象中以及从表单对象保存邮件时使用。  <br/> |必需  <br/> |
|[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md) <br/> |由表单对象用于跟踪邮件客户端状态并查明表单对象是否能够在文件夹中显示下一封邮件或上一封邮件。  <br/> |可选  <br/> |
|[IClassFactory](https://msdn.microsoft.com/library/f624f833-2b69-43bc-92cd-c4ecbe6051c5%28Office.15%29.aspx) <br/> |表单对象用于符合 OLE 类工厂机制的 OLE 类工厂接口。  <br/> |必需  <br/> |
|[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md) <br/> |在表单服务器支持多种类型的表单时使用。 在这种情况下 **，IMAPIFormFactory** 接口允许客户端应用程序访问多个 IClassFactory 接口 (表单服务器也必须实现表单服务器必须实现) 类型的表单访问一个 **IClassFactory** 接口。  <br/> |可选  <br/> |
   
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

