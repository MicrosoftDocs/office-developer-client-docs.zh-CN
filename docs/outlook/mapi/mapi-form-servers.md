---
title: MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 855292b8-028e-4c1e-87ed-3f20b9ba584a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0b73e246ad5e396ef67e89bff5f1e04a47f6ebcb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569923"
---
# <a name="mapi-form-servers"></a><span data-ttu-id="5214b-103">MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="5214b-103">MAPI Form Servers</span></span>

  
  
<span data-ttu-id="5214b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5214b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5214b-105">从用户的角度来看，窗体通常是一条消息或数据输入表单使用户能够输入结构化的信息的属性页。</span><span class="sxs-lookup"><span data-stu-id="5214b-105">From the user's perspective, a form is usually a property sheet for a message or a data-entry form that enables users to enter structured information.</span></span> <span data-ttu-id="5214b-106">但是，它可以是任何与邮件类关联的用户界面。</span><span class="sxs-lookup"><span data-stu-id="5214b-106">However, it can be any user interface that is associated with a message class.</span></span> <span data-ttu-id="5214b-107">从程序员的角度来看，窗体组成：</span><span class="sxs-lookup"><span data-stu-id="5214b-107">From a programmer's point of view, a form consists of:</span></span>
  
- <span data-ttu-id="5214b-108">一种具有自己的邮件类和 OLE 标识符的 MAPI 邮件类型。</span><span class="sxs-lookup"><span data-stu-id="5214b-108">A type of MAPI message with its own message class and OLE identifier.</span></span>
    
- <span data-ttu-id="5214b-109">实现表单服务器的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5214b-109">The executable file that implements the form server.</span></span>
    
- <span data-ttu-id="5214b-110">MAPI 属性的集合 — 自定义或非 — 窗体服务器使用。</span><span class="sxs-lookup"><span data-stu-id="5214b-110">A collection of MAPI properties — custom or otherwise — that the form server uses.</span></span> <span data-ttu-id="5214b-111">部分或所有这些可供使用的消息客户端。</span><span class="sxs-lookup"><span data-stu-id="5214b-111">Some or all of these may be available to messaging clients for use.</span></span>
    
- <span data-ttu-id="5214b-112">描述窗体和窗体管理器使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="5214b-112">The configuration file that describes the form and is used by the form manager.</span></span>
    
<span data-ttu-id="5214b-113">窗体是[IMessage](imessageimapiprop.md)对象，因为它们表现属性和与 MAPI 消息对象一致的行为。</span><span class="sxs-lookup"><span data-stu-id="5214b-113">Because forms are [IMessage](imessageimapiprop.md) objects, they exhibit properties and behavior that is consistent with MAPI message objects.</span></span> <span data-ttu-id="5214b-114">但是，因为自定义属性、 控件和显示呈现的是接口的特定于应用程序，可以有窗体，窗体使用的 MAPI 接口是接口的足够通用的允许任何种类的所需。</span><span class="sxs-lookup"><span data-stu-id="5214b-114">However, because forms can have custom properties, controls, and a display rendering that is application-specific, the MAPI interfaces that forms use are generic enough to permit any sort of interface that is needed.</span></span> <span data-ttu-id="5214b-115">窗体的实际定义存储在表单库，其中更高版本本节中讨论。</span><span class="sxs-lookup"><span data-stu-id="5214b-115">The actual definition of a form is stored in a form library, which is discussed later in this section.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5214b-116">更准确地说，所有消息都都 MAPI 窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="5214b-116">More accurately, all messages are instances of MAPI forms.</span></span> <span data-ttu-id="5214b-117">但是，通常更容易看作自定义窗体的邮件，特殊情况的撰写窗体相和阅读典型电子邮件的最常用的窗体。</span><span class="sxs-lookup"><span data-stu-id="5214b-117">However, it is usually easier to think of custom forms as special cases of messages, since forms for composing and reading typical email messages are the most commonly used forms.</span></span> <span data-ttu-id="5214b-118">MAPI 系统中的所有消息都都实际上只是自定义窗体提供的这一事实 forms 相同状态为任何其他消息。</span><span class="sxs-lookup"><span data-stu-id="5214b-118">The fact that all messages are really just forms gives custom forms the same status as any other message in the MAPI system.</span></span> 
  
<span data-ttu-id="5214b-119">每个窗体有一组属性，其中一些可见窗体的用户界面中。</span><span class="sxs-lookup"><span data-stu-id="5214b-119">Every form has a set of properties, some of which are visible in the form's user interface.</span></span> <span data-ttu-id="5214b-120">通常，属性映射到窗体的用户界面中的字段。</span><span class="sxs-lookup"><span data-stu-id="5214b-120">Usually, properties are matched to fields in the form's user interface.</span></span> <span data-ttu-id="5214b-121">例如，采购订单表单中可能有项目、 说明、 价格、 税款和分类汇总字段。</span><span class="sxs-lookup"><span data-stu-id="5214b-121">For example, a purchase order form might have the fields Item, Description, Price, Tax, and Subtotal.</span></span> <span data-ttu-id="5214b-122">这些字段是只需 visual 呈现表单属性的相同的名称。</span><span class="sxs-lookup"><span data-stu-id="5214b-122">These fields are simply visual renderings of form properties of the same names.</span></span> <span data-ttu-id="5214b-123">客户端知晓通过[IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md)方法，由 MAPI 窗体管理器实现支持的特定邮件类的属性。</span><span class="sxs-lookup"><span data-stu-id="5214b-123">Clients ascertain which properties are supported by a particular message class through the [IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md) method, which is implemented by the MAPI form manager.</span></span> 
  
