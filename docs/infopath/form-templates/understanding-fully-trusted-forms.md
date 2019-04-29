---
title: 了解完全信任的表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 64d62990-6275-edef-c639-b6ba8d10c38c
description: InfoPath 提供了创建完全信任的表单的功能，这些表单的安全权限更高，可以访问用户计算机上的系统资源和其他组件。本文介绍什么是完全信任的表单以及为什么要使用这种表单，还介绍如何通过手动转换和注册标准表单或通过对标准表单进行数字签名来创建完全信任的表单。
ms.openlocfilehash: 04560e0c844d6a6ff681fd366ca7da2e4db36ba1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430390"
---
# <a name="understanding-fully-trusted-forms"></a>了解完全信任的表单

InfoPath 提供了创建完全信任的表单的功能，这些表单的安全权限更高，可以访问用户计算机上的系统资源和其他组件。本文介绍什么是完全信任的表单以及为什么要使用这种表单，还介绍如何通过手动转换和注册标准表单或通过对标准表单进行数字签名来创建完全信任的表单。

InfoPath 表单模板可用各种安全级别来部署。所用级别取决于您希望表单具有的对外部资源的访问级别。默认情况下，系统会限制 InfoPath 表单模板访问系统资源，也不允许其使用未被标记为可安全编写脚本的任何软件组件。不过，可以替代此行为，使表单能够访问系统资源和其他外部资源，包括未被标记为可安全编写脚本的软件组件。
  
对于要使用的表单，InfoPath 必须能够访问表单所基于的表单模板。 创建表单模板时，InfoPath 会在表单定义 (.xsf) 文件（其中包含该表单模板位置的 URL）中创建一个条目。 基于 URL 的表单称为*沙盒表单*。 当用户进行填写时，会将表单添加在本地缓存中并拒绝表单访问系统资源。 此类表单将从打开它的域中继承权限。 
  
但您可以修改表单，使其基于统一资源名称 (URN)，从而允许其访问系统资源。此类表单称为*完全信任的表单*。 
  
## <a name="why-use-a-fully-trusted-form"></a>为什么使用完全信任的表单？

与沙盒表单相比，完全信任的表单具有一组更高级别的权限。例如，完全信任的表单可以包含使用外部对象来访问系统资源的编程代码，可以使用未被标记为可安全编写脚本的软件组件或 Microsoft ActiveX 控件，还可以使用 .NET 程序集提供的自定义业务逻辑。
  
