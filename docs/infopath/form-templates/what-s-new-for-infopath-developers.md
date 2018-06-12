---
title: 为 InfoPath 开发人员提供的新功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- what's new [infopath 2007],developer features [InfoPath 2007],InfoPath 2007, what's new,new features [InfoPath 2007]
localization_priority: Normal
ms.assetid: d0ad3111-bd41-4f35-8a34-62c17f20fc19
description: InfoPath 旨在让您轻松地在 Microsoft SharePoint Server 平台上构建各种基于表单的应用程序。Microsoft SharePoint Server 2013 与 InfoPath Forms Services 和 Microsoft InfoPath 2013 结合使用可提供面向开发人员的许多功能。利用 SharePoint Server 2013 中提供的 InfoPath Forms Services，您可以将 InfoPath 表单模板部署到 SharePoint Server，以便没有 InfoPath 富客户端的用户可以在 Web 浏览器中打开并填写 InfoPath 表单。
ms.openlocfilehash: a11c6b4018e60a470197ecd7ffdf3b79a13658b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774092"
---
# <a name="whats-new-for-infopath-developers"></a><span data-ttu-id="020b8-106">为 InfoPath 开发人员提供的新功能</span><span class="sxs-lookup"><span data-stu-id="020b8-106">What's New for InfoPath Developers</span></span>

<span data-ttu-id="020b8-p102">InfoPath 旨在让您轻松地在 Microsoft SharePoint Server 平台上构建各种基于表单的应用程序。Microsoft SharePoint Server 2013 与 InfoPath Forms Services 和 Microsoft InfoPath 2013 结合使用可提供面向开发人员的许多功能。利用 SharePoint Server 2013 中提供的 InfoPath Forms Services，您可以将 InfoPath 表单模板部署到 SharePoint Server，以便没有 InfoPath 富客户端的用户可以在 Web 浏览器中打开并填写 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="020b8-p102">InfoPath is designed to make it easy to build rich forms-based applications on the Microsoft SharePoint Server platform. Microsoft InfoPath 2013 in conjunction with Microsoft SharePoint Server 2013 and InfoPath Forms Services have many features for developers. InfoPath Forms Services, which is available in SharePoint Server 2013, enables you to deploy an InfoPath form template to a SharePoint Server so that users without the InfoPath rich client can open and fill out InfoPath forms in a Web browser.</span></span>
  
<span data-ttu-id="020b8-p103">使用 InfoPath 2013 创建的表单模板继续支持针对 **Microsoft.Office.InfoPath** 命名空间的类和成员编写的业务逻辑，此业务逻辑对于在 InfoPath Filler 中打开的表单和在 Web 浏览器中打开的表单的工作方式相同。通过使用针对此托管对象模型编写的业务逻辑并使用 InfoPath Designer 中的设计检查功能，您可以创建一个可部署到 SharePoint Server 2013 中适当配置的文档库的表单模板，该表单模板将在 InfoPath Filler 和 Web 浏览器中运行。</span><span class="sxs-lookup"><span data-stu-id="020b8-p103">Form templates created using InfoPath 2013 continue to support business logic written against the classes and members of the **Microsoft.Office.InfoPath** namespace, which works the same way for a form opened in the InfoPath filler and in a form opened in a Web browser. By using business logic written to this managed object model, and by working with design checking features in InfoPath Designer, you can create a single form template that you can deploy to an appropriately configured document library on SharePoint Server 2013, which will run in both the InfoPath filler and in a Web browser.</span></span> 
  
## <a name="new-features-and-improvements"></a><span data-ttu-id="020b8-112">新的功能和改进</span><span class="sxs-lookup"><span data-stu-id="020b8-112">New Features and Improvements</span></span>

<span data-ttu-id="020b8-113">以下几节简短描述了 InfoPath 开发人员所关注的这些功能和改进：</span><span class="sxs-lookup"><span data-stu-id="020b8-113">The following sections briefly describe these features and improvements that are interesting to InfoPath developers:</span></span>
  
- <span data-ttu-id="020b8-114">编写和编辑代码的新方法</span><span class="sxs-lookup"><span data-stu-id="020b8-114">New Way to Write and Edit Code</span></span>
    
- <span data-ttu-id="020b8-115">SharePoint 沙盒解决方案</span><span class="sxs-lookup"><span data-stu-id="020b8-115">SharePoint Sandboxed Solutions</span></span>
    
