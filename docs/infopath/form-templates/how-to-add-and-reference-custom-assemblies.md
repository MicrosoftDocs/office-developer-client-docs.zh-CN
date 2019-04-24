---
title: 添加和引用自定义程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, using custom assemblies,assemblies [InfoPath 2007], adding custom using InfoPath 2003 object model
localization_priority: Normal
ms.assetid: 20e1f43e-8279-48fc-8f34-16a2729dbc9b
description: 如果在托管代码表单模板项目中添加一个对自定义程序集的引用，则编译和发布项目时，该程序集将包含在表单模板文件 (.xsn) 内。
ms.openlocfilehash: 19b5f06231bb03cfac8b32b157e03956b5fc334e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303659"
---
# <a name="add-and-reference-custom-assemblies"></a><span data-ttu-id="8bbe3-104">添加和引用自定义程序集</span><span class="sxs-lookup"><span data-stu-id="8bbe3-104">Add and Reference Custom Assemblies</span></span>

<span data-ttu-id="8bbe3-105">如果在托管代码表单模板项目中添加一个对自定义程序集的引用，则编译和发布项目时，该程序集将包含在表单模板文件 (.xsn) 内。</span><span class="sxs-lookup"><span data-stu-id="8bbe3-105">When you add a reference to a custom assembly in a managed-code form template project, that assembly is included within the form template file (.xsn) when your project is compiled and published.</span></span>
  
## <a name="add-and-reference-a-custom-assembly"></a><span data-ttu-id="8bbe3-106">添加和引用自定义程序集</span><span class="sxs-lookup"><span data-stu-id="8bbe3-106">Add and Reference a Custom Assembly</span></span>

<span data-ttu-id="8bbe3-p101">为了避免与 InfoPath 项目系统管理文件（即添加到表单模板中文件）的方式相冲突，请勿将要引用的任何自定义程序集复制到表单模板项目的顶级文件夹中。默认情况下，其路径的格式如下：< *驱动器*  >:\Users\  *用户名*  \Documents\InfoPath Projects\  *项目名*</span><span class="sxs-lookup"><span data-stu-id="8bbe3-p101">To avoid a conflict with how the InfoPath project system manages files that are added to the form template file, do not copy any custom assemblies that you want to reference into the top-level folder of a form template project. By default, this will be a path in the following format: < *drive*  >:\Users\  *UserName*  \Documents\InfoPath Projects\  *ProjectName*</span></span> 
  
<span data-ttu-id="8bbe3-p102">如果确实要将所引用的自定义程序集移动到项目文件夹内的某个位置，则必须在主项目文件夹下创建一个子文件夹，然后从该子文件夹复制和引用自定义程序集。但是请注意，为引用的程序集创建子文件夹不是必需的。只要引用的程序集不在项目的顶级文件夹内，InfoPath 项目系统就会在编译和发布项目时，将程序集复制到表单模板文件 (.xsn) 中。</span><span class="sxs-lookup"><span data-stu-id="8bbe3-p102">If you do want to move custom assemblies that you reference to a location within the project folder, you must create a subfolder under the main project folder, and then copy and reference custom assemblies from that subfolder. However, be aware that creating a subfolder for referenced assemblies is not necessary. As long as a referenced assembly is not located within the project's top-level folder, the InfoPath project system will copy the assembly into the form template file (.xsn) when the project is compiled and published.</span></span>
  
### <a name="reference-a-custom-assembly-from-its-default-location"></a><span data-ttu-id="8bbe3-112">从默认位置引用自定义程序集</span><span class="sxs-lookup"><span data-stu-id="8bbe3-112">Reference a custom assembly from its default location</span></span>

1. <span data-ttu-id="8bbe3-113">在 Visual Studio 2008 中打开表单模板项目。</span><span class="sxs-lookup"><span data-stu-id="8bbe3-113">Open the form template project in Visual Studio 2012.</span></span>
    
2. <span data-ttu-id="8bbe3-114">在“项目”\*\*\*\* 菜单上，单击“添加引用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8bbe3-114">On the **Project** menu, click **Add Reference**.</span></span>
    
3. <span data-ttu-id="8bbe3-115">单击“浏览”\*\*\*\* 选项卡，找到并指定程序集，再单击“确定”\*\*\*\*，以添加引用。</span><span class="sxs-lookup"><span data-stu-id="8bbe3-115">Click the **Browse** tab, locate and specify the assembly, and then click **OK** to add the reference.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8bbe3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bbe3-116">See also</span></span>

#### <a name="tasks"></a><span data-ttu-id="8bbe3-117">任务</span><span class="sxs-lookup"><span data-stu-id="8bbe3-117">Tasks</span></span>

[<span data-ttu-id="8bbe3-118">使用 InfoPath 2003 对象模型创建表单模板</span><span class="sxs-lookup"><span data-stu-id="8bbe3-118">Create a Form Template Using the InfoPath 2003 Object Model</span></span>](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)

