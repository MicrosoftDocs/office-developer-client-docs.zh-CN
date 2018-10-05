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
# <a name="develop-with-visual-studio"></a><span data-ttu-id="da9b9-104">使用 Visual Studio 进行开发</span><span class="sxs-lookup"><span data-stu-id="da9b9-104">Develop with Visual Studio</span></span>

<span data-ttu-id="da9b9-p102">通过使用在 Visual Studio 2008 中开发的托管代码扩展 InfoPath 表单，您可以大大增强这些表单的功能。随后，您可以将包含代码的表单发布到 SharePoint Server 2013 中的表单库。</span><span class="sxs-lookup"><span data-stu-id="da9b9-p102">You can greatly enhance the functionality of your InfoPath forms by extending them with managed code developed in Visual Studio 2012. You can then publish your forms with code to form libraries on SharePoint Server 2013.</span></span>
  
<span data-ttu-id="da9b9-107">您可以通过三个高级步骤开始编程并部署包含托管代码的 InfoPath 表单：</span><span class="sxs-lookup"><span data-stu-id="da9b9-107">You can start programming and deploying your InfoPath forms with managed code in three high-level steps:</span></span>
  
1. <span data-ttu-id="da9b9-108">使用 [Microsoft Visual Studio Tools for Applications 2012](https://www.microsoft.com/en-us/download/details.aspx?id=38807) 附加设备安装 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="da9b9-108">Install Visual Studio 2012 with the [Microsoft Visual Studio Tools for Applications 2012](https://www.microsoft.com/en-us/download/details.aspx?id=38807) add-on.</span></span> 
    
2. <span data-ttu-id="da9b9-109">设置编程语言，然后在 Visual Studio 2008 代码编辑器中编写和调试代码。</span><span class="sxs-lookup"><span data-stu-id="da9b9-109">Set your programming language, and then write and debug code in the Visual Studio 2012 code editor.</span></span>
    
3. <span data-ttu-id="da9b9-110">完成设计表单和开发代码的工作后，可以将表单模板发布到 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="da9b9-110">When you have finished designing the form and developing your code, the form template can be published to SharePoint Server 2013.</span></span>
    
<span data-ttu-id="da9b9-111">应考虑创建与 SharePoint Server 2013 兼容的表单的原因如下：</span><span class="sxs-lookup"><span data-stu-id="da9b9-111">Here are some reasons to consider creating forms that are compatible with SharePoint Server 2013:</span></span>
  
- <span data-ttu-id="da9b9-p103">可以在浏览器中填写通过 InfoPath Forms Services 部署到 SharePoint Server 2013 的表单。这将使未安装 InfoPath 的用户能够打开和使用表单。</span><span class="sxs-lookup"><span data-stu-id="da9b9-p103">Forms deployed to SharePoint Server 2013 with InfoPath Forms Services can be filled out in a browser. This enables users who do not have InfoPath installed to open and use your forms.</span></span>
    
- <span data-ttu-id="da9b9-p104">您只设计一个版本的表单。与 Microsoft SharePoint Server 兼容的表单也与 InfoPath Filler 兼容，但仅与 InfoPath Filler 兼容的表单将无法在浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="da9b9-p104">You design only one version of the form. Forms that are compatible with Microsoft SharePoint Server are also compatible with the InfoPath Filler, but forms that are compatible only with the InfoPath Filler cannot be opened in the browser.</span></span>
    
<span data-ttu-id="da9b9-p105">可通过两种方式将表单发布到 SharePoint：SharePoint 沙盒解决方案和管理员部署的解决方案。有关每种发布方法的详细信息以及有关最适合您方案的方法的建议，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。有关沙盒解决方案的示例解决方案，请参阅[示例沙盒解决方案](sample-sandboxed-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="da9b9-p105">There are two ways to publish your form to SharePoint: SharePoint sandboxed solutions, and administrator-deployed solutions. For more information about each publication method and suggestions about which method is best for your scenario, see [Publishing Forms with Code](publishing-forms-with-code.md). For example solutions for sandboxed solutions, see [Sample Sandboxed Solutions](sample-sandboxed-solutions.md).</span></span>
  
## <a name="developing-with-visual-studio"></a><span data-ttu-id="da9b9-119">使用 Visual Studio 进行开发</span><span class="sxs-lookup"><span data-stu-id="da9b9-119">Developing with Visual Studio</span></span>

<span data-ttu-id="da9b9-120">在安装 Visual Studio 2008 和 Microsoft Visual Studio Tools for Applications 2012 加载项后，您便能够开始开发 InfoPath 托管代码解决方案。</span><span class="sxs-lookup"><span data-stu-id="da9b9-120">With Visual Studio 2012 and the Microsoft Visual Studio Tools for Applications 2012 add-on installed, you are ready to start to develop InfoPath managed code solutions.</span></span>
  
### <a name="choosing-a-programming-language"></a><span data-ttu-id="da9b9-121">选择编程语言</span><span class="sxs-lookup"><span data-stu-id="da9b9-121">Choosing a Programming Language</span></span>

<span data-ttu-id="da9b9-p106">InfoPath 提供了使用用两种语言（Visual Basic 和 C#）编写的四种版本的 InfoPath 对象模型进行编程的选项。该对象模型的四种版本提供了与 InfoPath 2013、InfoPath、Office InfoPath 2007 和 Microsoft InfoPath 2003 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="da9b9-p106">InfoPath provides the options to program by using four versions of the InfoPath object model in two languages: Visual Basic and C#. The four versions of the object model provide compatibility with InfoPath 2013, InfoPath, Office InfoPath 2007, and Microsoft InfoPath 2003.</span></span>
  
### <a name="to-specify-the-programming-language-and-object-model"></a><span data-ttu-id="da9b9-124">指定编程语言和对象模型</span><span class="sxs-lookup"><span data-stu-id="da9b9-124">To specify the programming language and object model</span></span>

1. <span data-ttu-id="da9b9-125">当表单模板项目在 InfoPath 设计器中处于打开状态时，在“开发工具”\*\*\*\* 选项卡上单击“语言”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9b9-125">With a form template project open in the InfoPath designer, click **Language** on the **Developer** tab.</span></span> 
    
2. <span data-ttu-id="da9b9-126">在“表单选项”\*\*\*\* 对话框的“编程”\*\*\*\* 类别中，从“表单模板代码语言”\*\*\*\* 下拉列表中选择你想要使用的语言。</span><span class="sxs-lookup"><span data-stu-id="da9b9-126">In the **Programming** category of the **Form Options** dialog box, select the language that you want to work with from the **Form template code language** drop-down list.</span></span> <span data-ttu-id="da9b9-127">然后，从“目标版本”\*\*\*\* 下拉列表中选择对象模型的版本。</span><span class="sxs-lookup"><span data-stu-id="da9b9-127">Then, select the version of the object model from the **Target version** drop-down list.</span></span> <span data-ttu-id="da9b9-128">仅与 InfoPath 2013 兼容的“目标版本”\*\*\*\* 选项没有后跟“InfoPath”\*\*\*\* 名称的版本年。</span><span class="sxs-lookup"><span data-stu-id="da9b9-128">The **Target version** option that is compatible only with InfoPath 2013 does not have a version year following the **InfoPath** name.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="da9b9-129">并非所有表单模板类型都支持代码。</span><span class="sxs-lookup"><span data-stu-id="da9b9-129">Not all form template types support code.</span></span> <span data-ttu-id="da9b9-130">例如，“SharePoint 列表”\*\*\*\* 表单模板类型和“模板部件”\*\*\*\* 不支持表单代码。</span><span class="sxs-lookup"><span data-stu-id="da9b9-130">For example, the **SharePoint List** form template type and **Template Parts** do not support form code.</span></span> <span data-ttu-id="da9b9-131">当设计不支持代码的表单模板类型时，“开发工具”\*\*\*\* 选项卡将不可用。</span><span class="sxs-lookup"><span data-stu-id="da9b9-131">When designing a form template type that does not support code, the **Developer** tab will not be available.</span></span> <span data-ttu-id="da9b9-132">此外，只有某些表单模板类型才支持所有四种版本的对象模型。</span><span class="sxs-lookup"><span data-stu-id="da9b9-132">Also, only some form template types support all four versions of the object model.</span></span> <span data-ttu-id="da9b9-133">例如，“空白表单 (InfoPath Filler)”\*\*\*\* 模板类型支持所有四种版本的对象模型（并创建仅与这些版本中的 InfoPath Filler 兼容的表单模板），而“空白表单”\*\*\*\* 模板仅支持 InfoPath 2013 和 InfoPath（并创建与 InfoPath Filler 和浏览器都兼容的表单模板）。</span><span class="sxs-lookup"><span data-stu-id="da9b9-133">For example, the **Blank Form (InfoPath Filler)** template type supports all four versions of the object model (and creates form template that are compatible only with the InfoPath Filler in those versions), but the **Blank Form** template supports only InfoPath 2013 and InfoPath (and creates form templates that are compatible with both the InfoPath Filler and the browser).</span></span> 
  
    <span data-ttu-id="da9b9-134">您可以设置默认编程语言，以便 InfoPath 表单设计器在启动时将始终使用您选择的语言和对象模型版本。</span><span class="sxs-lookup"><span data-stu-id="da9b9-134">You can set a default programming language so that the InfoPath form designer will always start with the language and object model version of your choice.</span></span>
    
### <a name="to-set-the-default-programming-language"></a><span data-ttu-id="da9b9-135">设置默认编程语言</span><span class="sxs-lookup"><span data-stu-id="da9b9-135">To set the default programming language</span></span>

1. <span data-ttu-id="da9b9-136">单击“文件”\*\*\*\* 选项卡，然后单击“选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9b9-136">Click the **File** tab, and then click **Options**.</span></span>
    
2. <span data-ttu-id="da9b9-137">在“InfoPath 选项”\*\*\*\* 对话框的“常规”\*\*\*\* 部分，单击“更多选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9b9-137">In the **General** section of the **InfoPath Options** dialog box, click **More Options**.</span></span>
    
3. <span data-ttu-id="da9b9-138">在“选项”\*\*\*\* 对话框的“设计”\*\*\*\* 选项卡上，选择“编程默认语言”\*\*\*\* 部分中的默认编程语言。</span><span class="sxs-lookup"><span data-stu-id="da9b9-138">On the **Design** tab of the **Options** dialog box, select the default programming language in the **Programming Defaults** section.</span></span> 
    
### <a name="writing-code"></a><span data-ttu-id="da9b9-139">编写代码</span><span class="sxs-lookup"><span data-stu-id="da9b9-139">Writing Code</span></span>

<span data-ttu-id="da9b9-140">现在即可开始使用 InfoPath 2013 和 Visual Studio 2008 进行开发。</span><span class="sxs-lookup"><span data-stu-id="da9b9-140">You can now start to develop with InfoPath 2013 and Visual Studio 2012.</span></span> 
  
### <a name="to-start-the-visual-studio-code-editor"></a><span data-ttu-id="da9b9-141">启动 Visual Studio 代码编辑器</span><span class="sxs-lookup"><span data-stu-id="da9b9-141">To start the Visual Studio Code Editor</span></span>

1. <span data-ttu-id="da9b9-142">在 InfoPath 设计器中打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="da9b9-142">Open a form template in the InfoPath designer.</span></span>
    
2. <span data-ttu-id="da9b9-143">单击“开发人员”\*\*\*\* 选项卡上的“代码编辑器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9b9-143">Click **Code Editor** on the **Developer** tab.</span></span> 
    
> [!TIP]
> <span data-ttu-id="da9b9-144">也可以启动代码编辑器，并使用“开发工具”\*\*\*\* 选项卡上的命令、上下文菜单和其他用户界面方法自动添加表单和控件事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="da9b9-144">You can also start the code editor and automatically add event handlers for form and control events using commands on the **Developer** tab, context menus, and other user interface methods.</span></span> <span data-ttu-id="da9b9-145">有关详细信息，请参阅[添加事件处理程序](how-to-add-an-event-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="da9b9-145">For more information, see [Add an Event Handler](how-to-add-an-event-handler.md)</span></span>
  

