---
title: 启动表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a439e75a-92b3-4830-9dfc-e723d046be7b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c70fd9eb771268db4030cefdf2f27b75ae5963b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776142"
---
# <a name="launching-a-form-server"></a><span data-ttu-id="56c48-103">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="56c48-103">Launching a Form Server</span></span>

  
  
<span data-ttu-id="56c48-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="56c48-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="56c48-105">从持久存储加载表单时发生的交互非常系列 (即，从表单库) 显示一条消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="56c48-105">The series of interactions that occurs when a form is loaded from persistent storage (that is, from a form library) to display a message is as follows:</span></span>
  
1. <span data-ttu-id="56c48-106">消息客户端获取消息的邮件类、 邮件标志和邮件状态。</span><span class="sxs-lookup"><span data-stu-id="56c48-106">The messaging client gets the message's message class, message flags, and message status.</span></span> <span data-ttu-id="56c48-107">此步骤是可选的;如果在步骤 2 中未提供这些部分数据，窗体管理器将检索它们。</span><span class="sxs-lookup"><span data-stu-id="56c48-107">This step is optional; if these pieces of data are not provided in step 2, the form manager will retrieve them.</span></span>
    
2. <span data-ttu-id="56c48-108">消息客户端呼叫与目标邮件[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) 。</span><span class="sxs-lookup"><span data-stu-id="56c48-108">The messaging client calls [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) with the target message.</span></span> 
    
3. <span data-ttu-id="56c48-109">窗体管理器从相应的表单库加载的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="56c48-109">The form manager loads the form server from the appropriate form library.</span></span> <span data-ttu-id="56c48-110">如果未安装了目标邮件的窗体服务器，则窗体管理器安装窗体的可执行文件，以及。</span><span class="sxs-lookup"><span data-stu-id="56c48-110">If the form server for the target message is not installed, the form manager installs the form's executable files, as well.</span></span>
    
4. <span data-ttu-id="56c48-111">窗体管理器来获取的窗体对象在窗体对象上调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) [IMAPIForm: IUnknown](imapiformiunknown.md)和[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="56c48-111">The form manager calls [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) on the form object to obtain the form object's [IMAPIForm : IUnknown](imapiformiunknown.md) and [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interfaces.</span></span> 
    
5. <span data-ttu-id="56c48-112">窗体管理器调用[IPersistMessage::Load](ipersistmessage-load.md)邮件与网站和邮件接口从查看器对象。</span><span class="sxs-lookup"><span data-stu-id="56c48-112">The form manager calls [IPersistMessage::Load](ipersistmessage-load.md) with the message site and message interfaces from the viewer object.</span></span> 
    
6. <span data-ttu-id="56c48-113">Form 对象的邮件客户端[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)方法回拨。</span><span class="sxs-lookup"><span data-stu-id="56c48-113">The form object calls back to the messaging client's [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) method.</span></span> 
    
7. <span data-ttu-id="56c48-114">窗体管理器从消息客户端调用视图上下文接口 form 对象的[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法。</span><span class="sxs-lookup"><span data-stu-id="56c48-114">The form manager calls the form object's [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method with the view context interface from the messaging client.</span></span> 
    
8. <span data-ttu-id="56c48-115">Form 对象的邮件客户端[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法回拨。</span><span class="sxs-lookup"><span data-stu-id="56c48-115">The form object calls back to the messaging client's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method.</span></span> 
    
9. <span data-ttu-id="56c48-116">Form 对象的邮件客户端[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)方法回拨。</span><span class="sxs-lookup"><span data-stu-id="56c48-116">The form object calls back to the messaging client's [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
    
10. <span data-ttu-id="56c48-117">消息客户端调用 form 对象的[IMAPIForm::Advise](imapiform-advise.md)方法与视图上下文接口从查看器对象和消息网站对象。</span><span class="sxs-lookup"><span data-stu-id="56c48-117">The messaging client calls the form object's [IMAPIForm::Advise](imapiform-advise.md) method with the view context interfaces from the viewer object and the message site object.</span></span> 
    
11. <span data-ttu-id="56c48-118">消息客户端调用 form 对象的[IMAPIForm::DoVerb](imapiform-doverb.md)方法。</span><span class="sxs-lookup"><span data-stu-id="56c48-118">The messaging client calls the form object's [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> 
    
12. <span data-ttu-id="56c48-119">Form 对象创建其用户界面，如有必要，以及与用户交互。</span><span class="sxs-lookup"><span data-stu-id="56c48-119">The form object creates its user interface, if necessary, and interacts with the user.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56c48-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56c48-120">See also</span></span>



[<span data-ttu-id="56c48-121">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="56c48-121">Form Server Interactions</span></span>](form-server-interactions.md)

