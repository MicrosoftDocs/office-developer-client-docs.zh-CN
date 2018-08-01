---
title: 启动要读取邮件的表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 54a4b805-2ab7-4fb7-b0ea-4a33ead27451
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 675de7eeda534d8761887cdcb6d5c94a209ca18b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776141"
---
# <a name="launching-a-form-to-read-a-message"></a><span data-ttu-id="e9234-103">启动要读取邮件的表单</span><span class="sxs-lookup"><span data-stu-id="e9234-103">Launching a Form to Read a Message</span></span>

  
  
<span data-ttu-id="e9234-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e9234-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e9234-105">客户端应用程序加载一条消息时，窗体服务器实施应产生预期方法调用其窗体服务器和窗体对象的以下序列：</span><span class="sxs-lookup"><span data-stu-id="e9234-105">Form server implementers should expect the following sequence of method calls to their form server and form objects when a client application loads a message:</span></span>
  
1. <span data-ttu-id="e9234-106">客户端应用程序调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开的窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="e9234-106">The client application opens the form manager with a call to the [MAPIOpenFormMgr](mapiopenformmgr.md) function.</span></span> 
    
2. <span data-ttu-id="e9234-107">客户端应用程序调用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法，它返回[IMAPIForm](imapiformiunknown.md)对象。</span><span class="sxs-lookup"><span data-stu-id="e9234-107">The client application calls the [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) method, which returns an object with [IMAPIForm](imapiformiunknown.md).</span></span> <span data-ttu-id="e9234-108">窗体管理器可能会立即发布，如果它将不用于进一步表单激活。</span><span class="sxs-lookup"><span data-stu-id="e9234-108">The form manager may be released now if it will not be used for further form activations.</span></span> <span data-ttu-id="e9234-109">请注意**LoadForm**调用可能需要一些时间，因为窗体管理器可能必须安装该窗体服务器的可执行文件，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="e9234-109">Note that a call to **LoadForm** may take some time because the form manager may have to install the form server's executable files before proceeding.</span></span> 
    
3. <span data-ttu-id="e9234-110">（可选） 客户端应用程序可以准备[IMAPIViewContext](imapiviewcontextiunknown.md)控制操作可能会导致加载文件夹中的上一个或下一步邮件的 form 对象。</span><span class="sxs-lookup"><span data-stu-id="e9234-110">Optionally, the client application can prepare [IMAPIViewContext](imapiviewcontextiunknown.md) to control operations that may cause the form object to load the previous or next message in the folder.</span></span> <span data-ttu-id="e9234-111">客户端应用程序可以使用[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法以更改已设置的默认视图上下文**LoadForm**呼叫中。</span><span class="sxs-lookup"><span data-stu-id="e9234-111">The client application can use the [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method to change the default view context that was set in the **LoadForm** call.</span></span> 
    
4. <span data-ttu-id="e9234-112">客户端应用程序调用[IPersistMessage::Load](ipersistmessage-load.md)方法来将消息数据加载到 form 对象。</span><span class="sxs-lookup"><span data-stu-id="e9234-112">The client application calls the [IPersistMessage::Load](ipersistmessage-load.md) method to load message data into the form object.</span></span> 
    
5. <span data-ttu-id="e9234-113">客户端应用程序调用[IMAPIForm::DoVerb](imapiform-doverb.md)调用传递可选[IMAPIViewContext](imapiviewcontextiunknown.md)接口指针打开动词。</span><span class="sxs-lookup"><span data-stu-id="e9234-113">The client application calls [IMAPIForm::DoVerb](imapiform-doverb.md) to invoke the open verb, passing the optional [IMAPIViewContext](imapiviewcontextiunknown.md) interface pointer.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e9234-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9234-114">See also</span></span>



[<span data-ttu-id="e9234-115">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="e9234-115">Form Server Interactions</span></span>](form-server-interactions.md)

