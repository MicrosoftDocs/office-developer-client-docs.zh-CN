---
title: 选择邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ca8edd2-41b7-40e2-b755-b28eecb49786
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 279df7f07c8c8b66347488c6224d04f70292e968
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428051"
---
# <a name="choosing-a-message-class"></a><span data-ttu-id="d6917-103">选择邮件类别</span><span class="sxs-lookup"><span data-stu-id="d6917-103">Choosing a Message Class</span></span>

  
  
<span data-ttu-id="d6917-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6917-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6917-105">如[MAPI 消息类](mapi-message-classes.md)中所述, 邮件类对于在表单服务器本身之间建立自定义邮件类型和扩展之间的关系非常重要。</span><span class="sxs-lookup"><span data-stu-id="d6917-105">As described in [MAPI Message Classes](mapi-message-classes.md), message classes are important for establishing the relationship between types of custom messages and, by extension, between form servers themselves.</span></span> <span data-ttu-id="d6917-106">幸运的是, 选择邮件类字符串相当简单。</span><span class="sxs-lookup"><span data-stu-id="d6917-106">Fortunately, choosing a message class string is fairly simple.</span></span> <span data-ttu-id="d6917-107">邮件类的邮件类字符串是任意字符串, 但它应使用以下约定:</span><span class="sxs-lookup"><span data-stu-id="d6917-107">The message class string of a message class is an arbitrary string, but it should use the following conventions:</span></span>
  
- <span data-ttu-id="d6917-108">该字符串应满足**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性的文档中所述的所有约定。</span><span class="sxs-lookup"><span data-stu-id="d6917-108">The string should satisfy all the conventions described in the documentation for the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span> <span data-ttu-id="d6917-109">重要的是, 该字符串必须完全由 ANSI 字符组成, 并且长度不超过256个字符。</span><span class="sxs-lookup"><span data-stu-id="d6917-109">Importantly, the string must be composed entirely of ANSI characters and be less than 256 characters long.</span></span>
    
- <span data-ttu-id="d6917-110">如果您的表单服务器是从现有表单服务器派生的, 或者是现有表单服务器的扩展, 则应通过向您的表单所基于的表单服务器的邮件类字符串添加一个句点和另一个词来形成您的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="d6917-110">If your form server is derived from an existing form server or is an extension of an existing form server, your message class string should be formed by adding a period and another word to the message class string of the form server that your form is based on.</span></span> <span data-ttu-id="d6917-111">例如, 您可能希望实施一个表单以重新安排会议, 而您的表单基于现有表单来安排会议。</span><span class="sxs-lookup"><span data-stu-id="d6917-111">For example, you might want to implement a form to reschedule a meeting, and your form is based on an existing form for scheduling meetings.</span></span> <span data-ttu-id="d6917-112">如果会议计划表单的邮件类字符串为 "IPM。会议 ", 您的邮件类字符串可能是" IPM。会议 "重新安排"。</span><span class="sxs-lookup"><span data-stu-id="d6917-112">If the meeting scheduling form's message class string is "IPM.Meeting", your message class string could be "IPM.Meeting.Reschedule".</span></span>
    
- <span data-ttu-id="d6917-113">如果窗体不基于任何现有的窗体, 则邮件类字符串仍应以 "IPM" 开头。</span><span class="sxs-lookup"><span data-stu-id="d6917-113">If your form is not based on any existing form, your message class string should still begin with either the "IPM."</span></span> <span data-ttu-id="d6917-114">或 "IPC"。</span><span class="sxs-lookup"><span data-stu-id="d6917-114">or "IPC."</span></span> <span data-ttu-id="d6917-115">前缀, 具体取决于窗体是供用户接收还是由其他应用程序接收。</span><span class="sxs-lookup"><span data-stu-id="d6917-115">prefix, depending on whether the form is intended to be received by a person or by another application.</span></span> <span data-ttu-id="d6917-116">"IPM."</span><span class="sxs-lookup"><span data-stu-id="d6917-116">"IPM."</span></span> <span data-ttu-id="d6917-117">指定通常在用户的收件箱中结束的人际邮件和 "IPC"。</span><span class="sxs-lookup"><span data-stu-id="d6917-117">designates an interpersonal message that usually ends up in a user's Inbox, and "IPC."</span></span> <span data-ttu-id="d6917-118">指定通常不传递到用户收件箱的进程间通信消息。</span><span class="sxs-lookup"><span data-stu-id="d6917-118">designates an interprocess communication message that is not typically delivered to a user's Inbox.</span></span>
    
