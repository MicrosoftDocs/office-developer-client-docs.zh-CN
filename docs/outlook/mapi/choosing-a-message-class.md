---
title: 选择邮件类
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
# <a name="choosing-a-message-class"></a><span data-ttu-id="5ad5e-103">选择邮件类</span><span class="sxs-lookup"><span data-stu-id="5ad5e-103">Choosing a Message Class</span></span>

  
  
<span data-ttu-id="5ad5e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ad5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ad5e-105">如 [MAPI 邮件类中所述](mapi-message-classes.md)，邮件类对于在自定义邮件类型之间以及表单服务器本身（按扩展名）之间建立关系非常重要。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-105">As described in [MAPI Message Classes](mapi-message-classes.md), message classes are important for establishing the relationship between types of custom messages and, by extension, between form servers themselves.</span></span> <span data-ttu-id="5ad5e-106">幸运的是，选择邮件类字符串相当简单。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-106">Fortunately, choosing a message class string is fairly simple.</span></span> <span data-ttu-id="5ad5e-107">邮件类的邮件类字符串是任意字符串，但它应使用以下约定：</span><span class="sxs-lookup"><span data-stu-id="5ad5e-107">The message class string of a message class is an arbitrary string, but it should use the following conventions:</span></span>
  
- <span data-ttu-id="5ad5e-108">该字符串应满足文档中介绍的所有约定，如 PR_MESSAGE_CLASS ( [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-108">The string should satisfy all the conventions described in the documentation for the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span> <span data-ttu-id="5ad5e-109">重要的是，字符串必须完全由 ANSI 字符组成，且长度必须少于 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-109">Importantly, the string must be composed entirely of ANSI characters and be less than 256 characters long.</span></span>
    
- <span data-ttu-id="5ad5e-110">如果您的表单服务器派生自现有表单服务器或现有表单服务器的扩展，则应该通过向表单所基于的表单服务器的邮件类字符串添加句点和另一个单词来形成邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-110">If your form server is derived from an existing form server or is an extension of an existing form server, your message class string should be formed by adding a period and another word to the message class string of the form server that your form is based on.</span></span> <span data-ttu-id="5ad5e-111">例如，您可能希望实现一个表单来重新安排会议，并且您的表单基于用于安排会议的现有表单。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-111">For example, you might want to implement a form to reschedule a meeting, and your form is based on an existing form for scheduling meetings.</span></span> <span data-ttu-id="5ad5e-112">如果会议安排表单的邮件类字符串为"IPM"。Meeting，你的邮件类字符串可能是"IPM"。Meeting.Reschedule"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-112">If the meeting scheduling form's message class string is "IPM.Meeting", your message class string could be "IPM.Meeting.Reschedule".</span></span>
    
- <span data-ttu-id="5ad5e-113">如果您的表单不基于任何现有表单，则邮件类字符串仍应该以"IPM"开头。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-113">If your form is not based on any existing form, your message class string should still begin with either the "IPM."</span></span> <span data-ttu-id="5ad5e-114">或"IPC"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-114">or "IPC."</span></span> <span data-ttu-id="5ad5e-115">前缀，具体取决于表单是供人员接收还是由另一个应用程序接收。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-115">prefix, depending on whether the form is intended to be received by a person or by another application.</span></span> <span data-ttu-id="5ad5e-116">"IPM"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-116">"IPM."</span></span> <span data-ttu-id="5ad5e-117">指定通常以用户收件箱结尾的外向邮件和"IPC"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-117">designates an interpersonal message that usually ends up in a user's Inbox, and "IPC."</span></span> <span data-ttu-id="5ad5e-118">指定通常不传递到用户收件箱的进程间通信邮件。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-118">designates an interprocess communication message that is not typically delivered to a user's Inbox.</span></span>
    
- <span data-ttu-id="5ad5e-119">如果邮件类是可人工读取的，则邮件类字符串应以"IPM"开头。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-119">If your message class is intended to be human-readable, the message class string should start with "IPM."</span></span> <span data-ttu-id="5ad5e-120">如果邮件类使用包含 RTF 格式的纯文本、HTML 或 RTF 格式的任何属性，则通常 (可读) 数据。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-120">A message class is generally considered human-readable if it uses any properties that contain plain text, HTML, or Rich Text Format (RTF) data.</span></span> <span data-ttu-id="5ad5e-121">如果您的表单使用 PidTagBody **PR_BODY (** [PidTagBody](pidtagbody-canonical-property.md)) ，它几乎一定使用"IPM"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-121">If your form uses the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, it should almost certainly use an "IPM."</span></span> <span data-ttu-id="5ad5e-122">message 类字符串。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-122">message class string.</span></span> <span data-ttu-id="5ad5e-123">例如，如果要为采购订单实现表单，并且您的组织要求经理批准采购订单，则邮件类字符串可以是"IPM"。Purchase_Order"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-123">For example, if you are implementing a form for purchase orders, and your organization requires that purchase orders be approved by a manager, your message class string could be "IPM.Purchase_Order".</span></span> <span data-ttu-id="5ad5e-124">设计为与公用文件夹或公用文件夹应用程序一同使用的表单通常被视为一种社会性表单，因为它们由用户读取，即使它们实际上并未寻址到任何人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-124">Forms that are designed for use with public folders or public folder applications are typically considered to be interpersonal because they are read by people even though they are not actually addressed to any person's email address.</span></span> <span data-ttu-id="5ad5e-125">公用文件夹邮件类的典型前缀为"IPM"。Post"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-125">The typical prefix for public folder message classes is "IPM.Post".</span></span> 
    
- <span data-ttu-id="5ad5e-126">如果邮件类由另一个应用程序而不是人员接收，则邮件类字符串应以"IPC"开头。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-126">If your message class is intended to be received by another application instead of by a person, the message class string should start with "IPC."</span></span> <span data-ttu-id="5ad5e-127">例如，如果要实现使用户能够自动订阅邮件列表的窗体，则邮件类字符串可以是"IPC"。订阅"。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-127">For example, if you are implementing a form that enables people to automatically subscribe to mailing lists, your message class string could be "IPC.Subscribe".</span></span>
    
- <span data-ttu-id="5ad5e-128">您的邮件类字符串永远不应以一个时间段结尾。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-128">Your message class string should never end with a period.</span></span>
    
<span data-ttu-id="5ad5e-129">邮件类字符串应放在表单配置文件的 **[Description]** 部分中的 **MessageClass** 条目中，类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="5ad5e-129">The message class string should be put in the **[Description]** section of the form configuration file, in the **MessageClass** entry, similar to the following:</span></span> 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
<span data-ttu-id="5ad5e-130">选择适当的邮件类字符串后，应生成其类标识符。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-130">After you have chosen an appropriate message class string, you should generate a class identifier for it.</span></span> <span data-ttu-id="5ad5e-131">类标识符可以使用包含在 Visual Studio 中的 **Create GUID** 命令生成。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-131">Class identifiers can be generated with the **Create GUID** command that is included in Visual Studio.</span></span> <span data-ttu-id="5ad5e-132">类标识符必须与 **MessageClass** 条目一起放在表单配置文件的 **CLSID** 条目中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ad5e-132">The class identifier must be put in the form configuration file's **CLSID** entry, along with the **MessageClass** entry, similar to the following:</span></span> 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
<span data-ttu-id="5ad5e-133">当然，你的类标识符几乎肯定不同。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-133">Your class identifier will almost certainly be different, of course.</span></span> <span data-ttu-id="5ad5e-134">有关详细信息，请参阅 [创建表单配置文件](creating-a-form-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-134">For more information, see [Creating a Form Configuration File](creating-a-form-configuration-file.md).</span></span>
  
<span data-ttu-id="5ad5e-135">在用户计算机上安装表单时，您的安装过程（无论是安装程序还是其他过程）必须在注册表的 \**HKEY_CLASSES_ROOT\CLSID\** 部分中为类标识符创建注册表项。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-135">When the form is installed on a user's computer, your installation process — whether it is a setup program or something else — must make a registry entry in the \**HKEY_CLASSES_ROOT\CLSID\** section of the registry for the class identifier.</span></span> <span data-ttu-id="5ad5e-136">此项必须设置为邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-136">This entry must be set to the message class string.</span></span> <span data-ttu-id="5ad5e-137">例如，您将为上述示例类标识符创建类似于下面的注册表项：</span><span class="sxs-lookup"><span data-stu-id="5ad5e-137">For example, you would create a registry entry similar to the following for the example class identifier above:</span></span> 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
<span data-ttu-id="5ad5e-138">有关详细信息，请参阅 [将窗体安装到库中](installing-a-form-into-a-library.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad5e-138">For more information, see [Installing a Form into a Library](installing-a-form-into-a-library.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ad5e-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ad5e-139">See also</span></span>



[<span data-ttu-id="5ad5e-140">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="5ad5e-140">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

