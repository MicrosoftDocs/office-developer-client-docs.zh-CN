---
title: 将 MAPI 表单服务器代码与 Windows 代码集成
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 47ec3e97-ad2b-43ea-842a-b2a0675eef48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b37ae47e40906342aeecf179848311556a7d4ba4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573990"
---
# <a name="integrating-mapi-form-server-code-with-windows-code"></a><span data-ttu-id="5baa4-103">将 MAPI 表单服务器代码与 Windows 代码集成</span><span class="sxs-lookup"><span data-stu-id="5baa4-103">Integrating MAPI Form Server Code with Windows Code</span></span>

  
  
<span data-ttu-id="5baa4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5baa4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5baa4-105">记住，表单服务器是 Win32 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5baa4-105">Recall that your form server is a Win32 application.</span></span> <span data-ttu-id="5baa4-106">因此，有一些与加载到内存中窗体服务器和完全退出相关的任务。</span><span class="sxs-lookup"><span data-stu-id="5baa4-106">As such, there are some tasks related to loading your form server into memory and exiting cleanly.</span></span> <span data-ttu-id="5baa4-107">类似于所有 Windows 应用程序，您窗体的服务器的入口点是**WinMain**函数。</span><span class="sxs-lookup"><span data-stu-id="5baa4-107">Like all Windows applications, the entry point for your form server is the **WinMain** function.</span></span> <span data-ttu-id="5baa4-108">此函数为适当的位置，以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5baa4-108">This function is the appropriate place to perform the following tasks:</span></span> 
  
- <span data-ttu-id="5baa4-109">创建并注册 window 类，以便您窗体的服务器可以与其他 OLE 组件交互。</span><span class="sxs-lookup"><span data-stu-id="5baa4-109">Creating and registering a window class so that your form server can interact with other OLE components.</span></span>
    
- <span data-ttu-id="5baa4-110">创建并注册 window 类或表单对象的用户界面的类。</span><span class="sxs-lookup"><span data-stu-id="5baa4-110">Creating and registering a window class or classes for your form objects' user interfaces.</span></span>
    
- <span data-ttu-id="5baa4-111">调用[MAPIInitialize](mapiinitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="5baa4-111">Calling the [MAPIInitialize](mapiinitialize.md) function.</span></span> <span data-ttu-id="5baa4-112">**MAPIInitialize**处理所需的 OLE 的初始化，以及。</span><span class="sxs-lookup"><span data-stu-id="5baa4-112">**MAPIInitialize** handles the required OLE initialization for you, as well.</span></span> <span data-ttu-id="5baa4-113">必须进行这一次，每个窗体服务器的实例。</span><span class="sxs-lookup"><span data-stu-id="5baa4-113">This must be done once per instance of your form server.</span></span> 
    
- <span data-ttu-id="5baa4-114">全局 atom 注册窗体服务器的类标识符 (CLSID) 的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="5baa4-114">Registering a global atom with a string representation of the form server's class identifier (CLSID).</span></span> <span data-ttu-id="5baa4-115">此 atom 应存在的生存期内的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="5baa4-115">This atom should exist for the lifetime of the form server.</span></span>
    
- <span data-ttu-id="5baa4-116">调用 OLE 函数[CoRegisterClassObject](http://msdn.microsoft.com/en-us/library/ms693407.aspx)与 OLE 中注册窗体服务器的类工厂。</span><span class="sxs-lookup"><span data-stu-id="5baa4-116">Calling the OLE function [CoRegisterClassObject](http://msdn.microsoft.com/en-us/library/ms693407.aspx) to register your form server's class factory with OLE.</span></span> 
    
- <span data-ttu-id="5baa4-117">创建主窗口中接收邮件。</span><span class="sxs-lookup"><span data-stu-id="5baa4-117">Creating a main window to receive messages.</span></span> <span data-ttu-id="5baa4-118">此窗口可能不必是可见的因为用户将与单个窗体对象关联的特定 windows 进行交互。</span><span class="sxs-lookup"><span data-stu-id="5baa4-118">This window probably does not need to be visible because the user will be interacting with the specific windows associated with individual form objects.</span></span> <span data-ttu-id="5baa4-119">但是，在开发期间，主窗口中可以是用于调试输出或窗体服务器的控制方便的位置。</span><span class="sxs-lookup"><span data-stu-id="5baa4-119">However, during development, the main window can be a convenient place for debugging output or control of your form server.</span></span>
    
- <span data-ttu-id="5baa4-120">创建窗体服务器的生存期内运行的邮件循环、 转换和 windows 将消息调度至活动窗体对象。</span><span class="sxs-lookup"><span data-stu-id="5baa4-120">Creating a message loop that runs for the lifetime of the form server, translating and dispatching windows messages to active form objects.</span></span>
    
<span data-ttu-id="5baa4-121">当窗体服务器退出时，应执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5baa4-121">When your form server exits, it should perform the following tasks:</span></span>
  
- <span data-ttu-id="5baa4-122">调用 OLE 函数[CoRevokeClassObject](http://msdn.microsoft.com/en-us/library/ms688650%28VS.85%29.aspx)要取消您的邮件类的 OLE 注册。</span><span class="sxs-lookup"><span data-stu-id="5baa4-122">Call the OLE function [CoRevokeClassObject](http://msdn.microsoft.com/en-us/library/ms688650%28VS.85%29.aspx) to revoke your message class's OLE registration.</span></span> 
    
- <span data-ttu-id="5baa4-123">调用**MAPIUninitialize**正确关闭到 MAPI 表单服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="5baa4-123">Call **MAPIUninitialize** to properly close the form server's connection to MAPI.</span></span> 
    
- <span data-ttu-id="5baa4-124">删除全局 atom 包含的类标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="5baa4-124">Delete the global atom that contains the string representation of the class identifier.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5baa4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5baa4-125">See also</span></span>



[<span data-ttu-id="5baa4-126">编写表单服务器代码</span><span class="sxs-lookup"><span data-stu-id="5baa4-126">Writing Form Server Code</span></span>](writing-form-server-code.md)

