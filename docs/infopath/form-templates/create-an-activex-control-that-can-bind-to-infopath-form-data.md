---
title: 创建可绑定到 InfoPath 表单数据的 ActiveX 控件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a0d62047-bf08-9f70-de00-7f81ef1331f1
description: 您可以在 InfoPath 表单中承载设计为要在 InfoPath 编辑器中打开的 ActiveX 控件。这些控件可以预先存在（带有某些限制），也可以专门针对 InfoPath 编写。
ms.openlocfilehash: 70ac6a16b305403ffa99d8fe840a165913642f57
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392793"
---
# <a name="create-an-activex-control-that-can-bind-to-infopath-form-data"></a>创建可绑定到 InfoPath 表单数据的 ActiveX 控件

您可以在 InfoPath 表单中承载设计为要在 InfoPath 编辑器中打开的 ActiveX 控件。这些控件可以预先存在（带有某些限制），也可以专门针对 InfoPath 编写。
  
## <a name="write-an-activex-control"></a>编写 ActiveX 控件

与 InfoPath 中的其他控件一样，ActiveX 控件应支持现有组件对象模型 (COM) 接口：
  
- **IDispatch**
    
- **IPersistPropertyBag**
    
- **IPersistStreamInit**
    
- **IPropertyPage**
    
- **IObjectSafety**
    
- **IPropertyNotifySink**
    
- **IViewObject**
    
- **IOleObject**
    
- **IOleInPlaceObject**
    
为了使文档对象模型 (DOM) 中的属性在控件中发生更改时让 InfoPath 更新这些属性，控件应实现以下接口：
  
- **IConnectionPointContainer**
    
- **IEnumConnectionPoints**
    
- **IConnectionPoint**
    
- **IEnumConnections**
    
此外，还有两个特定于 InfoPath 的 COM 接口，这些接口提供更为紧密的控件集成：
  
- [IInfoPathControl](https://msdn.microsoft.com/library/bb264625.aspx)
    
- [IInfoPathControlSite](https://msdn.microsoft.com/library/bb264627.aspx)
    
## <a name="add-an-activex-control-to-the-infopath-design-environment"></a>向 InfoPath 设计环境中添加 ActiveX 控件

利用“控件”**** 任务窗格中的“添加或删除自定义控件”**** 命令，您可以使用“添加自定义控件向导”**** 来添加自定义控件。通过使用该向导，您可以选择已注册的 ActiveX 控件，或在 Office 市场上查找其他自定义控件。选择控件之后，您可以指定以下各项。 
  
- 指定 CAB 以随表单模板一起安装 ActiveX 控件。
    
- 指定绑定属性以绑定到 XML。
    
- 指定一个属性，该属性用于启用或禁用控件以响应规则或数字签名，举例来说，当 XML 不存在或使用条件格式设置时，这样做将非常有用。
    
- 指定数据类型绑定。
    
> [!NOTE]
> 如果你在开发 ActiveX 控件并已将其添加到 InfoPath 中的“控件”**** 任务窗格，则在关闭 InfoPath 之前，你将无法重建 ActiveX 控件。 
  
## <a name="deploy-an-activex-control"></a>部署 ActiveX 控件

若要分发 ActiveX 控件，您可以编写一个安装程序，该安装程序将控件安装在目标计算机上，并将 InfoPath 控件模板 (ICT) 文件和 CAB 文件复制到用户的文件夹，即 \Users\\<用户名\>\AppData\Local\Microsoft\InfoPath\Controls。请注意，如果两名或更多开发人员在协作开发使用 ActiveX 控件的表单，则每名开发人员都应有已添加到 InfoPath 设计环境的控件，否则他们将无法从 InfoPath 中修改控件的属性。
  
## <a name="see-also"></a>另请参阅

实验室 6：在 InfoPath 2003 中添加 ActiveX 控件
  
[使用 C# 和 .NET（InfoPath 团队博客）创建 InfoPath 自定义控件](https://blogs.msdn.microsoft.com/infopath/2005/04/15/creating-an-infopath-custom-control-using-c-and-net/)

