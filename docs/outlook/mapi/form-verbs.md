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
ms.openlocfilehash: 1ecc80feec2b0a86f35d03f1ca4f75ea9ff094e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774969"
---
# <a name="form-verbs"></a><span data-ttu-id="fb191-103">窗体谓词</span><span class="sxs-lookup"><span data-stu-id="fb191-103">Form verbs</span></span>

<span data-ttu-id="fb191-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fb191-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fb191-105">窗体的用户界面通常提供菜单项或允许用户执行某些类型的操作与窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="fb191-105">A form's user interface typically offers menu items or controls that enable users to take some kind of action with the form.</span></span> <span data-ttu-id="fb191-106">它是窗体服务器的作业处理这些用户操作。</span><span class="sxs-lookup"><span data-stu-id="fb191-106">It is the form server's job to handle these user actions.</span></span> <span data-ttu-id="fb191-107">使用标准 Win32 Api; 实现此接口写入一就如同编写正则 Win32 程序其他接口。</span><span class="sxs-lookup"><span data-stu-id="fb191-107">This interface is implemented using standard Win32 APIs; writing one is just like writing other interfaces for regular Win32 programs.</span></span>
  
<span data-ttu-id="fb191-108">通常，用户操作是与动作相关联。</span><span class="sxs-lookup"><span data-stu-id="fb191-108">Often, user actions are associated with verbs.</span></span> <span data-ttu-id="fb191-109">动词是特定于特定邮件类别的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="fb191-109">A verb is the name for an action that is specific to a certain message class.</span></span> <span data-ttu-id="fb191-110">例如，**答复**是动作的由许多窗体服务器，其中每个可能的不同的解释实现动词。</span><span class="sxs-lookup"><span data-stu-id="fb191-110">For example, **Reply** is a verb that is implemented by many form servers, each of which may have a different interpretation of that verb.</span></span> <span data-ttu-id="fb191-111">动词有时称为命令。</span><span class="sxs-lookup"><span data-stu-id="fb191-111">Verbs are sometimes referred to as commands.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fb191-112">并非所有的菜单项和窗体上的控件对应于动词。</span><span class="sxs-lookup"><span data-stu-id="fb191-112">Not all menu items and controls on a form correspond to a verb.</span></span> <span data-ttu-id="fb191-113">例如，**取消**按钮不对应于窗体服务器内取消动词。</span><span class="sxs-lookup"><span data-stu-id="fb191-113">For example, a **Cancel** button does not correspond to a Cancel verb within the form server.</span></span> <span data-ttu-id="fb191-114">通常，谓词是与特定于特定的邮件类或一组的邮件类的操作关联。</span><span class="sxs-lookup"><span data-stu-id="fb191-114">Usually, verbs are associated with actions that are specific to a particular message class or a set of message classes.</span></span> <span data-ttu-id="fb191-115">尽管不同邮件类可以支持不同的谓词集，所有至少支持打开动作，其中显示窗体的用户界面和消息的属性值加载它。</span><span class="sxs-lookup"><span data-stu-id="fb191-115">Although different message classes can support different sets of verbs, all support at least the Open verb, which displays the form's user interface and loads it with the message's property values.</span></span> 
  
<span data-ttu-id="fb191-116">动词可能不带任何参数。</span><span class="sxs-lookup"><span data-stu-id="fb191-116">Verbs may take no parameters.</span></span> <span data-ttu-id="fb191-117">窗体的导出命令与变量参数必须使用自动化机制。</span><span class="sxs-lookup"><span data-stu-id="fb191-117">Forms that export commands with variable parameters must use the Automation mechanisms.</span></span>
  
<span data-ttu-id="fb191-118">客户端可以确定哪些谓词通过[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法，由 MAPI 窗体管理器实现支持的特定邮件类别。</span><span class="sxs-lookup"><span data-stu-id="fb191-118">Clients can determine which verbs are supported by a particular message class through the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method, which is implemented by the MAPI form manager.</span></span> <span data-ttu-id="fb191-119">窗体管理器从窗体的配置文件中获取此信息。</span><span class="sxs-lookup"><span data-stu-id="fb191-119">The form manager gets this information from the form's configuration file.</span></span> <span data-ttu-id="fb191-120">客户端使用此方法返回的动词集显示一条消息，可执行的命令的用户。</span><span class="sxs-lookup"><span data-stu-id="fb191-120">The verb set returned by this method is used by the client to show the user which commands can be executed on a message.</span></span> <span data-ttu-id="fb191-121">例如，客户端可能会使用户能够通过要显示动词不适用于该邮件的消息中单击鼠标右键。</span><span class="sxs-lookup"><span data-stu-id="fb191-121">For example, a client might enable users to click the right mouse button over a message to display verbs applicable to that message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fb191-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb191-122">See also</span></span>

- [<span data-ttu-id="fb191-123">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="fb191-123">MAPI Forms</span></span>](mapi-forms.md)

