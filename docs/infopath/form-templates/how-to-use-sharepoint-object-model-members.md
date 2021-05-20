---
title: 使用 SharePoint 对象模型成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8cbafca3-7831-4231-8e61-38330b5ad61b
description: 在您可以通过运行在 InfoPath 表单模板中的代码针对 SharePoint 对象模型的成员进行编程之前，您必须在表单的 Visual Studio 2008 项目中引用 Microsoft.SharePoint.dll 程序集。为此，您必须具有对 Microsoft SharePoint Server 2010 的授权副本或运行 Microsoft SharePoint Foundation 2010 的服务器的文件系统的访问权限，这样您才能够获得 Microsoft.SharePoint.dll 程序集的副本。
ms.openlocfilehash: e29725450a6a1bdcba99215e337493f8686491e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431657"
---
# <a name="use-sharepoint-object-model-members"></a><span data-ttu-id="f6e32-104">使用 SharePoint 对象模型成员</span><span class="sxs-lookup"><span data-stu-id="f6e32-104">Use SharePoint Object Model Members</span></span>

<span data-ttu-id="f6e32-p102">在您可以通过运行在 InfoPath 表单模板中的代码针对 SharePoint 对象模型的成员进行编程之前，您必须在表单的 Visual Studio 2008 项目中引用 Microsoft.SharePoint.dll 程序集。为此，您必须具有对 Microsoft SharePoint Server 2010 的授权副本或运行 Microsoft SharePoint Foundation 2010 的服务器的文件系统的访问权限，这样您才能够获得 Microsoft.SharePoint.dll 程序集的副本。</span><span class="sxs-lookup"><span data-stu-id="f6e32-p102">Before you can program against members of the SharePoint object model from code running in an InfoPath form template, you must reference the Microsoft.SharePoint.dll assembly in the Visual Studio 2012 project for your form. To do that, you must have access to the file system of a licensed copy of Microsoft SharePoint Server 2010 or a server that is running Microsoft SharePoint Foundation 2010 so that you can obtain a copy of the Microsoft.SharePoint.dll assembly.</span></span> 
  
<span data-ttu-id="f6e32-p103">此外，还必须将您的表单模板作为沙盒解决方案或经管理员核准的解决方案部署到服务器中。有关这些部署选项的详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f6e32-p103">Additionally, your form template must be deployed to the server as either a sandboxed or administrator-approved solution. For more information about these deployment options, see [Publishing Forms with Code](publishing-forms-with-code.md).</span></span>
  
## <a name="add-and-reference-the-microsoftsharepoint-assembly-from-an-infopath-form-template"></a><span data-ttu-id="f6e32-109">从 InfoPath 表单模板中添加和引用 Microsoft.SharePoint 程序集</span><span class="sxs-lookup"><span data-stu-id="f6e32-109">Add and Reference the Microsoft.SharePoint Assembly from an InfoPath Form Template</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6e32-p104">为了避免与 InfoPath 项目系统管理文件（即添加到表单模板中文件）的方式相冲突，请勿将要引用的任何程序集复制到表单模板项目的顶级文件夹中。默认情况下，其路径的格式如下：< *驱动器*  >:\Users\  *用户名*  \Documents\InfoPath Projects\  *项目名* > 如果确实要将所引用的程序集移动到项目文件夹内的某个位置，则必须在主 *项目名*  项目文件夹下创建一个子文件夹，然后从该子文件夹复制和引用程序集。但是请注意，为引用的程序集创建子文件夹不是必需的。只要引用的程序集不在项目的顶级文件夹内，InfoPath 项目系统就会在编译和发布项目时，将程序集复制到表单模板文件 (.xsn) 中。</span><span class="sxs-lookup"><span data-stu-id="f6e32-p104">To avoid a conflict with how the InfoPath project system manages files that are added to the form template file, do not copy any assemblies that you want to reference into the top-level folder of a form template project. By default, this will be a path in the following format: < *drive*  >:\Users\  *UserName*  \Documents\InfoPath Projects\  *ProjectName* > If you do want to move assemblies that you reference to a location within the project folder, you must create a subfolder under the main  *ProjectName*  project folder, and then copy and reference assemblies from that subfolder. However, be aware that creating a subfolder for referenced assemblies is not necessary. As long as a referenced assembly is not located within the project's top-level folder, the InfoPath project system will copy the assembly into the form template file (.xsn) when the project is compiled and published.</span></span> 
  
<span data-ttu-id="f6e32-114">默认情况下，Microsoft.SharePoint.Server.dll 安装在 SharePoint Server 2010 或运行 SharePoint Foundation 2010 的服务器的文件系统中的 C:\Program Files\Common Files\Microsoft Shared\Web Server\Extensions\14\ISAPI 中。</span><span class="sxs-lookup"><span data-stu-id="f6e32-114">By default, Microsoft.SharePoint.Server.dll is installed in C:\Program Files\Common Files\Microsoft Shared\Web Server\Extensions\14\ISAPI in the file system of SharePoint Server 2010 or a server that is running SharePoint Foundation 2010.</span></span>
  
### <a name="to-reference-the-microsoftsharepoint-assembly-from-an-infopath-forms-code-project"></a><span data-ttu-id="f6e32-115">从 InfoPath 表单的代码项目中引用 Microsoft.SharePoint 程序集</span><span class="sxs-lookup"><span data-stu-id="f6e32-115">To reference the Microsoft.SharePoint assembly from an InfoPath form's code project</span></span>

1. <span data-ttu-id="f6e32-116">将服务器上的 Microsoft.SharePoint.Server.dll 程序集复制到本地文件夹，或者获取从共享文件夹访问该程序集的权限。</span><span class="sxs-lookup"><span data-stu-id="f6e32-116">Copy the Microsoft.SharePoint.Server.dll assembly from the server to a local folder, or get access to the assembly from a shared folder.</span></span>
    
2. <span data-ttu-id="f6e32-117">在 Visual Studio 2008 中打开表单模板项目。</span><span class="sxs-lookup"><span data-stu-id="f6e32-117">Open the form template project in Visual Studio 2012.</span></span>
    
3. <span data-ttu-id="f6e32-118">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="f6e32-118">On the **Project** menu, click **Add Reference**.</span></span>
    
4. <span data-ttu-id="f6e32-119">单击“浏览”选项卡，找到并指定程序集，再单击“确定”，以添加引用。</span><span class="sxs-lookup"><span data-stu-id="f6e32-119">Click the **Browse** tab, locate and specify the assembly, and then click **OK** to add the reference.</span></span> 
    
<span data-ttu-id="f6e32-p105">现在，您即可通过表单代码针对 SharePoint 对象模型的成员编写代码。为了使引用 Microsoft.SharePoint 命名空间的成员更加容易，请将  `using Microsoft.SharePoint;` 或  `Imports Microsoft.SharePoint` 添加到代码文件开始处的指令中。有关演示如何在 InfoPath 表单中使用 SharePoint 对象模型的成员的示例，请参阅 [示例沙盒解决方案](sample-sandboxed-solutions.md)中的"示例 2：使用 SharePoint 列表管理供应商"。</span><span class="sxs-lookup"><span data-stu-id="f6e32-p105">Now you can write code against members of the SharePoint object model from your form code. To make it easier to reference members of the Microsoft.SharePoint namespace, add  `using Microsoft.SharePoint;` or  `Imports Microsoft.SharePoint` to the directives at the beginning of your code file. For an example that shows how to use members of the SharePoint object model in an InfoPath form, see "Example 2: Managing Vendors in a SharePoint List" in [Sample Sandboxed Solutions](sample-sandboxed-solutions.md).</span></span>

