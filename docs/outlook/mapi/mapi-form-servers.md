---
title: MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 855292b8-028e-4c1e-87ed-3f20b9ba584a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3c95f6a1d4d50dd6552c6e786d17c40da14f3f3c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419105"
---
# <a name="mapi-form-servers"></a><span data-ttu-id="8b006-103">MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="8b006-103">MAPI Form Servers</span></span>

  
  
<span data-ttu-id="8b006-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b006-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b006-105">从用户的角度来看, 窗体通常是邮件或数据输入窗体的属性表, 使用户能够输入结构化信息。</span><span class="sxs-lookup"><span data-stu-id="8b006-105">From the user's perspective, a form is usually a property sheet for a message or a data-entry form that enables users to enter structured information.</span></span> <span data-ttu-id="8b006-106">但是, 它可以是与邮件类关联的任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="8b006-106">However, it can be any user interface that is associated with a message class.</span></span> <span data-ttu-id="8b006-107">从程序员的角度来看, 表单包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="8b006-107">From a programmer's point of view, a form consists of:</span></span>
  
- <span data-ttu-id="8b006-108">一种 MAPI 邮件, 其中包含其自己的邮件类和 OLE 标识符。</span><span class="sxs-lookup"><span data-stu-id="8b006-108">A type of MAPI message with its own message class and OLE identifier.</span></span>
    
- <span data-ttu-id="8b006-109">实现表单服务器的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8b006-109">The executable file that implements the form server.</span></span>
    
- <span data-ttu-id="8b006-110">表单服务器使用的 MAPI 属性 (自定义或其他) 的集合。</span><span class="sxs-lookup"><span data-stu-id="8b006-110">A collection of MAPI properties — custom or otherwise — that the form server uses.</span></span> <span data-ttu-id="8b006-111">其中的部分或全部可供邮件客户端使用。</span><span class="sxs-lookup"><span data-stu-id="8b006-111">Some or all of these may be available to messaging clients for use.</span></span>
    
- <span data-ttu-id="8b006-112">描述表单并由表单管理器使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8b006-112">The configuration file that describes the form and is used by the form manager.</span></span>
    
<span data-ttu-id="8b006-113">由于表单是[IMessage](imessageimapiprop.md)对象, 因此它们展示了与 MAPI 邮件对象一致的属性和行为。</span><span class="sxs-lookup"><span data-stu-id="8b006-113">Because forms are [IMessage](imessageimapiprop.md) objects, they exhibit properties and behavior that is consistent with MAPI message objects.</span></span> <span data-ttu-id="8b006-114">但是, 由于表单可以具有特定于应用程序的自定义属性、控件和显示呈现, 因此表单使用的 MAPI 接口具有足够通用的功能, 以允许所需的任何类型的接口。</span><span class="sxs-lookup"><span data-stu-id="8b006-114">However, because forms can have custom properties, controls, and a display rendering that is application-specific, the MAPI interfaces that forms use are generic enough to permit any sort of interface that is needed.</span></span> <span data-ttu-id="8b006-115">表单的实际定义存储在表单库中, 本节后面将对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="8b006-115">The actual definition of a form is stored in a form library, which is discussed later in this section.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8b006-116">更准确地说, 所有邮件都是 MAPI 表单的实例。</span><span class="sxs-lookup"><span data-stu-id="8b006-116">More accurately, all messages are instances of MAPI forms.</span></span> <span data-ttu-id="8b006-117">但是, 由于用于撰写和阅读典型电子邮件的表单是最常用的窗体, 因此将自定义窗体视为邮件的特殊情况通常更易于使用。</span><span class="sxs-lookup"><span data-stu-id="8b006-117">However, it is usually easier to think of custom forms as special cases of messages, since forms for composing and reading typical email messages are the most commonly used forms.</span></span> <span data-ttu-id="8b006-118">所有邮件实际上只是表单, 自定义窗体的状态与 MAPI 系统中的任何其他邮件相同。</span><span class="sxs-lookup"><span data-stu-id="8b006-118">The fact that all messages are really just forms gives custom forms the same status as any other message in the MAPI system.</span></span> 
  
<span data-ttu-id="8b006-119">每个表单都有一组属性, 其中一些属性在表单的用户界面中可见。</span><span class="sxs-lookup"><span data-stu-id="8b006-119">Every form has a set of properties, some of which are visible in the form's user interface.</span></span> <span data-ttu-id="8b006-120">通常情况下, 属性与表单用户界面中的域相匹配。</span><span class="sxs-lookup"><span data-stu-id="8b006-120">Usually, properties are matched to fields in the form's user interface.</span></span> <span data-ttu-id="8b006-121">例如, 采购订单窗体可能具有字段 "项"、"说明"、"价格"、"税金" 和 "小计"。</span><span class="sxs-lookup"><span data-stu-id="8b006-121">For example, a purchase order form might have the fields Item, Description, Price, Tax, and Subtotal.</span></span> <span data-ttu-id="8b006-122">这些字段只是直观呈现来的窗体属性的名称。</span><span class="sxs-lookup"><span data-stu-id="8b006-122">These fields are simply visual renderings of form properties of the same names.</span></span> <span data-ttu-id="8b006-123">客户端通过[IMAPIFormInfo:: CalcFormPropSet](imapiforminfo-calcformpropset.md)方法 (由 MAPI 表单管理器实现) 确定特定邮件类支持哪些属性。</span><span class="sxs-lookup"><span data-stu-id="8b006-123">Clients ascertain which properties are supported by a particular message class through the [IMAPIFormInfo::CalcFormPropSet](imapiforminfo-calcformpropset.md) method, which is implemented by the MAPI form manager.</span></span> 
  
