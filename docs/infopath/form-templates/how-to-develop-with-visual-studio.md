---
title: 使用 Visual Studio 进行开发
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39d633d-d8fb-4e2f-a396-6cb50beb8c3e
description: 通过使用在 Visual Studio 2008 中开发的托管代码扩展 InfoPath 表单，您可以大大增强这些表单的功能。随后，您可以将包含代码的表单发布到 SharePoint Server 2013 中的表单库。
ms.openlocfilehash: 1c67b85823fe567b494366a505be5dad51d20b32
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401095"
---
# <a name="develop-with-visual-studio"></a>使用 Visual Studio 进行开发

通过使用在 Visual Studio 2008 中开发的托管代码扩展 InfoPath 表单，您可以大大增强这些表单的功能。随后，您可以将包含代码的表单发布到 SharePoint Server 2013 中的表单库。
  
您可以通过三个高级步骤开始编程并部署包含托管代码的 InfoPath 表单：
  
1. 使用 [Microsoft Visual Studio Tools for Applications 2012](https://www.microsoft.com/en-us/download/details.aspx?id=38807) 附加设备安装 Visual Studio 2008。 
    
2. 设置编程语言，然后在 Visual Studio 2008 代码编辑器中编写和调试代码。
    
3. 完成设计表单和开发代码的工作后，可以将表单模板发布到 SharePoint Server 2013。
    
应考虑创建与 SharePoint Server 2013 兼容的表单的原因如下：
  
- 可以在浏览器中填写通过 InfoPath Forms Services 部署到 SharePoint Server 2013 的表单。这将使未安装 InfoPath 的用户能够打开和使用表单。
    
- 您只设计一个版本的表单。与 Microsoft SharePoint Server 兼容的表单也与 InfoPath Filler 兼容，但仅与 InfoPath Filler 兼容的表单将无法在浏览器中打开。
    
可通过两种方式将表单发布到 SharePoint：SharePoint 沙盒解决方案和管理员部署的解决方案。有关每种发布方法的详细信息以及有关最适合您方案的方法的建议，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。有关沙盒解决方案的示例解决方案，请参阅[示例沙盒解决方案](sample-sandboxed-solutions.md)。
  
## <a name="developing-with-visual-studio"></a>使用 Visual Studio 进行开发

在安装 Visual Studio 2008 和 Microsoft Visual Studio Tools for Applications 2012 加载项后，您便能够开始开发 InfoPath 托管代码解决方案。
  
### <a name="choosing-a-programming-language"></a>选择编程语言

InfoPath 提供了使用用两种语言（Visual Basic 和 C#）编写的四种版本的 InfoPath 对象模型进行编程的选项。该对象模型的四种版本提供了与 InfoPath 2013、InfoPath、Office InfoPath 2007 和 Microsoft InfoPath 2003 的兼容性。
  
### <a name="to-specify-the-programming-language-and-object-model"></a>指定编程语言和对象模型

1. 当表单模板项目在 InfoPath 设计器中处于打开状态时，在“开发工具”**** 选项卡上单击“语言”****。 
    
2. 在“表单选项”**** 对话框的“编程”**** 类别中，从“表单模板代码语言”**** 下拉列表中选择你想要使用的语言。 然后，从“目标版本”**** 下拉列表中选择对象模型的版本。 仅与 InfoPath 2013 兼容的“目标版本”**** 选项没有后跟“InfoPath”**** 名称的版本年。 
    
    > [!NOTE]
    > 并非所有表单模板类型都支持代码。 例如，“SharePoint 列表”**** 表单模板类型和“模板部件”**** 不支持表单代码。 当设计不支持代码的表单模板类型时，“开发工具”**** 选项卡将不可用。 此外，只有某些表单模板类型才支持所有四种版本的对象模型。 例如，“空白表单 (InfoPath Filler)”**** 模板类型支持所有四种版本的对象模型（并创建仅与这些版本中的 InfoPath Filler 兼容的表单模板），而“空白表单”**** 模板仅支持 InfoPath 2013 和 InfoPath（并创建与 InfoPath Filler 和浏览器都兼容的表单模板）。 
  
    您可以设置默认编程语言，以便 InfoPath 表单设计器在启动时将始终使用您选择的语言和对象模型版本。
    
### <a name="to-set-the-default-programming-language"></a>设置默认编程语言

1. 单击“文件”**** 选项卡，然后单击“选项”****。
    
2. 在“InfoPath 选项”**** 对话框的“常规”**** 部分，单击“更多选项”****。
    
3. 在“选项”**** 对话框的“设计”**** 选项卡上，选择“编程默认语言”**** 部分中的默认编程语言。 
    
### <a name="writing-code"></a>编写代码

现在即可开始使用 InfoPath 2013 和 Visual Studio 2008 进行开发。 
  
### <a name="to-start-the-visual-studio-code-editor"></a>启动 Visual Studio 代码编辑器

1. 在 InfoPath 设计器中打开表单模板。
    
2. 单击“开发人员”**** 选项卡上的“代码编辑器”****。 
    
> [!TIP]
> 也可以启动代码编辑器，并使用“开发工具”**** 选项卡上的命令、上下文菜单和其他用户界面方法自动添加表单和控件事件的事件处理程序。 有关详细信息，请参阅[添加事件处理程序](how-to-add-an-event-handler.md)。
  

