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
# <a name="form-verbs"></a><span data-ttu-id="3df60-103">表单谓词</span><span class="sxs-lookup"><span data-stu-id="3df60-103">Form verbs</span></span>

<span data-ttu-id="3df60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3df60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3df60-105">窗体的用户界面通常提供了菜单项或控件, 使用户能够对窗体执行某种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="3df60-105">A form's user interface typically offers menu items or controls that enable users to take some kind of action with the form.</span></span> <span data-ttu-id="3df60-106">处理这些用户操作的表单服务器作业。</span><span class="sxs-lookup"><span data-stu-id="3df60-106">It is the form server's job to handle these user actions.</span></span> <span data-ttu-id="3df60-107">此接口是使用标准 Win32 api 实现的;编写一个规则就像为常规的 Win32 程序编写其他接口一样。</span><span class="sxs-lookup"><span data-stu-id="3df60-107">This interface is implemented using standard Win32 APIs; writing one is just like writing other interfaces for regular Win32 programs.</span></span>
  
<span data-ttu-id="3df60-108">通常, 用户操作与谓词相关联。</span><span class="sxs-lookup"><span data-stu-id="3df60-108">Often, user actions are associated with verbs.</span></span> <span data-ttu-id="3df60-109">动词是特定于特定邮件类别的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="3df60-109">A verb is the name for an action that is specific to a certain message class.</span></span> <span data-ttu-id="3df60-110">例如, **Reply**是一个由多个表单服务器实现的动词, 每个表单服务器可能对该动词有不同的解释。</span><span class="sxs-lookup"><span data-stu-id="3df60-110">For example, **Reply** is a verb that is implemented by many form servers, each of which may have a different interpretation of that verb.</span></span> <span data-ttu-id="3df60-111">谓词有时也称为命令。</span><span class="sxs-lookup"><span data-stu-id="3df60-111">Verbs are sometimes referred to as commands.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3df60-112">并非所有菜单项和窗体上的控件都对应于一个谓词。</span><span class="sxs-lookup"><span data-stu-id="3df60-112">Not all menu items and controls on a form correspond to a verb.</span></span> <span data-ttu-id="3df60-113">例如, "**取消**" 按钮不对应于表单服务器中的取消谓词。</span><span class="sxs-lookup"><span data-stu-id="3df60-113">For example, a **Cancel** button does not correspond to a Cancel verb within the form server.</span></span> <span data-ttu-id="3df60-114">通常, 谓词与特定的邮件类或一组邮件类的操作相关联。</span><span class="sxs-lookup"><span data-stu-id="3df60-114">Usually, verbs are associated with actions that are specific to a particular message class or a set of message classes.</span></span> <span data-ttu-id="3df60-115">虽然不同的邮件类可以支持不同的谓词集, 但它们都至少支持打开谓词, 该谓词显示窗体的用户界面, 并使用邮件的属性值加载该窗体。</span><span class="sxs-lookup"><span data-stu-id="3df60-115">Although different message classes can support different sets of verbs, all support at least the Open verb, which displays the form's user interface and loads it with the message's property values.</span></span> 
  
<span data-ttu-id="3df60-116">动词可能不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="3df60-116">Verbs may take no parameters.</span></span> <span data-ttu-id="3df60-117">导出带变量参数的命令的表单必须使用自动化机制。</span><span class="sxs-lookup"><span data-stu-id="3df60-117">Forms that export commands with variable parameters must use the Automation mechanisms.</span></span>
  
<span data-ttu-id="3df60-118">客户端可以通过[IMAPIFormInfo:: CalcVerbSet](imapiforminfo-calcverbset.md)方法 (由 MAPI 表单管理器实现) 确定特定邮件类别支持的动词。</span><span class="sxs-lookup"><span data-stu-id="3df60-118">Clients can determine which verbs are supported by a particular message class through the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method, which is implemented by the MAPI form manager.</span></span> <span data-ttu-id="3df60-119">表单管理器从表单的配置文件中获取此信息。</span><span class="sxs-lookup"><span data-stu-id="3df60-119">The form manager gets this information from the form's configuration file.</span></span> <span data-ttu-id="3df60-120">客户端使用此方法返回的谓词集向用户显示可对邮件执行哪些命令。</span><span class="sxs-lookup"><span data-stu-id="3df60-120">The verb set returned by this method is used by the client to show the user which commands can be executed on a message.</span></span> <span data-ttu-id="3df60-121">例如, 客户端可以让用户在邮件上单击鼠标右键, 以显示适用于该邮件的谓词。</span><span class="sxs-lookup"><span data-stu-id="3df60-121">For example, a client might enable users to click the right mouse button over a message to display verbs applicable to that message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3df60-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df60-122">See also</span></span>

- [<span data-ttu-id="3df60-123">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="3df60-123">MAPI Forms</span></span>](mapi-forms.md)

