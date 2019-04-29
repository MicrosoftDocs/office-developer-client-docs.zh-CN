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
# <a name="preview-and-debug-infopath-form-templates-with-code"></a><span data-ttu-id="5acc5-108">预览和调试包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="5acc5-108">Preview and Debug InfoPath Form Templates with Code</span></span>

<span data-ttu-id="5acc5-p102">使用带有 Visual Studio 2008 的 Microsoft InfoPath，您可以通过在预览模式下运行表单代码来进行调试。在开始调试表单代码时，系统将对项目进行编译，InfoPath 将在 InfoPath 预览窗口中显示表单。当遇到设置了断点的代码行时，焦点将移动到代码编辑器。当越过断点继续调试时，焦点将移回预览窗口。关闭预览窗口时调试也将停止。</span><span class="sxs-lookup"><span data-stu-id="5acc5-p102">Microsoft InfoPath with Visual Studio 2012 enables debugging by running form code in preview mode. When you start debugging form code, your project is compiled and InfoPath displays your form in the InfoPath preview window. When a line of code that has a breakpoint set for it is encountered, the focus moves to the code editor. When you continue past a breakpoint, the focus moves back to the preview window. Debugging stops when you close the preview window.</span></span>
  
<span data-ttu-id="5acc5-114">还可以修改表单模板的表单选项，以便使用特定的用户角色或示例数据文件或者通过指定表单将发布到的域来进行预览和调试。</span><span class="sxs-lookup"><span data-stu-id="5acc5-114">You can also modify the form options of the form template to preview and debug using a specific user role, a sample data file, or by specifying the domain to which the form will be published.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5acc5-115">在部署表单模板之后，不能在运行时从 Visual Studio 2008 调试这些表单模板。</span><span class="sxs-lookup"><span data-stu-id="5acc5-115">It is not possible to debug form templates after they are deployed at run time from Visual Studio 2012.</span></span> <span data-ttu-id="5acc5-116">这适用于只与 InfoPath 兼容的表单模板以及与 InfoPath 和使用 InfoPath Forms Services 的 Web 浏览器兼容的表单模板。</span><span class="sxs-lookup"><span data-stu-id="5acc5-116">This includes form templates that are compatible only with InfoPath, as well as those that are compatible with InfoPath and the Web browser using InfoPath Forms Services.</span></span> <span data-ttu-id="5acc5-117">但是，可以在运行时通过代码将值记录到某个域，以帮助调试表单模板的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="5acc5-117">However, it is possible to log values to a field from code at run time to help with debugging a form template's business logic.</span></span> <span data-ttu-id="5acc5-118">有关如何执行此操作的信息，请参阅[将值记录到字段中进行调试](how-to-log-values-to-a-field-for-debugging.md)。</span><span class="sxs-lookup"><span data-stu-id="5acc5-118">For information about how to do that, see [Log Values to a Field for Debugging](how-to-log-values-to-a-field-for-debugging.md).</span></span> 
  
## <a name="debugging-in-preview-mode"></a><span data-ttu-id="5acc5-119">在预览模式下调试</span><span class="sxs-lookup"><span data-stu-id="5acc5-119">Debugging in Preview Mode</span></span>

### <a name="to-debug-an-infopath-project-in-preview-mode"></a><span data-ttu-id="5acc5-120">在预览模式下调试 InfoPath 项目</span><span class="sxs-lookup"><span data-stu-id="5acc5-120">To debug an InfoPath project in Preview Mode</span></span>

1. <span data-ttu-id="5acc5-121">在 Visual Studio 2008 中创建或打开 InfoPath 托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="5acc5-121">Create or open an InfoPath managed code form template in Visual Studio 2012.</span></span>
    
2. <span data-ttu-id="5acc5-122">在代码编辑器中，通过单击要插入断点的代码行左侧的灰条在表单代码中设置一个或多个断点。</span><span class="sxs-lookup"><span data-stu-id="5acc5-122">Set one or more breakpoints in your form code in the code editor by clicking the grey bar to the left of the line of code where you want to insert a breakpoint.</span></span>
    
    <span data-ttu-id="5acc5-123">将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="5acc5-123">A red circle is displayed and the line of code is highlighted to indicate that the runtime will pause at this breakpoint in your form code.</span></span>
    
3. <span data-ttu-id="5acc5-124">在“调试”\*\*\*\* 菜单上，单击“启动调试”\*\*\*\*，或按 F5。</span><span class="sxs-lookup"><span data-stu-id="5acc5-124">On the **Debug** menu, click **Start Debugging**; or press F5.</span></span>
    
    <span data-ttu-id="5acc5-125">将对项目进行编译，并在预览窗口中显示表单。</span><span class="sxs-lookup"><span data-stu-id="5acc5-125">The project will be compiled and the form is displayed in the preview window.</span></span>
    
