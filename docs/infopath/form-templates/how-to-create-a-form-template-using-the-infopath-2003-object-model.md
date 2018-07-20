---
title: 使用 InfoPath 2003 对象模型创建表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates,form templates [InfoPath 2007], creating InfoPath 2003-compatible,InfoPath 2007, creating InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: c746aeb1-902c-440e-830b-5b9efad0ca04
description: 本主题中的过程介绍了如何创建使用 InfoPath 2003 兼容对象模型的表单模板。
ms.openlocfilehash: 0cea526c2d41674afc6fee152c3e0584e6b69564
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773983"
---
# <a name="create-a-form-template-using-the-infopath-2003-object-model"></a><span data-ttu-id="fa778-104">使用 InfoPath 2003 对象模型创建表单模板</span><span class="sxs-lookup"><span data-stu-id="fa778-104">How to: Create a Form Template Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="fa778-105">本主题中的过程介绍了如何创建使用 InfoPath 2003 兼容对象模型的表单模板。</span><span class="sxs-lookup"><span data-stu-id="fa778-105">The procedures in this topic describe how to create a form template that works with the InfoPath 2003-compatible object model.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa778-106">除了下面的过程以外，还必须单击“文件”**** 选项卡，单击“另存为”****，然后选择“另存为类型”**** 框中的“InfoPath 2003 表单模板”****，以将表单模板保存为 InfoPath 2003 兼容文件格式。</span><span class="sxs-lookup"><span data-stu-id="fa778-106">In addition to the procedures below, you must also click the **File** tab, click **Save As**, and then select **InfoPath 2003 Form Template** in the **Save as type** box to save the form template to the InfoPath 2003-compatible file format. Also, to open InfoPath 2003-compatible form templates created with ip14short, all InfoPath 2003 users must have the .NET Framework 2.0 or later installed on their computers.</span></span> <span data-ttu-id="fa778-107">此外，若要打开使用 InfoPath 创建的 InfoPath 2003 兼容表单模板，所有 InfoPath 2003 用户都必须在其计算机上安装 .NET Framework 2.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fa778-107">Also, to open InfoPath 2003-compatible form templates created with InfoPath, all InfoPath 2003 users must have the .NET Framework 2.0 or later installed on their computers.</span></span> 
  
### <a name="to-create-an-infopath-2003-compatible-form-template-in-infopath-with-visual-studio-tools-for-applications"></a><span data-ttu-id="fa778-108">在含有 Visual Studio Tools for Applications 的 InfoPath 中创建 InfoPath 2003 兼容表单模板</span><span class="sxs-lookup"><span data-stu-id="fa778-108">To create an InfoPath 2003-compatible form template in InfoPath with Visual Studio Tools for Applications</span></span>

1. <span data-ttu-id="fa778-109">启动 InfoPath Designer。</span><span class="sxs-lookup"><span data-stu-id="fa778-109">Start the InfoPath Designer.</span></span>
    
2. <span data-ttu-id="fa778-110">单击“文件”**** 选项卡，然后单击“表单选项”****。</span><span class="sxs-lookup"><span data-stu-id="fa778-110">Click the **File** tab, and then click **Form Options**.</span></span>
    
3. <span data-ttu-id="fa778-111">在“兼容性”**** 类别中，选择“InfoPath 2003 编辑器表单”****。</span><span class="sxs-lookup"><span data-stu-id="fa778-111">In the **Compatibility** category, select **InfoPath 2003 Editor Form**.</span></span>
    
4. <span data-ttu-id="fa778-112">在“编程”**** 类别中，从“表单模板代码语言”**** 下拉列表中选择“C# (兼容 InfoPath 2003)”**** 或“Visual Basic (兼容 InfoPath 2003)”****。</span><span class="sxs-lookup"><span data-stu-id="fa778-112">In the **Programming** category, select either **C# (InfoPath 2003 Compatible)** or **Visual Basic (InfoPath 2003 Compatible)** from the **Form template code language** drop-down list.</span></span> 
    
5. <span data-ttu-id="fa778-113">单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="fa778-113">Click **OK**.</span></span>
    
6. <span data-ttu-id="fa778-114">设计表单模板，然后按照[使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)中的说明，在 Visual Studio 2012 中添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa778-114">Design your form template, and then add event handlers in Visual Studio 2012, as described in [How to: Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fa778-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa778-115">See also</span></span>



[<span data-ttu-id="fa778-116">演练：使用 InfoPath 2003 对象模型创建和调试基本表单模板</span><span class="sxs-lookup"><span data-stu-id="fa778-116">Walkthrough: Creating and Debugging a Basic Form Template Using the InfoPath 2003 Object Model</span></span>](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md)
  
[<span data-ttu-id="fa778-117">使用 InfoPath 2003 对象模型创建表单模板</span><span class="sxs-lookup"><span data-stu-id="fa778-117">Creating Form Templates Using the InfoPath 2003 Object Model</span></span>](creating-form-templates-using-the-infopath-2003-object-model.md)
