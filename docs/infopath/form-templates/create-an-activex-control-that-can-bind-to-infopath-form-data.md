---
title: 创建可绑定到 InfoPath 表单数据的 ActiveX 控件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a0d62047-bf08-9f70-de00-7f81ef1331f1
description: 您可以在 InfoPath 表单中承载设计为要在 InfoPath 编辑器中打开的 ActiveX 控件。这些控件可以预先存在（带有某些限制），也可以专门针对 InfoPath 编写。
ms.openlocfilehash: 90378533a7c3cde4a1927753c0325fdd8d0b3ce5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773971"
---
# <a name="create-an-activex-control-that-can-bind-to-infopath-form-data"></a><span data-ttu-id="58372-104">创建可绑定到 InfoPath 表单数据的 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="58372-104">Create an ActiveX Control that can Bind to InfoPath Form Data</span></span>

<span data-ttu-id="58372-p102">您可以在 InfoPath 表单中承载设计为要在 InfoPath 编辑器中打开的 ActiveX 控件。这些控件可以预先存在（带有某些限制），也可以专门针对 InfoPath 编写。</span><span class="sxs-lookup"><span data-stu-id="58372-p102">You can host ActiveX controls in InfoPath forms that are designed to be opened in the InfoPath editor. These controls can be preexisting (with some constraints) or can be written specifically for InfoPath.</span></span>
  
## <a name="write-an-activex-control"></a><span data-ttu-id="58372-107">编写 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="58372-107">Write an ActiveX Control</span></span>

<span data-ttu-id="58372-108">与 InfoPath 中的其他控件一样，ActiveX 控件应支持现有组件对象模型 (COM) 接口：</span><span class="sxs-lookup"><span data-stu-id="58372-108">As with other controls in InfoPath, ActiveX controls should support existing Component Object Model (COM) interfaces:</span></span>
  
- <span data-ttu-id="58372-109">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="58372-109">**IDispatch**</span></span>
    
- <span data-ttu-id="58372-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="58372-110">**IPersistPropertyBag**</span></span>
    
- <span data-ttu-id="58372-111">**IPersistStreamInit**</span><span class="sxs-lookup"><span data-stu-id="58372-111">**IPersistStreamInit**</span></span>
    
- <span data-ttu-id="58372-112">**IPropertyPage**</span><span class="sxs-lookup"><span data-stu-id="58372-112">**IPropertyPage**</span></span>
    
- <span data-ttu-id="58372-113">**IObjectSafety**</span><span class="sxs-lookup"><span data-stu-id="58372-113">**IObjectSafety**</span></span>
    
- <span data-ttu-id="58372-114">**IPropertyNotifySink**</span><span class="sxs-lookup"><span data-stu-id="58372-114">**IPropertyNotifySink**</span></span>
    
- <span data-ttu-id="58372-115">**IViewObject**</span><span class="sxs-lookup"><span data-stu-id="58372-115">**IViewObject**</span></span>
    
- <span data-ttu-id="58372-116">**IOleObject**</span><span class="sxs-lookup"><span data-stu-id="58372-116">**IOleObject**</span></span>
    
- <span data-ttu-id="58372-117">**IOleInPlaceObject**</span><span class="sxs-lookup"><span data-stu-id="58372-117">**IOleInPlaceObject**</span></span>
    
<span data-ttu-id="58372-118">为了使文档对象模型 (DOM) 中的属性在控件中发生更改时让 InfoPath 更新这些属性，控件应实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="58372-118">In order for InfoPath to update properties in the Document Object Model (DOM) at the time that they change in the control, the control should implement the following interfaces:</span></span>
  
- <span data-ttu-id="58372-119">**IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="58372-119">**IConnectionPointContainer**</span></span>
    
- <span data-ttu-id="58372-120">**IEnumConnectionPoints**</span><span class="sxs-lookup"><span data-stu-id="58372-120">**IEnumConnectionPoints**</span></span>
    
- <span data-ttu-id="58372-121">**IConnectionPoint**</span><span class="sxs-lookup"><span data-stu-id="58372-121">**IConnectionPoint**</span></span>
    
- <span data-ttu-id="58372-122">**IEnumConnections**</span><span class="sxs-lookup"><span data-stu-id="58372-122">**IEnumConnections**</span></span>
    
<span data-ttu-id="58372-123">此外，还有两个特定于 InfoPath 的 COM 接口，这些接口提供更为紧密的控件集成：</span><span class="sxs-lookup"><span data-stu-id="58372-123">Also, there are two InfoPath-specific COM interfaces that provide tighter integration of controls:</span></span>
  
