---
title: 表单存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ddf9158-3c10-408a-aeaf-5a382c4339e7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 793a34b093ba69f73be7e186bec0a769584bbac4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414891"
---
# <a name="form-storage"></a><span data-ttu-id="a3de8-103">表单存储</span><span class="sxs-lookup"><span data-stu-id="a3de8-103">Form storage</span></span>

<span data-ttu-id="a3de8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3de8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3de8-105">尽管不必知道如何实际存储表单的所有详细信息, 但了解一些主要概念是很有用的。</span><span class="sxs-lookup"><span data-stu-id="a3de8-105">Although it is not necessary to know all the details of how forms are physically stored, it is useful to understand a few of the main concepts.</span></span> <span data-ttu-id="a3de8-106">因此, 在描述默认表单管理器支持的三种类型的窗体库之前, 本主题概述了窗体的存储方式。</span><span class="sxs-lookup"><span data-stu-id="a3de8-106">Therefore, before describing the three types of form libraries supported by the default form manager, this topic gives an overview of how forms are stored.</span></span>
  
<span data-ttu-id="a3de8-107">表单定义可以实际存储在一个或多个 MAPI 邮件存储区中的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="a3de8-107">Form definitions can be physically stored within folders in one or more MAPI message stores.</span></span> <span data-ttu-id="a3de8-108">每个 MAPI 文件夹都可以被视为有两个区域用于存储邮件对象: 标准部件和关联部件。</span><span class="sxs-lookup"><span data-stu-id="a3de8-108">Every MAPI folder can be thought of as having two areas for storing message objects: the standard part and the associated part.</span></span> <span data-ttu-id="a3de8-109">文件夹的标准部分包括用户操作的邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="a3de8-109">The standard part of the folder includes the messages and folders that users manipulate.</span></span>
  
<span data-ttu-id="a3de8-110">关联部件包括与文件夹相关联的隐藏邮件对象, 包括表单定义、视图、规则模板、答复模板等。</span><span class="sxs-lookup"><span data-stu-id="a3de8-110">The associated part includes hidden message objects that are associated with the folder, including form definitions, views, rule templates, reply templates, and so on.</span></span> <span data-ttu-id="a3de8-111">此替换部件称为与文件夹关联的内容表, 关联的内容表中的一组邮件称为与文件夹相关的信息。</span><span class="sxs-lookup"><span data-stu-id="a3de8-111">This alternate part is called the folder-associated contents table, and the set of messages in the associated contents table is referred to as the folder-associated information.</span></span> <span data-ttu-id="a3de8-112">隐藏的邮件是文件夹的一个有机组成部分, 并在复制文件夹时与标准文件夹内容一起复制。</span><span class="sxs-lookup"><span data-stu-id="a3de8-112">The hidden messages are an integral part of the folder and are copied along with the standard folder contents when the folder is copied.</span></span> <span data-ttu-id="a3de8-113">虽然物理存储为邮件, 但文件夹的关联内容表中的信息的行为与可查看的消息更像属性。</span><span class="sxs-lookup"><span data-stu-id="a3de8-113">Although physically stored as messages, information in a folder's associated contents table behaves more like properties than like viewable messages.</span></span> <span data-ttu-id="a3de8-114">任何支持关联的内容表的 folder 对象都能够存储自定义表单。</span><span class="sxs-lookup"><span data-stu-id="a3de8-114">Any folder object that supports an associated contents table is capable of storing custom forms.</span></span> <span data-ttu-id="a3de8-115">[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法可以返回标准内容或文件夹的关联内容, 具体取决于该方法的_ulflags_参数的值。</span><span class="sxs-lookup"><span data-stu-id="a3de8-115">The [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method can return either the standard contents or the associated contents of the folder, depending on the value of the method's  _ulflags_ parameter.</span></span> 
  
<span data-ttu-id="a3de8-116">表单库由存储在文件夹的关联内容表中的表单定义组成。</span><span class="sxs-lookup"><span data-stu-id="a3de8-116">A form library consists of form definitions stored in a folder's associated contents table.</span></span> <span data-ttu-id="a3de8-117">表单定义包括表单的属性、表单支持的操作, 甚至是存储为一个或多个邮件附件的表单服务器可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a3de8-117">The form definition includes the form's properties, the actions the form supports, and even the form server executable file, which is stored as one or more message attachments.</span></span>
  
