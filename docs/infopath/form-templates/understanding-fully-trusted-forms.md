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
# <a name="understanding-fully-trusted-forms"></a><span data-ttu-id="1f6eb-104">了解完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-104">Understanding Fully Trusted Forms</span></span>

<span data-ttu-id="1f6eb-p102">InfoPath 提供了创建完全信任的表单的功能，这些表单的安全权限更高，可以访问用户计算机上的系统资源和其他组件。本文介绍什么是完全信任的表单以及为什么要使用这种表单，还介绍如何通过手动转换和注册标准表单或通过对标准表单进行数字签名来创建完全信任的表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p102">InfoPath provides the ability to create fully trusted forms, which are forms that have greater security permissions and can access system resources and other components on a user's computer. This article describes what a fully trusted form is, and why it is used, and create a fully trusted form by manually converting and registering a standard form, or by digitally signing a standard form.</span></span>

<span data-ttu-id="1f6eb-p103">InfoPath 表单模板可用各种安全级别来部署。所用级别取决于您希望表单具有的对外部资源的访问级别。默认情况下，系统会限制 InfoPath 表单模板访问系统资源，也不允许其使用未被标记为可安全编写脚本的任何软件组件。不过，可以替代此行为，使表单能够访问系统资源和其他外部资源，包括未被标记为可安全编写脚本的软件组件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p103">InfoPath form templates can be deployed with varying levels of security. The level you use is dictated by the level of access to external resources that you want a form to have. By default, InfoPath form templates are restricted from accessing system resources and are not allowed to use any software components that are not marked as safe for scripting. However, this behavior can be overridden so that a form can access system resources and other external resources, including software components that are not marked as safe for scripting.</span></span>
  
<span data-ttu-id="1f6eb-111">对于要使用的表单，InfoPath 必须能够访问表单所基于的表单模板。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-111">For a form to be used, InfoPath must be able to access the form template that the form is based on.</span></span> <span data-ttu-id="1f6eb-112">创建表单模板时，InfoPath 会在表单定义 (.xsf) 文件（其中包含该表单模板位置的 URL）中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-112">When you create a form template, InfoPath creates an entry in the form definition (.xsf) file that contains the URL of the location of the form template.</span></span> <span data-ttu-id="1f6eb-113">基于 URL 的表单称为*沙盒表单*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-113">A URL-based form is said to be *sandboxed*.</span></span> <span data-ttu-id="1f6eb-114">当用户进行填写时，会将表单添加在本地缓存中并拒绝表单访问系统资源。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-114">When a user fills it out, the form is added in a local cache and denied access to system resources.</span></span> <span data-ttu-id="1f6eb-115">此类表单将从打开它的域中继承权限。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-115">This kind of form inherits its permissions from the domain in which it is opened.</span></span> 
  
<span data-ttu-id="1f6eb-p105">但您可以修改表单，使其基于统一资源名称 (URN)，从而允许其访问系统资源。此类表单称为*完全信任的表单*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p105">However, you can modify a form so that it is based on a Uniform Resource Name (URN) instead, which allows access to system resources. Forms of this kind are said to be *fully trusted*.</span></span> 
  
## <a name="why-use-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-118">为什么使用完全信任的表单？</span><span class="sxs-lookup"><span data-stu-id="1f6eb-118">Why Use a Fully Trusted Form?</span></span>

<span data-ttu-id="1f6eb-p106">与沙盒表单相比，完全信任的表单具有一组更高级别的权限。例如，完全信任的表单可以包含使用外部对象来访问系统资源的编程代码，可以使用未被标记为可安全编写脚本的软件组件或 Microsoft ActiveX 控件，还可以使用 .NET 程序集提供的自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p106">Fully trusted forms have a better set of permissions than sandboxed forms. For example, they can contain programming code that uses external objects for accessing system resources, they can use software components or Microsoft ActiveX controls that are not marked as safe for scripting, and they can use custom business logic provided by .NET assemblies.</span></span>
  