<span data-ttu-id="5214b-124">基本的邮件，类似 MAPI 窗体可以包含发件人，预期收件人，例如所有标准消息属性和发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="5214b-124">Like basic messages, MAPI forms can contain all the standard message properties such as the sender, the intended recipient, and when the message was sent.</span></span> <span data-ttu-id="5214b-125">表单还可包含任意数量的特定于窗体的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="5214b-125">Forms can also contain any number of custom properties that are specific to the form.</span></span> <span data-ttu-id="5214b-126">例如窗体"错误报告"可能的错误类型、 Bug 严重性和产品版本包含自定义属性。</span><span class="sxs-lookup"><span data-stu-id="5214b-126">For example a "Bug Report" form might contain custom properties for Bug Type, Bug Severity, and Product Version.</span></span>
  
<span data-ttu-id="5214b-127">若要创建窗体必须实现的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="5214b-127">To create a form you must implement a form server.</span></span> <span data-ttu-id="5214b-128">窗体服务器是消息客户端需要显示一条消息，是窗体服务器支持的类型时，将加载的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5214b-128">The form server is the executable file that is loaded when a messaging client needs to display a message that is the type supported by the form server.</span></span> <span data-ttu-id="5214b-129">窗体服务器轮流创建根据需要显示特定消息和处理这些邮件的用户交互的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="5214b-129">The form server in turn creates form objects as necessary to display specific messages and handle user interactions with those messages.</span></span>
  
<span data-ttu-id="5214b-130">每个窗体服务器具有与之关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5214b-130">Every form server has a configuration file associated with it.</span></span> <span data-ttu-id="5214b-131">此文件包含描述利益窗体管理器的窗体服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="5214b-131">This file contains information that describes the form server for the benefit of the form manager.</span></span> <span data-ttu-id="5214b-132">将窗体服务器安装到表单库时，窗体管理器将使用此信息。</span><span class="sxs-lookup"><span data-stu-id="5214b-132">The form manager uses this information when installing the form server into a form library.</span></span>
  
<span data-ttu-id="5214b-133">有关创建窗体的部件的详细信息，请参阅[开发 MAPI 表单服务器](developing-mapi-form-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="5214b-133">For details on creating the parts of a form, see [Developing MAPI Form Servers](developing-mapi-form-servers.md).</span></span>
  
<span data-ttu-id="5214b-134">窗体服务器遵循到组件对象模型 (COM)。</span><span class="sxs-lookup"><span data-stu-id="5214b-134">Form servers adhere to the Component Object Model (COM).</span></span> <span data-ttu-id="5214b-135">窗体作为独立的可执行文件，不为进程内服务器运行的服务器。</span><span class="sxs-lookup"><span data-stu-id="5214b-135">Form servers run as standalone executables, not as in-proc servers.</span></span> <span data-ttu-id="5214b-136">有关详细信息，请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务一节。</span><span class="sxs-lookup"><span data-stu-id="5214b-136">For more information, see the COM and ActiveX Object Services section in the Windows SDK.</span></span>
  
<span data-ttu-id="5214b-137">唯一的类标识符 (CLSID) 标识窗体中的每台服务器。</span><span class="sxs-lookup"><span data-stu-id="5214b-137">A unique class identifier (CLSID) identifies each form server.</span></span> <span data-ttu-id="5214b-138">始终是类标识符和其邮件类别之间的一对一映射。</span><span class="sxs-lookup"><span data-stu-id="5214b-138">There is always a one-to-one mapping between a class identifier and its message class.</span></span> <span data-ttu-id="5214b-139">但是，这并不意味着窗体服务器只能与一个邮件类的邮件。</span><span class="sxs-lookup"><span data-stu-id="5214b-139">This does not mean, however, that a form server can only work with messages of one message class.</span></span> <span data-ttu-id="5214b-140">如果没有窗体服务器可用服务的特定类一条消息，正在使用的窗体管理器应尝试查找邮件类层次结构; 中更快消息类表单服务器与 Windows SDK 一起提供的默认窗体管理器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5214b-140">If no form server is available to service a message of a particular class, the form manager being used should attempt to find a form server for a message class higher in the message class hierarchy; the default form manager supplied with the Windows SDK does this.</span></span> <span data-ttu-id="5214b-141">此类的窗体服务器可能能够呈现子集的消息的属性 （支持超链接），但它将优于 nothing。</span><span class="sxs-lookup"><span data-stu-id="5214b-141">Such a form server will probably be able to render only a subset of the message's properties (the ones supported by the superclass), but it will be better than nothing.</span></span> <span data-ttu-id="5214b-142">根本不找到任何匹配的窗体服务器时，会发生什么情况是特定于正在使用; 窗体管理器实现详细信息默认窗体管理器未打开邮件时发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5214b-142">What happens when no matching form server is found at all is an implementation detail specific to the form manager being used; the default form manager does not open messages when this happens.</span></span>
  
<span data-ttu-id="5214b-143">有关详细信息，请参阅[MAPI 邮件类](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="5214b-143">For more information, see [MAPI Message Classes](mapi-message-classes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5214b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5214b-144">See also</span></span>



[<span data-ttu-id="5214b-145">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="5214b-145">MAPI Forms</span></span>](mapi-forms.md)