- <span data-ttu-id="020b8-116">只需单击一次即可发布表单</span><span class="sxs-lookup"><span data-stu-id="020b8-116">Publish Forms with One Click</span></span>
    
- <span data-ttu-id="020b8-117">增强 SharePoint 列表表单</span><span class="sxs-lookup"><span data-stu-id="020b8-117">Enhance SharePoint List Forms</span></span>
    
- <span data-ttu-id="020b8-118">使用 InfoPath 表单 web 部件的门户页面上承载表单</span><span class="sxs-lookup"><span data-stu-id="020b8-118">Host Forms on Portal Pages using the InfoPath Form web part</span></span>
    
- <span data-ttu-id="020b8-119">更加丰富的 Web 表单</span><span class="sxs-lookup"><span data-stu-id="020b8-119">Richer Web Forms</span></span>
    
- <span data-ttu-id="020b8-120">符合标准的浏览器表单</span><span class="sxs-lookup"><span data-stu-id="020b8-120">Standards Compliant Browser Forms</span></span>
    
- <span data-ttu-id="020b8-121">使用数字签名提供增强的信息安全性和完整性</span><span class="sxs-lookup"><span data-stu-id="020b8-121">Provide Enhanced Information Security and Integrity with Digital Signatures</span></span>
    
- <span data-ttu-id="020b8-122">新控件</span><span class="sxs-lookup"><span data-stu-id="020b8-122">New Controls</span></span>
    
## <a name="new-way-to-write-and-edit-code"></a><span data-ttu-id="020b8-123">编写和编辑代码的新方法</span><span class="sxs-lookup"><span data-stu-id="020b8-123">New Way to Write and Edit Code</span></span>

