---
title: 选择邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ca8edd2-41b7-40e2-b755-b28eecb49786
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c3b486838c6ce2d7fc38d950a4de6f4589767073
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574235"
---
# <a name="choosing-a-message-class"></a><span data-ttu-id="e4fd6-103">选择邮件类别</span><span class="sxs-lookup"><span data-stu-id="e4fd6-103">Choosing a Message Class</span></span>

  
  
<span data-ttu-id="e4fd6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4fd6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4fd6-105">如[MAPI 邮件类](mapi-message-classes.md)中所述，邮件类很重要建立类型的自定义消息，并按扩展名，他们自己的窗体服务器之间的关系。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-105">As described in [MAPI Message Classes](mapi-message-classes.md), message classes are important for establishing the relationship between types of custom messages and, by extension, between form servers themselves.</span></span> <span data-ttu-id="e4fd6-106">幸运的是，选择消息类字符串是相当简单。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-106">Fortunately, choosing a message class string is fairly simple.</span></span> <span data-ttu-id="e4fd6-107">邮件类的邮件类字符串的任意字符串，但它应使用以下约定：</span><span class="sxs-lookup"><span data-stu-id="e4fd6-107">The message class string of a message class is an arbitrary string, but it should use the following conventions:</span></span>
  
- <span data-ttu-id="e4fd6-108">字符串应满足所有**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性文档中所述的约定。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-108">The string should satisfy all the conventions described in the documentation for the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span> <span data-ttu-id="e4fd6-109">重要的是，该字符串必须完全组成 ANSI 字符，为长度小于 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-109">Importantly, the string must be composed entirely of ANSI characters and be less than 256 characters long.</span></span>
    
- <span data-ttu-id="e4fd6-110">如果您的窗体服务器派生自现有表单服务器或是一种扩展的现有的窗体服务器，则邮件类字符串应通过将一个句点和另一个单词添加到表单服务器表单所基于的邮件类字符串格式正确。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-110">If your form server is derived from an existing form server or is an extension of an existing form server, your message class string should be formed by adding a period and another word to the message class string of the form server that your form is based on.</span></span> <span data-ttu-id="e4fd6-111">例如，您可能希望实现的窗体重新计划会议，并且表单基于现有表单安排会议。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-111">For example, you might want to implement a form to reschedule a meeting, and your form is based on an existing form for scheduling meetings.</span></span> <span data-ttu-id="e4fd6-112">如果会议安排窗体的邮件类字符串是"IPM。会议"，则邮件类字符串可以是"IPM。Meeting.Reschedule"。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-112">If the meeting scheduling form's message class string is "IPM.Meeting", your message class string could be "IPM.Meeting.Reschedule".</span></span>
    
- <span data-ttu-id="e4fd6-113">如果窗体不基于任何现有的窗体，则邮件类字符串应仍开头任一"IPM。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-113">If your form is not based on any existing form, your message class string should still begin with either the "IPM."</span></span> <span data-ttu-id="e4fd6-114">或者"IPC。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-114">or "IPC."</span></span> <span data-ttu-id="e4fd6-115">前缀，具体取决于是否窗体旨在接收由人员或另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-115">prefix, depending on whether the form is intended to be received by a person or by another application.</span></span> <span data-ttu-id="e4fd6-116">"IPM。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-116">"IPM."</span></span> <span data-ttu-id="e4fd6-117">指定一人际邮件，其中通常中的最终用户的收件箱中和"IPC。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-117">designates an interpersonal message that usually ends up in a user's Inbox, and "IPC."</span></span> <span data-ttu-id="e4fd6-118">指定通常未发送给用户的收件箱进程间通信消息。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-118">designates an interprocess communication message that is not typically delivered to a user's Inbox.</span></span>
    