- [<span data-ttu-id="58372-124">IInfoPathControl</span><span class="sxs-lookup"><span data-stu-id="58372-124">IInfoPathControl</span></span>](http://msdn.microsoft.com/zh-CN/library/bb264625.aspx)
    
- [<span data-ttu-id="58372-125">IInfoPathControlSite</span><span class="sxs-lookup"><span data-stu-id="58372-125">IInfoPathControlSite</span></span>](http://msdn.microsoft.com/zh-CN/library/bb264627.aspx)
    
## <a name="add-an-activex-control-to-the-infopath-design-environment"></a><span data-ttu-id="58372-126">向 InfoPath 设计环境中添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="58372-126">Add an ActiveX Control to the InfoPath Design Environment</span></span>

<span data-ttu-id="58372-127">通过“控件”**** 任务窗格上的 **Add or Remove Custom Controls** 命令，可以使用“添加自定义控件向导”**** 添加自定义控件。</span><span class="sxs-lookup"><span data-stu-id="58372-127">The **Add or Remove Custom Controls** command on the **Controls** task pane enables you to use the **Add Custom Control Wizard** to add a custom control. By using the wizard, you can select an ActiveX control that has already been registered or find additional custom controls on Office Marketplace. After you select a control, you can specify the following items.</span></span> <span data-ttu-id="58372-128">通过使用该向导，可以选择已注册的 ActiveX 控件或在 Office 市场上查找其他自定义控件。</span><span class="sxs-lookup"><span data-stu-id="58372-128">By using the wizard, you can select an ActiveX control that has already been registered or find additional custom controls on Office Marketplace.</span></span> <span data-ttu-id="58372-129">选择某个控件后，可以指定以下各项。</span><span class="sxs-lookup"><span data-stu-id="58372-129">After you select a control, you can specify the following items.</span></span> 
  
- <span data-ttu-id="58372-130">指定 CAB 以随表单模板一起安装 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="58372-130">Specify a CAB to install the ActiveX control with your form template.</span></span>
    
- <span data-ttu-id="58372-131">指定绑定属性以绑定到 XML。</span><span class="sxs-lookup"><span data-stu-id="58372-131">Specify a binding property to bind to the XML.</span></span>
    
- <span data-ttu-id="58372-132">指定一个属性，该属性用于启用或禁用控件以响应规则或数字签名，举例来说，当 XML 不存在或使用条件格式设置时，这样做将非常有用。</span><span class="sxs-lookup"><span data-stu-id="58372-132">Specify a property that is used to enable or disable the control in response to rules or digital signatures, which can be useful, for example, when the XML is not present or when conditional formatting is used.</span></span>
    
- <span data-ttu-id="58372-133">指定数据类型绑定。</span><span class="sxs-lookup"><span data-stu-id="58372-133">Specify data type binding.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58372-134">如果你在开发 ActiveX 控件并已将其添加到 InfoPath 中的“控件”**** 任务窗格，则在关闭 InfoPath 之前，你将无法重建 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="58372-134">If you are developing an ActiveX control and have added it to the Controls task pane in ipnover2, you will be unable to rebuild the ActiveX control until ipnover2 is closed.</span></span> 
  
## <a name="deploy-an-activex-control"></a><span data-ttu-id="58372-135">部署 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="58372-135">Deploy an ActiveX Control</span></span>

<span data-ttu-id="58372-p104">若要分发 ActiveX 控件，您可以编写一个安装程序，该安装程序将控件安装在目标计算机上，并将 InfoPath 控件模板 (ICT) 文件和 CAB 文件复制到用户的文件夹，即 \Users\\<用户名\>\AppData\Local\Microsoft\InfoPath\Controls。请注意，如果两名或更多开发人员在协作开发使用 ActiveX 控件的表单，则每名开发人员都应有已添加到 InfoPath 设计环境的控件，否则他们将无法从 InfoPath 中修改控件的属性。</span><span class="sxs-lookup"><span data-stu-id="58372-p104">To distribute an ActiveX control, you can write an installer that installs the control on the target computer and copies the InfoPath Control Template (ICT) file and the CAB file to the user's folder, \Users\\<username\>\AppData\Local\Microsoft\InfoPath\Controls. Note that if two or more developers are collaborating on developing forms that use ActiveX controls, each developer should have the controls that were added to the InfoPath design environment, or they will be unable to modify the properties of the controls from InfoPath.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58372-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58372-138">See also</span></span>



<span data-ttu-id="58372-139">实验室 6：在 InfoPath 2003 中添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="58372-139">Lab 6: Adding ActiveX Controls in InfoPath 2003</span></span>
  
[<span data-ttu-id="58372-140">使用 C# 和 .NET（InfoPath 团队博客）创建 InfoPath 自定义控件</span><span class="sxs-lookup"><span data-stu-id="58372-140">Creating an InfoPath Custom Control using C# and .NET (InfoPath Team Blog)</span></span>](http://blogs.msdn.com/infopath/archive/2005/04/15/creating-an-infopath-custom-control-using-c-and-net.aspx)