此外，InfoPath 对象模型的某些成员设置为安全级别 3，这意味着它们只能在完全信任的表单中使用。例如，为了访问 Microsoft Office **CommandBars** 对象，您可以使用 InfoPath [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) 类的 [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 属性设置对该对象的引用。由于此属性设置为安全级别 3，因此它不能用于非完全信任的表单中。 
  
> [!NOTE]
> 在非完全信任的表单中使用 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) 类的 [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 属性或安全级别为 3 的其他任何对象模型成员都将导致"权限被拒绝"错误。 
  
## <a name="what-makes-a-form-fully-trusted"></a>如何使表单成为完全信任的表单？

创建和使用完全信任的表单时必须执行以下操作，其中涉及 InfoPath 用户界面和表单文件：
  
- Enabling InfoPath to allow for the use of fully trusted forms on the **Trusted Publishers** category of the **Trust Center** dialog box. This option must be enabled for users to open fully trusted forms. 
    
- 使用 InfoPath **Application** 对象的 **RegisterSolution** 方法在目标计算机上注册完全信任的表单。 
    
## <a name="creating-a-fully-trusted-form"></a>创建完全信任的表单

- 可以手动创建表单，其中包括直接修改某些表单文件。
    
- 可对表单模板进行数字签名。
    
### <a name="manually-creating-a-fully-trusted-form"></a>手动创建完全信任的表单

#### <a name="to-manually-create-a-fully-trusted-form"></a>手动创建完全信任的表单

1. 创建要完全信任的表单模板的备份副本。
    
2. 在 InfoPath 中打开表单模板。
    
3. 依次单击“文件”**** 选项卡、“发布”**** 和“导出源文件”****，将表单源文件保存到硬盘上的一个文件夹中。
    
4. 指定保存表单源文件的文件夹，单击“确定”****，然后退出 InfoPath 设计器。
    
5. 在提取表单文件的文件夹中，使用 Microsoft 记事本之类的文本编辑器，打开默认情况下名为  `manifest.xsf` 的表单定义 (.xsf) 文件。 
    
6. 为 .xsf 文件中的 **xDocumentClass** 元素添加以下属性： 
   
   `requireFullTrust="yes"`<br/>
   `name="urn:MyForm:MyCompany`

   > [!NOTE]
   > 用于 URN 的值可以是任何类型的字符串值，只要此值唯一。 `urn:` 前缀后面必须至少有两个值，这两个值之间必须用冒号分隔。 此外，URN 不应超过 255 个字符。 
  
7. 保存并关闭 .xsf 文件，然后使用记事本之类的文本编辑器，打开默认情况下名为  `Template.xml` 的 XML 模板 (.xml) 文件。 
    
8. 从  **** 处理指令中删除 `mso-infoPathSolution` 属性，并将其替换为您在步骤 6 中对 .xsf 文件使用的同一 **name** 属性。 
    
   > [!NOTE]
   > 在 .xsf 文件和 XML 模板文件中用于 **name** 属性的 URN 值必须相同。 
  
9. 保存并关闭 XML 模板文件。
    
10. 使用 makecab.exe 之类的工具将文件重新打包为 .xsn CAB 格式。
    
    > [!NOTE]
    > 尽管 InfoPath 表单设计器支持将表单文件重新打包为 .xsn 文件，但此操作会将表单还原为基于 URL 的表单。因此，您必须手动将文件重新打包，以免覆盖您对表单文件所做的更改。 
  
11. 使用 InfoPath **Application** 对象的 **RegisterSolution** 方法创建自定义安装程序，以安装完全信任的表单。执行此操作的一个简单方法是，创建一个使用以下代码行（采用 Microsoft JScript 或 VBScript 语法）的脚本文件： 
    
    ```js
        objIPApp = new ActiveXObject("InfoPath.Application"); 
        objIPApp.RegisterSolution("C:\\MyForms\\MyTrustedForm.xsn"); 
        objIPApp.Quit(); 
        objIPApp = null;
    ```
   
    ```vb
        Public Sub InstallForm()
            Dim objIPApp As Object
            ' Create a reference to the Application object.
            Set objIPApp = CreateObject("InfoPath.Application")
            ' Register the InfoPath form template.
            objIPApp.RegisterSolution ("C:\\My Forms\\MyFormTemplate.xsn")
            MsgBox "The InfoPath form template has been registered."
            Set objIPApp = Nothing
        End Sub
        
    ```

> [!NOTE] 
> 虽然此示例使用的是简单脚本文件，但您也可以使用更稳固的安装机制，如 Microsoft Windows Installer (.msi) 文件。不过，一定要使用 **RegisterSolution** 方法在目标计算机上正确安装完全信任的表单。若要从 Visual Basic 或 Visual Studio 中访问 InfoPath **Application** 对象的 **RegisterSolution** 方法，可设置对 Microsoft InfoPath 3.0 类型库的引用，该类型库由安装在 C:\Program Files\Microsoft Office\Office14 文件夹中的 IPEDITOR.dll 提供。 
  
如果您不得不删除完全信任的表单，则可以使用 **Application** 对象的 **UnregisterSolution** 方法，如下面的 JScript 和 VBScript 示例所示。 
    
```js
    objIPApp = new ActiveXObject("InfoPath.Application"); 
    objIPApp.UnregisterSolution("C:\\MyForms\\MyTrustedForm.xsn"); 
    objIPApp.Quit(); 
    objIPApp = null;
```

```vb
    Public Sub UninstallForm()
        Dim objIPApp As Object
        ' Create a reference to the Application object.
        Set objIPApp = CreateObject("InfoPath.Application")
        ' Unregister the InfoPath form template.
        objIPApp.UnregisterSolution ("C:\My Forms\MyFormTemplate.xsn")
        MsgBox ("The InfoPath form template has been unregistered.")
        Set objIPApp = Nothing
    End Sub
    
```

### <a name="digitally-signing-a-form-template-to-create-a-fully-trusted-form"></a>对表单模板进行数字签名以创建完全信任的表单

对表单模板进行数字签名使你可以通过电子邮件或在 Web 服务器（如运行 Microsoft SharePoint Foundation 的服务器）上部署完全信任的表单模板。 使用以下三个过程中的步骤可使表单成为完全信任的表单：为表单指定完全信任选项、对表单进行数字签名，然后发布表单。
  
#### <a name="to-digitally-sign-a-form-template"></a>对表单模板进行数字签名

1. 在 InfoPath 设计器中打开表单，单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
2. 在“表单选项”**** 对话框中单击“安全和信任”**** 类别。 
    
3. 清除对“自动确定安全级别(推荐)”**** 的选择。
    
4. 选择“完全信任(表单有权访问用户计算机上的文件和设置)”****。
    
5. 在“表单模板签名”**** 下，选择“对此表单进行签名”****。
    
6. 单击“选择证书”****，选择之前从受信任证书供应商处下载并进行安装的证书。 
    
7. 单击"确定"两次，以完全退出。
    
#### <a name="to-publish-the-form-template-to-a-sharepoint-document-library"></a>将表单模板发布到 SharePoint 文档库

1. 单击“文件”**** 选项卡，然后依次单击“发布”**** 和“SharePoint Server”****。
    
2. 按照“发布向导”**** 中的说明操作，将表单模板发布到新的或现有的 SharePoint 文档库。 
    
#### <a name="to-a-create-a-form-that-is-based-on-your-fully-trusted-digitally-signed-form-template"></a>基于完全信任且已进行数字签名的表单模板创建表单

1. 在 SharePoint 文档库中，单击“填写表单”****。
    
   > [!NOTE]
   > After publishing the form template to a SharePoint document library using the **Publishing Wizard**, the template is not displayed as an item in the form library. When you create a form in that document library, the template will be used by default as the template for the new form. 
  
2. If the default form template was digitally signed, InfoPath displays a security warning about the digitally signed form template. Select **Always trust files from this publisher and open them automatically**, and then click **Open**.
    
## <a name="using-a-fully-trusted-form"></a>使用完全信任的表单

使用完全信任的表单与使用标准表单非常类似。仅有的显著差别在于完全信任的表单可以访问受限制的资源，并且不再显示警告。
  
> [!NOTE]
> To enable InfoPath to use a fully trusted form, users must ensure that the **Allow fully trusted forms to run on my computer** check box is selected on the **Trusted Publishers** category of the **Trust Center** dialog box. To open the **Trust Center** dialog box, click the **File** tab, click **Options** (below the **InfoPath** tab), click **Trust Center**, and then click **Trust Center Settings**. 
  
可从“填写表单”**** 对话框的 InfoPath 中打开完全信任的表单。 
  
当您单击“填写表单”**** 任务窗格中的“其他表单”**** 或单击“文件”**** 菜单上的“填写表单”**** 时，将打开“填写表单”**** 对话框。 
  
### <a name="making-changes-to-a-fully-trusted-form"></a>对完全信任的表单进行更改

如果您只需对 .xsn 文件进行更改，则可在完成更改后，让用户用新文件替换其现有的 .xsn 文件。用户将不必使用自定义安装程序重新安装该文件。
  
但是，如果您要对 .xsn 文件包含的表单文件进行更改，则必须按照前面介绍的过程对这些表单文件重新打包，然后让用户重新安装完全信任的表单。
  
> [!NOTE]
> 最佳方法是从 InfoPath Designer 中将表单模板重新保存为 .xsn 格式，然后按照本文中的步骤创建完全信任的表单。 
  
## <a name="conclusion"></a>结论

根据您的业务要求以及用户的需要，您可能必须创建一个比标准 InfoPath 表单拥有一组更高权限的表单。InfoPath 提供了修改表单的功能，使表单可以访问系统资源和未被标记为可安全编写脚本的其他外部资源。此操作可以手动完成，方法是修改表单模板包含的表单文件并运行安装脚本，或者对表单模板进行数字签名。
  