- <span data-ttu-id="e4fd6-119">如果您的邮件类用于为可读，消息类字符串应开头"IPM。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-119">If your message class is intended to be human-readable, the message class string should start with "IPM."</span></span> <span data-ttu-id="e4fd6-120">邮件类通常被视为可读如果它使用所有包含纯文本、 HTML 属性或富文本格式 (RTF) 数据。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-120">A message class is generally considered human-readable if it uses any properties that contain plain text, HTML, or Rich Text Format (RTF) data.</span></span> <span data-ttu-id="e4fd6-121">如果表单使用**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，它应几乎可以使用"IPM。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-121">If your form uses the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, it should almost certainly use an "IPM."</span></span> <span data-ttu-id="e4fd6-122">邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-122">message class string.</span></span> <span data-ttu-id="e4fd6-123">例如，如果要实现的采购订单表单，并且您的组织需要采购订单将经管理员，您的邮件类字符串可以是"IPM。Purchase_Order"。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-123">For example, if you are implementing a form for purchase orders, and your organization requires that purchase orders be approved by a manager, your message class string could be "IPM.Purchase_Order".</span></span> <span data-ttu-id="e4fd6-124">为设计的窗体使用公用文件夹或公用文件夹应用程序通常被视为是人际，由于它们读取的人员，即使它们不实际寻址到任何人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-124">Forms that are designed for use with public folders or public folder applications are typically considered to be interpersonal because they are read by people even though they are not actually addressed to any person's email address.</span></span> <span data-ttu-id="e4fd6-125">公用文件夹的邮件类的典型前缀是"IPM。文章"。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-125">The typical prefix for public folder message classes is "IPM.Post".</span></span> 
    
- <span data-ttu-id="e4fd6-126">如果您的邮件类用于由人员接收的而不是另一个应用程序，消息类字符串应开头"IPC。"</span><span class="sxs-lookup"><span data-stu-id="e4fd6-126">If your message class is intended to be received by another application instead of by a person, the message class string should start with "IPC."</span></span> <span data-ttu-id="e4fd6-127">例如，如果要实现，使人们能够自动订阅邮件列表窗体，则邮件类字符串可以是"IPC。订阅"。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-127">For example, if you are implementing a form that enables people to automatically subscribe to mailing lists, your message class string could be "IPC.Subscribe".</span></span>
    
- <span data-ttu-id="e4fd6-128">您的邮件类字符串应永远不会以句点结尾。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-128">Your message class string should never end with a period.</span></span>
    
<span data-ttu-id="e4fd6-129">邮件类字符串应置于中**MessageClass**条目，类似于以下的窗体配置文件的 **[描述]** 部分：</span><span class="sxs-lookup"><span data-stu-id="e4fd6-129">The message class string should be put in the **[Description]** section of the form configuration file, in the **MessageClass** entry, similar to the following:</span></span> 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
<span data-ttu-id="e4fd6-130">您已选择相应的消息类字符串后，您应为其生成的类标识符。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-130">After you have chosen an appropriate message class string, you should generate a class identifier for it.</span></span> <span data-ttu-id="e4fd6-131">可以使用包含在 Visual Studio 中**创建 GUID**命令生成的类标识符。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-131">Class identifiers can be generated with the **Create GUID** command that is included in Visual Studio.</span></span> <span data-ttu-id="e4fd6-132">必须在窗体配置文件的**CLSID**项，以及该**MessageClass**条目，类似于以下放置的类标识符：</span><span class="sxs-lookup"><span data-stu-id="e4fd6-132">The class identifier must be put in the form configuration file's **CLSID** entry, along with the **MessageClass** entry, similar to the following:</span></span> 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
<span data-ttu-id="e4fd6-133">您的类标识符几乎可以将不同，当然。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-133">Your class identifier will almost certainly be different, of course.</span></span> <span data-ttu-id="e4fd6-134">有关详细信息，请参阅[创建窗体配置文件](creating-a-form-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-134">For more information, see [Creating a Form Configuration File](creating-a-form-configuration-file.md).</span></span>
  
<span data-ttu-id="e4fd6-135">在安装过程的用户的计算机上安装该窗体的时 — 是否安装程序或其他内容 — 必须进行中的注册表项 **HKEY_CLASSES_ROOT\CLSID\** 部分中的类标识符的注册表。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-135">When the form is installed on a user's computer, your installation process — whether it is a setup program or something else — must make a registry entry in the **HKEY_CLASSES_ROOT\CLSID\** section of the registry for the class identifier.</span></span> <span data-ttu-id="e4fd6-136">此条目必须设置为邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-136">This entry must be set to the message class string.</span></span> <span data-ttu-id="e4fd6-137">例如，将创建一个注册表项与上面的示例类标识符的以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="e4fd6-137">For example, you would create a registry entry similar to the following for the example class identifier above:</span></span> 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
<span data-ttu-id="e4fd6-138">有关详细信息，请参阅[安装到库窗体](installing-a-form-into-a-library.md)。</span><span class="sxs-lookup"><span data-stu-id="e4fd6-138">For more information, see [Installing a Form into a Library](installing-a-form-into-a-library.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4fd6-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4fd6-139">See also</span></span>



[<span data-ttu-id="e4fd6-140">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="e4fd6-140">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

