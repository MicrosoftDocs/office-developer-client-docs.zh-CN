---
title: 添加事件处理程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- versionupgrade event [infopath 2007],handling events [InfoPath 2007],Changing event [InfoPath 2007],InfoPath 2007, adding event handlers,Changed event [InfoPath 2007],ContextChanged event [InfoPath 2007],Click event [InfoPath 2007],events [InfoPath 2007], adding event handlers,Sign event [InfoPath 2007],ViewSwitched event [InfoPath 2007],event handling [InfoPath 2007],Merge event [InfoPath 2007],Validating event [InfoPath 2007],Submit event [InfoPath 2007],Save event [InfoPath 2007],Loading event [InfoPath 2007]
localization_priority: Normal
ms.assetid: d69393fb-fb5a-4edb-abc0-38f5d7e80bcc
description: 本主题介绍使用 Visual Studio 2008 向 Microsoft InfoPath 托管代码表单模板中添加事件处理程序的过程。若要向表单模板中添加事件处理程序，需要先在 InfoPath Designer 中打开该表单模板，然后为要编写代码的事件选择适当的用户界面命令。在 InfoPath Designer 中为事件选择命令后，焦点会自动切换到 Visual Studio 2008 代码编辑器中该事件的框架事件处理程序。
ms.openlocfilehash: 5bac409fb859337b82bf6567dd4636e6d384ba59
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774017"
---
# <a name="add-an-event-handler"></a>添加事件处理程序

本主题介绍使用 Visual Studio 2008 向 Microsoft InfoPath 托管代码表单模板中添加事件处理程序的过程。若要向表单模板中添加事件处理程序，需要先在 InfoPath Designer 中打开该表单模板，然后为要编写代码的事件选择适当的用户界面命令。在 InfoPath Designer 中为事件选择命令后，焦点会自动切换到 Visual Studio 2008 代码编辑器中该事件的框架事件处理程序。
  
> [!IMPORTANT]
> 应始终使用 InfoPath Designer 用户界面来添加事件处理程序。使用用户界面添加事件处理程序会在表单模板项目的 FormCode.cs 或 FormCode.vb 文件的 **InternalStartup** 方法中生成事件绑定代码。您不应自己创建 **InternalStartup** 方法或在其中添加其他任何代码。 
  
### <a name="add-an-event-handler-for-the-click-event-of-a-button-control"></a>为按钮控件的 Click 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板，然后向该表单中添加一个“按钮”**** 控件。 
    
2. 单击此按钮，然后在功能区的“属性”**** 选项卡上单击“自定义代码”****。
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) 事件的框架事件处理程序。 
    
### <a name="add-an-event-handler-for-the-changing-validating-or-changed-event-of-a-field-or-group"></a>为域或组的 Changing、Validating 或 Changed 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 右键单击绑定到字段或组的数据输入控件，例如“文本框”**** 控件。 
    
3. 指向“编程”****，然后单击要为其创建事件处理程序的事件。 焦点将切换到 Visual Studio 2012 代码编辑器中 [Changing](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Changing.aspx)、[Validating](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Validating.aspx) 或 [Changed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Changed.aspx) 事件的框架事件处理程序。 
    
    > [!NOTE]
    > 如果表单模板的兼容性设置被设置为“Web 浏览器表单”****，则无法使用为 **Changing** 事件创建事件处理程序的命令。 这是因为在使用 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上发布到文档库的表单模板的业务逻辑中不支持 **Changing** 事件。 若要为 **Changing** 事件创建事件处理程序，必须在 InfoPath Designer 中将兼容性设置更改为“InfoPath 编辑器”****。 为此，请依次单击“文件”**** 选项卡、“表单选项”**** 和“兼容性”****，然后将“表单类型”**** 设置为“InfoPath 编辑器表单”****。 
  