<span data-ttu-id="a3de8-118">此外, 表单可以存储在所使用的表单管理器所支持的任何文件或位置中。</span><span class="sxs-lookup"><span data-stu-id="a3de8-118">Additionally, forms can be stored in any file or location that the form manager being used supports.</span></span> <span data-ttu-id="a3de8-119">默认表单管理器将表单服务器存储在 MAPI 文件夹中, 但自定义表单管理器可以实现自己的表单服务器存储。</span><span class="sxs-lookup"><span data-stu-id="a3de8-119">The default form manager stores form servers in MAPI folders, but a custom form manager could implement its own storage for form servers.</span></span>
  
<span data-ttu-id="a3de8-120">一个窗体可以有多个绑定到其邮件类的用户界面。</span><span class="sxs-lookup"><span data-stu-id="a3de8-120">A form can have multiple user interfaces that are bound to its message class.</span></span> <span data-ttu-id="a3de8-121">例如, 窗体可以具有单独的撰写和读取用户界面。</span><span class="sxs-lookup"><span data-stu-id="a3de8-121">For example, a form can have separate Compose and Read user interfaces.</span></span> <span data-ttu-id="a3de8-122">该窗体负责为不同的用户请求调用适当的用户界面, 具体取决于调用的是哪个窗体谓词。</span><span class="sxs-lookup"><span data-stu-id="a3de8-122">The form takes care of invoking the proper user interface for different user requests, depending on which of the form's verbs is being called.</span></span> <span data-ttu-id="a3de8-123">例如, 如果您的表单服务器具有单独的撰写和读取用户界面, 则当用户创建窗体的邮件类的新邮件时, 可以自动打开撰写用户界面, 并且可以在将阅读用户界面用户打开窗体的邮件类的现有邮件。</span><span class="sxs-lookup"><span data-stu-id="a3de8-123">For example, if your form server has separate composing and reading user interfaces, the Compose user interface can be opened automatically when the user creates a new message of the form's message class and the Read user interface can be opened automatically when the user opens an existing message of the form's message class.</span></span>
  
<span data-ttu-id="a3de8-124">通过对**IMAPIFormInfo**对象调用[IMAPIFormInfo:: IMAPIProp](imapiforminfoimapiprop.md)方法, 可以获取在表单定义中存储的大部分信息。</span><span class="sxs-lookup"><span data-stu-id="a3de8-124">Most of the information stored within a form definition is available by invoking the [IMAPIFormInfo::IMAPIProp](imapiforminfoimapiprop.md) method on an **IMAPIFormInfo** object.</span></span> <span data-ttu-id="a3de8-125">**IMAPIFormInfo**接口通过调用检索信息所需的所有 MAPI 文件夹和邮件方法来简化对表单信息的访问。</span><span class="sxs-lookup"><span data-stu-id="a3de8-125">The **IMAPIFormInfo** interface simplifies access to form information by calling all the MAPI folder and message methods needed to retrieve the information.</span></span> <span data-ttu-id="a3de8-126">可以通过调用[IMAPIFormContainer:: ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法来获取**IMAPIFormInfo**对象。</span><span class="sxs-lookup"><span data-stu-id="a3de8-126">An **IMAPIFormInfo** object can be obtained by calling the [IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) method.</span></span> 
  
<span data-ttu-id="a3de8-127">在 "[本地表单库](local-form-libraries.md)"、"[文件夹表单库](folder-form-libraries.md)" 和 "[个人表单库](personal-form-libraries.md)" 主题中介绍了这三种类型的表单库。</span><span class="sxs-lookup"><span data-stu-id="a3de8-127">The three types of form libraries are described in the topics [Local Form Libraries](local-form-libraries.md), [Folder Form Libraries](folder-form-libraries.md) and [Personal Form Libraries](personal-form-libraries.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3de8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3de8-128">See also</span></span>

- [<span data-ttu-id="a3de8-129">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="a3de8-129">MAPI Forms</span></span>](mapi-forms.md)