- <span data-ttu-id="d6917-119">如果您的邮件类可供人工阅读, 则邮件类字符串应以 "IPM." 开头。</span><span class="sxs-lookup"><span data-stu-id="d6917-119">If your message class is intended to be human-readable, the message class string should start with "IPM."</span></span> <span data-ttu-id="d6917-120">如果邮件类别使用任何包含纯文本、HTML 或 rtf 格式 (rtf) 数据的属性, 通常会将邮件类别视为可读邮件。</span><span class="sxs-lookup"><span data-stu-id="d6917-120">A message class is generally considered human-readable if it uses any properties that contain plain text, HTML, or Rich Text Format (RTF) data.</span></span> <span data-ttu-id="d6917-121">如果您的表单使用**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性, 则几乎一定要使用 "IPM"。</span><span class="sxs-lookup"><span data-stu-id="d6917-121">If your form uses the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, it should almost certainly use an "IPM."</span></span> <span data-ttu-id="d6917-122">邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="d6917-122">message class string.</span></span> <span data-ttu-id="d6917-123">例如, 如果您要为采购订单实施一个表单, 并且您的组织要求由经理批准该采购订单, 则您的邮件类字符串可能是 "IPM。Purchase_Order "。</span><span class="sxs-lookup"><span data-stu-id="d6917-123">For example, if you are implementing a form for purchase orders, and your organization requires that purchase orders be approved by a manager, your message class string could be "IPM.Purchase_Order".</span></span> <span data-ttu-id="d6917-124">设计为与公用文件夹或公用文件夹应用程序一起使用的表单通常被视为 "人际", 因为他们会被人阅读, 即使它们实际上并不是发往任何人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d6917-124">Forms that are designed for use with public folders or public folder applications are typically considered to be interpersonal because they are read by people even though they are not actually addressed to any person's email address.</span></span> <span data-ttu-id="d6917-125">公用文件夹邮件类别的典型前缀是 "IPM。Post "。</span><span class="sxs-lookup"><span data-stu-id="d6917-125">The typical prefix for public folder message classes is "IPM.Post".</span></span> 
    
- <span data-ttu-id="d6917-126">如果您的邮件类打算由另一个应用程序而不是某人接收, 则邮件类字符串应以 "IPC" 开头。</span><span class="sxs-lookup"><span data-stu-id="d6917-126">If your message class is intended to be received by another application instead of by a person, the message class string should start with "IPC."</span></span> <span data-ttu-id="d6917-127">例如, 如果您要实现一个使用户能够自动订阅邮件列表的表单, 则邮件类字符串可能为 "IPC。订阅 "。</span><span class="sxs-lookup"><span data-stu-id="d6917-127">For example, if you are implementing a form that enables people to automatically subscribe to mailing lists, your message class string could be "IPC.Subscribe".</span></span>
    
- <span data-ttu-id="d6917-128">您的邮件类字符串永远不应以句点结尾。</span><span class="sxs-lookup"><span data-stu-id="d6917-128">Your message class string should never end with a period.</span></span>
    
<span data-ttu-id="d6917-129">邮件类字符串应放在表单配置文件的 "**说明**" 部分的 " **MessageClass** " 条目中, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d6917-129">The message class string should be put in the **[Description]** section of the form configuration file, in the **MessageClass** entry, similar to the following:</span></span> 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
<span data-ttu-id="d6917-130">选择适当的邮件类字符串后, 应为其生成类标识符。</span><span class="sxs-lookup"><span data-stu-id="d6917-130">After you have chosen an appropriate message class string, you should generate a class identifier for it.</span></span> <span data-ttu-id="d6917-131">可以使用 Visual Studio 中包含的**Create GUID**命令生成类标识符。</span><span class="sxs-lookup"><span data-stu-id="d6917-131">Class identifiers can be generated with the **Create GUID** command that is included in Visual Studio.</span></span> <span data-ttu-id="d6917-132">类标识符必须放在表单配置文件的**CLSID**条目中, 以及**MessageClass**条目, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d6917-132">The class identifier must be put in the form configuration file's **CLSID** entry, along with the **MessageClass** entry, similar to the following:</span></span> 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
<span data-ttu-id="d6917-133">当然, 您的类标识符几乎也是不同的。</span><span class="sxs-lookup"><span data-stu-id="d6917-133">Your class identifier will almost certainly be different, of course.</span></span> <span data-ttu-id="d6917-134">有关详细信息, 请参阅[创建表单配置文件](creating-a-form-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="d6917-134">For more information, see [Creating a Form Configuration File](creating-a-form-configuration-file.md).</span></span>
  
<span data-ttu-id="d6917-135">当表单安装在用户计算机上时, 您的安装过程 (无论是安装程序还是其他内容) 必须在注册表的 \*\*HKEY_CLASSES_ROOT\CLSID\* \*部分中为类标识符生成一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="d6917-135">When the form is installed on a user's computer, your installation process — whether it is a setup program or something else — must make a registry entry in the \**HKEY_CLASSES_ROOT\CLSID\** section of the registry for the class identifier.</span></span> <span data-ttu-id="d6917-136">此条目必须设置为邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="d6917-136">This entry must be set to the message class string.</span></span> <span data-ttu-id="d6917-137">例如, 您可以为上面的示例类标识符创建类似于以下的注册表项:</span><span class="sxs-lookup"><span data-stu-id="d6917-137">For example, you would create a registry entry similar to the following for the example class identifier above:</span></span> 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
<span data-ttu-id="d6917-138">有关详细信息, 请参阅将[表单安装到库](installing-a-form-into-a-library.md)中。</span><span class="sxs-lookup"><span data-stu-id="d6917-138">For more information, see [Installing a Form into a Library](installing-a-form-into-a-library.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6917-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6917-139">See also</span></span>



[<span data-ttu-id="d6917-140">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="d6917-140">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