### <a name="add-an-event-handler-for-the-loading-viewswitched-contextchanged-and-sign-events-of-a-form"></a>为表单的 Loading、ViewSwitched、ContextChanged 和 Sign 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 在功能区的“开发人员”**** 选项卡上，单击要为其编写事件处理程序的表单事件。 
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 、 [ViewSwitched](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ViewSwitched.aspx) 、 [ContextChanged](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ContextChanged.aspx) 或 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件的框架事件处理程序。 
    
    > [!NOTE]
    > 如果表单模板的兼容性设置被设置为“Web 浏览器表单”****，则无法使用为 [ContextChanged](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ContextChanged.aspx) 或 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件创建事件处理程序的命令。 这是因为在使用 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上发布到文档库的表单模板的业务逻辑中不支持这些事件。 若要为 [ContextChanged](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ContextChanged.aspx) 或 [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) 事件创建事件处理程序，必须在 InfoPath Designer 中将兼容性设置更改为“InfoPath 编辑器表单”****。 为此，请依次单击“文件”**** 选项卡、“表单选项”**** 和“兼容性”****，然后将“表单类型”**** 设置为“InfoPath 编辑器表单”****。 
  
### <a name="add-an-event-handler-for-the-submit-event-of-a-form"></a>为表单的 Submit 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 单击“文件”**** 选项卡，单击“信息”**** 选项卡上的“提交到”****，然后单击“提交选项”。
    
3. 单击“允许用户提交此表单”****，单击“使用代码执行自定义操作”****，然后单击“编辑代码”****。
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) 事件的框架事件处理程序。 
    
### <a name="add-an-event-handler-for-the-save-event-of-a-form"></a>为表单的 Save 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 单击“保存”**** 类别，选中“使用自定义代码保存”**** 复选框，然后单击“编辑”****。
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Save.aspx) 事件的框架事件处理程序。 
    
    > [!NOTE]
    > 如果表单模板的兼容性设置被设置为“InfoPath Forms Services”****，则无法使用“使用自定义代码保存”**** 复选框。 这是因为在使用 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上发布到文档库的表单模板的业务逻辑中不支持 [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Save.aspx) 事件。 若要为 [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Save.aspx) 事件创建事件处理程序，必须在 InfoPath Designer 中将兼容性设置更改为“InfoPath 编辑器表单”****。 为此，请依次单击“文件”**** 选项卡、“表单选项”**** 和“兼容性”****，然后将“表单类型”**** 设置为“InfoPath 编辑器表单”****。 
  
### <a name="add-an-event-handler-for-the-versionupgrade-event-of-a-form"></a>为表单的 VersionUpgrade 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 单击“版本控制”**** 类别，在“更新现有表单”**** 下拉框中选择“使用自定义事件”****，然后单击“编辑”****。
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Save.aspx) 事件的框架事件处理程序。 
    
### <a name="add-an-event-handler-for-the-merge-event-of-a-form"></a>为表单的 Merge 事件添加事件处理程序

1. 在 InfoPath Designer 中打开表单模板。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 单击“高级”**** 类别，单击“启用表单合并”**** 复选框，单击“使用自定义代码合并”**** 复选框，然后单击“编辑”****。
    
    焦点将切换到 Visual Studio 2008 代码编辑器中 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件的框架事件处理程序。 
    
    > [!NOTE]
    > 如果表单模板的兼容性设置被设置为“InfoPath Forms Services”****，则无法使用“启用表单合并”**** 复选框。 这是因为在使用 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上发布到文档库的表单模板的业务逻辑中不支持 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件。 若要为 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件创建事件处理程序，必须在 InfoPath Designer 中将兼容性设置更改为“InfoPath 编辑器表单”****。 为此，请依次单击“文件”**** 选项卡、“表单选项”**** 和“兼容性”****，然后将“表单类型”**** 设置为“InfoPath 编辑器表单”****。 
  
## <a name="see-also"></a>另请参阅



[演练：创建包含代码的基本表单模板](walkthrough-creating-a-basic-form-template-with-code.md)

