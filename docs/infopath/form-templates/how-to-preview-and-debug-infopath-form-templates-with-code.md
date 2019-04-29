---
title: 预览和调试包含代码的 InfoPath 表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- previewing form templates [infopath 2007],debugging form templates [InfoPath 2007],form templates [InfoPath 2007], previewing,debugging [InfoPath 2007], managed-code form templates,form templates [InfoPath 2007], debugging,InfoPath 2007, debugging form templates,InfoPath 2007, previewing form templates
localization_priority: Normal
ms.assetid: c8387f1c-b34c-490e-8bf9-d824bf98d826
description: 使用带有 Visual Studio 2008 的 Microsoft InfoPath，您可以通过在预览模式下运行表单代码来进行调试。在开始调试表单代码时，系统将对项目进行编译，InfoPath 将在 InfoPath 预览窗口中显示表单。当遇到设置了断点的代码行时，焦点将移动到代码编辑器。当越过断点继续调试时，焦点将移回预览窗口。关闭预览窗口时调试也将停止。
ms.openlocfilehash: 8f9ff97fdd5b4b016d96129304fa6f994d7b4561
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405238"
---
# <a name="preview-and-debug-infopath-form-templates-with-code"></a>预览和调试包含代码的 InfoPath 表单模板

使用带有 Visual Studio 2008 的 Microsoft InfoPath，您可以通过在预览模式下运行表单代码来进行调试。在开始调试表单代码时，系统将对项目进行编译，InfoPath 将在 InfoPath 预览窗口中显示表单。当遇到设置了断点的代码行时，焦点将移动到代码编辑器。当越过断点继续调试时，焦点将移回预览窗口。关闭预览窗口时调试也将停止。
  
还可以修改表单模板的表单选项，以便使用特定的用户角色或示例数据文件或者通过指定表单将发布到的域来进行预览和调试。 
  
> [!NOTE]
> 在部署表单模板之后，不能在运行时从 Visual Studio 2008 调试这些表单模板。 这适用于只与 InfoPath 兼容的表单模板以及与 InfoPath 和使用 InfoPath Forms Services 的 Web 浏览器兼容的表单模板。 但是，可以在运行时通过代码将值记录到某个域，以帮助调试表单模板的业务逻辑。 有关如何执行此操作的信息，请参阅[将值记录到字段中进行调试](how-to-log-values-to-a-field-for-debugging.md)。 
  
## <a name="debugging-in-preview-mode"></a>在预览模式下调试

### <a name="to-debug-an-infopath-project-in-preview-mode"></a>在预览模式下调试 InfoPath 项目

1. 在 Visual Studio 2008 中创建或打开 InfoPath 托管代码表单模板。
    
2. 在代码编辑器中，通过单击要插入断点的代码行左侧的灰条在表单代码中设置一个或多个断点。
    
    将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。
    
3. 在“调试”**** 菜单上，单击“启动调试”****，或按 F5。
    
    将对项目进行编译，并在预览窗口中显示表单。
    
4. 与表单进行交互，直到遇到包含断点的一行代码。
    
    焦点将返回到代码编辑器。
    
5. 在“调试”**** 菜单上，单击“继续”****，或按 F5。
    
6. 完成调试后，关闭预览窗口，或在“调试”**** 菜单上，单击“停止调试”****。
    
> [!NOTE]
> 要在使用需要完全信任的对象模型成员时调试 InfoPath 托管代码表单模板，必须按照[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)中的说明配置你的表单模板。 
  
## <a name="using-a-sample-data-file"></a>使用示例数据文件

默认情况下，调试和预览使用在创建表单模板时创建的 template.xml 文件。您可以创建自己的数据文件，并按照以下过程之一指定在预览或调试过程中使用该文件。 
  
### <a name="to-specify-a-sample-data-file-to-use-while-debugging-or-previewing-in-visual-studio-tools-for-applications"></a>指定在 Visual Studio Tools for Applications 中调试或预览时使用的示例数据文件

1. 要查看 template.xml，请在 InfoPath 设计模式下打开表单模板。
    
2. 依次单击“文件”**** 选项卡、“保存”****、“将表单模板另存为”**** 和“源文件”****。
    
3. 将表单模板文件保存到一个文件夹中，然后在文本编辑器中打开该 template.xml 文件。
    
4. 利用要使用的示例数据创建并保存与 template.xml 具有相同结构的文件。
    
5. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
6. 单击“表单选项”**** 对话框中的“预览”**** 类别，然后在“示例数据”**** 下的“文件位置”**** 框中指定您创建的示例数据文件。 
    
## <a name="specifying-a-user-role-to-use-while-debugging-or-previewing"></a>指定调试或预览过程中使用的用户角色

如果正在使用的表单已定义了用户角色，则可以指定在调试或预览表单时使用的用户角色。有关如何定义用户角色的信息，请在 InfoPath 帮助中搜索"用户角色"。
  
> [!NOTE]
> The option to specify a user role is not available if the compatibility setting for your form template is set to **Web Browser Form**. User roles are not supported in form templates opened in the browser from InfoPath Forms Services. 
  
### <a name="to-specify-a-role-to-use-while-debugging-or-previewing"></a>指定在调试或预览过程中使用的角色

1. 如果您在 Visual Studio 2008 中工作，请切换到 InfoPath Designer。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 单击“表单选项”**** 对话框中的“预览”**** 类别，然后在“以以下角色预览”**** 下拉框中指定要使用的用户角色。 
    
## <a name="specifying-a-domain-to-use-while-debugging-or-previewing"></a>指定在调试或预览过程中使用的域

可以预览表单，就像该表单已发布到某个特定域一样。仅当表单模板的安全级别明确设置为“域”**** 时，此设置才适用。
  
### <a name="to-specify-a-domain-to-use-while-debugging-or-previewing"></a>指定在调试或预览过程中要使用的域

1. 如果您在 Visual Studio 2008 中工作，请切换到 InfoPath Designer。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 单击“表单选项”**** 对话框中的“预览”**** 类别，然后在“域”**** 框中指定要在预览和调试过程中使用的域。 
    
4. 单击“表单选项”**** 对话框中的“安全和信任”**** 类别，清除“自动确定安全级别”**** 复选框，然后单击“域”****。
    