4. <span data-ttu-id="5acc5-126">与表单进行交互，直到遇到包含断点的一行代码。</span><span class="sxs-lookup"><span data-stu-id="5acc5-126">Interact with the form until a line of code containing a breakpoint is encountered.</span></span>
    
    <span data-ttu-id="5acc5-127">焦点将返回到代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="5acc5-127">The focus returns to the code editor.</span></span>
    
5. <span data-ttu-id="5acc5-128">在“调试”\*\*\*\* 菜单上，单击“继续”\*\*\*\*，或按 F5。</span><span class="sxs-lookup"><span data-stu-id="5acc5-128">On the **Debug** menu, click **Continue**; or press F5.</span></span>
    
6. <span data-ttu-id="5acc5-129">完成调试后，关闭预览窗口，或在“调试”\*\*\*\* 菜单上，单击“停止调试”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-129">When you are finished debugging, close the preview window; or on the **Debug** menu, click **Stop Debugging**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5acc5-130">要在使用需要完全信任的对象模型成员时调试 InfoPath 托管代码表单模板，必须按照[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)中的说明配置你的表单模板。</span><span class="sxs-lookup"><span data-stu-id="5acc5-130">To debug an InfoPath managed code form template when using an object model member that requires full trust, you must configure your form template as described in [Preview and Debug Form Templates that Require Full Trust](how-to-preview-and-debug-form-templates-that-require-full-trust.md).</span></span> 
  
## <a name="using-a-sample-data-file"></a><span data-ttu-id="5acc5-131">使用示例数据文件</span><span class="sxs-lookup"><span data-stu-id="5acc5-131">Using a Sample Data File</span></span>

<span data-ttu-id="5acc5-p104">默认情况下，调试和预览使用在创建表单模板时创建的 template.xml 文件。您可以创建自己的数据文件，并按照以下过程之一指定在预览或调试过程中使用该文件。</span><span class="sxs-lookup"><span data-stu-id="5acc5-p104">By default, debugging and previewing uses the template.xml file that is created when a form template is created. You can create your own data file and specify to use it when previewing or debugging by using one of the following procedures.</span></span> 
  
### <a name="to-specify-a-sample-data-file-to-use-while-debugging-or-previewing-in-visual-studio-tools-for-applications"></a><span data-ttu-id="5acc5-134">指定在 Visual Studio Tools for Applications 中调试或预览时使用的示例数据文件</span><span class="sxs-lookup"><span data-stu-id="5acc5-134">To specify a sample data file to use while debugging or previewing in Visual Studio Tools for Applications</span></span>

1. <span data-ttu-id="5acc5-135">要查看 template.xml，请在 InfoPath 设计模式下打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="5acc5-135">To view template.xml, open the form template in InfoPath design mode.</span></span>
    
2. <span data-ttu-id="5acc5-136">依次单击“文件”\*\*\*\* 选项卡、“保存”\*\*\*\*、“将表单模板另存为”\*\*\*\* 和“源文件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-136">Click the **File** tab, click **Saving**, click **Save Form Template As**, and the click **Source Files**.</span></span>
    
3. <span data-ttu-id="5acc5-137">将表单模板文件保存到一个文件夹中，然后在文本编辑器中打开该 template.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5acc5-137">Save the form template files to a folder, and then open the template.xml file in a text editor.</span></span>
    
4. <span data-ttu-id="5acc5-138">利用要使用的示例数据创建并保存与 template.xml 具有相同结构的文件。</span><span class="sxs-lookup"><span data-stu-id="5acc5-138">Create and save a file with the same structure as template.xml with the sample data you want to use.</span></span>
    
5. <span data-ttu-id="5acc5-139">单击“文件”\*\*\*\* 选项卡，然后单击“信息”\*\*\*\* 选项卡上的“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-139">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
6. <span data-ttu-id="5acc5-140">单击“表单选项”\*\*\*\* 对话框中的“预览”\*\*\*\* 类别，然后在“示例数据”\*\*\*\* 下的“文件位置”\*\*\*\* 框中指定您创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="5acc5-140">Click the **Preview** category of the **Form Options** dialog box, and then under **Sample data** specify the sample data file you created in the **File location** box.</span></span> 
    
## <a name="specifying-a-user-role-to-use-while-debugging-or-previewing"></a><span data-ttu-id="5acc5-141">指定调试或预览过程中使用的用户角色</span><span class="sxs-lookup"><span data-stu-id="5acc5-141">Specifying a User Role to Use While Debugging or Previewing</span></span>

