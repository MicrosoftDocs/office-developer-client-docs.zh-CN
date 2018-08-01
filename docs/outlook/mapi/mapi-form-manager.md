---
title: MAPI 窗体管理器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0bbbd06-d47d-45ad-8179-2372d1d023d0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d12d879ea5a82c5e0e3978d90694b3851aaac5cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776229"
---
# <a name="mapi-form-manager"></a><span data-ttu-id="76f72-103">MAPI 窗体管理器</span><span class="sxs-lookup"><span data-stu-id="76f72-103">MAPI Form Manager</span></span>

  
  
<span data-ttu-id="76f72-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="76f72-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="76f72-105">窗体管理器是实现[IMAPIFormMgr](imapiformmgriunknown.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="76f72-105">A form manager is an object that implements the [IMAPIFormMgr](imapiformmgriunknown.md) interface.</span></span> <span data-ttu-id="76f72-106">大多数组织将使用 MAPI，称为默认窗体管理器与提供的窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="76f72-106">Most organizations will use the form manager supplied with MAPI, referred to as the default form manager.</span></span> <span data-ttu-id="76f72-107">但是，组织可以替换默认窗体管理器自定义窗体管理器如果需要。</span><span class="sxs-lookup"><span data-stu-id="76f72-107">However, an organization can replace the default form manager with a custom form manager if desired.</span></span> <span data-ttu-id="76f72-108">窗体管理器负责表单库中查找窗体，加载用户请求的响应中的窗体并安装到用户的本地表单库、 文件夹表单库或个人表单库的表单。</span><span class="sxs-lookup"><span data-stu-id="76f72-108">The form manager takes care of locating forms within form libraries, loading forms in response to user requests, and installing forms into a user's local form library, folder form library, or personal form library.</span></span> 
  
<span data-ttu-id="76f72-109">与邮件进行交互的用户，必须创建和激活来显示消息，执行对邮件请求的操作的消息的邮件类的窗体服务器实例。</span><span class="sxs-lookup"><span data-stu-id="76f72-109">For a user to interact with a message, an instance of the form server for the message's message class must be created and activated to display the message and carry out the requested operation on the message.</span></span> <span data-ttu-id="76f72-110">[MAPI 表单库](mapi-form-libraries.md)的主题中所述，窗体的实现可以存在几个不同的位置 （窗体库） 中，不能保证窗体或其服务器将在本地或为正在运行中的状态时用户希望交互使用它。</span><span class="sxs-lookup"><span data-stu-id="76f72-110">As described in the topic [MAPI Form Libraries](mapi-form-libraries.md), a form's implementation can exist in several different locations (form libraries) and there is no guarantee that a form or its server will be locally available or in a running state when a user wants to interact with it.</span></span> <span data-ttu-id="76f72-111">负责定位和激活窗体的详细信息窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="76f72-111">The form manager takes care of the details of locating and activating the form.</span></span>
  
<span data-ttu-id="76f72-112">客户端使用提供的窗体管理器服务来查找和激活窗体。</span><span class="sxs-lookup"><span data-stu-id="76f72-112">Clients use services provided by the form manager to find and activate forms.</span></span> <span data-ttu-id="76f72-113">**IMAPIFormMgr**接口由窗体管理器和客户端访问其服务调用。</span><span class="sxs-lookup"><span data-stu-id="76f72-113">The **IMAPIFormMgr** interface is implemented by the form manager and is called by clients to access its services.</span></span> <span data-ttu-id="76f72-114">窗体管理器是必备组件，因为它会隐藏查找并激活消息客户端中的窗体的几乎所有的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76f72-114">The form manager is an essential component because it hides almost all the details of finding and activating forms from messaging clients.</span></span> 
  
<span data-ttu-id="76f72-115">加载表单服务器时, 的默认窗体管理器从第一个窗体库中找到的窗体的邮件类实现加载窗体。</span><span class="sxs-lookup"><span data-stu-id="76f72-115">When loading form servers, the default form manager loads the form from the first form library in which an implementation for the form's message class is found.</span></span> <span data-ttu-id="76f72-116">默认窗体管理器按以下顺序搜索表单库：</span><span class="sxs-lookup"><span data-stu-id="76f72-116">The default form manager searches the form libraries in the following order:</span></span>
  
1. <span data-ttu-id="76f72-117">用户的本地表单库。</span><span class="sxs-lookup"><span data-stu-id="76f72-117">The user's local form library.</span></span> <span data-ttu-id="76f72-118">因为它提供了最快访问表单的实现，如果实现安装在本地表单库，首先搜索此表单库。</span><span class="sxs-lookup"><span data-stu-id="76f72-118">This form library is searched first because it provides the fastest access to a form's implementation if the implementation is installed in the local form library.</span></span>
    
2. <span data-ttu-id="76f72-119">消息的容器文件夹表单库 — 要加载的消息存储在其中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="76f72-119">The folder form library of the message's container — the folder in which the message being loaded is stored.</span></span>
    
3. <span data-ttu-id="76f72-120">用户的个人窗体库。</span><span class="sxs-lookup"><span data-stu-id="76f72-120">The user's personal form library.</span></span>
    
<span data-ttu-id="76f72-121">自定义窗体管理器可以按任意顺序，搜索可用表单库，也可以实现其他表单库，如组织范围内表单库。</span><span class="sxs-lookup"><span data-stu-id="76f72-121">A custom form manager can search the available form libraries in any order, or can implement other form libraries such as an organization-wide form library.</span></span> <span data-ttu-id="76f72-122">表单库的详细信息，请参阅[MAPI 表单库](mapi-form-libraries.md)。</span><span class="sxs-lookup"><span data-stu-id="76f72-122">For more details on form libraries, see [MAPI Form Libraries](mapi-form-libraries.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="76f72-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76f72-123">See also</span></span>



[<span data-ttu-id="76f72-124">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="76f72-124">MAPI Forms</span></span>](mapi-forms.md)

