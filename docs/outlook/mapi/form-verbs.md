---
title: 表单谓词
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a63bf0a7-24e6-4eef-98e8-3744ce5f9f2d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dbd08437dfdd38c3a43cbf12eae8710cc8e3661e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424026"
---
# <a name="form-verbs"></a><span data-ttu-id="c85aa-103">表单谓词</span><span class="sxs-lookup"><span data-stu-id="c85aa-103">Form verbs</span></span>

<span data-ttu-id="c85aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c85aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c85aa-105">窗体的用户界面通常提供菜单项或控件，使用户能够对表单执行某种操作。</span><span class="sxs-lookup"><span data-stu-id="c85aa-105">A form's user interface typically offers menu items or controls that enable users to take some kind of action with the form.</span></span> <span data-ttu-id="c85aa-106">表单服务器的作业用于处理这些用户操作。</span><span class="sxs-lookup"><span data-stu-id="c85aa-106">It is the form server's job to handle these user actions.</span></span> <span data-ttu-id="c85aa-107">此接口使用标准 Win32 API 实现;编写一个就像为常规 Win32 程序编写其他接口一样。</span><span class="sxs-lookup"><span data-stu-id="c85aa-107">This interface is implemented using standard Win32 APIs; writing one is just like writing other interfaces for regular Win32 programs.</span></span>
  
<span data-ttu-id="c85aa-108">通常，用户操作与动词关联。</span><span class="sxs-lookup"><span data-stu-id="c85aa-108">Often, user actions are associated with verbs.</span></span> <span data-ttu-id="c85aa-109">动词是特定于特定邮件类的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="c85aa-109">A verb is the name for an action that is specific to a certain message class.</span></span> <span data-ttu-id="c85aa-110">例如 **，Reply** 是由许多表单服务器实现的一个动词，每个窗体服务器对此动词的解释可能不同。</span><span class="sxs-lookup"><span data-stu-id="c85aa-110">For example, **Reply** is a verb that is implemented by many form servers, each of which may have a different interpretation of that verb.</span></span> <span data-ttu-id="c85aa-111">动词有时称为命令。</span><span class="sxs-lookup"><span data-stu-id="c85aa-111">Verbs are sometimes referred to as commands.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c85aa-112">并非窗体上的所有菜单项和控件都与动词相对应。</span><span class="sxs-lookup"><span data-stu-id="c85aa-112">Not all menu items and controls on a form correspond to a verb.</span></span> <span data-ttu-id="c85aa-113">例如，" **取消"** 按钮与窗体服务器中的"取消"动作不对应。</span><span class="sxs-lookup"><span data-stu-id="c85aa-113">For example, a **Cancel** button does not correspond to a Cancel verb within the form server.</span></span> <span data-ttu-id="c85aa-114">通常，动词与特定于特定邮件类或一组邮件类的操作相关联。</span><span class="sxs-lookup"><span data-stu-id="c85aa-114">Usually, verbs are associated with actions that are specific to a particular message class or a set of message classes.</span></span> <span data-ttu-id="c85aa-115">尽管不同的邮件类可以支持不同的动词集，但所有邮件类都至少支持 Open 动词，该动词显示窗体的用户界面，并加载该窗体的属性值。</span><span class="sxs-lookup"><span data-stu-id="c85aa-115">Although different message classes can support different sets of verbs, all support at least the Open verb, which displays the form's user interface and loads it with the message's property values.</span></span> 
  
<span data-ttu-id="c85aa-116">动词可以不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="c85aa-116">Verbs may take no parameters.</span></span> <span data-ttu-id="c85aa-117">使用变量参数导出命令的表单必须使用自动化机制。</span><span class="sxs-lookup"><span data-stu-id="c85aa-117">Forms that export commands with variable parameters must use the Automation mechanisms.</span></span>
  
<span data-ttu-id="c85aa-118">客户端可以通过 [IMAPIFormInfo：：CalcVerbSet](imapiforminfo-calcverbset.md) 方法确定特定邮件类支持哪些谓词，该方法由 MAPI 表单管理器实现。</span><span class="sxs-lookup"><span data-stu-id="c85aa-118">Clients can determine which verbs are supported by a particular message class through the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method, which is implemented by the MAPI form manager.</span></span> <span data-ttu-id="c85aa-119">表单管理器从表单的配置文件获取此信息。</span><span class="sxs-lookup"><span data-stu-id="c85aa-119">The form manager gets this information from the form's configuration file.</span></span> <span data-ttu-id="c85aa-120">客户端使用此方法返回的动词集向用户显示可以在邮件上执行哪些命令。</span><span class="sxs-lookup"><span data-stu-id="c85aa-120">The verb set returned by this method is used by the client to show the user which commands can be executed on a message.</span></span> <span data-ttu-id="c85aa-121">例如，客户端可能允许用户在邮件上单击鼠标右键以显示适用于该消息的动词。</span><span class="sxs-lookup"><span data-stu-id="c85aa-121">For example, a client might enable users to click the right mouse button over a message to display verbs applicable to that message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c85aa-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c85aa-122">See also</span></span>

- [<span data-ttu-id="c85aa-123">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="c85aa-123">MAPI Forms</span></span>](mapi-forms.md)

