---
title: 窗体存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ddf9158-3c10-408a-aeaf-5a382c4339e7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a99ef76e63e634c661bf82bdab10b86c843e0df0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774972"
---
# <a name="form-storage"></a><span data-ttu-id="d17bc-103">窗体存储</span><span class="sxs-lookup"><span data-stu-id="d17bc-103">Form storage</span></span>

<span data-ttu-id="d17bc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d17bc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d17bc-105">尽管不需要知道的如何从物理上隔离存储窗体的所有详细信息，它可了解几个主要概念。</span><span class="sxs-lookup"><span data-stu-id="d17bc-105">Although it is not necessary to know all the details of how forms are physically stored, it is useful to understand a few of the main concepts.</span></span> <span data-ttu-id="d17bc-106">因此之前描述的三种类型的默认窗体管理器支持的表单库，本主题概述了如何存储窗体。</span><span class="sxs-lookup"><span data-stu-id="d17bc-106">Therefore, before describing the three types of form libraries supported by the default form manager, this topic gives an overview of how forms are stored.</span></span>
  
<span data-ttu-id="d17bc-107">表单定义可以从物理上隔离存储在一个或多个 MAPI 消息存储中的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d17bc-107">Form definitions can be physically stored within folders in one or more MAPI message stores.</span></span> <span data-ttu-id="d17bc-108">每个 MAPI 文件夹可以被认为是具有用于存储消息对象的两个方面： 标准部件和关联的部件。</span><span class="sxs-lookup"><span data-stu-id="d17bc-108">Every MAPI folder can be thought of as having two areas for storing message objects: the standard part and the associated part.</span></span> <span data-ttu-id="d17bc-109">文件夹的标准部分包括消息和用户操作的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d17bc-109">The standard part of the folder includes the messages and folders that users manipulate.</span></span>
  
<span data-ttu-id="d17bc-110">相关联的部分包括隐藏的邮件对象与该文件夹，包括表单定义、 视图、 规则模板关联的答复模板，等等。</span><span class="sxs-lookup"><span data-stu-id="d17bc-110">The associated part includes hidden message objects that are associated with the folder, including form definitions, views, rule templates, reply templates, and so on.</span></span> <span data-ttu-id="d17bc-111">此备用部件调用文件夹关联的内容表中，并的关联的内容表中的消息集被称为的文件夹关联的信息。</span><span class="sxs-lookup"><span data-stu-id="d17bc-111">This alternate part is called the folder-associated contents table, and the set of messages in the associated contents table is referred to as the folder-associated information.</span></span> <span data-ttu-id="d17bc-112">隐藏的邮件的文件夹的必要组成部分，并复制文件夹时标准文件夹内容以及复制。</span><span class="sxs-lookup"><span data-stu-id="d17bc-112">The hidden messages are an integral part of the folder and are copied along with the standard folder contents when the folder is copied.</span></span> <span data-ttu-id="d17bc-113">物理存储为邮件，尽管文件夹关联的内容表中的信息行为更像属性比 like 可查看邮件。</span><span class="sxs-lookup"><span data-stu-id="d17bc-113">Although physically stored as messages, information in a folder's associated contents table behaves more like properties than like viewable messages.</span></span> <span data-ttu-id="d17bc-114">支持的关联的内容表的任何文件夹对象是可存储自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="d17bc-114">Any folder object that supports an associated contents table is capable of storing custom forms.</span></span> <span data-ttu-id="d17bc-115">[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法可以返回标准内容或关联的文件夹，具体取决于该方法的_ulflags_参数的值的内容。</span><span class="sxs-lookup"><span data-stu-id="d17bc-115">The [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method can return either the standard contents or the associated contents of the folder, depending on the value of the method's  _ulflags_ parameter.</span></span> 
  
<span data-ttu-id="d17bc-116">表单库包含的文件夹关联的内容表中存储的表单定义。</span><span class="sxs-lookup"><span data-stu-id="d17bc-116">A form library consists of form definitions stored in a folder's associated contents table.</span></span> <span data-ttu-id="d17bc-117">窗体定义包含窗体的属性，该窗体支持的操作，并且即使窗体服务器可执行文件，它将被视为一个或多个邮件附件。</span><span class="sxs-lookup"><span data-stu-id="d17bc-117">The form definition includes the form's properties, the actions the form supports, and even the form server executable file, which is stored as one or more message attachments.</span></span>
  