<span data-ttu-id="020b8-p104">已从 InfoPath 2013 中删除已与 InfoPath 2010 集成的 Microsoft Visual Studio Tools for Applications IDE 工具。现在，若要在 InfoPath 2013 中编写或编辑表单代码，则需要 Visual Studio 2008 和已安装的 [Microsoft Visual Studio Tools for Applications 2012（该链接可能指向英文页面）](http://www.microsoft.com/en-us/download/details.aspx?id=38807) 加载项。虽然编程体验基本上未发生更改，但在为 InfoPath 表单编写托管代码时，您可以使用完整的 Visual Studio 开发体验。</span><span class="sxs-lookup"><span data-stu-id="020b8-p104">The Microsoft Visual Studio Tools for Applications IDE that was integrated with InfoPath 2010 has been removed in InfoPath 2013. To write or edit form code in InfoPath 2013 now requires Visual Studio 2012 with the [Microsoft Visual Studio Tools for Applications 2012](http://www.microsoft.com/en-us/download/details.aspx?id=38807) add-on installed. The programming experience itself has not fundamentally changed, but you can now use the full Visual Studio development experience when writing managed code for your InfoPath forms.</span></span> 
  
<span data-ttu-id="020b8-127">以下几节描述了 InfoPath 2010 和 SharePoint Server 2010 中首次添加的功能，并继续为使用 InfoPath 2013 和 SharePoint Server 2013 的开发人员提供了有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="020b8-127">The following sections describe features that were first added in InfoPath 2010 and SharePoint Server 2010 and continue to add value for developers using InfoPath 2013 and SharePoint Server 2013.</span></span>
  
## <a name="sharepoint-server-sandboxed-solutions"></a><span data-ttu-id="020b8-128">SharePoint Server 沙盒解决方案</span><span class="sxs-lookup"><span data-stu-id="020b8-128">SharePoint Server Sandboxed Solutions</span></span>

<span data-ttu-id="020b8-p105">利用 InfoPath，将包含代码的表单部署到 SharePoint Server 2013 比以前更为轻松。在 Office InfoPath 2007 中，所有包含代码的表单都必须由 SharePoint 场管理员批准和上载。利用 SharePoint Server 2013 中对沙盒解决方案的支持，具有网站集管理权限的表单设计人员现在可以将包含代码的大多数表单直接发布到其 SharePoint 网站。服务器上的资源配额设置可限制使用过多的资源。网站集管理员可继续保持控制，并做出有关解决方案的信任决策。服务器场管理员可以不干预。有关发布 InfoPath 表单模板作为沙盒解决方案的详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="020b8-p105">With InfoPath, it is easier than ever to deploy forms with code to SharePoint Server 2013. In Office InfoPath 2007, all forms with code had to be approved and uploaded by a SharePoint farm administrator. With support for sandboxed solutions in SharePoint Server 2013, form designers that have site collection administration permissions can now publish most forms with code, directly to their SharePoint sites. A resource quota setting on the server limits excessive resource usage. The site collection administrator remains in control and makes trust decisions about the solution. The farm administrator can be hands-off. For more information about publishing InfoPath form templates as sandboxed solutions, see [Publishing Forms with Code](publishing-forms-with-code.md).</span></span>
  
## <a name="publish-forms-with-one-click"></a><span data-ttu-id="020b8-136">只需单击一次即可发布表单</span><span class="sxs-lookup"><span data-stu-id="020b8-136">Publish Forms with One Click</span></span>

<span data-ttu-id="020b8-137">InfoPath 在设计上可轻松比以往任何时候都要将更新发布到窗体正在</span><span class="sxs-lookup"><span data-stu-id="020b8-137">InfoPath is designed to make it easier than ever to publish updates to your forms..</span></span> <span data-ttu-id="020b8-138">首次发布表单模板，而不是通过几个对话框中，单击之后，您可以完成的新**快速发布**按钮，这是可用的**快速访问工具栏**中，然后在新中单击一次此任务Microsoft Office Backstage，这是可通过单击**文件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="020b8-138">After the first time that you publish a form template, instead of clicking through several dialog boxes, you can complete this task with one click of the new **Quick Publish** button, which is available on the **Quick Access Toolbar**, and in the new Microsoft Office Backstage, which is available by clicking the **File** tab.</span></span> 
  
## <a name="enhance-sharepoint-list-forms"></a><span data-ttu-id="020b8-139">增强 SharePoint 列表表单</span><span class="sxs-lookup"><span data-stu-id="020b8-139">Enhance SharePoint List Forms</span></span>

<span data-ttu-id="020b8-140">使用 InfoPath，您现在可以扩展和增强用于创建、 编辑和查看 SharePoint 列表项的表单。</span><span class="sxs-lookup"><span data-stu-id="020b8-140">Using InfoPath, you can now extend and enhance the forms used for creating, editing and viewing items in a SharePoint list.</span></span> <span data-ttu-id="020b8-141">通过打开列表，在**列表工具**，单击**列表**选项卡，然后单击**自定义窗体**，您可以自动生成类似于默认的 InfoPath 表单、 开的 SharePoint 列表表单。</span><span class="sxs-lookup"><span data-stu-id="020b8-141">By opening a list, clicking the **List** tab under **List Tools**, and then clicking **Customize Form**, you can auto generate an InfoPath form which resembles the default, out-of-the-box SharePoint list form.</span></span> <span data-ttu-id="020b8-142">然后，您可以自定义和增强修改布局、 创建其他视图，并在 InfoPath 中添加规则和数据验证此窗体。</span><span class="sxs-lookup"><span data-stu-id="020b8-142">You can then customize and enhance this form by modifying the layout, creating additional views, and adding rules and data validation in InfoPath.</span></span> <span data-ttu-id="020b8-143">当您完成修改改进的列表窗体时，您可以将其发布到 SharePoint 中使用新的一键式发布功能在 InfoPath 中。</span><span class="sxs-lookup"><span data-stu-id="020b8-143">When you are finished modifying your improved list form, you can publish it to SharePoint using the new one-click publish feature in InfoPath.</span></span>
  
## <a name="host-forms-on-portal-pages-using-the-infopath-form-web-part"></a><span data-ttu-id="020b8-144">使用 InfoPath 表单 web 部件的门户页面上承载表单</span><span class="sxs-lookup"><span data-stu-id="020b8-144">Host Forms on Portal Pages using the InfoPath Form web part</span></span>

<span data-ttu-id="020b8-145">SharePoint Server 2013 中为比以往任何时候都以承载窗体使用新的**InfoPath 表单 web 部件**的网页上更轻松。</span><span class="sxs-lookup"><span data-stu-id="020b8-145">In SharePoint Server 2013, it is easier than ever to host your forms on Web pages using the new **InfoPath Form web part**.</span></span> <span data-ttu-id="020b8-146">在 Microsoft Office SharePoint Server 2007，希望承载其网页上的 InfoPath 表单的用户必须在 Visual Studio 中编写代码。</span><span class="sxs-lookup"><span data-stu-id="020b8-146">In Microsoft Office SharePoint Server 2007, users who want host their InfoPath forms on Web pages have to write code in Visual Studio.</span></span> <span data-ttu-id="020b8-147">现在，无需编写一行代码，您可以将**InfoPath 表单 web 部件**添加到 Web 部件页和其指向您已发布表单。您可以使用**InfoPath 表单 web 部件**来承载任何 InfoPath 浏览器表单发布到 SharePoint 列表或表单库的。</span><span class="sxs-lookup"><span data-stu-id="020b8-147">Now, without writing a single line of code, you can add the **InfoPath Form web part** to a Web Parts page and point it to your published form.You can use the **InfoPath Form web part** to host any InfoPath browser form that is published to a SharePoint list or form library.</span></span> <span data-ttu-id="020b8-148">您还可以将其连接到在上其他 Web 部件，以发送或接收数据。</span><span class="sxs-lookup"><span data-stu-id="020b8-148">You can also connect it to other Web Parts on the page to send or receive data.</span></span> <span data-ttu-id="020b8-149">有关如何使用**InfoPath 表单 web 部件**的详细信息，请参阅 SharePoint 2010 SDK 中[使用 InfoPath 表单 web 部件](http://msdn.microsoft.com/library/bb87e126-1a07-45aa-af36-b294df3a2576%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="020b8-149">For more information about how to use the **InfoPath Form web part**, see [Working with the InfoPath Form web part](http://msdn.microsoft.com/library/bb87e126-1a07-45aa-af36-b294df3a2576%28Office.15%29.aspx) in the SharePoint 2010 SDK.</span></span> 
  
## <a name="richer-web-forms"></a><span data-ttu-id="020b8-150">更加丰富的 Web 表单</span><span class="sxs-lookup"><span data-stu-id="020b8-150">Richer Web Forms</span></span>

<span data-ttu-id="020b8-p109">客户端表单和浏览器表单之间的功能差距已经缩小，从而可为所有用户创造更加一致的表单填写体验。浏览器表单中现在支持的控件和功能包括：</span><span class="sxs-lookup"><span data-stu-id="020b8-p109">The feature gap between client and browser forms has been narrowed, creating a more consistent form filling experience for all users. Controls and functionality that are now supported in browser forms include the following:</span></span>
  
- <span data-ttu-id="020b8-153">项目符号列表、编号列表和普通列表</span><span class="sxs-lookup"><span data-stu-id="020b8-153">Bulleted, numbered, and plain lists</span></span>
    
- <span data-ttu-id="020b8-154">多重选择列表框</span><span class="sxs-lookup"><span data-stu-id="020b8-154">Multiple selection list boxes</span></span>
    
- <span data-ttu-id="020b8-155">组合框</span><span class="sxs-lookup"><span data-stu-id="020b8-155">Combo boxes</span></span>
    
- <span data-ttu-id="020b8-156">图片按钮</span><span class="sxs-lookup"><span data-stu-id="020b8-156">Picture buttons</span></span>
    
- <span data-ttu-id="020b8-157">超链接功能</span><span class="sxs-lookup"><span data-stu-id="020b8-157">Hyperlink capabilities</span></span>
    
- <span data-ttu-id="020b8-158">选项组和节</span><span class="sxs-lookup"><span data-stu-id="020b8-158">Choice group and section</span></span> 
    
- <span data-ttu-id="020b8-159">日期和时间控件</span><span class="sxs-lookup"><span data-stu-id="020b8-159">Date and time controls</span></span>
    
- <span data-ttu-id="020b8-160">个人/组选取器</span><span class="sxs-lookup"><span data-stu-id="020b8-160">Person/group pickers</span></span>
    
- <span data-ttu-id="020b8-161">筛选功能</span><span class="sxs-lookup"><span data-stu-id="020b8-161">Filtering functionality</span></span>
    
## <a name="standards-compliant-browser-forms"></a><span data-ttu-id="020b8-162">符合标准的浏览器表单</span><span class="sxs-lookup"><span data-stu-id="020b8-162">Standards Compliant Browser Forms</span></span>

<span data-ttu-id="020b8-163">InfoPath 浏览器表单现在符合 Web 内容辅助功能准则 2.0 (WCAG 2.0) AA，从而使表单设计人员能够创建可供残疾用户使用的表单。</span><span class="sxs-lookup"><span data-stu-id="020b8-163">InfoPath browser forms are now compliant with Web Content Accessibility Guidelines 2.0 (WCAG 2.0) AA, which enables form designers to create forms that are available for users with disabilities.</span></span>
  
## <a name="provide-enhanced-information-security-and-integrity-with-digital-signatures"></a><span data-ttu-id="020b8-164">使用数字签名提供增强的信息安全性和完整性</span><span class="sxs-lookup"><span data-stu-id="020b8-164">Provide Enhanced Information Security and Integrity with Digital Signatures</span></span>

<span data-ttu-id="020b8-p110">InfoPath 支持下一代加密技术 (CNG) 数字签名内容。为了帮助您确保表单中所含信息的完整性，InfoPath 客户端和 SharePoint Server 2013 提供了为整个表单或表单的节启用单一、联署和副署方案所必需的控件。可以在 Internet Explorer 中使用 ActiveX 签名行控件对表单进行签名。可以在 SharePoint Server 2013 支持的任何浏览器中查看经过签名的表单。</span><span class="sxs-lookup"><span data-stu-id="020b8-p110">InfoPath supports Cryptography Next Generation (CNG) digitally signed content. To help you ensure the integrity of the information that is contained in your forms, the InfoPath client and SharePoint Server 2013 provide the controls necessary to enable single, co-sign, and counter-sign scenarios for the full form or sections of the form. Forms can be signed in Internet Explorer using the ActiveX signature line control. Signed forms can be viewed in any browser supported by SharePoint Server 2013.</span></span>
  
## <a name="new-controls"></a><span data-ttu-id="020b8-169">新控件</span><span class="sxs-lookup"><span data-stu-id="020b8-169">New Controls</span></span>

<span data-ttu-id="020b8-p111">InfoPath 提供了更加丰富的控件集，可以将这些控件添加到表单。以下列表简要描述了部分新控件：</span><span class="sxs-lookup"><span data-stu-id="020b8-p111">InfoPath provides a richer set of controls that can be added to your forms. The following list briefly describes some of the new controls:</span></span>
  
- <span data-ttu-id="020b8-172">**图片按钮** - 在表单中使用任何图像作为按钮，而不是灰色矩形。</span><span class="sxs-lookup"><span data-stu-id="020b8-172">**Picture Button** — Instead of a gray rectangle; use any image as a button in your form.</span></span> 
    
- <span data-ttu-id="020b8-173">**超链接** - 使用户能够在填写表单时输入自己的超链接。</span><span class="sxs-lookup"><span data-stu-id="020b8-173">**Hyperlink** — Enable users to enter their own hyperlinks when filling out forms.</span></span> 
    
- <span data-ttu-id="020b8-174">**个人/组选取器** - 使用户能够在填写表单时检查和查询帐户名称和组。</span><span class="sxs-lookup"><span data-stu-id="020b8-174">**Person/Group Picker** — Enable users to check and query account names and groups when filling out forms.</span></span> 
    
- <span data-ttu-id="020b8-175">**实体选取器** - 使用户能够在填写表单时从运行 SharePoint Server 2013 的服务器上的外部列表中选择值。</span><span class="sxs-lookup"><span data-stu-id="020b8-175">**Entity Picker** — Enable users to select values from external lists on a server that is running SharePoint Server 2013 when forms.</span></span> 
    
- <span data-ttu-id="020b8-176">**签名行** - 在以数字方式对表单进行签名时，向用户提供签名行或图章图像（例如印鉴或判子图章）。</span><span class="sxs-lookup"><span data-stu-id="020b8-176">**Signature Line** — Provide users with a signature line or stamp image, such as an inkan or hanko seal, when digitally signing forms.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="020b8-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="020b8-177">See also</span></span>



[<span data-ttu-id="020b8-178">开发包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="020b8-178">Developing InfoPath Form Templates with Code</span></span>](developing-infopath-form-templates-with-code.md)
  
[<span data-ttu-id="020b8-179">使用 InfoPath 2003 对象模型开发表单模板</span><span class="sxs-lookup"><span data-stu-id="020b8-179">Developing Form Templates Using the InfoPath 2003 Object Model</span></span>](developing-form-templates-using-the-infopath-2003-object-model.md)