<span data-ttu-id="1f6eb-p107">此外，InfoPath 对象模型的某些成员设置为安全级别 3，这意味着它们只能在完全信任的表单中使用。例如，为了访问 Microsoft Office **CommandBars** 对象，您可以使用 InfoPath [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) 类的 [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 属性设置对该对象的引用。由于此属性设置为安全级别 3，因此它不能用于非完全信任的表单中。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p107">In addition, some members of the InfoPath object model are set to security level 3, which means that they can only be used in a fully trusted form. For example, to access the Microsoft Office **CommandBars** object, you use the [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) property of the InfoPath [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) class to set a reference to it. Because this property is set to security level 3, it cannot be used in a form that is not fully trusted.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f6eb-124">在非完全信任的表单中使用 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) 类的 [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 属性或安全级别为 3 的其他任何对象模型成员都将导致"权限被拒绝"错误。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-124">Using the [CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) property of the [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) class, or any other object model member that has a security level of 3, in a form that is not fully trusted will result in a "permission denied" error.</span></span> 
  
## <a name="what-makes-a-form-fully-trusted"></a><span data-ttu-id="1f6eb-125">如何使表单成为完全信任的表单？</span><span class="sxs-lookup"><span data-stu-id="1f6eb-125">What Makes a Form Fully Trusted?</span></span>

<span data-ttu-id="1f6eb-126">创建和使用完全信任的表单时必须执行以下操作，其中涉及 InfoPath 用户界面和表单文件：</span><span class="sxs-lookup"><span data-stu-id="1f6eb-126">The following actions, involving both the InfoPath user interface and the form files, are required to create and use a fully trusted form:</span></span>
  
- <span data-ttu-id="1f6eb-p108">Enabling InfoPath to allow for the use of fully trusted forms on the **Trusted Publishers** category of the **Trust Center** dialog box. This option must be enabled for users to open fully trusted forms.</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p108">Enabling InfoPath to allow for the use of fully trusted forms on the **Trusted Publishers** category of the **Trust Center** dialog box. This option must be enabled for users to open fully trusted forms.</span></span> 
    
- <span data-ttu-id="1f6eb-129">使用 InfoPath **Application** 对象的 **RegisterSolution** 方法在目标计算机上注册完全信任的表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-129">Registering the fully trusted form on the target computer by using the **RegisterSolution** method of the InfoPath **Application** object.</span></span> 
    
## <a name="creating-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-130">创建完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-130">Creating a Fully Trusted Form</span></span>

- <span data-ttu-id="1f6eb-131">可以手动创建表单，其中包括直接修改某些表单文件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-131">You can create the form manually, which involves modifying some of the form files directly.</span></span>
    
- <span data-ttu-id="1f6eb-132">可对表单模板进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-132">You can digitally sign the form template.</span></span>
    
### <a name="manually-creating-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-133">手动创建完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-133">Manually Creating a Fully Trusted Form</span></span>

#### <a name="to-manually-create-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-134">手动创建完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-134">To manually create a fully trusted form</span></span>

1. <span data-ttu-id="1f6eb-135">创建要完全信任的表单模板的备份副本。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-135">Make a backup copy of the form template that you want to make fully trusted.</span></span>
    
2. <span data-ttu-id="1f6eb-136">在 InfoPath 中打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-136">Open the form template in InfoPath.</span></span>
    
3. <span data-ttu-id="1f6eb-137">依次单击“文件”\*\*\*\* 选项卡、“发布”\*\*\*\* 和“导出源文件”\*\*\*\*，将表单源文件保存到硬盘上的一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-137">Save the form source files to a folder on your hard disk by clicking the **File** tab, clicking **Publish**, and then clicking **Export Source Files**.</span></span>
    
4. <span data-ttu-id="1f6eb-138">指定保存表单源文件的文件夹，单击“确定”\*\*\*\*，然后退出 InfoPath 设计器。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-138">Specify the folder in which to save the form source files, click **OK**, and then exit the InfoPath designer.</span></span>
    
5. <span data-ttu-id="1f6eb-139">在提取表单文件的文件夹中，使用 Microsoft 记事本之类的文本编辑器，打开默认情况下名为  `manifest.xsf` 的表单定义 (.xsf) 文件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-139">In the folder in which you extracted the form files, open the form definition (.xsf) file, named  `manifest.xsf` by default, in a text editor such as Microsoft Notepad.</span></span> 
    
6. <span data-ttu-id="1f6eb-140">为 .xsf 文件中的 **xDocumentClass** 元素添加以下属性：</span><span class="sxs-lookup"><span data-stu-id="1f6eb-140">Add the following attributes to the **xDocumentClass** element in the .xsf file:</span></span> 
   
   `requireFullTrust="yes"`<br/>
   `name="urn:MyForm:MyCompany`

   > [!NOTE]
   > 用于 URN 的值可以是任何类型的字符串值，只要此值唯一。 `urn:` 前缀后面必须至少有两个值，这两个值之间必须用冒号分隔。 <span data-ttu-id="1f6eb-143">此外，URN 不应超过 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-143">In addition, the URN should not exceed 255 characters.</span></span> 
  
7. <span data-ttu-id="1f6eb-144">保存并关闭 .xsf 文件，然后使用记事本之类的文本编辑器，打开默认情况下名为  `Template.xml` 的 XML 模板 (.xml) 文件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-144">Save and close the .xsf file, and then open the XML template (.xml) file that is named  `Template.xml` by default, in a text editor such as Notepad.</span></span> 
    
8. <span data-ttu-id="1f6eb-145">从  \*\*\*\* 处理指令中删除 `mso-infoPathSolution` 属性，并将其替换为您在步骤 6 中对 .xsf 文件使用的同一 **name** 属性。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-145">Remove the **href** attribute from the  `mso-infoPathSolution` processing instruction and replace it with the same **name** attribute that you used in step 6 for the .xsf file.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="1f6eb-146">在 .xsf 文件和 XML 模板文件中用于 **name** 属性的 URN 值必须相同。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-146">The URN values that are used for the **name** attribute must be the same in both the .xsf file and XML template file.</span></span> 
  
9. <span data-ttu-id="1f6eb-147">保存并关闭 XML 模板文件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-147">Save and close the XML template file.</span></span>
    
10. <span data-ttu-id="1f6eb-148">使用 makecab.exe 之类的工具将文件重新打包为 .xsn CAB 格式。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-148">Repackage the files into the .xsn CAB format with a tool such as makecab.exe.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f6eb-p110">尽管 InfoPath 表单设计器支持将表单文件重新打包为 .xsn 文件，但此操作会将表单还原为基于 URL 的表单。因此，您必须手动将文件重新打包，以免覆盖您对表单文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p110">Although InfoPath form designer supports repackaging the form files into an .xsn file, doing this will revert the form to a URL-based form. For this reason, you must repackage the files manually to avoid overwriting your changes to the form files.</span></span> 
  
11. <span data-ttu-id="1f6eb-p111">使用 InfoPath **Application** 对象的 **RegisterSolution** 方法创建自定义安装程序，以安装完全信任的表单。执行此操作的一个简单方法是，创建一个使用以下代码行（采用 Microsoft JScript 或 VBScript 语法）的脚本文件：</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p111">Create a custom installation program by using the **RegisterSolution** method of the InfoPath **Application** object to install the fully trusted form. A simple way to do this is to create a script file that uses the following lines of code (in either Microsoft JScript or VBScript syntax):</span></span> 
    
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
> <span data-ttu-id="1f6eb-p112">虽然此示例使用的是简单脚本文件，但您也可以使用更稳固的安装机制，如 Microsoft Windows Installer (.msi) 文件。不过，一定要使用 **RegisterSolution** 方法在目标计算机上正确安装完全信任的表单。若要从 Visual Basic 或 Visual Studio 中访问 InfoPath **Application** 对象的 **RegisterSolution** 方法，可设置对 Microsoft InfoPath 3.0 类型库的引用，该类型库由安装在 C:\Program Files\Microsoft Office\Office14 文件夹中的 IPEDITOR.dll 提供。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p112">Although this example uses a simple script file, you can also use a more robust installation mechanism such as Microsoft Windows Installer (.msi) files. Be sure, however, to use the **RegisterSolution** method to correctly install the fully trusted form on the target computer. To access the **RegisterSolution** method of the InfoPath the **Application** object from Visual Basic or Visual Studio, set a reference to the Microsoft InfoPath 3.0 Type Library, which is provided by IPEDITOR.dll that is installed in the C:\Program Files\Microsoft Office\Office14 folder.</span></span> 
  
<span data-ttu-id="1f6eb-156">如果您不得不删除完全信任的表单，则可以使用 **Application** 对象的 **UnregisterSolution** 方法，如下面的 JScript 和 VBScript 示例所示。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-156">If you have to remove a fully trusted form, you can use the **UnregisterSolution** method of the **Application** object as shown in the following JScript and VBScript examples.</span></span> 
    
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

### <a name="digitally-signing-a-form-template-to-create-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-157">对表单模板进行数字签名以创建完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-157">Digitally Signing a Form Template to Create a Fully Trusted Form</span></span>

<span data-ttu-id="1f6eb-158">对表单模板进行数字签名使你可以通过电子邮件或在 Web 服务器（如运行 Microsoft SharePoint Foundation 的服务器）上部署完全信任的表单模板。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-158">Digitally signing a form template enables you to deploy a fully trusted form template by email or on a Web server, such as a server that is running Microsoft SharePoint Foundation.</span></span> <span data-ttu-id="1f6eb-159">使用以下三个过程中的步骤可使表单成为完全信任的表单：为表单指定完全信任选项、对表单进行数字签名，然后发布表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-159">Use the steps in the following three procedures to make a form fully trusted by specifying full trust for the form, signing it digitally, and then publishing it.</span></span>
  
#### <a name="to-digitally-sign-a-form-template"></a><span data-ttu-id="1f6eb-160">对表单模板进行数字签名</span><span class="sxs-lookup"><span data-stu-id="1f6eb-160">To digitally sign a form template</span></span>

1. <span data-ttu-id="1f6eb-161">在 InfoPath 设计器中打开表单，单击“文件”\*\*\*\* 选项卡，然后单击“信息”\*\*\*\* 选项卡上的“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-161">Open the form in the InfoPath designer, click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
2. <span data-ttu-id="1f6eb-162">在“表单选项”\*\*\*\* 对话框中单击“安全和信任”\*\*\*\* 类别。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-162">In the **Form Options** dialog box, click the **Security and Trust** category.</span></span> 
    
3. <span data-ttu-id="1f6eb-163">清除对“自动确定安全级别(推荐)”\*\*\*\* 的选择。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-163">Clear the selection for **Automatically determine security level (recommended)**.</span></span>
    
4. <span data-ttu-id="1f6eb-164">选择“完全信任(表单有权访问用户计算机上的文件和设置)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-164">Select **Full Trust (the form has access to files and settings on the user's computer)**.</span></span>
    
5. <span data-ttu-id="1f6eb-165">在“表单模板签名”\*\*\*\* 下，选择“对此表单进行签名”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-165">Under **Form Template Signature**, select **Sign this form template**.</span></span>
    
6. <span data-ttu-id="1f6eb-166">单击“选择证书”\*\*\*\*，选择之前从受信任证书供应商处下载并进行安装的证书。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-166">Click **Select Certificate** to select a certificate that was previously downloaded and installed from a trusted certificate provider.</span></span> 
    
7. <span data-ttu-id="1f6eb-167">单击"确定"两次，以完全退出。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-167">Click OK two times to exit completely.</span></span>
    
#### <a name="to-publish-the-form-template-to-a-sharepoint-document-library"></a><span data-ttu-id="1f6eb-168">将表单模板发布到 SharePoint 文档库</span><span class="sxs-lookup"><span data-stu-id="1f6eb-168">To publish the form template to a SharePoint Document Library</span></span>

1. <span data-ttu-id="1f6eb-169">单击“文件”\*\*\*\* 选项卡，然后依次单击“发布”\*\*\*\* 和“SharePoint Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-169">Click the **File** tab, click **Publish**, and then click **SharePoint Server**.</span></span>
    
2. <span data-ttu-id="1f6eb-170">按照“发布向导”\*\*\*\* 中的说明操作，将表单模板发布到新的或现有的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-170">Follow the instructions in the **Publishing Wizard** to publish the form template to a new or existing SharePoint document library.</span></span> 
    
#### <a name="to-a-create-a-form-that-is-based-on-your-fully-trusted-digitally-signed-form-template"></a><span data-ttu-id="1f6eb-171">基于完全信任且已进行数字签名的表单模板创建表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-171">To a create a form that is based on your fully trusted, digitally signed form template</span></span>

1. <span data-ttu-id="1f6eb-172">在 SharePoint 文档库中，单击“填写表单”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-172">In the SharePoint document library, click **Fill Out the Form**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="1f6eb-p114">After publishing the form template to a SharePoint document library using the **Publishing Wizard**, the template is not displayed as an item in the form library. When you create a form in that document library, the template will be used by default as the template for the new form.</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p114">After publishing the form template to a SharePoint document library using the **Publishing Wizard**, the template is not displayed as an item in the form library. When you create a form in that document library, the template will be used by default as the template for the new form.</span></span> 
  
2. <span data-ttu-id="1f6eb-p115">If the default form template was digitally signed, InfoPath displays a security warning about the digitally signed form template. Select **Always trust files from this publisher and open them automatically**, and then click **Open**.</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p115">If the default form template was digitally signed, InfoPath displays a security warning about the digitally signed form template. Select **Always trust files from this publisher and open them automatically**, and then click **Open**.</span></span>
    
## <a name="using-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-177">使用完全信任的表单</span><span class="sxs-lookup"><span data-stu-id="1f6eb-177">Using a Fully Trusted Form</span></span>

<span data-ttu-id="1f6eb-p116">使用完全信任的表单与使用标准表单非常类似。仅有的显著差别在于完全信任的表单可以访问受限制的资源，并且不再显示警告。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p116">Using a fully trusted form is very similar to using a standard form. The only significant differences are that the form can access restricted resources and warnings will no longer be displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f6eb-p117">To enable InfoPath to use a fully trusted form, users must ensure that the **Allow fully trusted forms to run on my computer** check box is selected on the **Trusted Publishers** category of the **Trust Center** dialog box. To open the **Trust Center** dialog box, click the **File** tab, click **Options** (below the **InfoPath** tab), click **Trust Center**, and then click **Trust Center Settings**.</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p117">To enable InfoPath to use a fully trusted form, users must ensure that the **Allow fully trusted forms to run on my computer** check box is selected on the **Trusted Publishers** category of the **Trust Center** dialog box. To open the **Trust Center** dialog box, click the **File** tab, click **Options** (below the **InfoPath** tab), click **Trust Center**, and then click **Trust Center Settings**.</span></span> 
  
<span data-ttu-id="1f6eb-182">可从“填写表单”\*\*\*\* 对话框的 InfoPath 中打开完全信任的表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-182">A fully trusted form can be opened in InfoPath from the **Fill Out a Form** dialog box.</span></span> 
  
<span data-ttu-id="1f6eb-183">当您单击“填写表单”\*\*\*\* 任务窗格中的“其他表单”\*\*\*\* 或单击“文件”\*\*\*\* 菜单上的“填写表单”\*\*\*\* 时，将打开“填写表单”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-183">The **Fill Out a Form** dialog box opens when you click **More Forms** in the **Fill Out a Form** task pane, or you click **Fill Out a Form** on the **File** menu.</span></span> 
  
### <a name="making-changes-to-a-fully-trusted-form"></a><span data-ttu-id="1f6eb-184">对完全信任的表单进行更改</span><span class="sxs-lookup"><span data-stu-id="1f6eb-184">Making Changes to a Fully Trusted Form</span></span>

<span data-ttu-id="1f6eb-p118">如果您只需对 .xsn 文件进行更改，则可在完成更改后，让用户用新文件替换其现有的 .xsn 文件。用户将不必使用自定义安装程序重新安装该文件。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p118">If you only have to make changes to the .xsn file, you can have users replace their existing .xsn file with the new one after the changes are made. They will not have to reinstall it by using a custom installation program.</span></span>
  
<span data-ttu-id="1f6eb-187">但是，如果您要对 .xsn 文件包含的表单文件进行更改，则必须按照前面介绍的过程对这些表单文件重新打包，然后让用户重新安装完全信任的表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-187">However, if you are making changes to the form files that the .xsn file contains, you must repackage the files, as explained earlier, and then have users reinstall the fully trusted form.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f6eb-188">最佳方法是从 InfoPath Designer 中将表单模板重新保存为 .xsn 格式，然后按照本文中的步骤创建完全信任的表单。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-188">The best approach is to save the form template back to the .xsn format from the InfoPath designer, and then follow the steps in this article to create a fully trusted form.</span></span> 
  
## <a name="conclusion"></a><span data-ttu-id="1f6eb-189">结论</span><span class="sxs-lookup"><span data-stu-id="1f6eb-189">Conclusion</span></span>

<span data-ttu-id="1f6eb-p119">根据您的业务要求以及用户的需要，您可能必须创建一个比标准 InfoPath 表单拥有一组更高权限的表单。InfoPath 提供了修改表单的功能，使表单可以访问系统资源和未被标记为可安全编写脚本的其他外部资源。此操作可以手动完成，方法是修改表单模板包含的表单文件并运行安装脚本，或者对表单模板进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="1f6eb-p119">Depending on your business requirements and the needs of your users, you may have to create a form that has a higher set of permissions than the standard InfoPath form. InfoPath provides the ability to modify a form so that it can access system resources and other external resources that are not marked as safe for scripting. This can be done manually by making modifications to the form files that a form template contains and running an installation script, or by digitally signing the form template.</span></span>
  