<span data-ttu-id="d17bc-118">此外，窗体可以存储在任何文件或要使用的窗体管理器支持的位置。</span><span class="sxs-lookup"><span data-stu-id="d17bc-118">Additionally, forms can be stored in any file or location that the form manager being used supports.</span></span> <span data-ttu-id="d17bc-119">默认窗体管理器 MAPI 文件夹中存储窗体服务器，但自定义窗体管理器无法实现自己的窗体服务器的存储。</span><span class="sxs-lookup"><span data-stu-id="d17bc-119">The default form manager stores form servers in MAPI folders, but a custom form manager could implement its own storage for form servers.</span></span>
  
<span data-ttu-id="d17bc-120">可以有多个绑定到其邮件类别的用户界面。</span><span class="sxs-lookup"><span data-stu-id="d17bc-120">A form can have multiple user interfaces that are bound to its message class.</span></span> <span data-ttu-id="d17bc-121">例如，窗体可以有单独的撰写和阅读用户界面。</span><span class="sxs-lookup"><span data-stu-id="d17bc-121">For example, a form can have separate Compose and Read user interfaces.</span></span> <span data-ttu-id="d17bc-122">正在调用窗体考虑护理的调用适当的用户界面的不同用户请求，具体取决于该窗体的动作。</span><span class="sxs-lookup"><span data-stu-id="d17bc-122">The form takes care of invoking the proper user interface for different user requests, depending on which of the form's verbs is being called.</span></span> <span data-ttu-id="d17bc-123">例如，如果窗体服务器具有单独的撰写和阅读用户界面，撰写用户界面可以自动打开当用户创建窗体的邮件类的新邮件并读取用户界面可以自动打开时用户打开窗体的邮件类的现有邮件。</span><span class="sxs-lookup"><span data-stu-id="d17bc-123">For example, if your form server has separate composing and reading user interfaces, the Compose user interface can be opened automatically when the user creates a new message of the form's message class and the Read user interface can be opened automatically when the user opens an existing message of the form's message class.</span></span>
  
<span data-ttu-id="d17bc-124">通过调用**IMAPIFormInfo**对象的[IMAPIFormInfo::IMAPIProp](imapiforminfoimapiprop.md)方法，表单定义中存储的信息的大多数位于。</span><span class="sxs-lookup"><span data-stu-id="d17bc-124">Most of the information stored within a form definition is available by invoking the [IMAPIFormInfo::IMAPIProp](imapiforminfoimapiprop.md) method on an **IMAPIFormInfo** object.</span></span> <span data-ttu-id="d17bc-125">**IMAPIFormInfo**接口简化了通过调用所有的 MAPI 文件夹和消息方法检索信息所需表单信息的访问。</span><span class="sxs-lookup"><span data-stu-id="d17bc-125">The **IMAPIFormInfo** interface simplifies access to form information by calling all the MAPI folder and message methods needed to retrieve the information.</span></span> <span data-ttu-id="d17bc-126">可通过调用[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法获取**IMAPIFormInfo**对象。</span><span class="sxs-lookup"><span data-stu-id="d17bc-126">An **IMAPIFormInfo** object can be obtained by calling the [IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) method.</span></span> 
  
<span data-ttu-id="d17bc-127">三种类型的表单库[本地表单库](local-form-libraries.md)、[文件夹表单库](folder-form-libraries.md)和[个人窗体库](personal-form-libraries.md)主题所述。</span><span class="sxs-lookup"><span data-stu-id="d17bc-127">The three types of form libraries are described in the topics [Local Form Libraries](local-form-libraries.md), [Folder Form Libraries](folder-form-libraries.md) and [Personal Form Libraries](personal-form-libraries.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d17bc-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d17bc-128">See also</span></span>

- [<span data-ttu-id="d17bc-129">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="d17bc-129">MAPI Forms</span></span>](mapi-forms.md)

