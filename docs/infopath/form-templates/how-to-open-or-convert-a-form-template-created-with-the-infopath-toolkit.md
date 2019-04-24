---
title: 打开或转换用 InfoPath 工具包创建的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- converting form templates [infopath 2007],InfoPath Toolkit, opening form templates from,form templates [InfoPath 2007], opening,InfoPath 2007, converting InfoPath Toolkit form templates,opening form templates [InfoPath 2007],form templates [InfoPath 2007], converting,script [InfoPath 2007], converting to managed code
localization_priority: Normal
ms.assetid: af8eca2e-ba9a-4c37-94af-662815fff518
description: 如果您使用某个 InfoPath 2003 Toolkits for Visual Studio 创建了 InfoPath 2003 托管代码表单模板，并且希望保持与 InfoPath 2003 的兼容性，只需在 Microsoft InfoPath 和 Visual Studio 2008 中打开您的表单模板项目，即可继续处理和进一步开发该项目。
ms.openlocfilehash: 0acbfab4a83a71d94a1c70a667a963056f5b9a38
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300110"
---
# <a name="open-or-convert-a-form-template-created-with-the-infopath-toolkit"></a><span data-ttu-id="992df-104">打开或转换用 InfoPath 工具包创建的表单模板</span><span class="sxs-lookup"><span data-stu-id="992df-104">Open or Convert a Form Template Created with the InfoPath Toolkit</span></span>

<span data-ttu-id="992df-105">如果您使用某个 InfoPath 2003 Toolkits for Visual Studio 创建了 InfoPath 2003 托管代码表单模板，并且希望保持与 InfoPath 2003 的兼容性，只需在 Microsoft InfoPath 和 Visual Studio 2008 中打开您的表单模板项目，即可继续处理和进一步开发该项目。</span><span class="sxs-lookup"><span data-stu-id="992df-105">If you created an InfoPath 2003 managed code form template using one of the InfoPath 2003 Toolkits for Visual Studio and want to maintain compatibility with InfoPath 2003, you can continue to work on and further develop your form template project by opening it in Microsoft InfoPath and Visual Studio 2012.</span></span>
  
<span data-ttu-id="992df-p101">您也可以迁移和升级 InfoPath 2003 项目中的代码，以使用由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的新的 .NET 项目模型。执行该操作时，将需要重新编写所有代码，以使用 **Microsoft.Office.InfoPath** 命名空间的成员，但以前项目的所有代码都将保留，并用 **#if InfoPathManagedObjectModel** 和 **#endif** (C#) 或者 **#If InfoPathManagedObject Model** 和 **#End If** (Visual Basic) 语句围起来，以供您参考。</span><span class="sxs-lookup"><span data-stu-id="992df-p101">Alternatively, you can migrate and upgrade the code in your InfoPath 2003 project to use the new .NET object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace. When doing so, all of your code will need to be re-written to use members of the **Microsoft.Office.InfoPath** namespace, but all of the code from your previous project is retained and surrounded by **#if InfoPathManagedObjectModel** and **#endif** (C#) or **#If InfoPathManagedObject Model** and **#End If** (Visual Basic) statements for your reference.</span></span> 
  
<span data-ttu-id="992df-108">下面的过程描述了如何打开使用 InfoPath 工具包创建的托管代码表单模板，并保持与 InfoPath 2003 的兼容性，或迁移和升级到新的 InfoPath 对象模型。</span><span class="sxs-lookup"><span data-stu-id="992df-108">The following procedures describe how to open a managed code form template created by using the InfoPath Toolkit and maintain compatibility with InfoPath 2003 or migrate and upgrade to the new InfoPath object model.</span></span> 
  
### <a name="open-a-managed-code-form-template-created-with-the-infopath-toolkit-and-maintain-compatibility-with-infopath-2003-using-visual-studio-tools-for-applications"></a><span data-ttu-id="992df-109">打开使用 InfoPath 工具包创建的托管代码表单模板，并保持与使用 Visual Studio Tools for Applications 的 InfoPath 2003 的兼容性</span><span class="sxs-lookup"><span data-stu-id="992df-109">Open a managed code form template created with the InfoPath Toolkit and maintain compatibility with InfoPath 2003 using Visual Studio Tools for Applications</span></span>

