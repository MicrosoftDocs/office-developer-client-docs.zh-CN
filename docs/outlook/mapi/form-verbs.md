---
title: 窗体谓词
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a63bf0a7-24e6-4eef-98e8-3744ce5f9f2d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 27999c141fdeb3e1610213db128bc4ad3d049e6d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594100"
---
# <a name="form-verbs"></a><span data-ttu-id="bf16e-103">窗体谓词</span><span class="sxs-lookup"><span data-stu-id="bf16e-103">Form verbs</span></span>

<span data-ttu-id="bf16e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf16e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf16e-105">窗体的用户界面通常提供菜单项或允许用户执行某些类型的操作与窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="bf16e-105">A form's user interface typically offers menu items or controls that enable users to take some kind of action with the form.</span></span> <span data-ttu-id="bf16e-106">它是窗体服务器的作业处理这些用户操作。</span><span class="sxs-lookup"><span data-stu-id="bf16e-106">It is the form server's job to handle these user actions.</span></span> <span data-ttu-id="bf16e-107">使用标准 Win32 Api; 实现此接口写入一就如同编写正则 Win32 程序其他接口。</span><span class="sxs-lookup"><span data-stu-id="bf16e-107">This interface is implemented using standard Win32 APIs; writing one is just like writing other interfaces for regular Win32 programs.</span></span>
  
<span data-ttu-id="bf16e-108">通常，用户操作是与动作相关联。</span><span class="sxs-lookup"><span data-stu-id="bf16e-108">Often, user actions are associated with verbs.</span></span> <span data-ttu-id="bf16e-109">动词是特定于特定邮件类别的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="bf16e-109">A verb is the name for an action that is specific to a certain message class.</span></span> <span data-ttu-id="bf16e-110">例如，**答复**是动作的由许多窗体服务器，其中每个可能的不同的解释实现动词。</span><span class="sxs-lookup"><span data-stu-id="bf16e-110">For example, **Reply** is a verb that is implemented by many form servers, each of which may have a different interpretation of that verb.</span></span> <span data-ttu-id="bf16e-111">动词有时称为命令。</span><span class="sxs-lookup"><span data-stu-id="bf16e-111">Verbs are sometimes referred to as commands.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf16e-112">并非所有的菜单项和窗体上的控件对应于动词。</span><span class="sxs-lookup"><span data-stu-id="bf16e-112">Not all menu items and controls on a form correspond to a verb.</span></span> <span data-ttu-id="bf16e-113">例如，**取消**按钮不对应于窗体服务器内取消动词。</span><span class="sxs-lookup"><span data-stu-id="bf16e-113">For example, a **Cancel** button does not correspond to a Cancel verb within the form server.</span></span> <span data-ttu-id="bf16e-114">通常，谓词是与特定于特定的邮件类或一组的邮件类的操作关联。</span><span class="sxs-lookup"><span data-stu-id="bf16e-114">Usually, verbs are associated with actions that are specific to a particular message class or a set of message classes.</span></span> <span data-ttu-id="bf16e-115">尽管不同邮件类可以支持不同的谓词集，所有至少支持打开动作，其中显示窗体的用户界面和消息的属性值加载它。</span><span class="sxs-lookup"><span data-stu-id="bf16e-115">Although different message classes can support different sets of verbs, all support at least the Open verb, which displays the form's user interface and loads it with the message's property values.</span></span> 
  
<span data-ttu-id="bf16e-116">动词可能不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="bf16e-116">Verbs may take no parameters.</span></span> <span data-ttu-id="bf16e-117">窗体的导出命令与变量参数必须使用自动化机制。</span><span class="sxs-lookup"><span data-stu-id="bf16e-117">Forms that export commands with variable parameters must use the Automation mechanisms.</span></span>
  
<span data-ttu-id="bf16e-118">客户端可以确定哪些谓词通过[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法，由 MAPI 窗体管理器实现支持的特定邮件类别。</span><span class="sxs-lookup"><span data-stu-id="bf16e-118">Clients can determine which verbs are supported by a particular message class through the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method, which is implemented by the MAPI form manager.</span></span> <span data-ttu-id="bf16e-119">窗体管理器从窗体的配置文件中获取此信息。</span><span class="sxs-lookup"><span data-stu-id="bf16e-119">The form manager gets this information from the form's configuration file.</span></span> <span data-ttu-id="bf16e-120">客户端使用此方法返回的动词集显示一条消息，可执行的命令的用户。</span><span class="sxs-lookup"><span data-stu-id="bf16e-120">The verb set returned by this method is used by the client to show the user which commands can be executed on a message.</span></span> <span data-ttu-id="bf16e-121">例如，客户端可能会使用户能够通过要显示动词不适用于该邮件的消息中单击鼠标右键。</span><span class="sxs-lookup"><span data-stu-id="bf16e-121">For example, a client might enable users to click the right mouse button over a message to display verbs applicable to that message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bf16e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf16e-122">See also</span></span>

- [<span data-ttu-id="bf16e-123">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="bf16e-123">MAPI Forms</span></span>](mapi-forms.md)