<span data-ttu-id="8b006-124">与基本邮件一样, MAPI 表单可以包含所有标准邮件属性, 如发件人、预期收件人和邮件发送时间。</span><span class="sxs-lookup"><span data-stu-id="8b006-124">Like basic messages, MAPI forms can contain all the standard message properties such as the sender, the intended recipient, and when the message was sent.</span></span> <span data-ttu-id="8b006-125">窗体还可以包含任意数量的窗体特有的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="8b006-125">Forms can also contain any number of custom properties that are specific to the form.</span></span> <span data-ttu-id="8b006-126">例如, "bug 报告" 表单可能包含 bug 类型、bug 严重性和产品版本的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="8b006-126">For example a "Bug Report" form might contain custom properties for Bug Type, Bug Severity, and Product Version.</span></span>
  
<span data-ttu-id="8b006-127">若要创建窗体, 您必须实现窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="8b006-127">To create a form you must implement a form server.</span></span> <span data-ttu-id="8b006-128">表单服务器是邮件客户端需要显示表单服务器支持的类型的邮件时加载的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8b006-128">The form server is the executable file that is loaded when a messaging client needs to display a message that is the type supported by the form server.</span></span> <span data-ttu-id="8b006-129">然后, 表单服务器将根据需要创建表单对象, 以显示特定邮件并处理用户与这些邮件的交互。</span><span class="sxs-lookup"><span data-stu-id="8b006-129">The form server in turn creates form objects as necessary to display specific messages and handle user interactions with those messages.</span></span>
  
<span data-ttu-id="8b006-130">每个窗体服务器都有一个与之关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8b006-130">Every form server has a configuration file associated with it.</span></span> <span data-ttu-id="8b006-131">此文件包含为表单管理器的优势描述表单服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="8b006-131">This file contains information that describes the form server for the benefit of the form manager.</span></span> <span data-ttu-id="8b006-132">在表单库中安装表单服务器时, 表单管理器将使用此信息。</span><span class="sxs-lookup"><span data-stu-id="8b006-132">The form manager uses this information when installing the form server into a form library.</span></span>
  
<span data-ttu-id="8b006-133">有关创建窗体的各个部分的详细信息, 请参阅[开发 MAPI 表单服务器](developing-mapi-form-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="8b006-133">For details on creating the parts of a form, see [Developing MAPI Form Servers](developing-mapi-form-servers.md).</span></span>
  
<span data-ttu-id="8b006-134">表单服务器遵循组件对象模型 (COM)。</span><span class="sxs-lookup"><span data-stu-id="8b006-134">Form servers adhere to the Component Object Model (COM).</span></span> <span data-ttu-id="8b006-135">表单服务器作为独立可执行文件运行, 而不是作为进程内服务器运行。</span><span class="sxs-lookup"><span data-stu-id="8b006-135">Form servers run as standalone executables, not as in-proc servers.</span></span> <span data-ttu-id="8b006-136">有关详细信息, 请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。</span><span class="sxs-lookup"><span data-stu-id="8b006-136">For more information, see the COM and ActiveX Object Services section in the Windows SDK.</span></span>
  
<span data-ttu-id="8b006-137">唯一的类标识符 (CLSID) 标识每个表单服务器。</span><span class="sxs-lookup"><span data-stu-id="8b006-137">A unique class identifier (CLSID) identifies each form server.</span></span> <span data-ttu-id="8b006-138">类标识符和它的邮件类之间始终存在一次一对一映射。</span><span class="sxs-lookup"><span data-stu-id="8b006-138">There is always a one-to-one mapping between a class identifier and its message class.</span></span> <span data-ttu-id="8b006-139">但是, 这并不意味着窗体服务器只能处理一个邮件类别的邮件。</span><span class="sxs-lookup"><span data-stu-id="8b006-139">This does not mean, however, that a form server can only work with messages of one message class.</span></span> <span data-ttu-id="8b006-140">如果没有可用于为特定类的邮件提供服务的表单服务器, 则使用的表单管理器应尝试在邮件类层次结构中更高的邮件类中查找窗体服务器;由 Windows SDK 提供的默认表单管理器将执行此工作。</span><span class="sxs-lookup"><span data-stu-id="8b006-140">If no form server is available to service a message of a particular class, the form manager being used should attempt to find a form server for a message class higher in the message class hierarchy; the default form manager supplied with the Windows SDK does this.</span></span> <span data-ttu-id="8b006-141">这样的窗体服务器可能只会呈现邮件属性 (超类支持的) 的子集, 但其效果将会更好。</span><span class="sxs-lookup"><span data-stu-id="8b006-141">Such a form server will probably be able to render only a subset of the message's properties (the ones supported by the superclass), but it will be better than nothing.</span></span> <span data-ttu-id="8b006-142">如果 "完全找不到匹配的表单服务器" 是特定于所使用的表单管理器的实现详细信息, 会发生什么情况;在这种情况下, 默认表单管理器不会打开邮件。</span><span class="sxs-lookup"><span data-stu-id="8b006-142">What happens when no matching form server is found at all is an implementation detail specific to the form manager being used; the default form manager does not open messages when this happens.</span></span>
  
<span data-ttu-id="8b006-143">有关详细信息, 请参阅[MAPI 邮件类别](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="8b006-143">For more information, see [MAPI Message Classes](mapi-message-classes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b006-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b006-144">See also</span></span>



[<span data-ttu-id="8b006-145">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="8b006-145">MAPI Forms</span></span>](mapi-forms.md)