1. <span data-ttu-id="992df-110">打开 InfoPath Designer，然后单击“文件”\*\*\*\* 选项卡上的“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-110">Open the InfoPath Designer, and then click **Open** on the **File** tab.</span></span> 
    
2. <span data-ttu-id="992df-111">在“在设计模式中打开”\*\*\*\* 对话框中，导航到保存 InfoPath 工具包表单模板项目的项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="992df-111">In the **Open in Design Mode** dialog box, navigate to the project folder where the InfoPath Toolkit form template project is saved.</span></span> 
    
    <span data-ttu-id="992df-p102">默认情况下，这是创建项目的计算机上的  `C:\Users\` *用户名*  `\Documents\Visual Studio Projects` 中的文件夹。您也可以将该文件夹移动到 InfoPath 存储 Visual Studio 2008 项目的位置，该位置默认情况下为  `C:\Users\` *用户名*  `\Documents\InfoPath Projects`</span><span class="sxs-lookup"><span data-stu-id="992df-p102">By default, this will be a folder in  `C:\Users\` *username*  `\Documents\Visual Studio Projects` on the computer where the project was created. Or, you can move the folder to the location where InfoPath stores Visual Studio 2012 projects, which by default is  `C:\Users\` *username*  `\Documents\InfoPath Projects`</span></span>
    
3. <span data-ttu-id="992df-114">单击名为 manifest.xsf 的文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-114">Click the file that is named manifest.xsf, and then click **Open**.</span></span>
    
4. <span data-ttu-id="992df-115">在“开发工具”\*\*\*\* 选项卡上，单击“代码编辑器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-115">On the **Developer** tab, click **Code Editor**.</span></span>
    
5. <span data-ttu-id="992df-p103">The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p103">The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue.</span></span> 
    
6. <span data-ttu-id="992df-118">导航到要保存文件的位置，命名该文件，然后单击 **"保存"**。</span><span class="sxs-lookup"><span data-stu-id="992df-118">Navigate to the location where you want to save the file, name the file, and then click **Save**.</span></span>
    
7. <span data-ttu-id="992df-p104">The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p104">The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue.</span></span> 
    
8. <span data-ttu-id="992df-122">选择项目的 Visual Studio 解决方案 (.sln) 文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-122">Select the Visual Studio Solution (.sln) file for the project, and then click **Open**.</span></span>
    
9. <span data-ttu-id="992df-p105">The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p105">The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue.</span></span> 
    
10. <span data-ttu-id="992df-p106">将显示消息"此表单中的代码使用 InfoPath 2003 对象模型"，并显示提示"是否升级代码，以使用 Microsoft Office InfoPath 对象模型?"。单击 **"否"** 将保持与 InfoPath 2003 的兼容性，并继续使用由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的对象模型。</span><span class="sxs-lookup"><span data-stu-id="992df-p106">The message "The code in this form uses the InfoPath 2003 object model" is displayed with the prompt "Do you want to upgrade your code to use the Microsoft Office InfoPath object model?" Click **No** to retain compatibility with InfoPath 2003 and to continue working with the object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
    
    <span data-ttu-id="992df-127">有关如何使用与 InfoPath 2003 兼容的托管代码表单模板的信息，请参阅[使用 InfoPath 2003 对象模型开发表单模板](developing-form-templates-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="992df-127">For information about how to work with managed code form templates that are compatible with InfoPath 2003, see [Developing Form Templates Using the InfoPath 2003 Object Model](developing-form-templates-using-the-infopath-2003-object-model.md).</span></span>
    
### <a name="open-a-managed-code-form-template-created-with-the-infopath-toolkit-and-upgrade-it-to-use-the-new-infopath-object-model-using-visual-studio-tools-for-applications"></a><span data-ttu-id="992df-128">打开使用 InfoPath 工具包创建的托管代码表单模板，并使用 Visual Studio Tools for Applications 升级该模板以使用新的 InfoPath 对象模型</span><span class="sxs-lookup"><span data-stu-id="992df-128">Open a managed code form template created with the InfoPath Toolkit and upgrade it to use the new InfoPath object model using Visual Studio Tools for Applications</span></span>

1. <span data-ttu-id="992df-129">打开 InfoPath Designer，然后单击“文件”\*\*\*\* 选项卡上的“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-129">Open the InfoPath Designer, and then click **Open** on the **File** tab.</span></span> 
    
2. <span data-ttu-id="992df-130">在 **"打开表单模板"** 下，单击 **"在'我的电脑'上"**。</span><span class="sxs-lookup"><span data-stu-id="992df-130">Under **Open a form template**, click **On My Computer**.</span></span>
    
3. <span data-ttu-id="992df-131">在“在设计模式中打开”\*\*\*\* 对话框中，导航到保存 InfoPath 工具包表单模板项目的项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="992df-131">In the **Open in Design Mode** dialog box, navigate to the project folder where the InfoPath Toolkit form template project is saved.</span></span> 
    
    <span data-ttu-id="992df-p107">默认情况下，这是创建项目的计算机上的  `C:\Users\` *用户名*  `\Documents\Visual Studio Projects` 中的文件夹。您也可以将该文件夹移动到 InfoPath 存储 Visual Studio 2008 项目的位置，该位置默认情况下为  `C:\Users\` *用户名*  `\Documents\InfoPath Projects`</span><span class="sxs-lookup"><span data-stu-id="992df-p107">By default this will be a folder in  `C:\Users\` *username*  `\Documents\Visual Studio Projects` on the computer where the project was created. Or, you can move the folder to the location where InfoPath stores Visual Studio 2012 projects, which by default is  `C:\Users\` *username*  `\Documents\InfoPath Projects`</span></span>
    
4. <span data-ttu-id="992df-134">单击名为 manifest.xsf 的文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-134">Click the file that is named manifest.xsf, and then click **Open**.</span></span>
    
5. <span data-ttu-id="992df-135">在“开发工具”\*\*\*\* 选项卡上，单击“代码编辑器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-135">On the **Developer** tab, click **Code Editor**.</span></span>
    
6. <span data-ttu-id="992df-p108">The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p108">The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue.</span></span> 
    
7. <span data-ttu-id="992df-138">导航到要保存文件的位置，命名该文件，然后单击 **"保存"**。</span><span class="sxs-lookup"><span data-stu-id="992df-138">Navigate to the location where you want to save the file, name the file, and then click **Save**.</span></span>
    
8. <span data-ttu-id="992df-p109">The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p109">The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue.</span></span> 
    
9. <span data-ttu-id="992df-142">选择项目的 Visual Studio 解决方案 (.sln) 文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="992df-142">Select the Visual Studio Solution (.sln) file for the project, and then click **Open**.</span></span>
    
10. <span data-ttu-id="992df-p110">The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue.</span><span class="sxs-lookup"><span data-stu-id="992df-p110">The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue.</span></span> 
    
11. <span data-ttu-id="992df-p111">The message "The code in this form uses the InfoPath 2003 object model" is displayed with the prompt "Do you want to upgrade your code to use the Microsoft Office InfoPath object model?" Click **Yes** to upgrade the form template to use the new managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span><span class="sxs-lookup"><span data-stu-id="992df-p111">The message "The code in this form uses the InfoPath 2003 object model" is displayed with the prompt "Do you want to upgrade your code to use the Microsoft Office InfoPath object model?" Click **Yes** to upgrade the form template to use the new managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
    
    <span data-ttu-id="992df-p112">将在 Visual Studio 2008 代码编辑器中打开您的表单代码，并且以前项目中的所有代码都用 **#if** **InfoPathManagedObjectModel** 和 **#endif** (C#) 或者 **#If InfoPathManagedObjectModel** 和 **#End If** (Visual Basic) 语句围起来，以供您参考。将需要重新编写所有这些代码，以使用由 **Microsoft.Office.InfoPath** 命名空间提供的对象模型的成员。</span><span class="sxs-lookup"><span data-stu-id="992df-p112">Your form code is opened in the Visual Studio 2012 code editor with all of the code from your previous project surrounded by **#if** **InfoPathManagedObjectModel** and **#endif** (C#) or **#If InfoPathManagedObjectModel** and **#End If** (Visual Basic) statements for your reference. All of this code will have to be re-written to use members of the object model provided by the **Microsoft.Office.InfoPath** namespace.</span></span> 
    
    <span data-ttu-id="992df-149">有关如何处理使用新的 InfoPath 托管代码对象模型的托管代码表单模板的信息，请参阅[开发包含代码的 InfoPath 表单模板](developing-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="992df-149">For information about how to work with managed code form templates that use the new InfoPath managed code object model, see [Developing InfoPath Form Templates with Code](developing-infopath-form-templates-with-code.md).</span></span>
    