<span data-ttu-id="5acc5-p105">如果正在使用的表单已定义了用户角色，则可以指定在调试或预览表单时使用的用户角色。有关如何定义用户角色的信息，请在 InfoPath 帮助中搜索"用户角色"。</span><span class="sxs-lookup"><span data-stu-id="5acc5-p105">If the form you are working with has user roles defined for it, you can specify a user role to use while debugging or previewing your form. For information on how to define user roles, search InfoPath help for "user role".</span></span>
  
> [!NOTE]
> <span data-ttu-id="5acc5-p106">The option to specify a user role is not available if the compatibility setting for your form template is set to **Web Browser Form**. User roles are not supported in form templates opened in the browser from InfoPath Forms Services.</span><span class="sxs-lookup"><span data-stu-id="5acc5-p106">The option to specify a user role is not available if the compatibility setting for your form template is set to **Web Browser Form**. User roles are not supported in form templates opened in the browser from InfoPath Forms Services.</span></span> 
  
### <a name="to-specify-a-role-to-use-while-debugging-or-previewing"></a><span data-ttu-id="5acc5-146">指定在调试或预览过程中使用的角色</span><span class="sxs-lookup"><span data-stu-id="5acc5-146">To specify a role to use while debugging or previewing</span></span>

1. <span data-ttu-id="5acc5-147">如果您在 Visual Studio 2008 中工作，请切换到 InfoPath Designer。</span><span class="sxs-lookup"><span data-stu-id="5acc5-147">If you are working in Visual Studio 2012, switch to the InfoPath designer.</span></span>
    
2. <span data-ttu-id="5acc5-148">单击“文件”\*\*\*\* 选项卡，然后单击“信息”\*\*\*\* 选项卡上的“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-148">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
3. <span data-ttu-id="5acc5-149">单击“表单选项”\*\*\*\* 对话框中的“预览”\*\*\*\* 类别，然后在“以以下角色预览”\*\*\*\* 下拉框中指定要使用的用户角色。</span><span class="sxs-lookup"><span data-stu-id="5acc5-149">Click the **Preview** category of the **Form Options** dialog box, and then specify the user role to use in the **Preview as** drop-down box.</span></span> 
    
## <a name="specifying-a-domain-to-use-while-debugging-or-previewing"></a><span data-ttu-id="5acc5-150">指定在调试或预览过程中使用的域</span><span class="sxs-lookup"><span data-stu-id="5acc5-150">Specifying a Domain to Use While Debugging or Previewing</span></span>

<span data-ttu-id="5acc5-p107">可以预览表单，就像该表单已发布到某个特定域一样。仅当表单模板的安全级别明确设置为“域”\*\*\*\* 时，此设置才适用。</span><span class="sxs-lookup"><span data-stu-id="5acc5-p107">You can preview a form as if it was published to a specific domain. This setting will only apply if the security level of the form template is explicitly set to **Domain**.</span></span>
  
### <a name="to-specify-a-domain-to-use-while-debugging-or-previewing"></a><span data-ttu-id="5acc5-153">指定在调试或预览过程中要使用的域</span><span class="sxs-lookup"><span data-stu-id="5acc5-153">To specify a domain to use while debugging or previewing</span></span>

1. <span data-ttu-id="5acc5-154">如果您在 Visual Studio 2008 中工作，请切换到 InfoPath Designer。</span><span class="sxs-lookup"><span data-stu-id="5acc5-154">If you are working in Visual Studio 2012, switch to the InfoPath designer.</span></span>
    
2. <span data-ttu-id="5acc5-155">单击“文件”\*\*\*\* 选项卡，然后单击“信息”\*\*\*\* 选项卡上的“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-155">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
3. <span data-ttu-id="5acc5-156">单击“表单选项”\*\*\*\* 对话框中的“预览”\*\*\*\* 类别，然后在“域”\*\*\*\* 框中指定要在预览和调试过程中使用的域。</span><span class="sxs-lookup"><span data-stu-id="5acc5-156">Click the **Preview** category of the **Form Options** dialog box, and then specify the domain to use while previewing and debugging in the **Domain** box.</span></span> 
    
4. <span data-ttu-id="5acc5-157">单击“表单选项”\*\*\*\* 对话框中的“安全和信任”\*\*\*\* 类别，清除“自动确定安全级别”\*\*\*\* 复选框，然后单击“域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5acc5-157">Click the **Security and Trust** category of the **Forms Options** dialog box, clear the **Automatically determine security level** check box, and then click **Domain**.</span></span>
    

